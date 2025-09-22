# 3-Tier-Application

This project demonstrates the deployment of a 3-Tier Web Application Architecture on AWS using Route 53, CloudFront, S3, EC2, Auto Scaling, ALB, RDS, and EFS. The architecture is designed to be scalable, secure, and highly available.

Project Architecture

The application is divided into three tiers:

Presentation Layer (Frontend)

Amazon Route 53 for domain name resolution.

Amazon CloudFront as CDN to deliver static & dynamic content globally.

Amazon S3 to store static content (media, CSS, JS, files).

Application Layer (Business Logic)

Auto Scaling Group of EC2 instances running Nginx web servers.

Application Load Balancer (ALB) distributes incoming traffic across multiple EC2 instances in different Availability Zones.

Amazon EFS for shared storage across EC2 instances (configs, plugins, XML, CSS, etc.).

Database Layer (Data Storage)

Amazon RDS (Aurora/MySQL) to host the application database.

Simplifies database management, provides backups, replication, and high availability.

Steps Implemented

DNS & CDN

Configured Amazon Route 53 with a custom domain.

Integrated Amazon CloudFront to deliver static/dynamic content efficiently.

Static Content Hosting

Used Amazon S3 to store static assets (media, downloadable files, etc.).

Networking

Created a VPC with public & private subnets across multiple Availability Zones.

Attached an Internet Gateway for external communication.

Load Balancing & Scaling

Configured Application Load Balancer to distribute traffic.

Deployed EC2 instances in Auto Scaling Group using a custom AMI with Nginx.

Security Groups

Allowed SSH and DB access only from trusted IPs.

Opened HTTP (80) for web traffic via ALB.

Database Layer

Launched Amazon RDS (Aurora/MySQL) for relational database management.

Storage Layer

Created an EFS file system with mount targets.

Attached to EC2 instances for shared storage.

Custom AMI

Installed Nginx and required dependencies.

Built an AMI to be reused in the Auto Scaling Group.

Tools & Services Used

Amazon Route 53 – Domain Name Service

Amazon CloudFront – Content Delivery Network

Amazon S3 – Static content hosting

Amazon VPC – Networking

Amazon EC2 + Auto Scaling Group – Application servers

Amazon ALB (Load Balancer) – Traffic distribution

Amazon RDS (Aurora/MySQL) – Database tier

Amazon EFS – Shared storage for EC2 instances

Outcome

A fully functional 3-Tier Web Application deployed on AWS.

Highly available & scalable architecture with Auto Scaling and ALB.

Secure & fault-tolerant system with Route 53 DNS and CloudFront caching.

Centralized database (RDS) and shared storage (EFS) for consistency.
