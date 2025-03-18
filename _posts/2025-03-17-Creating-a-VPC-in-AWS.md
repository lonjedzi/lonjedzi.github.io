### Creating a VPC in AWS

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
