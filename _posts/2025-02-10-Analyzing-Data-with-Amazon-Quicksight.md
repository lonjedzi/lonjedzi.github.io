### Analyzing Data with Amazon Quicksight 

![Quicksight-blog-hero2](https://github.com/user-attachments/assets/6fa7e405-16a7-4cc9-a9a2-27dcaab43bce)

Data is powerful—but only when it’s transformed into meaningful insights. That’s why I’m diving into Amazon QuickSight to analyze a massive Netflix dataset and create an interactive dashboard.

This project is part of my self-education in cloud technologies and security, helping me develop data analysis and visualization skills. Along the way, I’ll explore how QuickSight makes complex data more accessible, even for beginners.

In this blog, I’ll share my plan, my steps, and the insights I hope to uncover.  

## Step 1: Download the Dataset 
First, we need two files that have been provided to us by the lovely people at Nextwork:

1️⃣ netflix_titles.csv – Contains all the data we'll analyze. (Right-click > Save Link As)
2️⃣ manifest.json – Essential for setup (more on this soon). (Right-click > Save Link As)

## Step 2: Create an S3 Bucket
Next, we'll set up an Amazon S3 bucket to store our dataset.

🔹 We head to AWS S3 and click "Create Bucket"
🔹 Give the bucket a name, in this case, we will name the bucket: nextwork-quicksight-project-lonje
🔹 Choose a region (Africa (Cape Town) af-south-1)
🔹 Click "Create"—and that’s it! 🚀

![b](https://github.com/user-attachments/assets/ff61f319-138c-4c00-a979-948bb9551de5)
 

## Step 3: Uploading Files 
Next, we upload manifest.json and netflix_titles.csv to the S3 bucket we just created, making them ready for analysis in Amazon QuickSight. 

![d](https://github.com/user-attachments/assets/4768d455-8e28-45fa-9648-25c80afe782a) 

The next step we have to do is Copy the S3 URL of the netflix_titles.csv file. The reason for this is to put this into our manifest.json file using any editor of your choice on the local machine. 

![e](https://github.com/user-attachments/assets/48fd4f5a-1107-46b0-8f97-269420e92c8c) 

We then open manifest.json in visual studio code on the local machine and paste the link in URLs after which we then reupload the manifest.json file into our S3 Bucket: 

![f](https://github.com/user-attachments/assets/177e6b51-ba3d-4ebb-b3f9-7fad21aaf255)

## Step 4: Signing up for Quicksight  
The next step is to create an Amazon QuickSight account. We search for QuickSight in the AWS search bar and click on the result. This takes us to the signup page, where we enter the required details, including email, region, and authentication settings.

![g](https://github.com/user-attachments/assets/cdc96196-2793-49eb-a1dc-c83400e1a9bc)

This step allows us to configure which Amazon services QuickSight can access. For this project, we grant QuickSight access to our S3 bucket, enabling it to retrieve the dataset for analysis.

![h](https://github.com/user-attachments/assets/15f7606e-6cf9-47ad-bbc4-dc9cf325d964)

It is important to uncheck "Add pixel perfect reports" to avoid any unnecessary charges!
![j](https://github.com/user-attachments/assets/aeff192a-7225-4a2f-bd19-26323c1b1a1f)



