# Project 1: AWS IAM Users and Groups

> Designed IAM users and department-based groups with controlled permissions using AWS managed policies. The project demonstrates role-based access control and the Principle of Least Privilege.

## 🏗️ Architecture Diagram

```text
                    AWS IAM
                       |
        +--------------+--------------+
        |              |              |
        v              v              v
   Developers       DBAdmins        Support
        |              |              |
        v              v              v
     EC2 Read       RDS Full      CloudWatch
      Only           Access       Read Only
        |              |              |
   +----+----+         |              |
   |         |         |              |
  dev1      dev2      dba1         support1
🛠️ Tech Stack & Services Used
Identity & Access: AWS IAM
Compute: Amazon EC2
Database: Amazon RDS
Monitoring: Amazon CloudWatch
Security: IAM Groups, AWS Managed Policies, Least Privilege
Tools: AWS Management Console
📋 Key Implementation Highlights
Created department-based IAM groups for Developers, DBAdmins, and Support.
Assigned AWS managed policies based on each group's responsibilities.
Added IAM users to the appropriate groups.
Used group-based permissions instead of assigning unnecessary permissions directly to users.
Applied the Principle of Least Privilege.
Verified that an EC2 read-only user could view EC2 resources but could not terminate an instance.
IAM Groups and Permissions
IAM Group	Policy	Access
Developers	AmazonEC2ReadOnlyAccess	EC2 Read Only
DBAdmins	AmazonRDSFullAccess	RDS Full Access
Support	CloudWatchReadOnlyAccess	CloudWatch Read Only
IAM Users
User	Group
dev1	Developers
dev2	Developers
dba1	DBAdmins
support1	Support
🧪 Verification & Testing

The dev1 user was tested with the AmazonEC2ReadOnlyAccess policy.

Test Results
View EC2 resources       → ALLOWED
Terminate EC2 instance   → DENIED

The termination attempt was denied because the user did not have the required ec2:TerminateInstances permission.

This verified that the IAM group provided the intended read-only access.

📸 Screenshots
IAM Users and Groups

Developers Group Permissions

EC2 Termination Denied

🧹 Teardown & Resource Cleanup

After completing the lab:

Remove test IAM users that are no longer required.
Remove IAM users from groups if the groups are no longer needed.
Delete test IAM groups that were created specifically for this project.
Review attached policies before deleting any IAM resources.
Keep IAM resources that are required by other AWS projects.

Security Note: Never upload IAM passwords, access keys, secret access keys, MFA secrets, recovery codes, or other credentials to GitHub.

🎯 Learning Outcomes
IAM Users
IAM Groups
AWS Managed Policies
Group-based permissions
Role-Based Access Control
Principle of Least Privilege
EC2 permission testing
IAM security best practices
✅ Project Result

Successfully implemented department-based IAM access control and verified that permissions were restricted according to each user's assigned group.
