# Project 8: IAM Billing Access

> Demonstrates how to grant a Finance user access to only the AWS Billing Dashboard, while explicitly restricting access to core services like EC2, IAM, and S3 — a common real-world need for separating financial oversight from technical access.

## 🏗️ Architecture

```text
Finance User
     |
     v
Billing Policy
     |
     v
Billing Dashboard
     |
     +-- No EC2
     +-- No IAM
     +-- No S3
```

## 🛠️ Tech Stack & Services Used

- **Identity & Access:** AWS IAM (Users, Billing Permissions)
- **Billing:** AWS Billing & Cost Management Console
- **Security:** Principle of Least Privilege, Role Separation
- **Tools:** AWS Management Console

## 📋 Key Implementation Highlights

- Created a dedicated IAM user for the Finance team.
- Enabled IAM access to the Billing console at the account level (a prerequisite for any non-root user to view billing information).
- Attached a billing-scoped policy granting access to the Billing Dashboard and cost/usage data only.
- Verified the Finance user could view billing information but had no access to EC2, IAM, or S3 — keeping financial and technical access strictly separated.
- Demonstrated a real-world access pattern: Finance teams typically need cost visibility without any operational or administrative permissions.

### Access Summary

| IAM User      | Group/Policy         | Access Granted           | Access Denied         |
|-----------------|-----------------------|-----------------------------|--------------------------|
| Finance User      | Billing Policy          | Billing Dashboard, Cost & Usage | EC2, IAM, S3            |

## 🧪 Verification & Testing

Signed in as the Finance user and attempted to access both the Billing console and core AWS services.

**Test Results**

| Action                              | Result   |
|-----------------------------------------|------------|
| View Billing Dashboard                    | ALLOWED  |
| View Cost & Usage reports                  | ALLOWED  |
| Access EC2 console                          | DENIED   |
| Access IAM console                           | DENIED   |
| Access S3 console                             | DENIED   |

This confirmed that the Finance user's access was correctly scoped to billing-related information only, with no visibility or control over compute, identity, or storage resources.

## 📸 Screenshots

**Finance User Billing Access**
![Finance User Billing Access](screenshots/01-finance-user-billing-access.png)


## 🧹 Teardown & Resource Cleanup

After completing the lab:

- Remove the test Finance IAM user if it was created solely for this exercise.
- Detach the billing policy if it is not required for another project.
- Review the account's "IAM access to Billing" setting to confirm it reflects your intended security posture going forward.

**Security Note:** Never upload IAM passwords, access keys, secret access keys, MFA secrets, recovery codes, or other credentials to GitHub.

## 🎯 Learning Outcomes

- Scoping IAM access to Billing and Cost Management only
- Enabling IAM access to the Billing console at the account level
- Separating financial access from technical/operational access
- Applying least privilege for non-technical departments

## ✅ Project Result

Successfully configured a Finance IAM user with access limited to the Billing Dashboard and cost data, and verified that the user had no access to EC2, IAM, or S3 — confirming correct separation between financial and technical permissions.
