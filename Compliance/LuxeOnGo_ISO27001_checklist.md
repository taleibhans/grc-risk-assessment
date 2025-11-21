## `03_LuxeOnGo_ISO27001_Checklist.xlsx` 

| Control # | Control Name                           | Requirement Description                                                               | Implemented? | Evidence                         | Owner         | Notes |
| --------- | -------------------------------------- | ------------------------------------------------------------------------------------- | :----------: | -------------------------------- | ------------- | ----- |
| A.5.1     | Information Security Policies          | Policies should be approved, communicated, and periodically reviewed.                 |     Yes      | 02_LuxeOnGo_AUP.pdf              | Security Lead | Reviewed annually. |
| A.6.1     | Internal Organization                  | Define roles, responsibilities and reporting lines for information security.          |   Partial    | org_chart.png                    | Security Lead | RACI chart not formalized. |
| A.7.2     | Information Security Awareness         | Provide security training and regular phishing simulations for staff.                 |   Partial    | training_log.xlsx                | HR / IT       | Quarterly training planned. |
| A.8.1     | Asset Inventory                        | Maintain an up-to-date inventory of hardware, software, cloud apps, and data assets. |   Partial    | asset_inventory.csv              | IT Manager    | Needs automation. |
| A.9.2     | User Access Management                 | Provision, review, and deprovision access; log privilege changes.                     |   Partial    | access_review_logs/              | Cloud Admin   | Manual reviews only. |
| A.12.2    | Malware Protection                     | Deploy EDR/AV on endpoints and ensure regular signature/behavior updates.             |     Yes      | edr_dashboard.png                | IT Security   | Using modern EDR. |
| A.12.4    | Logging & Monitoring                   | Centralized logging, retention policy, critical alerts.                               |   Partial    | SIEM_screenshots/                | SecOps        | SIEM not fully deployed. |
| A.13.1    | Network Security                       | Firewalls, segmentation, secure Wi-Fi, VPN for remote access.                        |   Partial    | network_config.pdf               | IT Manager    | Firewall rules need audit. |
| A.14.2    | Secure Development                     | Secure SDLC, dependency scanning, code review.                                        |     No       | N/A                              | Dev Lead      | No formal SDLC. |
| A.16.1    | Incident Management                    | IR plan, incident reporting, escalation, communication.                               |   Partial    | IRP_v1.0.pdf                     | Security Lead | No tabletop exercises yet. |
| A.17.1    | Business Continuity & DR               | Backup policy, restore testing, DR plan.                                              |   Partial    | backup_test_results.xlsx         | IT Ops        | Testing inconsistent. |
| A.18.1    | Compliance with Legal/Contractual Req. | Track applicable laws (privacy, PCI) and evidence of compliance.                      |   Partial    | compliance_register.docx         | Legal/Finance | DPIA needed. |

---
