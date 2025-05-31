Terraform 3-Tier AWS Architecture
This repository contains Terraform configurations to provision a highly available, scalable, and modular 3-tier architecture on AWS. Designed with infrastructure-as-code best practices, it leverages reusable Terraform modules to automate and standardize cloud infrastructure deployments.

🏗️ Architecture Overview
The infrastructure is deployed within a single AWS region across two Availability Zones (AZs) to ensure high availability. It is logically divided into the following tiers:

1. Web Tier (Public Subnets)
EC2 instances hosted behind a public Application Load Balancer (ALB)

Internet Gateway for external connectivity

Public route tables for direct internet access

2. Application Tier (Private Subnets)
EC2 instances deployed in private subnets

Traffic routed through a private ALB

Supports internal communication with enhanced security

3. Database Tier (Private Subnets)
Amazon RDS deployed in private subnets

No direct internet access to ensure secure database operations

✨ Key Features
✅ Highly Available (Multi-AZ architecture)

✅ Modular and reusable Terraform code

✅ NAT Gateway for controlled outbound access from private subnets

✅ Application Load Balancers for public and internal traffic routing

✅ Launch Templates with Auto Scaling Groups for scalability

✅ Secure and production-ready infrastructure

✅ Environment customization via terraform.tfvars

---

## Repository Structure

```bash
Terraform
├──readme.md
├── main.tf
├── provider.tf
├── version.tf
├── terraform.tfvars
├── variables.tf
├── output.tf
└── modules/
    ├── vpc/
    ├── subnet/
    ├── igw/
    ├── nat_gateway/
    ├── route_table/
    ├── alb/
    ├── launch_template/
    ├── asg/
    ├── ec2/
    ├── security_group/
    ├── rds/
    └── key_pair/


Prerequisites
Terraform v1.3+

AWS CLI configured with appropriate credentials

SSH key pair (for EC2 access)

## Usage

### Initialize Terraform:

```bash
terraform init

terraform plan

terraform apply

terraform destroy
