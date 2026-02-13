# 📜 AWS Commands Reference

---

# 🔐 IAM

## Create IAM Group
aws iam create-group --group-name MyGroup

## Create IAM User
aws iam create-user --user-name MyUser

## Add User to Group
aws iam add-user-to-group --user-name MyUser --group-name MyGroup

## Attach Policy to Group
aws iam attach-group-policy \
--group-name MyGroup \
--policy-arn arn:aws:iam::aws:policy/AmazonEC2FullAccess

## Create Access Key
aws iam create-access-key --user-name MyUser

---

# 🖥 EC2

## Create Security Group
aws ec2 create-security-group \
--group-name my-sg \
--description "My security group" \
--vpc-id vpc-xxxx

## Open Port 22
aws ec2 authorize-security-group-ingress \
--group-id sg-xxxx \
--protocol tcp \
--port 22 \
--cidr 0.0.0.0/0

## Create Key Pair
aws ec2 create-key-pair \
--key-name MyKeyPair \
--query 'KeyMaterial' \
--output text > MyKeyPair.pem

chmod 400 MyKeyPair.pem

## Launch EC2 Instance
aws ec2 run-instances \
--image-id ami-xxxxxxxx \
--count 1 \
--instance-type t2.micro \
--key-name MyKeyPair \
--security-group-ids sg-xxxx \
--subnet-id subnet-xxxx

## SSH into EC2
ssh -i MyKeyPair.pem ec2-user@<public-ip>

---

# 🐳 Docker on EC2

sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker

docker login
docker pull <image>
docker run -d -p 3080:3080 <image>

---

# 🐳 Docker Compose

sudo curl -L \
"https://github.com/docker/compose/releases/download/v2.20.0/docker-compose-linux-x86_64" \
-o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose up -d

---

# 📦 Amazon ECR

## Authenticate Docker
aws ecr get-login-password --region us-east-1 | \
docker login --username AWS --password-stdin <account-id>.dkr.ecr.us-east-1.amazonaws.com

## Create Repository
aws ecr create-repository --repository-name my-app

## Tag Image
docker tag myapp:latest \
<account-id>.dkr.ecr.us-east-1.amazonaws.com/my-app:latest

## Push Image
docker push <account-id>.dkr.ecr.us-east-1.amazonaws.com/my-app:latest

---

# ⚙️ AWS CLI Setup

aws configure

aws configure set aws_access_key_id YOUR_KEY
aws configure set aws_secret_access_key YOUR_SECRET
aws configure set region us-east-1

---

# 🧹 Cleanup

aws ec2 terminate-instances --instance-ids i-xxxx
aws ec2 delete-security-group --group-id sg-xxxx
aws iam delete-user --user-name MyUser
aws iam delete-group --group-name MyGroup

