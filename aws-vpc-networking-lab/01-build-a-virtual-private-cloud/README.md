<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud (VPC)

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com

---

## Project Overview

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-vpc_2facf927)

In this project, I built a **Virtual Private Cloud (VPC)** using AWS to understand how secure cloud networking works. The goal was to gain practical experience with:

- Amazon VPC
- Public and Private Subnets
- Internet Gateways
- IPv4 CIDR blocks
- AWS Console and CLI tools

This hands-on project helped me understand how AWS networking services create secure environments for cloud resources while controlling internet accessibility.

---

## What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is an AWS service that allows users to create a logically isolated virtual network within AWS. It gives full control over:

- IP address ranges
- Subnets
- Route tables
- Internet gateways
- Security configurations

Using Amazon VPC, organizations can securely launch AWS resources such as EC2 instances while protecting them from unauthorized external access.

### Why VPC is Important

Amazon VPC helps:

- Secure cloud resources
- Separate public and private environments
- Control network traffic
- Improve infrastructure scalability
- Protect applications from unauthorized access


---

# Step 1: Creating a Virtual Private Cloud (VPC)

## What I Did

- Accessed the AWS VPC Console
- Created a custom VPC
- Defined IPv4 CIDR block range
- Configured network boundaries

## How VPCs Work

A VPC acts like a private data center inside AWS, allowing users to control:

- Which resources can communicate
- Internet exposure
- Security layers
- Internal architecture

## Default VPC Explanation

AWS automatically provides a default VPC when an account is created so users can launch resources immediately without advanced configuration.

### IPv4 CIDR Block

CIDR blocks define the IP address range for the VPC.

Example:
- `10.0.0.0/16`

This creates a large private network range for managing cloud resources efficiently.

---

# Step 2: Creating Subnets

## What I Did

- Created subnets within my VPC
- Configured subnet ranges
- Enabled public IP assignment

## Understanding Subnets

Subnets divide a VPC into smaller network segments.

### Public Subnet:
- Connected to internet gateway
- Internet accessible
- Used for public-facing services

### Private Subnet:
- No direct internet access
- Used for databases or sensitive resources

---

## Public vs Private Subnets

| Public Subnet | Private Subnet |
|---------------|----------------|
| Internet accessible | Internal access only |
| Public IP support | No public IP |
| Web servers | Databases |

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-vpc_157c4219)

### Auto-Assign Public IPv4

By enabling this option:

- EC2 instances automatically receive public IP addresses
- Instances become reachable from the internet
- Useful for hosting websites or public applications

---

# Step 3: Configuring Internet Gateway

## What I Did

- Created an Internet Gateway
- Attached it to my VPC
- Enabled internet communication

## Purpose of Internet Gateway

An Internet Gateway acts as a bridge between:

- AWS private network
- Public internet

Without it:

- Public subnets cannot access the internet
- EC2 instances remain isolated

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-vpc_4ae90410)

---

# Using AWS CLI (Project Extension)

## What I Explored

I also learned how VPC resources can be managed using:

- AWS CloudShell
- AWS CLI commands

### Benefits of AWS CLI:
- Faster automation
- Scriptable deployments
- Better for DevOps workflows
- Repeatable infrastructure creation

### Example Commands:
```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16
aws ec2 create-subnet --vpc-id vpc-id --cidr-block 10.0.1.0/24
aws ec2 create-internet-gateway