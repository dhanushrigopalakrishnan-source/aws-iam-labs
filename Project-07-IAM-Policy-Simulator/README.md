````markdown
# Project 7 – IAM Policy Simulator

## 📌 Objective

The objective of this project is to understand how the **AWS IAM Policy Simulator** evaluates permissions before an AWS action is performed.

The project demonstrates how IAM policies determine whether an action is **Allowed** or **Denied**.

---

## 🔐 IAM Concept

AWS IAM policies define what actions an IAM identity is allowed to perform.

The IAM Policy Simulator can be used to test these permissions without actually performing the AWS operation.

### Access Flow

```text
IAM User
    ↓
IAM Policy
    ↓
IAM Policy Simulator
    ↓
Test AWS Action
    ↓
Allowed / Denied
````

---

## 🛠️ AWS Services Used

| AWS Service          | Purpose                                     |
| -------------------- | ------------------------------------------- |
| IAM                  | Create the test user and manage permissions |
| IAM Policy Simulator | Test and evaluate IAM permissions           |
| Amazon EC2           | AWS service used for permission testing     |

---

## 👤 IAM User

A dedicated IAM user was created for testing:

```text
PolicySimulatorUser
```

The user was used as the principal in the IAM Policy Simulator.

---

## 📜 Custom IAM Policy

A customer-managed policy was created:

```text
Project7-EC2-ReadReboot
```

The policy provides permission to perform the following EC2 actions:

```text
ec2:DescribeInstances
ec2:RebootInstances
```

The policy does not grant:

```text
ec2:TerminateInstances
```

### Policy Permissions

```text
DescribeInstances → Allow
RebootInstances   → Allow
TerminateInstances → No permission
```

---

## 🧪 Policy Simulator Testing

The IAM Policy Simulator was used to test three EC2 actions:

### 1. DescribeInstances

Result:

```text
Allowed
```

The custom policy contains an explicit Allow statement for this action.

---

### 2. RebootInstances

Result:

```text
Allowed
```

The custom policy contains an explicit Allow statement for this action.

---

### 3. TerminateInstances

Result:

```text
Denied
```

The custom policy does not contain an Allow statement for this action.

The Policy Simulator reported:

```text
Implicit deny due to no statement(s) matching
```

---

## 📊 Simulation Results

| EC2 Action         | Result    | Reason                      |
| ------------------ | --------- | --------------------------- |
| DescribeInstances  | ✅ Allowed | Explicit Allow              |
| RebootInstances    | ✅ Allowed | Explicit Allow              |
| TerminateInstances | ❌ Denied  | No matching Allow statement |

---

## 🔄 Access Evaluation Flow

```text
PolicySimulatorUser
        |
        v
Project7-EC2-ReadReboot
        |
        +---- DescribeInstances ----> ✅ Allowed
        |
        +---- RebootInstances ------> ✅ Allowed
        |
        +---- TerminateInstances ---> ❌ Denied
```

---


## 🔒 Security Principle

This project demonstrates the **Principle of Least Privilege**.

Instead of allowing all EC2 actions, the custom policy grants only the permissions required for the test:

```text
DescribeInstances
RebootInstances
```

The user does not receive permission to terminate EC2 instances through this custom policy.

Limiting permissions reduces the potential impact of unauthorized or accidental actions.

---

## ✅ Result

The IAM Policy Simulator successfully evaluated the EC2 permissions.

The test demonstrated that:

* `DescribeInstances` is allowed.
* `RebootInstances` is allowed.
* `TerminateInstances` is denied.
* IAM policies determine whether an AWS action is permitted.
* The Policy Simulator can test permissions without actually performing the selected EC2 operations.


## 🎯 Learning Outcomes

Through this project, I learned:

* What the IAM Policy Simulator is.
* How IAM policies control AWS actions.
* How explicit Allow statements work.
* How implicit Deny works.
* How to test EC2 permissions using the Policy Simulator.
* How the Principle of Least Privilege can be applied to IAM policies.

````


