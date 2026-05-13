# Cloud Security with AWS IAM

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam?utm_source=chatgpt.com)

**Author:** Jayasri Selvi
**Email:** [jayasriselvi23@gmail.com](mailto:jayasriselvi23@gmail.com)

---

![Cloud Security with AWS IAM](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_1c864649)

---

# Introducing Today’s Project!

## Project Overview

In this project, I explored cloud security concepts using Amazon Web Services Identity and Access Management (IAM). The main goal of this project was to understand how permissions and access control work inside an AWS environment.

To demonstrate this, I launched multiple EC2 instances and configured IAM policies, IAM users, and user groups to control which resources users could access. I also tested real-world permission scenarios by logging in as different IAM users and verifying access restrictions.

This project helped me gain practical experience in securing cloud resources and implementing role-based access control in AWS.

---

# Tools and Concepts

## AWS Services Used

* Amazon Web Services IAM (Identity and Access Management)
* Amazon EC2 EC2 Instances

## Key Concepts Learned

* Creating and managing IAM users and user groups
* Writing IAM policies using JSON
* Understanding IAM policy elements such as:

  * Effect
  * Action
  * Resource
  * Condition
* Using tags to organize AWS resources
* Launching and managing EC2 instances
* Restricting access based on resource tags
* Creating AWS account aliases for easier login
* Testing permissions using IAM users
* Using the IAM Policy Simulator

---

# Project Reflection

This project took me approximately **3 hours** to complete.

The most challenging part was understanding how IAM policies interact with EC2 instances and how permissions are evaluated based on resource tags and policy conditions.

One of the most interesting parts of this project was testing IAM permissions in real time and seeing how AWS blocks unauthorized actions automatically.

Overall, this project improved my understanding of cloud security fundamentals and taught me how organizations manage secure access in AWS environments.

---

# Architecture Overview

## Project Workflow

1. Launch EC2 instances
2. Add tags to resources
3. Create IAM policies
4. Create IAM user groups
5. Attach policies to groups
6. Create IAM users
7. Test permissions using IAM users
8. Verify access restrictions with IAM Policy Simulator

---

# Launching EC2 Instances

## What I Did

In this step, I launched two EC2 instances to simulate different environments:

* Development Environment
* Production Environment

These instances represent real-world infrastructure where different permissions are applied depending on the environment.

---

# Understanding Tags

## What Are Tags?

Tags are key-value pairs used to organize and identify AWS resources.

They help administrators:

* Group resources
* Apply access control
* Track billing
* Manage environments easily

For example:

* `Env = development`
* `Env = production`

---

# My Tag Configuration

I configured tags for both EC2 instances:

| Instance Type      | Tag Key | Tag Value   |
| ------------------ | ------- | ----------- |
| Development Server | Env     | development |
| Production Server  | Env     | production  |

This tagging strategy allowed IAM policies to control access based on environment type.

![EC2 Tags](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_2e0e5a5d)

---

# IAM Policies

## What I Did

In this step, I created a custom IAM policy that allowed users to access only development EC2 instances.

The policy was written in JSON format and used resource tags to control permissions.

---

# Understanding IAM Policies

IAM policies are JSON-based permission documents used to define:

* What actions are allowed or denied
* Which AWS resources can be accessed
* Who can perform those actions

Policies are the foundation of security and access management in AWS.

---

# Understanding Policy Components

## Effect

The `Effect` element determines whether access is:

* `Allow`
* `Deny`

Example:

```json
"Effect": "Allow"
```

---

## Action

The `Action` element specifies which AWS operations users can perform.

Example:

```json
"Action": "ec2:*"
```

This allows EC2-related actions.

---

## Resource

The `Resource` element defines which AWS resources the policy applies to.

Example:

```json
"Resource": "*"
```

This means the policy applies to all matching resources.

---

## Condition

The `Condition` element applies rules that must be met before access is granted.

In this project, access was allowed only if the EC2 instance had the tag:

