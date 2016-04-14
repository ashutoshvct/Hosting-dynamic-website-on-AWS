<b>What is EC2? </b>

>Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud. Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy applications faster. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage. Amazon EC2 enables you to scale up or down to handle changes in requirements or spikes in popularity, reducing your need to forecast traffic.


#Creating EC2 instance for our website


1. Click on Services--->Then, EC2.

2. Click on the left panel Instances--->Then click Launch instance.

3. Choose Amazon Linux AMI 2016---->Select the instance type you want and then click Next.

4. Leave everything default and check if the VPC is Default or not.
<b>(If not please choose the default one)</b>

5. Next add Storage enter the size you want for your instance and then click next .
<b>(The default size is 8GB)</b>

6. Now, tag your instance, In key enter Name and in Value enter anything you will remember your instance with like "mywebsite".
<b>(Please do not use double inverted quotes as i have used)</b>

7. Now, click next configure Security Groups--->create new security group-->Enter security group name and description for it.

8. Now, add rules to your instance---select type SSH---in source select my ip from drop down.
   
 >   Add another rule--select type HTTP---in source select anywhere from drop down.
   
 >   Add another rule--select type HTTPS---in source select anywhere from drop down.

9. Click on review and launch, here you can confirm your selections and click launch.

10. It will now ask for a key, create a new one and download it to your pc.
<b>(we will require it for connecting to our instance. Please do not loose this Key.)</b>

11. Now click on Elastic IPs from the left panel and click allocate new ip---> Then click actions and then associate Address-->type the tag name you gave or select the instance from the list.


<b>Now wait for the instance to get to the running state and status checks (2/2).
You have now created an instance, now you will have to install an apache server on that.</b>


#Installing apache server/ Lamp webserver on the ec2 instance that you have created


1. Click Service---> EC2--->On the left panel select instance and then select your instance.
<b>(You can see the tag name that you have given for the instance)</b>

2. Click Connect ---> now go to your pc and open terminal/shell--->change the directory where you have Downloaded the key (cd /Users/xyz/Downloads) or whichever directory---> Give permission to the file by typing chmod 600 xyz.pem.
<b>(Your key will be in .pem format)</b>

3. Now go back to your browser and copy the example and paste it in your terminal/shell---->it will ask for authentication type yes.
<b>(Now you are connected to your instance)</b>

4. Type 
   
   > sudo yum update -y

   > sudo yum upgrade -y
   
   > sudo yum install -y httpd24 php56 mysql55-server php56-mysqlnd
   
   > sudo service httpd start
   
   > sudo chkconfig httpd on

5. To check if you have successfully installed the webserver, go to EC2 instance page and select your instance and then see public DNS at the bottom of the page.
   
  >  Copy that and paste in the web browser, you will see an apache server page.

6. Go back to your terminal/shell/cmd.
   
   > Type sudo groupadd www
   
   > Type sudo usermod -a -G www ec2-user
   (Here ec2-user is your username example ec2-user@ip)
   
   > Type exit/quit.
   
  <b> Note exit or quit command is necessary for the changes to take place.</b>

7. Connect to your instance again via terminal/shell/cmd.
    
  >  Type groups
   <b>(Here you will see www is added to the group)</b>
    
   > Type sudo chown -R root:www /var/www
    
   > sudo chmod 7777 /var/www
    
   > find /var/www -type d -exec sudo chmod 7777 {} \;
    
   > find /var/www -type f -exec sudo chmod 7777 {} \;
   <b>(You can set the permission as per required for example : 2775 or 0664)</b>

8. Test your Lamp/apache webserver
    
   > Type echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
   
   Go to your AWS console----> EC2 ----> select your instance---> Copy the public DNS.
   
   Now go in browser and paste it and edit the url by adding /phpinfo.php
   
  <b> Now you can see the phpinfo page.
   
   That's it you are done configuring your webserver.
</b>

#Adding files in your webserver via FileZilla


For this step please take a note of your public DNS or IP.

1. Download and install filezilla, and then open it.
      
   > In the host name enter the public DNS or ip.
      
   > In username enter ec2-user.
      
   > In port enter 22.
      
   > Click quick connect.
      
   > Select yes for authentication.

   <b>Now you are connected to your instance via FileZilla.</b>

2. Go to folder var/www/html/ and paste your website.

3. <b>Now you go to your EC2 instance and paste the DNS in the web browser, you should see the website is live.</b>


#Pointing our webserver to domain (Optional)

1. Go to AWS console, then Route 53 service.

2. Select the Domain name we have created.

3. Now, click on Create record set.


   > Select type "A-IPv4 address".
      
   >   In the value paste the public IP of the instance.
      
   >   Then, Click Create.
      
   >   Create an another record set and now in the name field add www .
      
   >  Select type "A-IPv4 address"
      
   >   In the value paste the public IP of the instance.
      
   >  Then, Click Create.
   
4. Now you can go to your browser and enter your domain to view your website.
