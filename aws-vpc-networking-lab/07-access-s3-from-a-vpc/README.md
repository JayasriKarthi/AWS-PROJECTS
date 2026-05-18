

# Introducing Today's Project!!


# How I used Amazon VPC in this project

In this project, I:

- Created a custom VPC  
- Configured a public subnet  
- Launched an EC2 instance  
- Created an S3 bucket  
- Configured IAM access keys  
- Installed and configured AWS CLI  
- Created a Gateway Endpoint for S3  
- Applied bucket policies  
- Updated route tables  
- Validated secure private connectivity  

This allowed my EC2 instance to communicate securely with Amazon S3 without using the public internet.

---

# One thing I didn’t expect

I didn’t expect how:

- Route tables  
- Bucket policies  
- Endpoint policies  

must all work together precisely to maintain secure private access while simultaneously blocking public traffic.

---


# Part 1: Initial Infrastructure Setup

## Step 1 - Architecture Setup

In this step, I:

- Created a custom VPC  
- Configured a public subnet  
- Launched an EC2 instance  
- Created an S3 bucket  

### Result:
A functional networking and storage environment was established.

---

## Step 2 - Connect to EC2 Instance

I connected to my EC2 instance using:

- EC2 Instance Connect  

### Purpose:
Provides secure browser-based terminal access without SSH key pair complexity.

---

## Step 3 - Set Up Access Keys

I created IAM access keys and configured AWS CLI on my EC2 instance.

### Configured:

- AWS Access Key ID  
- AWS Secret Access Key  
- Default Region  

![alt text](<screenshots/Screenshot from 2026-05-16 16-06-54.png>)

### Purpose:
Allows EC2 to authenticate securely with AWS services.

### Best Practice:
Although access keys were used here, IAM Roles are the recommended production approach for temporary, secure credential management.

---

## Step 4 - Interact with S3 Bucket

![alt text](<screenshots/Screenshot from 2026-05-16 16-00-38.png>)

![alt text](image.png)

![alt text](<screenshots/Screenshot from 2026-05-16 16-06-54.png>)

### Command:
```bash
aws s3 ls

