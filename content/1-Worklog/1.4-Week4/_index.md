---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---



### Week 4 Objectives:
* Configure conditional DNS forwarding between on-premise systems and AWS using Amazon Route 53 Resolver.
* Automate resource management and data extraction using the AWS Command Line Interface (CLI), including scripting and multi-account profiles.
* Strengthen data protection through lifecycle-managed and cross-region backups with AWS Backup and Amazon SNS.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **Hybrid DNS with Route 53 Resolver:** Configure conditional forwarding rules to route specific domain queries between on-premise DNS and Route 53, and validate name resolution using DNS query logging. | 11/05/2026 | 11/05/2026 | https://000010.awsstudygroup.com/ |
| 3-5 | **AWS Command Line Interface (CLI):** Write shell scripts to automate common resource provisioning tasks, use `--query` and JMESPath filtering to parse CLI output, and configure named profiles with assumed roles for multi-account access. | 12/05/2026 | 14/05/2026 | https://000011.awsstudygroup.com/ |
| 6 | **System (AWS Backup & SNS):** Apply lifecycle rules to transition backups to cold storage, configure cross-region backup copies for disaster recovery, and set up SNS notifications to alert on failed backup jobs. | 15/05/2026 | 15/05/2026 | https://000013.awsstudygroup.com/ |

### Week 4 Achievements:
* **Networking & DNS (Route 53):** Configured conditional forwarding rules to accurately route DNS queries between simulated on-premise systems and AWS, and used DNS query logging to verify resolution paths end to end.
* **Command Line Management (AWS CLI):** Automated repetitive resource provisioning tasks through shell scripting, applied JMESPath filtering to extract precise data from CLI output, and configured multi-account access using named profiles with assumed roles.
* **Data Protection & Automation (AWS Backup & SNS):** Reduced long-term storage costs by applying lifecycle rules to transition older backups to cold storage, strengthened disaster recovery posture with cross-region backup copies, and set up SNS alerts to immediately flag failed backup jobs.