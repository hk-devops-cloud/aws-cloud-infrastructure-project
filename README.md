# aws-cloud-infrastructure-project
Building and configuring AWS cloud infrastructure using VPC, EC2, network and Linux

AWS Cloud Infrastructure — VPC, EC2 & Linux Administration

Project Overview

Designed and deployed a basic cloud infrastructure environment on Amazon Web Services (AWS). The project involved creating a custom Virtual Private Cloud (VPC), configuring public networking, deploying an Ubuntu Linux EC2 instance, and establishing secure remote access through SSH.

The objective was to understand how AWS networking components work together to provide internet connectivity and secure access to cloud-hosted compute resources.

Architecture



Infrastructure Configuration

Component

Configuration

Cloud Provider

Amazon Web Services

Region

US East (Ohio) — us-east-2

VPC

cloud-lab-vpc

VPC CIDR

10.0.0.0/16

Subnet

cloud-lab-public-subnet

Subnet CIDR

10.0.1.0/24

Internet Gateway

cloud-lab-igw

Route Table

cloud-lab-public-rt

EC2 Instance

cloud-lab-linux-01

Operating System

Ubuntu Server 24.04 LTS

Instance Type

t3.micro

Storage

8 GiB gp3

Security Group

cloud-lab-ec2-sg

AWS Services & Technologies

Amazon VPC

Amazon EC2

Internet Gateway

Route Tables

Public Subnets

Security Groups

AWS Key Pairs

Ubuntu Linux

SSH

Linux Networking Utilities

Implementation

1. VPC Configuration

Created a custom VPC with an IPv4 CIDR range of 10.0.0.0/16.

Established an isolated network environment for cloud resources.

2. Subnet Configuration

Created a public subnet with CIDR 10.0.1.0/24.

Selected an Availability Zone within the us-east-2 region.

3. Internet Gateway

Created an Internet Gateway.

Attached it to the custom VPC to enable internet connectivity.

4. Route Table Configuration

Created a dedicated route table.

Configured the local VPC route.

Added a default route (0.0.0.0/0) targeting the Internet Gateway.

Associated the route table with the public subnet.

5. Security Group Configuration

Created a dedicated Security Group for the EC2 instance.

Configured inbound SSH access on TCP port 22, restricted to my public IP address.

Retained the default outbound traffic rule.

6. EC2 Deployment

Launched an Ubuntu Server 24.04 LTS EC2 instance.

Configured the instance inside the custom public subnet.

Enabled public IPv4 addressing.

Created an SSH key pair for secure remote authentication.

Attached the custom Security Group.

7. Linux Administration

Connected to the EC2 instance remotely using SSH and performed basic Linux administration, including:

User and operating system identification.

CPU, memory, and disk inspection.

Package management using APT.

Network interface inspection using ip addr.

Routing table inspection using ip route.

DNS resolution using nslookup.

Connectivity testing using ping and curl.

Network socket inspection using ss.

Network Architecture Concepts Learned

VPC isolation and private IPv4 addressing.

CIDR notation and subnet allocation.

Public subnet routing.

Internet Gateway functionality.

Route table configuration and destination-based routing.

Stateful Security Groups and inbound/outbound traffic.

Public versus private IP addressing.

SSH authentication and remote Linux administration.

Layered network troubleshooting.

Security Considerations

Restricted inbound SSH access to my public IP address.

Used SSH key-based authentication.

Applied restrictive permissions to the private key.

Avoided exposing private SSH credentials.

Used a dedicated Security Group for the EC2 instance.

Cost Management

Configured AWS Budgets with a $5 monthly monitoring target.

Created an additional zero-spend budget alert.

Selected a small EC2 instance and limited storage allocation.

Avoided unnecessary services such as NAT Gateways and Load Balancers.

Note: AWS Budgets provide alerts, not hard spending limits.

Project Outcome

Successfully built and deployed a Linux server within a custom AWS VPC, configured public internet routing, implemented firewall restrictions, and established remote SSH administration.

This project provided practical experience with foundational AWS networking, cloud compute, infrastructure configuration, and Linux system administration.

Future Improvements

Recreate the infrastructure using Terraform.

Implement private subnets.

Introduce NAT Gateway architecture and evaluate its cost.

Configure IAM roles and least-privilege access.

Implement automated infrastructure deployment.

Introduce monitoring using Amazon CloudWatch.

Project Status: Completed — Manual AWS Console Deployment
