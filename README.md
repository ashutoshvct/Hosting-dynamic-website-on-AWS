# Hosting-dynamic-website-on-AWS

> Below are some steps for you to follow.

> If you need any help please contact me on ashutosh.vct@gmail.com 

<b>We will use the following services - EC2, Route 53, CloudFront, RDS and VPC.

We will also use softwares like FileZilla and Mysql Workbench.

> The scenario: We will move the website hosting to AWS. We already have a website and a database. We just need to migrate them to AWS.
</b>

<b>What is AWS?</b>

>Amazon Web Services (AWS) is a secure cloud services platform, offering compute power, database storage, content delivery and other functionality to help businesses scale and grow. Explore how millions of customers are currently leveraging AWS cloud products and solutions to build sophisticated applications with increased flexibility, scalability and reliability.

#Steps to follow:

1. We will now migrate your domain to route 53<b> (Follow these steps from the file called Route53)</b>.

2. Check that you have a Default VPC, If you don't have it or accidentally deleted it create a case in AWS Support Center for a new one.

3. Create an EC2 Instance - Here you will create an apache server and will upload your files via fileZilla. We will also point this server to our domain name <b>(Follow these steps from the file named EC2)</b>.

4. Create an RDS Instance - Here you will upload your database or if you want you can create a new one<b> (Follow these steps from the file named RDS)</b>.

5. Now Create a CloudFront Distribution where you will distribute the content to the world with low latency <b>(Follow these Steps from file named CloudFront)</b>.

6. Again we will have to make changes in Route53<b> (Follow these Steps from the file called Route53-v1)</b>.

7. <b> Now your website is Live with cloudfont in it.</b>


