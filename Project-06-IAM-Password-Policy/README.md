# Project 6 – IAM Password Policy

## 📌 Objective

The objective of this project is to configure and test an AWS IAM password policy.

The password policy is used to enforce strong password requirements for IAM users and reduce the risk of unauthorized access caused by weak or reused passwords.

---

## 🔐 Password Policy

The following custom password requirements were configured for IAM users:

- Minimum password length: **14 characters**
- At least one uppercase letter
- At least one lowercase letter
- At least one number
- At least one non-alphanumeric character
- Password reuse prevention for the previous **5 password changes**
- Users are allowed to change their own passwords
- Passwords do not expire

---

## 🛠️ AWS Service Used

| AWS Service | Purpose |
|---|---|
| IAM | Configure and enforce the password policy for IAM users |

---

## ⚙️ Password Policy Configuration

The password policy was configured from:

```text
AWS Console
    ↓
IAM
    ↓
Account Settings
    ↓
Password Policy

The following settings were applied:

Minimum password length: 14

Uppercase letter: Required
Lowercase letter: Required
Number: Required
Special character: Required

Password expiration: Disabled
Allow users to change their own password: Enabled
Prevent password reuse: Enabled
Previous passwords remembered: 5
🧪 Testing

A temporary IAM user named:

PasswordPolicyTest

was created to test the password policy.

Test 1 – Weak Password

A weak password was entered:

password123

AWS rejected the password because it did not meet the configured password requirements.

The error confirmed that the password:

Must be at least 14 characters long
Must contain an uppercase letter
Must contain a special character

This confirmed that the password policy was being enforced.

Test 2 – Strong Password

A strong test password satisfying the configured requirements was entered.

The password met the following requirements:

Minimum 14 characters
Uppercase letter
Lowercase letters
Number
Special character

AWS accepted the password and allowed the IAM user to be created successfully.

🔄 Password Policy Flow
IAM User
    |
    v
Enter Password
    |
    v
IAM Password Policy
    |
    +---- Does not meet requirements ----> ❌ Rejected
    |
    +---- Meets requirements ------------> ✅ Accepted
                                              |
                                              v
                                         IAM User Created
✅ Result

The IAM password policy was successfully configured and tested.

The project demonstrated that:

Weak passwords are rejected.
Strong passwords are accepted.
Password complexity requirements are enforced.
Password reuse prevention is enabled.
IAM users can change their own passwords.
Final Result
Strong Password Policy
          ↓
Weak Password → ❌ Rejected
          ↓
Strong Password → ✅ Accepted
🔒 Security Benefits

A strong IAM password policy helps protect AWS accounts from password-based attacks.

The configured policy improves security by:

Increasing password length
Requiring different character types
Preventing immediate password reuse
Allowing users to manage their own passwords

These controls help reduce the risk associated with weak or reused passwords.

