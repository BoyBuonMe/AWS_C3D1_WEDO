---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---



### Week 7 Objectives:
* Configure artifact encryption and multi-stage build validation within a CI/CD pipeline using AWS Developer Tools.
* Test failover and bandwidth optimization for a hybrid storage connection with File Storage Gateway.
* Configure quota enforcement, data protection, and capacity scaling for a shared file system with Amazon FSx.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2-3 | **CI/CD with AWS CodePipeline:** Configure branch-based triggers so commits to different branches deploy to separate environments, add a manual approval stage before production deployment, and set up rollback on deployment failure. | 01/06/2026 | 02/06/2026 | https://000023.awsstudygroup.com/1-introduction/ |
| 4 | **AWS File Storage Gateway:** Configure local caching to optimize read performance for frequently accessed files, test bandwidth throttling schedules, and validate failover behavior when the on-premises connection drops. | 03/06/2026 | 03/06/2026 | https://000024.awsstudygroup.com/1-introduction/ |
| 5-6 | **Amazon FSx for Windows File Server:** Configure Active Directory integration for user-based access control, set up automatic daily backups, and test capacity auto-scaling under simulated storage growth. | 04/06/2026 | 05/06/2026 | https://000025.awsstudygroup.com/1-introduction/ |

### Week 7 Achievements:
* **Release Automation (DevOps & CI/CD):** Configured branch-based deployment triggers and a manual approval gate to safely control production releases, and validated automatic rollback behavior when a deployment fails.
* **Hybrid Storage (Storage Gateway):** Improved read performance for frequently accessed files through local caching, and confirmed the storage connection maintains failover resilience when the on-premises link is interrupted.
* **Windows Storage Management (Amazon FSx):** Integrated Active Directory for granular user access control, automated daily backups for data protection, and verified that capacity scales correctly under simulated storage growth.