# 2-tierapp-terraform

================= AWC -CLI INSTALL ==================

Step1: Update package Lists by using below command
     
	 sudo apt-get update -y 

Step2: Install required dependencies
     
	 sudo apt install unzip curl -y

Step3: Download AWS CLI v2 installer & unzip the installer  
     
	 curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
 
     unzip awscliv2.zip

Step4: Install the AWS CLI
     
	 sudo ./aws/install

Step5: Verify the installation
    
	aws --version 

Step6: Configure AWS CLI by using below command
     aws configure 

Notice:You will be prompted to enter your AWS Access Key ID, AWS Secret Access Key, Default region name, and Default output format. If you do not have these credentials, you can obtain them from the AWS Identity and Access Management (IAM) service.

======Commands Frequently Used in AWS CLI======

1.to check s3 buckets
     
	 aws s3 ls

2.to check ec2 information
     
	 aws ec2 describe-instances  

3.to check IAM user lists
     
	 aws iam list-users

==================Terraform Installation===============

step1: Go to official website
     
       https://developer.hashicorp.com/terraform/install#linux 

step2:copy the Version link for install 
     
     wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
     echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
     sudo apt update && sudo apt install terraform  
	 
step3: Check if Terraform is successfully installed
     
	  terraform -v 
================ components deployed ====================

VPC
Internet Gateway
Public and Private Subnets (across two AZs)
Route Tables and Associations
Security Groups (for ALB, EC2, RDS)
Application Load Balancer (ALB)
Two EC2 Instances (Nginx Web Servers)
RDS MySQL Instance (Private)

============ project structure ===============

├── provider.tf

├── vpc.tf

├── security-resources.tf

├── ec2.tf

├── db.tf

==============terraform commands===========

1.terraform init

2.terraform validate

3.terraform plan

4.terraform apply
