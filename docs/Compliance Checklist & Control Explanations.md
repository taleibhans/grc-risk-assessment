
# **LuxeOnGo — Compliance Checklist & Control Explanations**

**Frameworks:** ISO/IEC 27001:2022 + NIST CSF 2.0
**Version:** 1.0
**Author:** Talei
**Date:** 2025

---

# **1. Purpose of This Checklist**

This checklist provides LuxeOnGo with:

* A **baseline maturity assessment**
* A structured understanding of **required controls**
* A tool for **internal audits**
* A clear map of **gaps and priorities**
* Evidence to hiring managers that you understand **industry standards**

It covers the five NIST CSF functions and relevant ISO 27001 Annex A controls:

1. Identify
2. Protect
3. Detect
4. Respond
5. Recover

Each section includes:

* Checklist items
* Control explanations (plain English)
* Owner assignment guidance
* Maturity scoring
* Diagrams for architecture understanding

---

# **2. How to Use This Checklist**

1. Review each control item
2. Mark it as **Yes / Partial / No**
3. Assign an **Owner**
4. Add comments or evidence
5. Calculate maturity score using the table in Section 7
6. Use findings to guide remediation

This is the same style used in real governance audits.

---

# **3. Compliance Checklist (with Explanations)**

Below is the **expanded, 4-page version**.

---

## **3.1 Identify (ID)**

*Objective: Understand what assets, data, systems, and risks exist.*

| Control                                                                | Status | Owner         | Explanation                                                                                                     |
| ---------------------------------------------------------------------- | :----: | ------------- | --------------------------------------------------------------------------------------------------------------- |
| **ID-01:** Asset inventory maintained (hardware, software, cloud apps) |   [ ]  | IT Manager    | You cannot secure what you don’t know exists. Inventory must include laptops, POS tablets, cloud apps, vendors. |
| **ID-02:** Data classification policy defined                          |   [ ]  | Security Lead | Defines what counts as Public, Internal, Confidential, Sensitive. Required by ISO 27001.                        |
| **ID-03:** Risk assessments performed annually                         |   [ ]  | GRC           | Identifies top threats and business impacts. Your risk assessment fits here.                                    |
| **ID-04:** System owners assigned for all major services               |   [ ]  | CTO           | Helps establish accountability for patching, monitoring, and incidents.                                         |
| **ID-05:** Third-party vendor assessments conducted                    |   [ ]  | GRC           | SaaS tools must be evaluated for MFA, encryption, and certifications.                                           |

---

## **3.2 Protect (PR)**

*Objective: Implement safeguards to limit security incidents.*

| Control                                                         | Status | Owner          | Explanation                                               |
| --------------------------------------------------------------- | :----: | -------------- | --------------------------------------------------------- |
| **PR-01:** MFA enabled for all accounts (admin & user)          |   [ ]  | Security Lead  | Single best control for account compromise prevention.    |
| **PR-02:** Patch management policy with monthly cadence         |   [ ]  | IT Manager     | ISO 27001 Annex A requires timely software updates.       |
| **PR-03:** Acceptable Use Policy (AUP) published & acknowledged |   [ ]  | HR + IT        | Required to enforce responsibilities and limit liability. |
| **PR-04:** Least privilege access implemented                   |   [ ]  | Cloud Admin    | Users only have access needed for their job.              |
| **PR-05:** Endpoint security (EDR/AV) deployed                  |   [ ]  | IT Security    | Required for detecting malware and unauthorized activity. |
| **PR-06:** Secure configurations applied (CIS benchmarks)       |   [ ]  | Infrastructure | Standardized builds reduce misconfigurations.             |
| **PR-07:** Awareness & phishing training held quarterly         |   [ ]  | HR + IT Sec    | Reduces human error, the largest threat vector.           |

---

## **3.3 Detect (DE)**

*Objective: Identify anomalies, threats, and potential security events.*

| Control                                                     | Status | Owner  | Explanation                                                     |
| ----------------------------------------------------------- | :----: | ------ | --------------------------------------------------------------- |
| **DE-01:** Centralized logging enabled (SIEM or cloud logs) |   [ ]  | SecOps | Required for fast detection and investigations.                 |
| **DE-02:** Alerts configured for brute-force attempts       |   [ ]  | SecOps | Critical for early account compromise detection.                |
| **DE-03:** Alerts for unusual data downloads                |   [ ]  | SecOps | Detects insider threats or stolen sessions.                     |
| **DE-04:** Vending machine POS logs monitored               |   [ ]  | IT Ops | Unique to LuxeOnGo — monitors theft, fraud, or tampering.       |
| **DE-05:** External attack surface reviewed monthly         |   [ ]  | SecOps | Helps catch open ports, cloud misconfigurations, expired certs. |

---

## **3.4 Respond (RS)**

*Objective: Contain and mitigate the effects of incidents.*

| Control                                                    | Status | Owner         | Explanation                                                 |
| ---------------------------------------------------------- | :----: | ------------- | ----------------------------------------------------------- |
| **RS-01:** Incident Response Plan documented               |   [ ]  | Security Lead | Defines roles, communication flow, escalation paths.        |
| **RS-02:** IR plan tested annually (tabletop exercise)     |   [ ]  | GRC           | Required for ISO 27001 compliance.                          |
| **RS-03:** Communications plan for security events defined |   [ ]  | Management    | Includes customer notifications and regulatory obligations. |
| **RS-04:** Dedicated mailbox or hotline for reporting      |   [ ]  | IT Support    | Must exist for employees to report incidents fast.          |

