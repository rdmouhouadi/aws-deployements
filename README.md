# ☁️ AWS Services — Cloud Infrastructure & Deployment Project

This project demonstrates hands-on implementation of core AWS services used in real-world DevOps environments.  
It covers infrastructure setup, IAM security, EC2 deployment, ECR usage, AWS CLI automation, and CI/CD integration with Jenkins.

---

# 🔍 Problem Statement / Background (Situation)

Modern applications must run in scalable, secure, and highly available cloud environments.  
AWS is the most widely used cloud provider and offers infrastructure services required for production-grade deployments.

This project simulates a real DevOps workflow and is composed of several mini-projects:

---

## 1️⃣ AWS Account & IAM Setup
Problem:
Using the root account is insecure and violates best practices.

Solution:
- Create AWS Free Tier account
- Create Admin IAM user
- Apply least-privilege policies
- Configure CLI access with access keys

---

## 2️⃣ VPC, Subnets & Security
Problem:
Applications must run inside isolated networks.

Solution:
- Understand Regions & Availability Zones
- Use default VPC
- Configure Subnets
- Configure Security Groups
- Open required ports (22, 8080, 3080)

---

## 3️⃣ EC2 Web Application Deployment
Problem:
We need compute infrastructure to host containerized applications.

Solution:
- Launch EC2 instance
- SSH into instance
- Install Docker
- Pull and run Docker container
- Configure Security Group for browser access

---

## 4️⃣ Jenkins → EC2 Deployment
Problem:
Manual deployments do not scale.

Solution:
- Install SSH Agent plugin in Jenkins
- Configure EC2 SSH credentials
- Execute remote docker commands from Jenkins pipeline
- Deploy via Multi-Branch Pipeline

---

## 5️⃣ Docker Compose Deployment
Problem:
Single container deployment is limited.

Solution:
- Install Docker Compose on EC2
- Create docker-compose.yaml
- Deploy multi-container application
- Automate via Jenkins pipeline

---

## 6️⃣ Amazon ECR (Elastic Container Registry)
Problem:
DockerHub is public by default.

Solution:
- Create private ECR repository
- Authenticate Docker client
- Tag image
- Push to AWS ECR

---

## 7️⃣ AWS CLI Automation
Problem:
Manual UI work does not scale and is not reproducible.

Solution:
- Install AWS CLI
- Configure with access keys
- Create EC2, IAM, Security Groups via CLI
- Filter and query AWS resources

---

## 8️⃣ Infrastructure as Code Preview (Terraform)
Problem:
Manual CLI commands are imperative and messy.

Solution:
- Use declarative IaC
- Define infrastructure in code
- Reproducible deployments

---

# 🎯 Objective

- Secure AWS account using IAM best practices
- Deploy Dockerized web application on EC2
- Automate deployment using Jenkins
- Use Docker Compose for multi-container deployment
- Push images to Amazon ECR
- Manage infrastructure using AWS CLI
- Understand Infrastructure as Code principles

---

# 🛠 Tech Stack

- AWS EC2
- AWS IAM
- AWS VPC
- AWS ECR
- AWS CLI
- Docker
- Docker Compose
- Jenkins
- GitHub

---

# ⚙️ Implementation Roadmap

1. Create AWS Free Tier account  
2. Create Admin IAM user  
3. Launch EC2 instance  
4. Install Docker & deploy container  
5. Configure Jenkins SSH deployment  
6. Deploy using Docker Compose  
7. Push image to ECR  
8. Automate using AWS CLI  
9. Cleanup resources  

---

# 📊 Results

- Secure AWS account setup
- Web application deployed on EC2
- CI/CD pipeline deploying to EC2
- Private container registry on ECR
- AWS resources managed via CLI
- Production-like cloud architecture

---

# 👤 Author

Richie MOUHOUADI 

---

# 🙏 Acknowledgements
- TWN DevOps Bootcamp 