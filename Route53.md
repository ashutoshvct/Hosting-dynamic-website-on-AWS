<b>What is Route 53? </b>

>Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. It is designed to give developers and businesses an extremely reliable and cost effective way to route end users to Internet applications by translating names like www.example.com into the numeric IP addresses like 192.0.2.1 that computers use to connect to each other.

#Migrating your domain to Amazon Route 53

This step is optional but recommended.

Note that if you are a Cpanel or WHM user you will not like AWS Hosting environment, but we need less load time around the world so we have to use AWS.

1. Go to AWS Management console---->Select Service---->then Route 53.

2. Now click on create Hosted Zone and then enter your domain name and click create. 
<b>(Remember in domain name enter your root domain name that is xyz.com and not www.xyz.com)</b>

3. Now open the the hosting zone you have created, Now copy the Name Servers(NS) and paste it in your current hosting provider that may be Godaddy or any other provider.
<b>(It may take 2 hours to 48 hours for this change to happen)</b>

You are done for now!!
