<b>What is CloudFront?</b>

>Amazon CloudFront is a global content delivery network (CDN) service. It integrates with other Amazon Web Services products to give developers and businesses an easy way to distribute content to end users with low latency, high data transfer speeds, and no minimum usage commitments.

#Creating a CloudFront distribution to speedup our website

1. Go to AWS Console
  
    
  > Click CloudFornt service.
    
  > Click create Distribution.
    
  > Click Web.
    
  > Enter the public DNS of Ec2 instance.
    <b>(Note: you have to go to EC2 Service to get the public DNS)</b>
    
   <b> Leave everything default and go to Default cache behaviour settings.</b>
    
  > In allowed HTTP method select the option with get,post,put,delete..etc.
    
  <b>Leave everything default and go to Distribution Settings.</b>
    
  > In the default root object enter your starting page.
    <b>(For example: index.php)</b>
    
  > Now, click create distribution.

2. <b>Wait for atleast 20-40 mins till the Distribution gets to Deployed status.</b>

3. When the deployed status is reached, use the cloudfront domain name to see the website with a great speed.

  
  
  
