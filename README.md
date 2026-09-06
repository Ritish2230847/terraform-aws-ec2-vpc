Terraform AWS EC2 VPC Infrastructure

📌 Project Overview

This project demonstrates how to provision AWS infrastructure using Terraform Infrastructure as Code (IaC).

The project creates a complete public web server environment including a VPC, public subnet, Internet Gateway, route table, security group, and EC2 instance.

🏗️ Architecture

                    AWS Cloud
                       |
                      VPC
                 10.0.0.0/16
                       |
                Public Subnet
                 10.0.1.0/24
                       |
              Internet Gateway
                       |
                 Route Table
                       |
                Security Group
                       |
                  EC2 Instance
                       |
                     Nginx
                       |
                 Web Browser

🛠️ Technologies Used

- Terraform
- AWS
- Amazon VPC
- Amazon EC2
- Security Groups
- Internet Gateway
- Route Tables
- Nginx
- Ubuntu Linux

📂 Project Structure

terraform-aws-ec2-vpc/
│
├── provider.tf
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars.example
├── .gitignore
└── README.md

☁️ AWS Resources Created

Terraform provisions the following resources:

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Route Table Association
- Security Group
- EC2 Instance
- Nginx Web Server

⚙️ Prerequisites

Before running this project, make sure you have:

1. An AWS account
2. Terraform installed
3. AWS CLI installed and configured
4. An existing EC2 Key Pair

Configure AWS credentials using the AWS CLI:

aws configure

Do not hardcode AWS access keys or secret keys inside Terraform files.

🚀 How to Deploy

1. Clone the repository

git clone https://github.com/YOUR_USERNAME/terraform-aws-ec2-vpc.git
cd terraform-aws-ec2-vpc

2. Create Terraform variables

Create a "terraform.tfvars" file:

aws_region    = "ap-south-1"
vpc_cidr      = "10.0.0.0/16"
subnet_cidr   = "10.0.1.0/24"
instance_type = "t2.micro"
key_name      = "your-key-pair-name"

3. Initialize Terraform

terraform init

4. Format the configuration

terraform fmt

5. Validate the configuration

terraform validate

6. Review the execution plan

terraform plan

7. Create the infrastructure

terraform apply

Type:

yes

🌐 Access the Web Server

After successful deployment, Terraform will display the EC2 public IP and website URL.

You can also run:

terraform output

Open the displayed "website_url" in a web browser.

The EC2 instance automatically installs Nginx using Terraform "user_data".

🧹 Destroy Infrastructure

When you finish testing, destroy the resources to avoid unnecessary AWS charges:

terraform destroy

Type:

yes

🔐 Security

Sensitive files and credentials should not be committed to GitHub.

The ".gitignore" file excludes:

.terraform/
*.tfstate
*.tfstate.*
*.tfvars

AWS credentials should never be hardcoded in Terraform configuration files.

📚 Terraform Workflow

Write Configuration
        ↓
terraform init
        ↓
terraform fmt
        ↓
terraform validate
        ↓
terraform plan
        ↓
terraform apply
        ↓
AWS Infrastructure
        ↓
terraform destroy

🎯 Learning Outcomes

Through this project, I learned how to:

- Use Terraform for Infrastructure as Code
- Configure the AWS provider
- Create an AWS VPC
- Create and configure public subnets
- Configure Internet Gateway and route tables
- Create EC2 security groups
- Provision EC2 instances using Terraform
- Use Terraform variables and outputs
- Automate Nginx installation using "user_data"
- Manage infrastructure using the Terraform lifecycle

🚀 Future Improvements

- Add private subnets
- Add NAT Gateway
- Create multiple EC2 instances
- Add Application Load Balancer
- Use Terraform modules
- Add remote Terraform state using S3
- Add CI/CD using GitHub Actions
- Add monitoring using Prometheus and Grafana

👨‍💻 Author

Ritish Kumar

DevOps / Cloud Engineering Portfolio Project