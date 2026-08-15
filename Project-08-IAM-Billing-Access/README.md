
---

# Project 8 — IAM Billing Access

```markdown
# Project 8: AWS IAM Billing Access

## Objective

Configure an IAM user with **read-only access to AWS Billing information** and verify access to the AWS Bills page.

## Project Overview

In this project, I configured an IAM user for finance-related AWS billing access.

The AWS managed policy `AWSBillingReadOnlyAccess` was used to provide read-only access to billing information without granting administrative permissions.

## AWS Services Used

* AWS IAM
* AWS Billing and Cost Management
* AWS Management Console

## IAM Configuration

The IAM user was:

```text
FinanceUser
