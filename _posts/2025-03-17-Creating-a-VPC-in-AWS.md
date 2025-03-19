### Creating a VPC in AWS

![P1](https://github.com/user-attachments/assets/94674596-3d21-40e8-85ae-cd4d357b14f3)

## Introduction
My latest project is a simple introduction to networking in AWS! In this project, I will create a Virtual Private Cloud (VPC) environment in AWS. Setting up a VPC is an essential skill for anyone looking to get familiar with AWS. This project consists of three main steps:

  1. Creating an Amazon VPC
  2. Configuring a Public Subnet
  3. Setting up an Internet Gateway

## Step 1:
After logging into the AWS Management Console, navigate to the search bar and type "VPC" to find the Virtual Private Cloud service, as shown in the image below.

![1](https://github.com/user-attachments/assets/8426e101-4948-4f1b-b336-9977cc231b63)

This will bring us to the VPC Console, where we can manage various networking resources. However, for this project, we are only focused on creating a Virtual Private Cloud (VPC).

## What is a VPC?
A Virtual Private Cloud (VPC) is an isolated network environment within AWS that allows us to define and control a virtual networking setup, including IP address ranges, subnets, route tables, and gateways.

![2](https://github.com/user-attachments/assets/2d77c9fe-044e-4a1c-8d42-cc2648b662b5)

In the VPC Console, we can see that under the VPCs section, a default VPC is already available. This default VPC is automatically provided when an AWS account is created, and it serves as the default network for our resources, such as S3 buckets, EC2 instances, and more.

Without VPCs, all resources would be publicly accessible, which is not ideal for security and isolation. A VPC allows us to control network access, ensuring that our infrastructure remains private and secure.

## Step 2 
Next, in the VPC Console, click on VPCs, then select Create VPC to begin setting up a new Virtual Private Cloud. 

![3](https://github.com/user-attachments/assets/012397db-7ab7-4e82-b2eb-a4b09f489e75)

We will now be taken to the VPC setup menu, where we need to configure our VPC. Since we only create a VPC, ensure that "VPC only" is selected.

## Configuration:
  1. Name tag: my-vpc-1
  2. IPv4 CIDR: Select "IPv4 CIDR manual input"
  3. IPv4 CIDR block: 10.0.0.0/16
  4. IPv6 CIDR block: Select "No IPv6 CIDR block"
  5. Leave all other settings as default.

Once these configurations are set, we can proceed to create the VPC!

![4](https://github.com/user-attachments/assets/d5580e75-adc0-4146-aa6b-c094551b5be3)

Now that we have created the VPC, we can see in the diagram below how our current architecture looks within AWS. Our next step is to create a subnet within the VPC.

![3](https://github.com/user-attachments/assets/fff68fe9-d20b-4a6f-a6e7-25a86de91964)

## Creating a Subnet
A subnet is a smaller network within our VPC that allows us to organize and manage resources more efficiently. Each subnet exists within a specific Availability Zone (AZ) and determines how resources communicate with each other and the internet.

In AWS, subnets can be classified into two types:

  1. Public Subnets – These allow resources, such as EC2 instances, to communicate with the Internet via an Internet Gateway.
  2. Private Subnets – These are isolated from the internet and are used for internal resources like databases.
  
## Creating our Subnet
To create our subnet, navigate to the Subnets dashboard by clicking on Subnets in the left navigation panel. 

![5](https://github.com/user-attachments/assets/43179327-bc64-4885-b2bf-5fc6bef2c192)

As we can see, our account already has three subnets set up. This is because the default VPC that comes with our AWS account includes a subnet in each Availability Zone (AZ) within our selected region.

In this case, our region, af-south-1 (South Africa), has three Availability Zones, which means our default VPC automatically includes three subnets, one in each AZ.

## Step 1
To create our subnet, click on the Create Subnet button. This will take us to the Create Subnet dashboard.

Since we want to create the subnet within the VPC we just set up, click on the VPC dropdown menu and select our created VPC (my-vpc-1)

![6](https://github.com/user-attachments/assets/4ab989f6-63b6-43d4-b193-1f22d6e9a7ed)

Next, we configure our subnet settings, and click on create subnet:

  1. Subnet Name: public-1
  2. Availability Zone: af-south-1a
  3. IPv4 VPC CIDR Block: Leave as default (This ensures the subnet remains within the address range, 65,536, of the VPC we created). 
  4. IPv4 Subnet CIDR Block: Set to 10.0.0.0/24, which provides 256 IP addresses for resources within this subnet.

![7](https://github.com/user-attachments/assets/ae6ed3d2-10d7-431b-ba11-e852b34ef467)

Next, we enable Auto-Assign Public IPv4 Address for public-1.

By default, resources have private IPs for internal VPC communication. However, a public IP is required for internet access. Enabling this option ensures that any EC2 instance launched in this subnet automatically receives a public IP, saving time and effort.

![8](https://github.com/user-attachments/assets/e071d676-f702-4629-a9ee-2afe4340c87e)

We select the subnet, click Actions, then choose Edit Subnet Settings to open the configuration dashboard. From there, we enable Auto-Assign Public IPv4 Address and save the changes. 

![9](https://github.com/user-attachments/assets/0889924e-5d8a-4bd6-9129-251b4c61043a)

![2](https://github.com/user-attachments/assets/6e9bd830-ae08-4135-af00-077145bfd375)

## Creating an Internet Gateway
Now that our subnet is created, we need to connect it to the internet to make it a public subnet.

Simply put, an Internet Gateway (IGW) allows our VPC to communicate with the Internet, enabling resources within the public subnet to send and receive external traffic. 

![10](https://github.com/user-attachments/assets/429f7f59-28a0-4090-b4aa-77a981f03c13)

To create an Internet Gateway, we navigate to the left navigation bar and click on Internet Gateways. This will take us to the Internet Gateway dashboard.

We can see that a default Internet Gateway is already set up—this is automatically provided with your AWS account. However, we need to create a new one for our custom VPC.

![11](https://github.com/user-attachments/assets/c0b38e99-4b24-4dc8-b9f0-f12756f24992)

We click on the Create Internet Gateway button in the top right corner. This will open the configuration panel, where we simply enter a name for our gateway (my-ig-1).

![12](https://github.com/user-attachments/assets/83727673-4691-4cbf-8286-c4c3f373296b)

Once named, click Create Internet Gateway to finalize the setup.

![13](https://github.com/user-attachments/assets/fbea1b0e-c89e-44b2-ba5c-09669fdcf2b8)

Next, we need to attach the Internet Gateway to our VPC.

To do this, select Actions and then click on Attach to VPC. This will take us to a dashboard where we can select our VPC (my-vpc-1) to attach the Internet Gateway.

![14](https://github.com/user-attachments/assets/f479f39d-9c27-46bf-847c-6adbf425cb93)

Once this is done, we will have successfully attached the Internet Gateway to our VPC, completing the setup! 

![15](https://github.com/user-attachments/assets/9681a40f-7f88-4459-98a8-f1484c40dbdf)

![P1](https://github.com/user-attachments/assets/89ae81e4-c4ad-461e-b8f4-cc0ba03533ec)

## Conclusion 

In conclusion, we have successfully created a Virtual Private Cloud (VPC), configured a subnet within it, and connected it to the internet by attaching an Internet Gateway. These steps lay the foundation for launching and managing resources within a secure and isolated network in AWS. With our public subnet now in place, we can begin deploying EC2 instances and other services that require internet access, ensuring a robust and flexible cloud environment.

