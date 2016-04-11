#Adding the newly created domain to route 53 for faster delivery

<b>Please check that your Cloudfront has a deployed state.</b>

1. Go to AWS Console.
  > Then go to Route 53 service.
   
  > Select your root domain name.
   
  > Click on the 'A' record you have created and then change Alias to yes.
   
  > Then in the Alias target select the CloudFornt Distribution.
   
  > Click create.
   
  > Repeat this step for sub-domain name.

2. <b>Now, your website migration has been Completed. </b>
