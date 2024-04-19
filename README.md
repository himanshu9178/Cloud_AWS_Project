# AWS Cloud Project

This repository contains the infrastructure code and configuration needed to deploy a highly available web application on Amazon Web Services (AWS). The architecture utilizes AWS's powerful services to ensure scalability, security, and high availability.

## Architecture Overview

The key components of this project include:

- **AWS Virtual Private Cloud (VPC)** with a custom subnet setup including multiple public and private subnets.
- **Networking Components** such as Internet Gateway, NAT Gateway, and custom Route Tables for optimal traffic flow.
- **Elastic Compute Cloud (EC2)** for hosting the web application across multiple instances.
- **Application Load Balancer (ALB)** to distribute incoming web traffic.
- **Auto Scaling Group** with CloudWatch metrics to automatically scale EC2 instances.
- **Relational Database Service (RDS)** hosted within a private subnet for secure database storage.
- **OpenVPN Server** for secure remote access.
- **SSL/TLS Certificates** for secure, encrypted communications.
- **Amazon Route 53** for DNS management and domain name resolution.

## Getting Started

### Prerequisites

- An AWS account
- AWS CLI installed and configured
- Basic knowledge of AWS services (VPC, EC2, RDS, etc.)
- Terraform (optional, for Infrastructure as Code deployment)

### Setup Instructions

#### 1. Setting Up AWS VPC
- Create a VPC with multiple public and private subnets.
- Set up an Internet Gateway and attach it to the VPC.
- Create NAT Gateways in the public subnet for outbound traffic from instances in the private subnet.
- Configure Route Tables for directing traffic appropriately between subnets.

#### 2. Launching EC2 Instances
- Launch EC2 instances in the public subnet to host the web application.
- Install necessary software and configure these instances to serve the web application.

#### 3. Configuring Application Load Balancer
- Set up an Application Load Balancer to distribute incoming traffic across the EC2 instances in the public subnets.

#### 4. Implementing Auto Scaling
- Create an Auto Scaling Group linked to the EC2 instances.
- Set up CloudWatch alarms and define scaling policies based on CPU utilization metrics.

#### 5. Creating an RDS Database
- Launch an RDS instance in a private subnet.
- Configure security groups and network access to ensure secure and private connectivity.

#### 6. Secure Database Access
- Deploy an OpenVPN server in a public subnet.
- Configure VPN settings to allow secure remote access to the RDS database.

#### 7. SSL Certificate and DNS Configuration
- Obtain and install an SSL/TLS certificate for the web application.
- Set up a Hosted Zone in Amazon Route 53 and configure DNS settings for domain management.

### Testing
- Test the application by accessing the public DNS name provided by the Load Balancer.
- Validate the Auto Scaling by simulating different loads on the application.

## Conclusion

This project serves as a robust template for deploying scalable and highly available web applications on AWS, leveraging advanced cloud architectures and best practices.

