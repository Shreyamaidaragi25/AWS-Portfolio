# AWS Fault-Tolerant Portfolio Hosting using CloudFront, ALB and EC2

## Project Overview

This project demonstrates a highly available and fault-tolerant web hosting architecture on AWS. A portfolio website is deployed across multiple Availability Zones and served through an Application Load Balancer (ALB) and CloudFront CDN to ensure high availability, scalability, and improved performance.

---

## Architecture Diagram

```text
                 +------------------+
                 |      Users       |
                 +--------+---------+
                          |
                          v
                 +------------------+
                 |   CloudFront     |
                 |      (CDN)       |
                 +--------+---------+
                          |
                          v
                 +------------------+
                 | Application Load |
                 |    Balancer      |
                 +---+----------+---+
                     |          |
                     v          v
            +------------+  +------------+
            | EC2 AZ-1   |  | EC2 AZ-2   |
            | Nginx      |  | Nginx      |
            +------------+  +------------+

                 CloudWatch Monitoring
                        |
                        v
              EC2 + ALB Metrics/Alarms
```

---

## AWS Services Used

* Amazon VPC
* Public Subnets
* Internet Gateway
* Route Tables
* Security Groups
* Amazon EC2
* Nginx Web Server
* Application Load Balancer (ALB)
* Target Groups
* Amazon CloudFront
* Amazon CloudWatch

---

## Features

* Multi-AZ deployment
* High availability architecture
* Load balancing across EC2 instances
* CDN acceleration using CloudFront
* Health checks and automatic traffic routing
* Infrastructure monitoring with CloudWatch
* Fault tolerance demonstration

---

## Implementation Steps

### 1. Networking Setup

* Created a custom VPC
* Created public subnets in different Availability Zones
* Attached Internet Gateway
* Configured Route Tables

### 2. EC2 Deployment

* Launched two Ubuntu EC2 instances
* Installed and configured Nginx
* Hosted portfolio website

### 3. Load Balancing

* Created Target Group
* Registered EC2 instances
* Configured health checks
* Created Application Load Balancer

### 4. CDN Configuration

* Created CloudFront Distribution
* Configured ALB as Origin
* Enabled global content delivery

### 5. Monitoring

* Created CloudWatch alarms
* Monitored EC2 health and CPU utilization

---

## Failover Testing

### Scenario

1. Both EC2 instances are healthy.
2. Website is accessible through CloudFront.
3. One EC2 instance is stopped manually.
4. ALB detects failed health checks.
5. Traffic is automatically routed to the healthy instance.
6. Website remains available without downtime.

### Result

Successfully demonstrated fault tolerance and high availability using AWS services.

---

## Screenshots

Add screenshots for:

* VPC Configuration and subnets
  <img width="1616" height="739" alt="Screenshot 2026-06-01 223612" src="https://github.com/user-attachments/assets/42782247-8502-4a33-9599-a05870e143bb" />
  
* EC2 Instances
  <img width="1304" height="470" alt="Screenshot 2026-06-01 235431" src="https://github.com/user-attachments/assets/83e13f95-4d4d-4d3b-944f-dafafa0edc08" />

* Target Group Health Checks
  <img width="1569" height="733" alt="Screenshot 2026-06-01 235545" src="https://github.com/user-attachments/assets/23313af4-91b4-4fc4-bed2-8089bd4dc88b" />
  <img width="1531" height="517" alt="Screenshot 2026-06-01 235558" src="https://github.com/user-attachments/assets/299adea3-b281-4b40-b7ea-f213ab3a9528" />

* Application Load Balancer
  <img width="1555" height="687" alt="Screenshot 2026-06-01 235610" src="https://github.com/user-attachments/assets/e71fa2e7-09c2-4817-9933-d520b1251ccc" />

* CloudFront Distribution
  <img width="1602" height="647" alt="Screenshot 2026-06-01 235259" src="https://github.com/user-attachments/assets/0bc24845-47d8-4b08-bab9-c34e19fc6163" />

* Failover Demonstration
  <img width="1289" height="446" alt="Screenshot 2026-06-01 222730" src="https://github.com/user-attachments/assets/a80a233f-7ea7-439e-beba-4ac054a2e27b" />
  <img width="1433" height="772" alt="Screenshot 2026-06-01 223633" src="https://github.com/user-attachments/assets/edf444ce-ba20-43fe-a822-8e3723a3ae68" />
  <img width="1415" height="897" alt="Screenshot 2026-06-01 235651" src="https://github.com/user-attachments/assets/f70a86e8-d8b0-4988-8ef3-49eed04dcc29" />

  

---

## Project Outcome

This project demonstrates practical knowledge of:

* AWS Networking
* Load Balancing
* CDN Configuration
* High Availability Design
* Monitoring and Alerting
* Troubleshooting Target Health Issues
* Production-Style Web Hosting Architecture

---

## Future Enhancements

* Route 53 Custom Domain
* HTTPS using ACM Certificates
* AWS WAF Integration
* CI/CD Pipeline using GitHub Actions and AWS

---

## Author

Shreya Maidaragi

Automotive Embedded Systems |






AWS & DevOps Enthusiast
