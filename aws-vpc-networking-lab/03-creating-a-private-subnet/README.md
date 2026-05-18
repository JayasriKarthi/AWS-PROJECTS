

# Creating a Private Subnet in AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com

---

# Project Overview

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_afe1fdbd)

In this project, I built a **Private Subnet** within an Amazon VPC to understand how AWS secures cloud resources by isolating sensitive infrastructure from direct internet access.

This hands-on project helped me explore:

- Amazon VPC
- Public vs Private Subnets
- Dedicated Route Tables
- Network ACLs
- CIDR Block Planning
- Secure AWS Cloud Architecture

---



## How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:

- Create a private subnet
- Configure a dedicated private route table
- Set up a custom Network ACL
- Restrict internet access
- Improve overall cloud security



---

# Private vs Public Subnets

## Understanding the Difference

### Public Subnet:
- Connected to an Internet Gateway
- Internet accessible
- Used for:
  - Web servers
  - Public applications
  - Frontend services

### Private Subnet:
- No direct internet connectivity
- Internal-only access
- Used for:
  - Databases
  - Backend systems
  - Sensitive applications

---

## Why Private Subnets Are Important

Private subnets improve security by:

- Preventing direct internet exposure
- Protecting sensitive data
- Limiting unauthorized access
- Supporting secure enterprise infrastructure

---

## CIDR Block Planning

Private and public subnets must have separate CIDR ranges to ensure proper traffic routing.

### Example:
- Public Subnet: `10.0.1.0/24`
- Private Subnet: `10.0.2.0/24`

This separation ensures organized network communication.

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_afe1fdbd)

---

# Dedicated Route Table Configuration

## What I Did

By default, my private subnet was linked to the main route table.

To secure it properly, I:

- Created a new private route table
- Removed public internet gateway routes
- Allowed only internal VPC communication

---

## Why Dedicated Route Tables Matter

A dedicated route table ensures:

- Secure traffic flow
- No direct internet access
- Controlled communication
- Better network segmentation

---

## Benefits:
- Improved security
- Isolated architecture
- Better compliance
- Enterprise-grade design

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_b4b904b5)

---

# Custom Network ACL Configuration

## What I Did

I created a dedicated Network ACL for my private subnet.

### ACL Rules:
- Denied unauthorized inbound traffic
- Denied unauthorized outbound traffic
- Controlled subnet-level access

---

## Why Network ACLs Matter

Network ACLs act as an additional security layer that controls traffic entering and leaving subnets.

### Security Benefits:
- Traffic filtering
- Stateless security
- Explicit deny/allow rules
- Enhanced infrastructure protection

---

## Final Security Design:
My custom Network ACL ensured that private resources remained protected from unnecessary network exposure.

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-networks-private_1ed2cb07)

---

# Skills Developed

Through this project, I strengthened my practical understanding of:

- AWS VPC design
- Private subnet implementation
- Route table management
- Network ACL security
- Cloud infrastructure protection
- Secure enterprise networking

---

# Final Thoughts

This project was an excellent learning experience in AWS networking and cloud security.

### Major Takeaways:
- Private subnets are essential for securing sensitive resources
- Route tables define network accessibility
- Network ACLs strengthen subnet security
- AWS VPC is critical for enterprise cloud design

---

# Conclusion

Creating a Private Subnet in AWS gave me practical experience in building secure cloud infrastructure.

This project enhanced my knowledge in:

- AWS Networking
- Cloud Security
- Infrastructure Design
- Secure Architecture

It also serves as a strong foundation for future projects involving:

- EC2 deployments
- NAT Gateways
- Load Balancers
- Advanced AWS Security


