# Hosting-dynamic-website-on-AWS

<b>I will use the following services - EC2, Route 53, CloudFront, RDS and VPC.

We will also use softwares like FileZilla and Mysql Workbench.
</b>
1. We will now migrate your domain to route 53<b>(Follow steps from file called Route 53)</b>.

2. Check that you have a Default VPC, If you don't have it or accidentally deleted it create a case in AWS Support Center for a new one.

3. Create an EC2 Instance - Here you will create an apache server and will upload your files via fileZilla. We will also point this server to our domain name <b>(Follow steps from other file named EC2)</b>.

4. Create an RDS Instance - Here you will upload your database or if you want you can create a new one<b> (Follow steps from other file named RDS)</b>.

5. Now Create a CloudFront Distribution where you will distribute the content to the world with low latency <b>(Follow Steps from file named CloudFront)</b>.

6. Again we will have to make changes in Route53<b> (Follow Steps from file called route 53-v1)</b>.

7.<b> Now your website is Live with cloudfont in it.</b>


