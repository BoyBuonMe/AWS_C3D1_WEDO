---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Week 6 Objectives:
* Enable automated compliance checks and cross-service finding aggregation with AWS Security Hub.
* Establish direct, non-transitive network paths between VPCs using VPC Peering.
* Simplify hub-and-spoke connectivity across multiple VPCs with AWS Transit Gateway.
* Automate EC2 cost optimization with AWS Lambda and evaluate Savings Plans commitment options.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **Study - AWS Security Hub & VPC Peering:** Enable Security Standards (CIS, PCI DSS) in Security Hub and review compliance scores, then update route tables on both sides of a VPC Peering connection and test connectivity with a traceroute. | 25/05/2026 | 25/05/2026 | https://000019.awsstudygroup.com/1-introduction/ |
| 3-4 | **AWS Transit Gateway:** Configure route propagation and static routes across multiple Transit Gateway Attachments, and set up a separate Route Table to isolate traffic between specific VPC segments. | 26/05/2026 | 27/05/2026 | https://000020.awsstudygroup.com/1-introduction/ |
| 6 | **Optimizing EC2 Costs with Lambda:** Configure a CloudWatch Events (EventBridge) rule to trigger the Lambda function on a schedule, add error handling and SNS notifications for failed executions, and compare estimated savings against a Compute Savings Plan. | 29/05/2026 | 29/05/2026 | https://000022.awsstudygroup.com/1-introduction/ |

### Week 6 Achievements:
* **Security & Monitoring (Security Hub & NACL):** Enabled Security Standards to automatically evaluate resource compliance against CIS and PCI DSS benchmarks, and gained a clearer picture of overall account security posture through the consolidated compliance score.
* **Network Architecture (VPC Peering vs Transit Gateway):** Updated bidirectional route tables to enable VPC Peering connectivity and verified the path with traceroute, while using route propagation and isolated Route Tables in Transit Gateway to control traffic flow between VPC segments.
* **Cost Optimization (AWS Lambda):** Automated EC2 start/stop scheduling with an EventBridge-triggered Lambda function, added SNS alerts to catch failed executions early, and evaluated how a Compute Savings Plan compares in cost savings for steady-state workloads.