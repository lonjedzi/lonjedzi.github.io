## Launching an Amazon EC2 Instance from Scratch

Amazon EC2 (Elastic Compute Cloud) is one of the foundational services in AWS and today, we’re launching our very first virtual server on the cloud together. By the end of this walkthrough, we’ll have a running Linux server, ready for anything from testing to web hosting.

Let’s get started.

## Step 1: Head to the EC2 Dashboard
First, we log into the AWS Management Console and type “EC2” in the search bar. From the EC2 Dashboard, we click on the “Launch Instance” button This is where we begin configuring our server. 

<img width="1366" height="728" alt="2  EC2 Launch Instance" src="https://github.com/user-attachments/assets/dbea0729-09f6-4ac5-a2ea-988eb37bedcb" />

## Step 2: Configure the Instance
##Name and Tag
Let’s give our instance a name: Linux-Server, since we want to launch a Linux Server and this will be very easy to remember. 

<img width="1366" height="728" alt="2  EC2 Launch Instance" src="https://github.com/user-attachments/assets/ad1e10c3-8ca1-4dce-a055-307aeec99b4e" />

## Choosing an Amazon Machine Image (AMI)
We select Amazon Linux 2023 AMI, a secure and lightweight image that works great for beginners and general-purpose workloads.

<img width="1366" height="697" alt="3  Amazon Linux AMI" src="https://github.com/user-attachments/assets/bf7f368a-7cab-4e8d-acb7-757aab6797c3" />

## Choose an Instance Type
Next, we choose t2.micro. It’s Free Tier eligible and perfect for learning and testing. 

<img width="1366" height="694" alt="4  Instance Type" src="https://github.com/user-attachments/assets/8eca916b-dea7-4e38-8314-ce2ccaf896eb" />

## Step 3: Create a Key Pair
To connect to our instance securely, we need a key pair. We click “Create new key pair”, give it a name, and download the .pem file.

<img width="1364" height="705" alt="5  Key Pair Login" src="https://github.com/user-attachments/assets/ac13ffd7-4a78-4bde-bd6a-58e9c5758e44" />

<img width="1366" height="712" alt="6  Key Pair Creation" src="https://github.com/user-attachments/assets/bf06c253-1252-4e5d-b5a4-9123954f8e49" />

Let’s store it safely, we won’t be able to download it again later. This file will be our private key for SSH access.

## Step 4: Set Up Network Settings
For networking: 
We go with the default VPC and subnet.

<img width="1363" height="700" alt="8  Network Settings Edits" src="https://github.com/user-attachments/assets/59bbb41b-b89a-491e-bb8b-5967b074721e" />

We make sure “Auto-assign public IP” is enabled, which gives us access to the server from our local machine.

## Step 5: Configure Firewall Rules (Security Group)
Now, we set up the security group by clicking edit, which will allow us to name our security group.

<img width="1366" height="706" alt="9  Security Group Name" src="https://github.com/user-attachments/assets/f6eb9a30-ef10-44fe-9473-d45af9fefb2c" />

To stay secure, we restrict access to My IP only, so only we can connect.

## Step 6: Review and Launch
We do a quick final review of all the settings: instance type, AMI, key pair, firewall, and networking.

Then we hit “Launch Instance”.

<img width="1366" height="704" alt="10  Storage" src="https://github.com/user-attachments/assets/492a6832-714b-41e1-b979-348bb4d252ba" />



AWS starts provisioning our server, and within a minute or so, we see the instance status switch to “running”. We now have our own Linux server live in the cloud!
