
---

# Project 3 — EC2 to S3 Using IAM Role

```markdown
# Project 3: EC2 Access to S3 Using IAM Role

## Objective

Configure an **IAM Role** to allow an Amazon EC2 instance to access Amazon S3 without storing AWS access keys on the EC2 instance.

## Project Overview

In this project, I created an IAM role and attached an Amazon S3 read-only policy to it.

The role was assigned to an EC2 instance through an **IAM Instance Profile**.

This demonstrates secure access to AWS services using temporary credentials instead of long-term access keys.

## AWS Services Used

* AWS IAM
* Amazon EC2
* Amazon S3
* AWS Management Console

## IAM Role Configuration

The following role was created:

```text
EC2S3ReadOnlyRole
