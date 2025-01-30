### Updating Website files on Amazon S3 and Bucket Versioning 

## Introduction
Keeping a website updated is essential for performance, security, and content accuracy. When hosting a website on Amazon S3, updating files isn’t as simple as overwriting them—without proper configuration, older versions can be lost, and unexpected issues may arise. This is where bucket versioning comes in.

With S3 bucket versioning, we can track changes, restore previous versions if needed, and prevent accidental deletions. In this post, we’ll walk through the process of updating website files on S3 while leveraging bucket versioning to maintain a secure and reliable update workflow.

## Task 1: Updating Website Files in S3
To update our index.html file in Amazon S3, we first need to modify the existing file on our local machine. We'll use Visual Studio Code to make the necessary changes before uploading the updated version to our S3 bucket. This ensures that our website reflects the latest updates while maintaining control over file versions. 

This is what the Website looks like in Code (Disclaimer: This image is not a representation of my coding skills as I did not create this mess 😂)
![a](https://github.com/user-attachments/assets/bb597313-2282-4749-aecc-af94834042a7)

To recall, our website currently looks like this:

![b](https://github.com/user-attachments/assets/ac91a5e4-5d53-4dba-bae7-908bbdd7dc09)

We are going to change the header of the website to: "Everyone deserves a career they enjoy."

Using the search feature in Visual Studio Code, we type "Everyone <first name>" to quickly locate the existing header text in our HTML file. Once found, we replace it with our updated statement and then save the file. 

![c](https://github.com/user-attachments/assets/7a5e3faf-3d68-4eb9-996a-72324e38f89f)

## Task 2: Uploading Updated index.html to S3
With our updated index.html file saved, the next step is to upload it to Amazon S3. We navigate to our S3 bucket, select Upload, and add the newly edited file—overwriting the existing version.

![d](https://github.com/user-attachments/assets/c87cf4c6-fe88-4836-8285-503e35e9c178)

An interesting thing to note is that we didn't need to delete the existing file manually. S3 automatically recognized that a file with the same name already existed and seamlessly replaced it with the updated version. This ensures that only the latest version of our index.html file is available, preventing confusion from having multiple versions of the same file. 

## Task 3: Re-Enabling Public Access

![e](https://github.com/user-attachments/assets/76c558ee-461f-4228-95c7-14e2e5a05f81)

After uploading the updated file, attempting to access the website results in an "Access Denied" error. This happens because S3 resets the file's permissions upon re-upload, revoking public access. To fix this, we need to update the object's access settings and re-enable public read permissions by using Make Public using ACL.

![f](https://github.com/user-attachments/assets/05ebc99c-594d-4ddf-9d6a-0648dc471d6f)

Once public access is re-enabled, we refresh the page and confirm that the website is accessible again. The updated hero text is now displayed, reflecting the changes made to the index.html file.

![h](https://github.com/user-attachments/assets/fa0f0be3-9b5b-4def-8d4e-e1f654e345ec)

## Task 4: Bucket Versioning 

Bucket versioning in Amazon S3 preserves every version of a file, allowing us to retrieve or restore previous versions. Since we enabled versioning when creating the bucket, we simply toggle "Show versions" in the object menu. This reveals the previous index.html file we updated. This feature ensures that we can always access earlier versions, protecting against accidental deletion or unwanted changes. From a security standpoint, versioning provides an extra layer of protection, as it ensures that even if a file is mistakenly overwritten or deleted, we can restore a previous, secure version, reducing the risk of data loss or unauthorized changes.

![g](https://github.com/user-attachments/assets/d0f59f93-272b-4675-87f1-d430d2ed3f22)

## Conclusion
In this post, we demonstrated how to update website files on Amazon S3 and use bucket versioning for added security. By uploading the updated index.html file, we replaced the old version seamlessly, ensuring only the latest file is available. We also re-enabled public access to the site after re-uploading. Bucket versioning provides an extra layer of protection, allowing us to restore previous versions if needed, reducing the risk of accidental data loss or unauthorized changes. This process ensures that updates are secure, efficient, and easily manageable.
