### Uploading and Sharing files using pre-signed URLs


## Introduction

In many cases, we may need to grant temporary access to specific files in our S3 bucket without publicizing the entire bucket. This is where pre-signed URLs come in. They allow us to generate time-limited links that users can use to upload or download files securely. In this section, we'll explore how to create and use pre-signed URLs to control file access while maintaining security.

## Task 1: Uploading the file
The first step is to upload the PDF certification to the S3 bucket, ensuring it's stored securely and ready for sharing.

![a](https://github.com/user-attachments/assets/ed6dcf02-c045-4d39-b63d-31b3cc45e555)


![b](https://github.com/user-attachments/assets/4c15f1dc-cbe3-4f2a-ba1d-aabeafc9e6a8)


## Task 2: Assigning Pre-Signed URL
To securely share the file, we generate a pre-signed URL, which grants temporary access without making the object fully public. We start by selecting the uploaded file from the S3 bucket, then navigate to the Actions menu and choose "Share with Pre-Signed URL." This will create a unique, time-limited link that allows access to the file while maintaining security.

![c](https://github.com/user-attachments/assets/e1239e9f-bacd-46b0-8d6b-ba44f3d86e6e)

Upon doing this, we will be taken to a pop-up that will allow us to select for how long we want to share that file as shown below: 

![d](https://github.com/user-attachments/assets/f18b301b-053f-481f-bd7d-ba32fe91e8bf)

For testing purposes, we will set the expiration time to 1 minute to quickly verify that the pre-signed URL grants access temporarily and expires as expected.

![e](https://github.com/user-attachments/assets/a78bb10b-efc9-403b-ae05-c8e593c1eb13)

After generating the pre-signed URL, we open it in an incognito tab to simulate access from an external user. As expected, the file is accessible to anyone with the link, confirming that the pre-signed URL is functioning correctly.

![f](https://github.com/user-attachments/assets/2fe1ca7a-f13d-4b0d-b6ed-e5303be8c528)

Since more than one minute has passed, we go back and try refreshing the URL. As expected, access is denied, and we receive an error message indicating that the request is no longer valid. This confirms that the pre-signed URL has expired, demonstrating its temporary access control in action.

![g](https://github.com/user-attachments/assets/887c79df-fc31-473c-98a9-ff1c05261939)

## Conclusion
We successfully used pre-signed URLs to grant temporary access to an S3 file without exposing the entire bucket. This ensures secure, time-limited sharing while preventing unauthorized access after expiration. This exercise reinforced key cloud security principles, highlighting the importance of controlled access in securing S3 objects.

