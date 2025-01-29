### Hosting a Website on AWS S3 (AWS Fundamentals) 

![b](https://github.com/user-attachments/assets/8b7d31f7-2d1e-46cf-9225-b178017edb24)

## Introduction 
Amazon S3 is simple, cost-effective, and perfect for hosting static websites. This project will teach us about bucket policies, permissions, and public access settings, key skills for anyone working with AWS.

Big thanks to Nextwork for the inspiration and resources! Check them out at https://www.nextwork.org/

## Step 1: Creating a Bucket in Amazon S3

Creating a bucket is the first step in hosting a website on Amazon S3. A bucket is essentially a container for storing your website files (like HTML, CSS, and JavaScript).
Since we are using S3 for this project, we go to the search bar and search for S3 

![a](https://github.com/user-attachments/assets/d142c8f9-59b0-445d-b098-50d702e8419c)

Next, we click the Create Bucket button on the S3 landing page. This will then take us to the bucket configuration

![b](https://github.com/user-attachments/assets/a9f949b0-1eca-47f1-ab46-0c0db80f716b) 

In the configuration dashboard, we changed our AWS Region from Europe (Stolckhome) to Africa (Cape Town) af-south-1. Using this tool, https://www.cloudping.info/, I determined the closest AWS region to me. (As a Newbie, I don't know where the regions are yet.)
We also give the bucket an appropriate name, nextwork-website-project-lonje for the project.  

![d](https://github.com/user-attachments/assets/9f64a68c-3d02-4c35-b43b-09e793d9e4a8)

The next section of the dash, object ownership, allows us to enable ACLs (Access Control Lists), meaning other AWS accounts can own Objects in this bucket. For this project, we will select the preferred bucket owner so we select that too. 

 ![e](https://github.com/user-attachments/assets/c982c6c6-7c57-40a0-b3eb-ece204ad8665)

In the next configuration, Block Public Access settings for this bucket, we will uncheck "Block all public access" because we want people to have access to the website. 

![F](https://github.com/user-attachments/assets/3149e05b-6b5e-406f-a93c-fff5d0507bbc)

We will enable our next configuration, Bucket Versioning. This is in simple terms just version control for the files that will be in our bucket 

![g](https://github.com/user-attachments/assets/b672f232-6c5a-4112-95a7-afc037f0ea5e)

For the remaining configurations, we will just leave them as default: 
![h](https://github.com/user-attachments/assets/4956930f-5e97-4586-b11e-daebf7c1ccda)

Now we have configurated everything, let's click Create Bucket: 

![i](https://github.com/user-attachments/assets/a2da3eab-c522-4417-a992-a808ac55ead6)

## Step 2: Uploading Website Files in S3 

Our next step is now downloading the files provided by NextWork for the website project and then uploading them to the bucket. Here are the files provided to us by the wonderful fellows from NextWork! (https://www.nextwork.org/)

![j](https://github.com/user-attachments/assets/11458fb4-2200-4404-8d5c-8ca4c708022a)

To add the files, we click on our bucket name in the buckets interface. This will lead us to the "Objects" dashboard, which allows us to manipulate the objects within the bucket. 

![k](https://github.com/user-attachments/assets/da3a2a5d-ea06-4d4a-831d-45c2fa179b67)


We want to add our downloaded files, so the first step is to click on the upload button, which will bring us to the upload dashboard. We then select add the index.html file we downloaded and then upload it. Next, we select the upload folder upload the folder that we downloaded as well, and click upload. 

![l](https://github.com/user-attachments/assets/aa746c90-4fd3-441a-b70e-cb7748719fd0)

Done! 

![n](https://github.com/user-attachments/assets/2502f9ae-5cbc-40ea-bb73-db73e678e178)

## Step 3: Configuring the Website
Back on our bucket page, we select the properties and locate static website hosting at the bottom of the page. 

![o](https://github.com/user-attachments/assets/f321f9f7-3ae9-4eec-9858-4e02b21ac29a)

We want to enable static website hosting so we click edit, and then click on "Enable" to do so. 
![p](https://github.com/user-attachments/assets/bc0aac30-82db-404c-b7b6-c09b93633646)

Clicking Enable will unleash another set of configurations that we have to tinker with before getting the website up. For this project, what we have to do is specify our home page, which is the index.html file we uploaded,d so we enter that and that's it!  

![q](https://github.com/user-attachments/assets/186f0c07-5ee8-4619-bd15-ed93bb67dc7c) 

Going back to our properties and heading to the static website, we now see that we have a link that has been generated for our site. We click the link and we go to our website! 

![r](https://github.com/user-attachments/assets/b1eaa7b7-a511-45f1-8865-24ff6539f28b)

Oh no! We get an error when trying to open the site!
![s](https://github.com/user-attachments/assets/16df0e8d-aec5-4008-984d-12dfd82fbacd)


# Step 4: Troubleshooting Website Access Denied 
Having already enabled public access to the bucket, we are still unable to open the index.html file. Although the bucket is visible to the outside world, we also need to make sure that the objects inside are also visible to the public. We navigate to the Objects again, click on actions, and then click on Make Public using ACL.

![t](https://github.com/user-attachments/assets/772a1e0b-306a-421b-9d02-50a98363a41b) 

We confirm the files and then click on make public. 
![u](https://github.com/user-attachments/assets/240e6a7e-0500-4ca4-91b5-56d2279b3a71) 

Refreshing the website link, we can now see that we can see it without any errors! 

![v](https://github.com/user-attachments/assets/da2667fe-24cc-46e1-a014-d47c56964f2f)

Link to site: http://nextwork-website-project-lonje.s3-website.af-south-1.amazonaws.com/ 

## Conclusion 

In this first part of the AWS Fundamentals Project, we successfully hosted a static website on Amazon S3, learning key skills like bucket creation, permissions management, and static website hosting. We also tackled troubleshooting access issues, ensuring the site was publicly available. This hands-on experience provided a solid foundation in AWS S3 and cloud hosting.

A big thank you to NextWork for the inspiration and resources. Stay tuned for Part 2, where we’ll explore more advanced AWS features! Check out Nextwork at https://www.nextwork.org/.






