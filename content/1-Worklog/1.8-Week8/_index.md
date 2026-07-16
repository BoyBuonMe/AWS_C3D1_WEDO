---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---



### Week 8 Objectives:
* Configure custom WAF rules with rate-based limiting to block malicious traffic patterns.
* Automate compliance checks and cost allocation using Tag-based Resource Groups.
* Design conditional IAM policies that scope EC2 permissions to specific Resource Tags.
* Build custom Grafana dashboards with alerting thresholds for critical AWS metrics.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2 | **AWS WAF:** Configure a rate-based rule to throttle requests from a single IP address, set up a Managed Rule Group for known bad inputs, and test rule behavior using both Count and Block modes. | 08/06/2026 | 08/06/2026 | https://000026.awsstudygroup.com/1-introduction/ |
| 3 | **Tags & Resource Groups:** Design a consistent tagging strategy across teams and environments, then use AWS Resource Groups Tag Editor to bulk-apply and audit tags across multiple resource types. | 09/06/2026 | 09/06/2026 | https://000027.awsstudygroup.com/1-introduction/ |
| 5 | **Manage EC2 Access with IAM & Tags:** Write IAM policies using the `aws:ResourceTag` condition key to restrict start/stop actions to specific teams, and test policy behavior with the IAM Policy Simulator. | 11/06/2026 | 11/06/2026 | https://000028.awsstudygroup.com/1-introduction/ |
| 6 | **Monitoring with Grafana:** Connect Grafana to CloudWatch as a data source, build a custom dashboard combining multiple metrics, and configure alert notifications when thresholds are breached. | 12/06/2026 | 12/06/2026 | https://000029.awsstudygroup.com/1-introduction/|

### Week 8 Achievements:
* **Application Security (AWS WAF):** Configured rate-based rules to throttle suspicious traffic from individual IPs, and validated rule effectiveness by comparing behavior between Count mode (logging only) and Block mode (active enforcement).
* **Resource Organization (Tags & Resource Groups):** Designed a standardized tagging convention applied consistently across teams, then used the Tag Editor to bulk-audit and correct inconsistent tags across a large resource set.
* **Access Control (IAM):** Wrote condition-based IAM policies scoping EC2 permissions to specific Resource Tags, and verified policy correctness using the IAM Policy Simulator before deploying to production.
* **Visual Monitoring (Grafana):** Connected Grafana directly to CloudWatch as a live data source and configured threshold-based alerts to proactively flag abnormal resource behavior.