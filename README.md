
# AWS Project: EC2 in Private Subnet with NAT Gateway

This project demonstrates how to host a basic web page from an EC2 instance in a **private subnet**, and provide internet access using a **NAT Gateway**. SSM is used to connect without a public IP.

---

##  Resources Created

- Custom VPC (CIDR: 10.0.0.0/25)
- Public Subnet (10.0.0.0/26)
- Private Subnet (10.0.0.64/26)
- Internet Gateway (IGW)
- NAT Gateway with Elastic IP
- Route Table for private subnet
- EC2 in private subnet with Apache server
- SSM Session Manager for access

---

##  Step-by-Step Setup

###  Step 1: Create VPC and Subnets
- VPC: `10.0.0.0/25`
- Public Subnet: `10.0.0.0/26`
- Private Subnet: `10.0.0.64/26`
- Attach IGW to VPC

###  Step 2: Create NAT Gateway
- Subnet: Public Subnet
- Elastic IP: Allocate new one
- Click **Create NAT Gateway**

###  Step 3: Private Route Table
- Add route: `0.0.0.0/0 → NAT Gateway`
- Associate with private subnet

###  Step 4: Launch EC2 in Private Subnet
- Instance type: t2.micro (Free Tier)
- Subnet: Private Subnet
- No Public IP
- Add SSM Role (AmazonSSMManagedInstanceCore)
- Add user Data - User.txt/


