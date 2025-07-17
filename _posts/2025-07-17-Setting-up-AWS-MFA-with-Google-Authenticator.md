<img width="1366" height="657" alt="14" src="https://github.com/user-attachments/assets/ed7c51de-4bb2-4759-9268-ea5e738f4ae4" />## 

## Introduction
On Day 2 of my AWS Cloud Practitioner journey, I set up Multi-Factor Authentication (MFA) to secure my IAM user account. MFA adds an extra layer of security by requiring a one-time code from an app, along with your password.
In this post, I’ll walk you through the simple steps I followed to enable MFA using the AWS Management Console.

Let’s get started.

## Pre-requisites
Before we get started, let’s make sure we have everything we need:
    1. We’re signed in to the AWS Management Console using our IAM user credentials (not the root account).
    2. We’ve installed an authenticator app on our smartphone or computer. For this project, we will be using Google Authenticator.
    3. We’re familiar with basic AWS navigation and ready to walk through the setup together.
    
## Step 1: Log In to the AWS Console
We begin by signing in to the AWS Management Console using our IAM user account. Once we’re in, we’ll likely notice a couple of security recommendations from AWS, one of which suggests enabling MFA for better protection. That’s exactly what we’re about to do. 

<img width="1362" height="606" alt="1" src="https://github.com/user-attachments/assets/6211b200-84e6-4d4d-86f7-0c5f0cd86e56" />

## Step 2: Navigate to Our Security Credentials
Next, let’s access our security settings:

1. We click on our IAM username in the top-right corner of the screen.
2. From the dropdown, we select “Security credentials.”
<img width="503" height="504" alt="Security Credentials" src="https://github.com/user-attachments/assets/534d28d3-b737-4aec-b61c-fc789bae0672" />

3. We scroll down until we find the Multi-Factor Authentication (MFA) section.
4. Here, we click “Assign MFA device” to begin the process.
<img width="1366" height="617" alt="4" src="https://github.com/user-attachments/assets/5f453617-488c-47fb-a20b-6007f0b2f589" />

## Step 3: Choose Our MFA Device Type
Now that we’re starting the setup, AWS asks us to name the MFA device name which we will go with the name of my device

<img width="1366" height="615" alt="5" src="https://github.com/user-attachments/assets/576edad7-1ece-4c13-a32f-b29ad396e20f" />

Next, We go with the Virtual MFA device option since we’re using Google Authenticator. This option is the most common and convenient for personal use.

<img width="1366" height="604" alt="6" src="https://github.com/user-attachments/assets/b4968afe-dcff-4eee-af98-8ea13f07f9b1" />

We select “Virtual MFA device” and click Next. AWS now shows us a QR code along with a secret key (in case we want to enter it manually).
<img width="1366" height="588" alt="8" src="https://github.com/user-attachments/assets/bb5b3e82-1558-4e8b-92d1-727355cb9177" />

On our phone, we open our authenticator app and either scan the QR code or manually enter the secret key if scanning isn’t an option. 
Once the app is linked, it starts generating time-based one-time passwords (TOTP) every few seconds. We will have to enter 2 of the codes as required at this step in the setup and completee it. 

<img width="1366" height="580" alt="10" src="https://github.com/user-attachments/assets/1d166cd0-cdb3-444f-81ab-4de16556a783" />

Step 5: Test Our MFA Login
To confirm everything’s working as expected, we now test our new login process. We log out of the AWS Management Console. 
Then, we head back to the AWS sign-in page and enter: Our Account ID or alias, Our IAM username, and Our password as we normally would. After that, AWS prompts us for a Multi-Factor Authentication (MFA) code, which is exactly what we want to see, as shown below:

<img width="1366" height="657" alt="14" src="https://github.com/user-attachments/assets/4528f49b-ff19-4613-9fb7-526b7222a2dc" />

We open our authenticator app, grab the current code, enter it, and hit Submit. And just like that, we’re back in this time with an extra layer of security protecting our account.

## Conclusion
And that’s it, we’ve successfully enabled MFA on our IAM user. It’s a simple step, but it adds a strong layer of security to our AWS account.
On to the next!

   


