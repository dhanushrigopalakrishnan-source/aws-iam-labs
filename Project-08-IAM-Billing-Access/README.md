
````markdown
# Project 8 – IAM Billing Access

## Objective

To create an IAM user with read-only access to AWS Billing information.

## AWS Services Used

- IAM
- Billing and Cost Management

## IAM User

```text
FinanceUser
````

## Permission

The following AWS managed policy was attached:

```text
AWSBillingReadOnlyAccess
```

This policy allows the user to view billing information without giving administrative access to AWS resources.

## Billing Access

IAM access to Billing was enabled at the AWS account level.

The `FinanceUser` was then used to access:

**Billing and Cost Management → Bills**

The Bills page was successfully accessible.

## Result

The `FinanceUser` successfully accessed the AWS Bills page and viewed the estimated bill summary.

```text
FinanceUser
     ↓
AWSBillingReadOnlyAccess
     ↓
Billing and Cost Management
     ↓
Bills → ✅ Accessible
```

