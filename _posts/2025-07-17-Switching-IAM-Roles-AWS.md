## Introduction

In managing cloud environments, controlling user permissions securely and efficiently is crucial. In this project, I explored how to create an IAM role in AWS and enable a test user to switch into that role to gain temporary permissions. This approach allows users to perform tasks only when necessary, adhering to the principle of least privilege and enhancing overall security. In this post, I’ll walk you through the step-by-step process I followed to set up IAM roles and policies, create a test user with minimal permissions, and successfully switch roles to access specific AWS services like EC2. Whether you’re new to AWS IAM or looking to reinforce best practices in permission management, this guide will help you understand the power and flexibility of role-based access.

Step 1: Create the IAM Role for EC2 Full Access
We begin by heading to the IAM dashboard, selecting Roles, and clicking on Create role. Since we want to simulate cross-account access, we choose another AWS account that we have created, called mike-ec2-demo, as the trusted entity type. 

<img width="1366" height="606" alt="5  Review Account" src="https://github.com/user-attachments/assets/4d281498-c2ec-47f9-9420-927b1815c94c" />

Next, we move to the permissions step and attach the AmazonEC2FullAccess policy. This gives the role full administrative privileges over EC2, meaning we’ll be able to create, start, stop, terminate, and manage instances freely once the role is assumed.

<img width="1366" height="598" alt="14  Create role 4" src="https://github.com/user-attachments/assets/fa2c7cf0-e746-4c69-a943-08a4848935a5" />

Finally, we name the role something clear and purposeful, such as ec2-role-full, and complete the setup.

<img width="1361" height="595" alt="15  Create Role 5" src="https://github.com/user-attachments/assets/9c2fdd36-7d3c-4a13-8c11-3884f165b7fd" />

By the end of this step, we’ve created a powerful IAM role that’s ready to be assumed. In the next step, we’ll define exactly who can assume it and from where.

## Step 2: We create an IAM User that can assume the role
Now that we have our EC2FullAccessAssumeRole ready, we shift our focus to creating an IAM user who will assume this role.

We head to the IAM dashboard, choose Users, and click “Add users.” We give the user a clear name mike-ec2-demo.

<img width="1366" height="603" alt="6  Console Sign in URL" src="https://github.com/user-attachments/assets/46a96733-4ee8-4b47-92a4-ce519c723a0c" />

Next, on the “Set permissions” page, we choose “Attach policies directly.” But instead of giving the user general EC2 permissions, we craft a custom policy that allows this user to assume the exact role we just created.

```{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "sts:AssumeRole",
    "Resource": "arn:aws:iam::964577536225:role/ec2-role-full"
  }
}
```
<img width="1366" height="584" alt="27  sts assumerole" src="https://github.com/user-attachments/assets/c33ed78c-b89a-45b0-a9e4-535e6168b64e" />

##  Step 3: We sign in as the IAM user and switch roles to ec2-role-full
Now that we’ve created the IAM user and assigned the AssumeRole policy, we sign in to the AWS Management Console using that IAM user’s credentials.

<img width="1363" height="629" alt="7  Logging in as mike" src="https://github.com/user-attachments/assets/373030da-82dd-4b85-88e3-541daeda604f" />

Once we’re signed in, we head to the top-right corner, click on the account name or number, and select “Switch Role.”
Here, we are brought to this page: 

<img width="1366" height="726" alt="20  Switch Role Page Mike" src="https://github.com/user-attachments/assets/8beee436-dc80-45f5-a53a-68f7d901848e" />
We have entered:
  1. Account ID: The AWS Account ID where the role is created
  2. Role name: ec2-role-full
  3. Display name & color: Anything we like to help us identify the role session

We hit “Switch Role”, and now  boom,  we are operating as the ec2-role-full.

To confirm it works, we go to the EC2 Dashboard, and see that we are not getting many API errors and are able to access some EC2 Functionalities. And we can see the tag attached to the role in the top right: 

<img width="1366" height="641" alt="31  Cleared errors" src="https://github.com/user-attachments/assets/9c887e65-ff5d-4e4a-9c36-94f0f6716624" />

## Conclusion
We’ve learned how to create an IAM role with EC2 full access and let a limited-permission user assume that role via the AWS Console. This setup follows the principle of least privilege, giving users only the access they need when they need it. Using role switching keeps our AWS environment secure and flexible.


