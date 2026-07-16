---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

- Learn identity and access management with AWS IAM.
- Design a secure network foundation with Amazon VPC and Site-to-Site VPN.
- Deploy compute resources on Amazon EC2 and resolve network connection problems.
- Build a basic understanding of relational databases with Amazon RDS.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                        | Start Date | Completion Date | Reference Material                |
| :-- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------- | :-------------- | :-------------------------------- |
| 2   | **AWS IAM Access Control:** Set up MFA for the root user and IAM users, create a custom Password Policy, write JSON-based Policies following the Least Privilege principle, and test permission boundaries across different Groups.         | 27/04/2026 | 27/04/2026      | https://000002.awsstudygroup.com/ |
| 3   | **Amazon VPC & Site-to-Site VPN:** Design a multi-tier VPC architecture (public/private subnets), configure a NAT Gateway for private subnet internet access, and implement VPC Peering between two separate VPCs.                          | 28/04/2026 | 28/04/2026      | https://000003.awsstudygroup.com/ |
| 4-5 | **Amazon EC2:** Configure an Auto Scaling Group combined with an Application Load Balancer for a Node.js application, set up CloudWatch Alarms to trigger auto-scaling based on load, and create a custom AMI to replicate the environment. | 29/04/2026 | 30/04/2026      | https://000004.awsstudygroup.com/ |
| 6   | **Amazon RDS:** Deploy a Read Replica to optimize read performance, practice Point-in-Time Recovery from a backup, configure a custom Parameter Group, and monitor performance using Performance Insights.                                  | 01/05/2026 | 01/05/2026      | https://000005.awsstudygroup.com/ |

### Week 2 Achievements:

- **Security & Identity (IAM):** Strengthened account security by enabling MFA, enforced a custom password policy, and authored fine-grained JSON policies aligned with the principle of least privilege.
- **Networking (VPC & VPN):** Designed a multi-tier network architecture with public and private subnets, enabled outbound internet access for private resources via a NAT Gateway, and connected two separate VPCs through VPC Peering.
- **Compute & Scalability (EC2):** Built a self-healing, auto-scaling infrastructure for a Node.js application using Auto Scaling Groups and an Application Load Balancer, with CloudWatch Alarms triggering scaling events based on real traffic load.
- **Database Management (RDS):** Improved database resilience and performance by deploying a Read Replica, practiced restoring data to a specific point in time, tuned engine behavior with a custom Parameter Group, and monitored query performance using Performance Insights.
