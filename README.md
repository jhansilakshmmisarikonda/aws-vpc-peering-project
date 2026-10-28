# aws-vpc-peering-project
AWS VPC Peering project demonstrating secure private connectivity between two VPCs using EC2, route tables, security groups, and a bastion host.
# AWS VPC Peering Project

This project demonstrates secure private connectivity between two AWS VPCs using VPC Peering.

# Project Overview

Two private application servers, App-A and App-B, are deployed in separate VPCs.
A VPC Peering connection allows them to communicate using private IPv4 addresses.
A public bastion host in VPC A is used for secure administrative SSH access.

## Architecture

- VPC A: 10.10.0.0/16
- VPC B: 10.20.0.0/16
- Public Subnet A: 10.10.1.0/24
- Private Subnet A: 10.10.2.0/24
- Private Subnet B: 10.20.1.0/24
- Bastion Host: 10.10.1.10
- App-A: 10.10.2.10
- App-B: 10.20.1.10

# AWS Resources Created

- VPC A and VPC B
- Public and private subnets
- Internet Gateway
- Custom route tables
- Security groups
- Three EC2 instances
- VPC Peering connection

 # Tests Performed

1. Baseline ping failure before peering
2. Forward ping success after peering routes
3. Reverse ping success
4. SSH access to App-B through bastion
5. Controlled ICMP failure and recovery

# Results

- Before peering, App-A could not reach App-B.
- After peering and route configuration, App-A and App-B communicated successfully using private IPs.
- SSH access to App-B was possible only through the bastion host.
- Removing the ICMP rule stopped ping traffic; restoring it recovered connectivity.

 Screenshots

All proof screenshots are available in the `screenshots/` folder.

 Project Report

The complete project report is available in the `report/` folder.
