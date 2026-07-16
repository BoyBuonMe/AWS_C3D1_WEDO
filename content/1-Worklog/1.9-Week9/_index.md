---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Week 9 Objectives:
* Prevent privilege escalation by scoping maximum permissions with IAM Permission Boundary.
* Automate patch compliance reporting and remote script execution with AWS Systems Manager.
* Analyze memory utilization and receive rightsizing recommendations with CloudWatch Agent and Compute Optimizer.
* Enable automatic key rotation with AWS KMS, and query encrypted API activity logs using CloudTrail and Athena.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **IAM Permission Boundary:** Attach a Permission Boundary to an IAM user that limits the maximum permissions they can delegate, then attempt to grant excessive permissions to verify the boundary blocks privilege escalation. | 15/06/2026 | 15/06/2026 | https://000030.awsstudygroup.com/1-introduction/ |
| 3 | **AWS Systems Manager:** Configure a Patch Baseline with custom approval rules, schedule patching through Maintenance Windows, and use Run Command to execute a script across a tag-filtered group of instances. | 16/06/2026 | 16/06/2026 | https://000031.awsstudygroup.com/1-introduction/ |
| 4 | **EC2 Right-sizing:** Configure the CloudWatch Agent to capture custom memory and disk metrics, then generate and interpret Compute Optimizer recommendations to identify over-provisioned instances. | 17/06/2026 | 17/06/2026 | https://000032.awsstudygroup.com/1-introduction/ |
| 6 | **Encryption with AWS KMS:** Enable automatic annual key rotation for a KMS key, apply a key policy restricting decrypt permissions to specific roles, and write an Athena query to filter CloudTrail logs for unauthorized decrypt attempts. | 19/06/2026 | 19/06/2026 | https://000033.awsstudygroup.com/1-introduction/ |
| 7 | **Event:** Participate in Event 3. | 20/06/2026 | 20/06/2026 | FCAJ Event |

### Week 9 Achievements:
* **Access Control Security (IAM):** Configured a Permission Boundary that caps the maximum permissions an IAM user can grant, and confirmed through testing that attempts to exceed the boundary are correctly blocked.
* **Operational Automation (Systems Manager):** Set up a custom Patch Baseline with scheduled Maintenance Windows, and used Run Command to execute scripts across tag-filtered instance groups without manual SSH access.
* **Cost & Performance Optimization (EC2 Right-sizing):** Captured detailed memory metrics through a custom CloudWatch Agent configuration, then used Compute Optimizer recommendations to identify and correct over-provisioned instances.
* **Data Security (KMS & Data logs):** Enabled automatic key rotation and restricted decrypt permissions through a scoped key policy, then used Athena to query CloudTrail logs and detect unauthorized decrypt attempts.