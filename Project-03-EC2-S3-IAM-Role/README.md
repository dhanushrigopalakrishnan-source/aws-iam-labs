# Project 3 – EC2 Access to S3 Using IAM Role

## 📌 Objective

The objective of this project is to understand how an **IAM Role** allows an Amazon EC2 instance to access Amazon S3 without storing AWS Access Keys on the EC2 instance.

This project demonstrates the use of:

- IAM Roles
- IAM Instance Profiles
- EC2
- Amazon S3
- AWS Managed Policies
- Temporary Credentials
- Principle of Least Privilege

---

## 🏗️ Architecture

```text
                    Amazon EC2
                        │
                        │ IAM Instance Profile
                        ▼
              EC2-S3-ReadOnly-Role
                        │
                        │
                        ▼
          AmazonS3ReadOnlyAccess
                        │
                        ▼
                  Amazon S3
                        │
                        ▼
              iam-project3-test.txt
