# AWS IAM User Setup

This guide outlines the steps to create a new IAM user, attach an inline policy to grant permissions, and generate access keys using the AWS Command Line Interface (CLI).

## Prerequisites

Before executing these commands, ensure that you have:

- Installed and configured the AWS CLI.
- Sufficient permissions to perform IAM operations.

## Steps

### 1. Create IAM User

Run the following command to create a new IAM user:

```bash
aws iam create-user --user-name unifyapps-infra-automator
```

### 2. Create Inline Policy

Create a policy document in JSON format (e.g., policy.json) defining the permissions you want to grant. Then, execute the following command to create an inline policy for the user:

```bash
aws iam create-policy \
    --policy-name YourPolicyName \
    --policy-document file://policy.json
```

### 3. Attach Policy to User

Attach the created policy to the user using the following command:

```bash
aws iam attach-user-policy --user-name unifyapps-infra-automator --policy-arn arn:aws:iam::aws:policy/YourManagedPolicyName
```

### 4. Generate Access Key

To generate access keys for the user, execute:

```bash
aws iam create-access-key --user-name unifyapps-infra-automator
```

