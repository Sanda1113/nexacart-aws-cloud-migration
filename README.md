# NexaCart – Enterprise Cloud Migration on AWS

Highly available, disaster-resilient AWS architecture for a high-traffic e-commerce platform.

## Architecture
![Architecture](docs/nexacart-architecture.png)

## Problem
The on-premise platform went down during traffic spikes and had no recovery plan for regional outages.

## Solution
- **3-tier design:** web, application and database tiers in separate subnets
- **High availability:** EC2 Auto Scaling + Application Load Balancer across multiple AZs
- **Database:** Amazon RDS Multi-AZ with automatic failover
- **Infrastructure as Code:** the whole environment is deployed with AWS CloudFormation
- **Disaster recovery:** cross-region warm standby with Route 53 DNS failover
- **Security:** tiered Security Groups and network segmentation

## Results
| Metric | Target |
|---|---|
| RTO | 15–30 minutes |
| RPO | < 1 hour |

## Tech stack
AWS EC2 · Auto Scaling · ALB · RDS Multi-AZ · CloudFormation · Route 53 · VPC · Security Groups

## Repository structure
- `cloudformation/` – IaC templates
- `docs/` – architecture diagram and design notes

## How to deploy
1. Upload the templates to S3
2. Create the stack: `aws cloudformation create-stack --stack-name nexacart --template-body file://cloudformation/main.yaml`

## Author
Sandakan Liyanage – [LinkedIn](LINKEDIN_URL) · [Portfolio](PORTFOLIO_URL)
