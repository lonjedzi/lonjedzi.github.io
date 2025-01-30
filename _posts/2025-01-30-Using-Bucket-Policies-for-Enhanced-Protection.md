### Using Bucket Policies for Enhanced Protection


## Introduction
When securing files in Amazon S3, it's not enough to rely on pre-signed URLs alone—bucket policies play a crucial role in defining who can access our data and under what conditions. While pre-signed URLs grant temporary, controlled access to specific objects, bucket policies enforce broader security rules at the bucket level. By combining both, we can create a robust security model that ensures data is only accessible to authorized users while maintaining flexibility for secure sharing. In this post, we’ll explore how to use pre-signed URLs alongside bucket policies for enhanced protection.

## Step 1: 
In our nextwork-website-project-lonje bucket, we navigate to Permissions, scroll down, and locate the Bucket Policy section right below the Block Public Access setting 

![a](https://github.com/user-attachments/assets/0fa6f476-71de-413c-9440-0eba4a75deef)

Bucket policies are written in JSON format, making them easy to configure if you're familiar with the syntax. We navigate to the Bucket Policy Editor input the following policy and click on the save changes button:

```tsql
{
	"Version": "2012-10-17",
	"Id": "MyBucketPolicy",
	"Statement": [
		{
			"Sid": "BucketPutDelete",
			"Principal": "*",
			"Effect": "Deny",
			"Action": "s3:DeleteObject",
			"Resource": "arn:aws:s3:::nextwork-website-project-lonje/index.html"
		}
	]
}
```

This bucket policy explicitly denies all users (Principal: "*") the ability to delete the index.html file from the nextwork-website-project-lonje S3 bucket. The policy applies to the s3:DeleteObject action and ensures that the specified file remains protected from accidental or unauthorized deletion. Even users with broader write permissions cannot override this restriction, adding an extra layer of security to critical website files. 

![b](https://github.com/user-attachments/assets/7a116943-8feb-4c9f-b693-c93d1b2773a1)


## Step 2: Testing
The best way to verify our policy is to attempt to delete the protected file. We navigate back to the Objects window, select index.html, and try deleting it. Let's see if our policy successfully prevents this action.

![c](https://github.com/user-attachments/assets/43da5cd4-a980-40b5-8d8e-e6076643e61f)


## Conclusion
By implementing bucket policies alongside pre-signed URLs, we achieve a stronger security model for our S3 storage. Pre-signed URLs provide temporary, controlled access, while bucket policies enforce strict, long-term restrictions at the bucket level. In this example, our policy successfully blocked deletion attempts, ensuring critical files remain protected.

This approach is essential for preventing accidental or unauthorized modifications to important assets while still allowing secure, time-limited access when needed. By carefully defining both access permissions and restrictions, we create a resilient, secure cloud storage environment.
