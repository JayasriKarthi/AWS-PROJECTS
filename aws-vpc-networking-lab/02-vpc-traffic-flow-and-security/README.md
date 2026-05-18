

# Creating a Private Subnet in AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com

---

# Project Overview

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_afe1fdbd)

In this project, I explored how to design a secure AWS network architecture by creating a **Private Subnet** inside an Amazon VPC. This project focused on understanding how AWS networking components work together to improve infrastructure security.

### Core Concepts Covered:
- Amazon VPC
- Public and Private Subnets
- Route Tables
- Network ACLs
- Secure traffic control
- AWS cloud networking design

---


### Why VPC Matters

Amazon VPC provides a private section of AWS where businesses can safely deploy applications, databases, and servers while maintaining full control over:

- IP ranges
- Routing
- Security
- Traffic permissions

---

# How I Used Amazon VPC in This Project

In this hands-on project, I used Amazon VPC to:

- Create a private subnet
- Configure a dedicated private route table
- Set up a custom Network ACL
- Restrict internet exposure
- Strengthen network-level security

---

# Private vs Public Subnets

## Understanding the Difference

### Public Subnet:
- Connected to an Internet Gateway
- Internet accessible
- Suitable for web servers and public applications

### Private Subnet:
- No direct internet access
- Used for internal resources such as:
  - Databases
  - Backend servers
  - Secure applications

---

## Why Private Subnets Are Important

Private subnets improve security by:

- Preventing unauthorized internet access
- Protecting confidential data
- Restricting exposure
- Supporting internal-only workloads

### CIDR Block Requirement

Private and public subnets must have unique CIDR blocks to ensure traffic routes correctly within the VPC.

---

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_afe1fdbd)

---

# Dedicated Route Table Configuration

## What I Did

By default, my private subnet was associated with the main route table.

To properly isolate it, I:

- Created a dedicated private route table
- Removed internet gateway routing
- Configured internal VPC traffic only

---

## Why This Matters

A private route table ensures:

- No direct internet connectivity
- Secure internal communication
- Controlled resource access
- Better network segmentation

---

## Route Table Benefits:
- Enhanced security
- Traffic isolation
- Better compliance
- Enterprise-grade architecture

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_b4b904b5)

---

# Custom Network ACL Configuration

## What I Did

I created a dedicated Network ACL for the private subnet to enforce stricter traffic control.

### Configuration Included:
- Deny unnecessary inbound traffic
- Deny unnecessary outbound traffic
- Allow only essential VPC communication

---

## Why Network ACLs Matter

Network ACLs act as an additional security layer by controlling traffic at the subnet level.

### Security Benefits:
- Stateless traffic filtering
- Explicit traffic control
- Extra protection beyond security groups
- Improved infrastructure security posture

---

## Final ACL Design:
- Restricted unauthorized traffic
- Protected private resources
- Improved subnet security

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_1ed2cb07)

---

# Skills Developed

Through this project, I strengthened my knowledge in:

- AWS VPC architecture
- Private subnet deployment
- Secure route table configuration
- Network ACL implementation
- Cloud security best practices
- Infrastructure segmentation

---

# Final Thoughts

This project provided valuable real-world experience in designing secure AWS cloud environments.

### Major Takeaways:
- Private networking is essential for cloud security
- Route tables control connectivity
- Network ACLs improve traffic management
- AWS networking services are critical for enterprise solutions

---

# Conclusion

Creating a Private Subnet in AWS helped me understand how organizations secure sensitive infrastructure by limiting internet exposure and applying multiple security layers.

This project strengthened my practical AWS networking and cybersecurity knowledge, making it an essential step toward mastering:

- Cloud Security
- AWS Solutions Architecture
- DevOps Infrastructure
- Enterprise Networking

---


