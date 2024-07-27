# Hosting-Website-on-Amazon-S3

## Table of Contents:
1. [Introduction](#1_Introduction) </br>
2. [Methodology](#2_Methodology) </br>
3. [Key Learnings](#3_Key_Learnings) </br>
     


## <a name="1_Introduction"></a> 1 Introduction

Amazon S3 is a scalable object storage service from AWS, designed for storing and retrieving data from anywhere.


How it’s useful:
- Developers and teams use Amazon S3 because its very convenient. 
- Highly available, durable, and secure with cost- effective pricing.
- It allows easy management of stored objects with Access Control Lists (ACLs) for fine-grained permissions and Identity and Access Management (IAM) policies for secure access control.
- It also supports versioning, which helps in maintaining backup and recovery of objects.

## <a name="2_Methodology"></a> 2 Methodology

I’m using Amazon S3 to host my static website. To create an Amazon S3 bucket,the configuration steps I needed to take include:
- The bucket’s Region: US East (N. Virginia) us-east-1, choosing server where the data will be stored.
- Access Control Lists: Enabling ACLs which dictates who can have access to a resource while allowing only the bucket owner to write to the bucket.
- Bucket versioning: Enabling bucket versioning allows you to keep multiple versions of a file, making it easy to manage updates and choose which version to use. This is useful for backup, recovery, and maintaining different file variations.
- Public Access: Enabled to allow anyone on the internet have access to the resources
  
- S3 bucket names have to be globally unique.

- Upload website files to S3
Next, I uploaded my website’s files into my S3 bucket.
It consisted an Index.html and other related files which were used to create and design the webpage. Below is an image of the files being uploaded in the bucket.

- Configuring Static web hosting on S3
Website hosting essentially is making your website publicly accessible.
To enable website hosting, under the properties tag on S3, I enabled static web hosting and specified the document I wanted to allow this for.
Once a static website is enabled, S3 produces a bucket endpoint URL which should direct you to the webpage.
However, unfortunately an error was made. The reason for this error was that the content was not accessible to the public. To resolve this error, I selected the items and made them public using ACL in the action tab.

-Using a bucket policy to secure your bucket
The Policy prevents all aws accounts from deleting the resource including the bucket owner.
This image is the bucket policy to deny delete privileges on your website files.

## <a name="3_Key_Learnings"></a> 3 Key Learnings
- #### What is Amazon S3?
  An object storage service that allows secure storage of data
- #### What is static website hosting?
  Publishing a website with fixed content that can be accessed publicl
- #### What settings make my website available to the public?
  Under the Action tab there was an option to make an object public using ACL
- #### Why did your bucket endpoint URL have an error? What will you need to do next time?
  Using ACLS to grant public access to the object
