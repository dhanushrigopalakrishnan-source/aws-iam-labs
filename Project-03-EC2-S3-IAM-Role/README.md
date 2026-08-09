# Project 3 – EC2 Access to S3 Using IAM Role

## 📌 Objective

The objective of this project is to understand how an **IAM Role** allows an Amazon EC2 instance to access Amazon S3 without storing AWS Access Keys on the EC2 instance.

This project demonstrates:

- IAM Roles
- IAM Instance Profiles
- Amazon EC2
- Amazon S3
- AWS Managed Policies
- Temporary Credentials
- Principle of Least Privilege

---

## 🏗️ Architecture

```text
                    AWS Account
                         |
                         v
                  Amazon EC2
                         |
                         | IAM Instance Profile
                         v
              EC2-S3-ReadOnly-Role
                         |
                         | Permission
                         v
            AmazonS3ReadOnlyAccess
                         |
                         v
                    Amazon S3
                         |
                         v
              iam-project3-test.txt
🛠️ AWS Services Used
AWS Service	Purpose
IAM	Create the IAM Role and manage permissions
EC2	Server used to access S3
S3	Store the test file
🔐 IAM Role Configuration
Role Name
EC2-S3-ReadOnly-Role
Attached Policy
AmazonS3ReadOnlyAccess

The role provides read-only access to Amazon S3.

The EC2 instance can read and list S3 resources but does not have permission to modify or delete S3 objects.

🪣 S3 Configuration

A private S3 bucket was created for testing.

Bucket
iam-project3-s3-dhanushri-2026
Test Object
iam-project3-test.txt

The test file was uploaded to the S3 bucket.

💻 EC2 Configuration

An Amazon Linux 2023 EC2 instance was launched.

Instance Configuration
Configuration	Value
Operating System	Amazon Linux 2023
Instance Type	t3.micro
Instance Name	IAM-Project3-S3-Role
IAM Role	EC2-S3-ReadOnly-Role
Storage	8 GiB gp3

The IAM Role was attached to the EC2 instance through an IAM Instance Profile.

🔑 Why Use an IAM Role?

Instead of storing long-term AWS Access Keys on the EC2 instance, an IAM Role provides temporary credentials to the instance.

Without IAM Role
EC2
 |
 +-- AWS Access Key
 |
 +-- Secret Access Key
 |
 v
S3

Storing long-term credentials on a server can create a security risk.

With IAM Role
EC2
 |
 v
IAM Role
 |
 v
Temporary Credentials
 |
 v
S3

This is the recommended approach for allowing AWS services such as EC2 to access other AWS services.

🧪 Testing

After launching the EC2 instance, EC2 Instance Connect was used to open a Linux terminal.

1. Verify the IAM Role

The following command was executed:

aws sts get-caller-identity

The output confirmed that the EC2 instance was using:

assumed-role/EC2-S3-ReadOnly-Role

This confirmed that the EC2 instance was using the IAM Role instead of manually configured AWS Access Keys.

2. List S3 Buckets

The following command was executed:

aws s3 ls

The S3 bucket was successfully displayed.

3. List Objects in the S3 Bucket

The following command was executed:

aws s3 ls s3://iam-project3-s3-dhanushri-2026

The following object was successfully displayed:

iam-project3-test.txt
🔄 Access Flow
EC2 Instance
     |
     | Uses IAM Instance Profile
     v
EC2-S3-ReadOnly-Role
     |
     | AmazonS3ReadOnlyAccess
     v
Amazon S3
     |
     v
iam-project3-test.txt
✅ Result

The EC2 instance successfully accessed the S3 bucket using the IAM Role.

The project verified that:

EC2 can obtain permissions through an IAM Role.
EC2 can list S3 buckets.
EC2 can read the contents of the S3 bucket.
No AWS Access Keys were stored on the EC2 instance.
S3 access is controlled using IAM permissions.
Final Result
EC2 → IAM Role → S3

Project completed successfully. ✅

🔒 Security Principle
Principle of Least Privilege

The EC2 instance was given:

AmazonS3ReadOnlyAccess

instead of full S3 access.

Therefore, the instance receives only the permissions required for this project.

This reduces the potential impact of unauthorized access.

📸 Screenshots
1. IAM Role Permission

Shows the EC2-S3-ReadOnly-Role with the AmazonS3ReadOnlyAccess policy attached.

2. S3 Bucket Object

Shows the test file stored in the S3 bucket.

3. EC2 Instance with IAM Role

Shows the EC2 instance running with the EC2-S3-ReadOnly-Role attached.

4. Successful S3 Access from EC2

Shows the AWS CLI commands proving that the EC2 instance is using the IAM Role and can access the S3 bucket.

🎯 Learning Outcomes

Through this project, I learned:

How to create an IAM Role.
How to attach an AWS Managed Policy to an IAM Role.
How to attach an IAM Role to an EC2 instance.
What an IAM Instance Profile is.
How EC2 can access S3 without Access Keys.
How to verify an IAM Role using AWS CLI.
How temporary credentials are used by AWS services.
How to apply the Principle of Least Privilege.

🏁 Project Information

Project: EC2 Access to S3 Using IAM Role

Difficulty: Beginner–Intermediate

AWS Domain: IAM + EC2 + S3

Status: Completed ✅
