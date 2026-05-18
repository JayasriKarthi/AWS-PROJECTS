
# 🌉 AWS VPC Peering Project

## 📌 Project Overview
This project demonstrates how to build and configure **VPC Peering** in AWS by creating two separate Virtual Private Clouds (VPCs), establishing a peering connection between them, configuring route tables, launching EC2 instances, and validating private communication using ICMP (ping).

By completing this project, you gain practical experience with:

- Amazon VPC setup
- Public subnet configuration
- VPC peering connections
- Route table updates
- Security groups
- Elastic IP allocation
- EC2 instance deployment
- Network troubleshooting
- Inter-VPC communication testing

---

## 🎯 Objectives

- Create two custom VPCs with unique CIDR blocks
- Configure subnets, route tables, and internet gateways
- Establish secure VPC peering
- Launch EC2 instances into each VPC
- Configure security rules for SSH and ICMP
- Test private connectivity between instances
- Troubleshoot common networking issues

---

## 🛠️ AWS Services Used

- **Amazon VPC**
- **VPC Peering**
- **Route Tables**
- **Internet Gateway**
- **Elastic IP**
- **Amazon EC2**
- **Security Groups**
- **Network ACLs**

---


## How I Used Amazon VPC in This Project

In this project, I created **two separate custom VPCs** with unique CIDR ranges:

- **VPC 1:** `10.1.0.0/16`
- **VPC 2:** `10.2.0.0/16`

I then connected these VPCs using **VPC Peering**, allowing private communication between EC2 instances in each network.

---

## Key Learning Experience

### One thing I didn’t expect:
I learned that even after establishing a peering connection, communication would still fail unless:

- Route tables were properly configured
- Security groups allowed ICMP/SSH traffic
- Elastic IPs were configured when required

This highlighted how multiple AWS networking layers work together.

---


# Part 1: Building Multi-VPC Architecture

## Step 1 - Set Up Two Custom VPCs

I created two VPCs from scratch with non-overlapping CIDR blocks to ensure proper routing.

### Why unique CIDRs are important:
Overlapping IP ranges would prevent successful peering communication.

---

## Step 2 - Create a VPC Peering Connection

I established a peering connection between:

- VPC 1 (Requester)
- VPC 2 (Accepter)

![alt text](<images/Screenshot from 2026-05-18 14-17-58.png>)

### Requester vs Accepter:
- **Requester:** Initiates the peering request
- **Accepter:** Accepts the request

![alt text](<images/Screenshot from 2026-05-18 14-17-30.png>)

---

## Step 3 - Update Route Tables

To enable traffic flow between both VPCs:

- VPC 1 route table directed traffic to VPC 2
- VPC 2 route table directed traffic to VPC 1

### Purpose:
This ensures that each VPC knows how to reach the other through the peering connection.

![
](<images/Screenshot from 2026-05-18 14-18-22.png>)


---

## Step 4 - Launch EC2 Instances

I launched:

- One EC2 instance in VPC 1
- One EC2 instance in VPC 2

These instances were used to validate connectivity across peered networks.

---

## Multi-VPC Architecture

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-peering_11111111)

---

# Part 2: Connectivity Testing and Troubleshooting

## Step 5 - Use EC2 Instance Connect

I used AWS EC2 Instance Connect for browser-based SSH access to test networking without managing traditional key pairs.

---

## Step 6 - Troubleshoot Connection Issues

Initially, SSH access failed due to:

- Missing public IP
- Security restrictions
- Networking misconfigurations

![alt text](<images/Screenshot from 2026-05-18 14-19-12.png>)

---

## Elastic IP Solution

To resolve connectivity issues, I assigned an **Elastic IP Address**.

### What is an Elastic IP?
A static public IPv4 address designed for dynamic cloud environments.

### Why it solved the issue:
It provided stable public access for secure SSH management.

---

![alt text](<images/Screenshot from 2026-05-18 14-19-31.png>)

## Step 7 - Test VPC Peering with Ping

To validate peering, I used:

```bash
ping <private-ip-address>