```json
"Env": "development"
```

---

# My IAM JSON Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:*",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "ec2:ResourceTag/Env": "development"
        }
      }
    }
  ]
}
```

This policy allows users to perform EC2 actions only on instances tagged as `development`.

![IAM Policy](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_1c864649)

---

# AWS Account Alias

## What I Did

In this step, I configured an AWS Account Alias to create a user-friendly login URL.

---

# Understanding Account Aliases

An account alias replaces the default AWS account ID in the login URL with a custom name, making it easier for IAM users to sign in.

---

# My AWS Sign-In URL

```text
https://nextwork-alias-jayasri.signin.aws.amazon.com/console
```

Creating the account alias took only a few minutes and improved accessibility for IAM users.

![AWS Account Alias](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_0eb4439b)

---

# IAM Users and User Groups

## What I Did

In this step, I created:

* IAM User Groups
* IAM Users for interns

I then attached the custom IAM policy to the user group.

---

# Understanding IAM User Groups

IAM user groups allow administrators to manage permissions for multiple users at once.

Instead of assigning permissions individually, policies can be attached directly to the group.

This makes permission management easier and more scalable.

---

# Understanding IAM Users

IAM users are individual identities created inside an AWS account.

Each IAM user can:

* Log in to the AWS Console
* Access AWS resources
* Receive specific permissions

---

# Attaching Policies to Groups

I attached the custom development-access policy to the intern user group.

As a result:

* Intern users could access development resources
* Production resources remained restricted

This demonstrates the principle of **least privilege access** in cloud security.

---

# Logging In as an IAM User

## What I Did

I tested the IAM configuration by logging in as an intern IAM user.

---

# Observations

After logging in:

* I successfully accessed allowed AWS resources
* Some actions displayed **Access Denied** errors

This happened because the IAM policy restricted access to production resources.

The test confirmed that the IAM policy was working correctly.

![IAM User Login](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_6f2ab446)

---

# Testing IAM Policies

## Testing Production Access

When I attempted to stop the production EC2 instance, AWS denied the action because the instance did not match the required tag condition.

This verified that the IAM policy successfully protected production resources.

![Production Access Denied](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_0e7a9d6a)

---

## Testing Development Access

Next, I tested access to the development instance.

The IAM user could interact only with resources allowed by the policy configuration.

This demonstrated how AWS IAM enforces secure and controlled access to cloud infrastructure.

![Development Instance Test](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-security-iam_1811801c)

---

# IAM Policy Simulator

## Understanding the IAM Policy Simulator

The IAM Policy Simulator is a tool provided by AWS that helps test and troubleshoot IAM permissions before applying them in production.

It allows administrators to:

* Simulate user permissions
* Verify policy behavior
* Detect permission issues
* Improve security configurations

---

# How I Used the Simulator

I used the IAM Policy Simulator to verify whether my IAM users could:

* Access development EC2 instances
* Stop production instances
* Perform EC2 actions correctly

The simulator helped me understand how AWS evaluates IAM policies and conditions.

---

# Key Takeaways

Through this project, I learned:

* How AWS IAM controls access securely
* How resource tags can be used for permission management
* How to create and test IAM policies
* How IAM users and groups simplify access management
* How AWS prevents unauthorized actions using policy conditions

This project gave me hands-on experience with real-world cloud security practices and strengthened my understanding of AWS IAM fundamentals.

---

# Suggested GitHub Repository Structure

```bash
cloud-security-with-aws-iam/
│
├── README.md
├── images/
│   ├── ec2-tags.png
│   ├── iam-policy.png
│   ├── iam-login.png
│   ├── production-access.png
│   └── development-test.png
│
├── policies/
│   └── development-ec2-policy.json
│
├── docs/
│   ├── architecture.md
│   ├── iam-notes.md
│   └── troubleshooting.md
│
└── screenshots/
    ├── account-alias.png
    ├── ec2-instances.png
    └── policy-simulator.png
```
