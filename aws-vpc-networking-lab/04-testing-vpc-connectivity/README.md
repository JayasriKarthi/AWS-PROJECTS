# Testing VPC Connectivity in AWS



**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com

---

# Project Overview

In this project, I explored **VPC Connectivity Testing** by setting up communication between public and private EC2 instances inside an Amazon VPC and verifying internet access.

This project provided practical experience with:

- Amazon VPC
- EC2 Instance Connectivity
- Security Groups
- SSH Access
- Ping Testing
- Curl Commands
- Public and Private Communication
- Network Troubleshooting

---



### Key Features:
- Network isolation from other AWS users
- Full control over:
  - IP address ranges
  - Subnets
  - Route tables
  - Internet gateways
- Enhanced security using:
  - Security Groups
  - Network ACLs
- Secure communication between resources

---

## How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:

- Connect public and private EC2 instances
- Configure security groups
- Test server-to-server communication
- Verify internet access
- Troubleshoot network connectivity issues

---



# Step 1: Connecting to an EC2 Instance

## What is Connectivity?

Connectivity refers to the ability of resources within a network to communicate with one another.

In this step, I tested whether I could successfully connect to my public EC2 instance.

### My First Test:
- Connected to the public server
- Verified server accessibility
- Confirmed network setup

---

# Step 2: Using EC2 Instance Connect

## What I Did

I used **EC2 Instance Connect** to securely access my public EC2 instance directly from the AWS Console.

### Why EC2 Instance Connect?
- Browser-based SSH access
- No external SSH client needed
- Simplified server management
- Secure remote access

---

## Initial Error:
My first attempt failed because:

- SSH inbound rules were missing
- Security group did not allow port 22 access

---

## Solution:
I fixed the issue by:

- Editing inbound security group rules
- Adding SSH access (Port 22)
- Restricting access securely

---

# Step 3: Testing Connectivity Between Public and Private Servers

## Using Ping

Ping is a network diagnostic tool used to verify whether one server can communicate with another.

 Project Screenshots



### SSH Failure for Troubleshooting
![alt text](<images/Screenshot from 2026-05-15 15-29-51.png>)

### Successful SSH Session
![alt text](<images/Screenshot from 2026-05-15 15-37-53.png>)


### Private Instance Connectivity Attempt
![alt text](<images/Screenshot from 2026-05-15 15-47-23.png>)

### Successful Internal Ping Test
![alt text](<images/Screenshot from 2026-05-15 16-16-58.png>)





## Skills Developed

Through this project, I strengthened my knowledge in:

- AWS VPC Networking  
- EC2 Access Management  
- Security Group Configuration  
- SSH Troubleshooting  
- Public & Private Communication  
- Network Diagnostics  
- Ping and Curl Tools  
- Cloud Infrastructure Security  

## Final Thoughts

This project was highly valuable for understanding how AWS cloud networking operates in real-world scenarios.

### Major Takeaways:

- Security groups control access  
- Connectivity testing is essential  
- Troubleshooting improves infrastructure reliability  
- Public and private subnet communication requires proper configuration  
- Internet access must be securely managed  

### Command Used:
```bash
ping <private-instance-ip>