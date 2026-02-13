# 📘 My Notes — AWS Services

---

# ☁️ What is AWS?

Amazon Web Services is the most widely used cloud platform offering computing, storage, networking, and deployment services.

---

# 🌍 Regions & Availability Zones

Region = Physical geographic location  
Availability Zone (AZ) = Isolated data center inside region  

Best Practice:
Deploy across multiple AZs for high availability.

---

# 🔐 IAM (Identity and Access Management)

IAM controls who can access AWS resources.

Important concepts:
- Root user → full access (avoid using it)
- IAM Users → for humans or systems
- Groups → assign permissions collectively
- Policies → JSON documents defining permissions
- Roles → grant AWS services permissions

Best Practice:
Use least privilege principle.

---

# 🌐 VPC (Virtual Private Cloud)

Your private network in AWS.

Contains:
- Subnets
- Route Tables
- Internet Gateway
- Security Groups
- NACLs

Every EC2 instance must run inside a VPC.

---

# 📍 Subnets

Subnet = range of IP addresses inside VPC.

Types:
- Public subnet → has internet access
- Private subnet → no direct internet access

---

# 🔥 Security Groups

Acts as firewall at instance level.

Controls:
- Inbound traffic
- Outbound traffic

---

# 🖥 EC2 (Elastic Compute Cloud)

Virtual machine in AWS.

Steps:
1. Choose AMI
2. Choose instance type
3. Configure networking
4. Add storage
5. Configure Security Group
6. Launch

Important: Connected to EC2 using PuTTY -- but also possible to use CMD line with OpenSSH apparently

Demo Project wrap up:
 - Created EC2 Instance
 - Installed Docker 
 - Pulled Image from Private Repo
 - Started Docker container
 - Modified Firewall: Open port to allow access from internet
---

# 🐳 ECR (Elastic Container Registry)

Private Docker registry in AWS.

Used to:
- Store Docker images
- Push from CI pipeline
- Pull into EC2/ECS/EKS

---

# ⚙️ AWS CLI

Command line interface for AWS.

Structure:
aws <service> <command> <options>

Example:
aws ec2 describe-instances

---

# 🔁 Jenkins + AWS

Deployment Flow:
1. Jenkins builds Docker image
2. Pushes to ECR
3. SSH into EC2
4. Run docker container

Better approach:
Use IAM Role instead of access keys.

---

# 🏗 Infrastructure as Code

Manual CLI → Imperative  
Terraform → Declarative  

IaC allows:
- Reproducible infrastructure
- Version control
- Automation

---

# ⚠️ AWS Best Practices

- Never use root for daily tasks
- Delete unused resources
- Protect .pem keys
- Use IAM roles instead of long-term credentials
- Restrict security groups
- Monitor costs