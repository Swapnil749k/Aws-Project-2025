🏗️ AWS 3-Tier Architecture Project
This project demonstrates a complete deployment of a highly available, secure, and scalable 3-Tier Web Application Architecture on AWS, following best practices.

📌 Project Overview
The application architecture is split into three distinct tiers:

1)Web Tier (Frontend Layer)

Hosted on EC2 instances in Public Subnets.

Receives internet traffic via an Application Load Balancer (ALB).

Handles HTTP/HTTPS requests from users.

2)App Tier (Application Layer)

Hosted on EC2 instances in Private Subnets.

Contains backend business logic (Node.js / Java / Python apps).

Communicates with the Web Tier and Database Tier securely.

3)Database Tier (Data Layer)

use Amazon Aurora (RDS) in Private Subnets.

Supports Multi-AZ for high availability.

Uses Read Replicas for read scaling and load distribution.

🚀 Features
✅ Highly Available with multi-AZ deployments.

✅ Auto Scaling Groups (ASG) for Web & App Tiers.

✅ Elastic Load Balancer (ELB) in the Web Tier.

✅ Amazon Aurora DB with Read Replica for performance and fault tolerance.

✅ Private Subnets for App and DB layers to enhance security.

✅ NAT Gateway to provide controlled outbound internet access to App Tier.

✅ Infrastructure as Code (IaC) ready for automation (Terraform/CloudFormation support planned).

🏗️ Architecture Diagram
<!-- img upload above code -->

🔧 Tech Stack
AWS Services: EC2, ELB, RDS Aurora, VPC, NAT Gateway, Auto Scaling, Security Groups, IAM

OS: Amazon Linux 2 / Ubuntu

Languages: Node.js / Python / Java (Based on App Tier code)

Infrastructure: Terraform / CloudFormation (optional)

Monitoring: AWS CloudWatch, VPC Flow Logs, CloudTrail

🔒 Security Best Practices
Web Tier: Public subnet, limited to HTTP/HTTPS.

App Tier: Private subnet, only reachable by Web Tier.

DB Tier: Private subnet, only reachable by App Tier.

Secrets & keys managed via AWS Secrets Manager (recommended).

📝 How to Deploy (Manual Steps)
Clone this repository:

git clone https://github.com/yourusername/your-repo-name.git
Configure AWS CLI and credentials.
edit in app tier> edit db config to set up db.
and nginx file change internal load balancer link..

Deploy Web and App Tier application code.

Verify the deployment using:
curl http://<Public-ELB-DNS-Name>
📚 Documentation
AWS 3-Tier Architecture Explained