---

## **3.5 Recover (RC)**

*Objective: Restore normal operations after an incident.*

| Control                                           | Status | Owner        | Explanation                                            |
| ------------------------------------------------- | :----: | ------------ | ------------------------------------------------------ |
| **RC-01:** Backup policy documented               |   [ ]  | Backup Admin | Defines retention, encryption, and frequency.          |
| **RC-02:** Backups tested quarterly               |   [ ]  | Backup Admin | Verifies they actually work — many do not.             |
| **RC-03:** Disaster Recovery (DR) plan exists     |   [ ]  | CTO + IT Ops | Defines how to restore operations after major outages. |
| **RC-04:** Cloud data retention rules implemented |   [ ]  | Cloud Admin  | Prevents accidental deletion or tampering.             |

---

# **4. Visual Diagrams**

Below are plain-text diagrams suitable for GitHub or documentation.

---

## **4.1 System Architecture Diagram (Simplified)**

```
                      +---------------------+
                      |   LuxeOnGo Cloud    |
                      | (CRM, Email, IAM)   |
                      +----------+----------+
                                 |
                                 | Auth, MFA
                                 |
+---------------+       +--------v---------+        +----------------+
| POS Tablets   +------->    API Layer     <--------+ Admin Laptops |
| (Vending)     |       | (TLS, Logging)   |        |  (VPN, EDR)    |
+-------+-------+       +--------+---------+        +--------+-------+
        |                        |                           |
        | Wi-Fi/VPN              | Cloud Storage             | SIEM/SOC Logs
        |                        |                           |
+-------v-------+       +--------v---------+        +--------v-------+
| On-site Wi-Fi |       |   Data Storage   |        | Security Tools |
| & Firewall    |       | (Encrypted)      |        | (Alerts, EDR)  |
+---------------+       +------------------+        +----------------+
```

---

## **4.2 NIST CSF Function Flow Diagram**

```
IDENTIFY → PROTECT → DETECT → RESPOND → RECOVER
      ↑                                           ↓
      +--------------- Continuous Improvement -----+
```

---

# **5. Maturity Scoring Model**

Use this to score LuxeOnGo from **0 (weak)** to **5 (strong)**.

| Level               | Description                                       |
| ------------------- | ------------------------------------------------- |
| **0 – Nonexistent** | No controls, ad hoc processes, no documentation   |
| **1 – Initial**     | Some controls exist but inconsistent or informal  |
| **2 – Developing**  | Controls exist but not fully deployed or measured |
| **3 – Defined**     | Policies documented, processes repeatable         |
| **4 – Managed**     | Controls monitored, metrics tracked               |
| **5 – Optimized**   | Automated, continuous improvement loop active     |

### Example use:

* If LuxeOnGo meets 16/30 controls → maturity ≈ Level 2.
* If it reaches 26/30 → maturity ≈ Level 4.

---

# **6. Remediation Priorities (Based on Common Gaps)**

For a company at LuxeOnGo’s size & structure, the top priorities usually are:

### **Priority 1: Enable MFA everywhere**

Covers ISO: A.5 & NIST: PR.AA
Greatest impact and fastest win.

### **Priority 2: Patch management + inventory**

You cannot secure assets you do not track.

### **Priority 3: Centralized logging + detection rules**

Essential for early attack detection.

### **Priority 4: Quarterly backup restore testing**

Backups are useless if untested.

### **Priority 5: Annual incident response testing**

Mandatory for ISO certification.

---

# **7. Quick Audit Summary Table**

Below is a final one-page summary you can use for interviews or GitHub.

| Function  | Total Controls  | Yes | Partial | No | Score   |
| --------- | --------------- | --- | ------- | -- | ------- |
| Identify  | 5               |     |         |    |         |
| Protect   | 7               |     |         |    |         |
| Detect    | 5               |     |         |    |         |
| Respond   | 4               |     |         |    |         |
| Recover   | 4               |     |         |    |         |
| **TOTAL** | **25 controls** |     |         |    | **/25** |

#### Interpretation:

* **0–10** → Low maturity (Level 1)
* **11–18** → Developing (Level 2–3)
* **19–23** → Managed (Level 4)
* **24–25** → Optimized (Level 5)

---

# **8. Appendix A — Definitions**

* **AUP:** Acceptable Use Policy
* **MFA:** Multi-factor authentication
* **EDR:** Endpoint Detection & Response
* **DRP:** Disaster Recovery Plan
* **SIEM:** Security Information & Event Management
* **IAM:** Identity & Access Management
* **PII:** Personally Identifiable Information
* **NIST CSF:** NIST Cybersecurity Framework
* **ISO 27001:** International standard for information security controls

---

# **9. Appendix B — Evidence Examples**

You can attach:

* Screenshots of Google Workspace MFA settings
* Asset inventory CSV
* Logging dashboard (even dummy data)
* Policy documents
* Backup logs
* Sample phishing training slides

This is excellent for your GitHub.

---

# **10. Appendix C — Control Mapping Table**

| ISO 27001 Annex A Control | Mapped NIST CSF Category |
| ------------------------- | ------------------------ |
| A.5 Access Control        | PR.AA                    |
| A.8 Asset Management      | ID.AM                    |
| A.12 Operations Security  | PR.PS                    |
| A.16 Incident Management  | RS.MI                    |
| A.17 Business Continuity  | RC                       |


---

