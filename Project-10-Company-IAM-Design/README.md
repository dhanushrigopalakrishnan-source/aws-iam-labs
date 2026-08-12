````markdown
# Project 10 – Company IAM Design

## Objective

To design a simple and secure AWS IAM structure for different company teams using **IAM Groups, Users, Policies, and Least Privilege**.

## IAM Structure

```text
AWS Account
│
├── Developers Group
│   ├── dev1
│   ├── dev2
│   ├── AmazonEC2ReadOnlyAccess
│   └── AmazonS3ReadOnlyAccess
│
├── Finance Group
│   ├── FinanceUser
│   └── AWSBillingReadOnlyAccess
│
└── Support Group
    ├── support1
    └── CloudWatchReadOnlyAccess
````

## Team Access

| Team       | Users          | Permissions                 |
| ---------- | -------------- | --------------------------- |
| Developers | `dev1`, `dev2` | EC2 Read Only, S3 Read Only |
| Finance    | `FinanceUser`  | Billing Read Only           |
| Support    | `support1`     | CloudWatch Read Only        |

## IAM Policies Used

### Developers

* `AmazonEC2ReadOnlyAccess`
* `AmazonS3ReadOnlyAccess`

Developers can view EC2 and S3 resources without unnecessary administrative permissions.

### Finance

* `AWSBillingReadOnlyAccess`

The Finance team can view AWS billing information without receiving permissions to manage AWS infrastructure.

### Support

* `CloudWatchReadOnlyAccess`

The Support team can view CloudWatch monitoring information without modifying AWS resources.

## Least Privilege

Permissions are assigned according to each team's responsibilities.

```text
Developers → EC2 + S3 Read Only
Finance    → Billing Read Only
Support    → CloudWatch Read Only
```

This reduces unnecessary access and follows the **Principle of Least Privilege**.

