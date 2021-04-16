# Deploy-Static-Website-on-AWS
Develop a Static website using AWS services like S3 (Simple Storage Service) and deploy it over the web using CDN (Content Dilevery Network) like CloudFront. 


## STEP 1 - CREATE S3 BUCKET ##

a. From the S3 dashboard, select the **create bucket** option. 
b. In the **bucket settings**, make sure to uncheck **Block all publick access**. This is highly required since we are ***Hosting*** the website. 
c. ***Hosting*** is the service used by user/organization to make thier website accessible via the World Wide Web (WWW.
d. Create bucket


## STEP 2 - UPLOAD FILES TO S3 BUCKET ##

a. Download [starter code] (https://drive.google.com/file/d/15vQ7-utH7wBJzdAX3eDmO9ls35J5_sEQ/view) for the static website. 
b. Click on Add files and add the **index.html** first and then make sure to add the remaining folders one by one. This will make sure that **index.html** will remain the root file. 


## STEP 3 - SECURE THE BUCKET VIA IAM ##

a. Go to the permissions tab on the bucket and scroll down to **Bucket Policy** option. 
b. Click **Edit** and paste the following code. 
c. Paste this code
```
{
"Version":"2012-10-17",
"Statement":[
 {
   "Sid":"AddPerm",
   "Effect":"Allow",
   "Principal": "*",
   "Action":["s3:GetObject"],
   "Resource":["arn:aws:s3:::your-website/*"]
 }
]
}
```
If the website was not hosted, then this step was not required as the CloduFront service will automatically update the policy.


