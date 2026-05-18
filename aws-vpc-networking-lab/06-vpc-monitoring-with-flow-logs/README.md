

# AWS VPC Peering & Network Monitoring Project

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-peering)  
**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com  

---

# 📌 Project Overview

This project demonstrates how to design, configure, and monitor a **multi-VPC AWS architecture** using:

- Amazon VPC
- EC2 Instances
- VPC Peering
- Route Tables
- Security Groups
- VPC Flow Logs
- CloudWatch Log Groups
- IAM Policies & Roles
- CloudWatch Logs Insights

The main objective was to establish **private communication between two VPCs** while also implementing **network traffic monitoring** for visibility, troubleshooting, and security analysis.

---

# 🎯 Project Goals

By completing this project, I learned how to:

- Build two custom VPCs from scratch
- Launch EC2 instances in separate VPCs
- Configure VPC Peering for private communication
- Update route tables for inter-VPC traffic
- Troubleshoot connectivity issues
- Enable and configure VPC Flow Logs
- Store logs in CloudWatch
- Create IAM policies and roles for logging permissions
- Analyze network activity using CloudWatch Logs Insights

---

# 🏗️ Architecture Design

## VPC Setup

| Resource | CIDR Block |
|---------|------------|
| VPC 1 | 10.1.0.0/16 |
| VPC 2 | 10.2.0.0/16 |

### Key Components:
- 2 Public Subnets
- 2 EC2 Instances
- Internet Gateways
- Security Groups
- VPC Peering Connection
- Flow Logs
- CloudWatch Monitoring

---


# 🚀 Project Implementation Steps

---

# Part 1: Infrastructure Setup

## Step 1 - Create Two VPCs

### VPC 1:
- Name: NextWork-1
- CIDR: 10.1.0.0/16

### VPC 2:
- Name: NextWork-2
- CIDR: 10.2.0.0/16

### Configuration:
- 1 Availability Zone each
- 1 Public Subnet each
- No NAT Gateway
- No Private Subnets
- DNS enabled

---

## Step 2 - Launch EC2 Instances

### Instance Details:
- Amazon Linux 2023 AMI
- t2.micro
- Public IP enabled
- No key pair
- EC2 Instance Connect enabled

### Security Groups:
- Allowed SSH
- Allowed ICMP (Ping)
- Public internet access for testing

---

# 🌉 Step 3 - Create VPC Peering Connection

### Process:
- Requester: VPC 1
- Accepter: VPC 2
- Same AWS Account
- Same Region

### Purpose:
To enable private communication between:
- EC2 in VPC 1
- EC2 in VPC 2

---

## 📷 VPC Peering Setup
![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-peering_1cbb1b88)

---

# 🛣️ Step 4 - Update Route Tables

### Added Routes:

### VPC 1 Route Table:
- Destination: 10.2.0.0/16
- Target: Peering Connection

### VPC 2 Route Table:
- Destination: 10.1.0.0/16
- Target: Peering Connection

### Why?
Without route updates, VPCs cannot locate each other’s private networks.

---

## 📷 Route Table Configuration
![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-peering_4a9e8014)

---

# Part 2: Monitoring & Logging Setup

# 📊 Step 5 - Configure CloudWatch Log Group

### Created:
- Log Group Name: NextWorkVPCFlowLogsGroup

### Purpose:
To store and centralize VPC network traffic logs.

![alt text](<screenshots/Screenshot from 2026-05-16 12-25-29.png>)


---

# 🔐 Step 6 - Create IAM Policy & Role for Flow Logs

## IAM Policy:
Permissions included:
- logs:CreateLogGroup
- logs:CreateLogStream
- logs:PutLogEvents
- logs:DescribeLogGroups
- logs:DescribeLogStreams

## IAM Role:
- Trusted Entity: vpc-flow-logs.amazonaws.com

### Purpose:
Allow VPC Flow Logs to publish traffic logs to CloudWatch.

## Log Insights

![alt text](<screenshots/Screenshot from 2026-05-16 12-37-27.png>)

---

# 📝 Step 7 - Enable VPC Flow Logs

### Configuration:
- Filter: ALL
- Aggregation Interval: 1 Minute
- Destination: CloudWatch Logs
- Log Group: NextWorkVPCFlowLogsGroup
- IAM Role: NextWorkVPCFlowLogsRole

### Monitoring Captures:
- Accepted traffic
- Rejected traffic
- Source IP
- Destination IP
- Protocols
- Packet counts
- Bytes transferred

---

## 📷 Flow Log Configuration

![alt text](<screenshots/Screenshot from 2026-05-16 12-26-01.png>)


---

# 🧪 Step 8 - Test VPC Connectivity

### Initial Test:
- Ping via Private IP ❌ Failed

### Cause:
- Missing peering route

### After Fix:
- Ping via Private IP ✅ Success

### Validation:
Confirmed secure private communication through VPC Peering.


---

# 📈 Step 9 - Monitor Traffic with CloudWatch Logs Insights

### Sample Analysis:
Used query:
- Top 10 byte transfers by source and destination IPs

### Insights:
- Network traffic patterns
- Successful packet transfers
- Rejected packets
- EC2 Instance Connect activity
- Security troubleshooting

### Key Benefits:
- Real-time monitoring
- Security auditing
- Traffic visibility
- Performance troubleshooting

---

# 📷 CloudWatch Logs Monitoring
 ![alt text](<screenshots/Screenshot from 2026-05-16 12-37-27.png>)

---

# 🛠️ Troubleshooting Challenges

## Issue 1:
### EC2 Instance Connect Failure
### Solution:
- Assigned Elastic IP addresses

---

## Issue 2:
### Private Ping Failure
### Solution:
- Added peering routes

---

## Issue 3:
### ICMP Traffic Blocked
### Solution:
- Updated Security Group rules

---

# 📚 Key Learnings

### Networking:
- VPC design
- CIDR planning
- Route tables
- Peering architecture

### Security:
- Security groups
- IAM roles
- IAM policies

### Monitoring:
- Flow Logs
- CloudWatch
- Log Insights
- Traffic analysis

---



# 🏁 Final Outcome

Successfully built and monitored a secure AWS network environment featuring:

✅ Dual VPC architecture  
✅ Private EC2 communication  
✅ VPC Peering  
✅ Route configuration  
✅ Security validation  
✅ Flow Logs monitoring  
✅ CloudWatch log analysis  

---

# 📖 Conclusion

This project provided practical hands-on experience in:

- AWS Networking
- Security
- Monitoring
- Troubleshooting
- Cloud Infrastructure Design

It strengthened my understanding of how AWS networking components interact while also introducing advanced monitoring strategies for production-grade architectures.

---
