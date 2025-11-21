
# 📄 **LuxeOnGo — IT Risk Assessment** 

**Author:** Talei
**Date:** 2025-11-21
**Version:** 1.0
**Company Type:** Beauty retail + e-commerce brand
**Document Purpose:** Portfolio sample for junior GRC / IT Compliance roles

---

# **1. Executive Summary**

This IT Risk Assessment evaluates the security posture of **LuxeOnGo**, a beauty-focused business operating an online storefront, corporate workstations, cloud services, and internal operational tools. The assessment identifies the company's key assets, threats, vulnerabilities, and control gaps, then prioritizes risks using a likelihood–impact scoring methodology.

LuxeOnGo is still in its scaling phase, meaning the technology environment is growing quickly. The business relies heavily on **cloud-based email**, **endpoint devices**, **a public-facing e-commerce website**, **third-party vendors**, and **digital payment processors**. These factors introduce risks ranging from phishing and credential compromise to cloud misconfiguration, data leakage, and operational downtime.

The goal of this assessment is to:

1. Provide leadership with a clear overview of current risks
2. Prioritize remediation steps based on business impact
3. Establish a baseline for future audits, compliance reviews, and SOC maturity

Primary findings show elevated exposure to credential-based compromise, inconsistent patching processes, lack of centralized logging, reliance on third-party vendors without formal risk assessments, and gaps in backup verification.

This assessment concludes with a formal **Risk Treatment Plan** to address these issues over the next 30–90 days.

---

# **2. Scope of Assessment**

**In Scope Assets:**

* Corporate laptops (Windows/macOS)
* Employee mobile devices (BYOD, partial access)
* Cloud email platform (Google Workspace / O365)
* Public e-commerce platform (shop.luxeongo.com)
* Payment processing integrations (Stripe/Shopify)
* Internal shared drives & cloud storage
* Wi-Fi networks (office + guest)
* Customer data (order information, emails)
* Backup storage (cloud-based snapshot backups)

**Out-of-Scope:**

* Physical building/access control
* HR processes unrelated to IT
* Marketing social media accounts (covered by separate policy)

**Assessment Period:** 30 days
**Methodology Used:**

* ISO 27005 risk assessment concepts
* NIST CSF Identify–Protect–Detect–Respond–Recover
* Standard qualitative scoring (1–5)

---

# **3. Methodology**

LuxeOnGo’s risks were evaluated by following four steps:

### **1. Asset Identification**

Business-critical assets were identified by function: data, infrastructure, users, devices, and third-party services.

### **2. Threat & Vulnerability Analysis**

Threats such as phishing, cloud misconfiguration, and system compromise were mapped against vulnerabilities like weak password practices, unpatched software, or poor access control.

### **3. Risk Scoring (Likelihood × Impact)**

Each risk receives two scores:

**Likelihood levels:**
1 — Rare
2 — Low
3 — Medium
4 — High
5 — Almost Certain

**Impact levels:**
1 — Negligible
2 — Minor
3 — Moderate
4 — Major
5 — Critical

### **Risk Matrix Diagram**

```
                 IMPACT
LIKELIHOOD   1  2  3  4  5
          ------------------
        5 |  M  M  H  H  C
        4 |  M  M  H  H  H
        3 |  L  M  M  H  H
        2 |  L  L  M  M  H
        1 |  L  L  L  M  M

L = Low   M = Medium   H = High   C = Critical
```

### **4. Risk Prioritization**

Risks scoring **High** or **Critical** require immediate attention (30–60 days). Medium risks require monitoring and planned remediation. Low risks are accepted with periodic review.

---

# **4. Asset Overview**

### **Critical Business Assets**

| Category | Asset                             | Explanation                                 |
| -------- | --------------------------------- | ------------------------------------------- |
| Data     | Customer PII, order data          | Needed for business operations & compliance |
| Systems  | E-commerce platform               | Main revenue channel                        |
| Identity | Email accounts, admin credentials | Gateway to sensitive systems                |
| Infra    | Endpoints, Wi-Fi, VPN             | Supports internal operations                |
| Vendors  | Shopify, Stripe, 3PLs             | High dependency risk                        |
| Backups  | Cloud snapshots                   | Required for recovery after incidents       |

### **System Diagram (Simplified)**

```
                 Internet
                    |
          ----------------------
          |                    |
    Public Website        Cloud Email
 (Shopify/Custom App)     (O365/G-Suite)
          |                    |
   Payment Processor       Staff Devices
         Stripe        --------------------
                   | Laptops | Phones | Tablets |
                    -----------------------------
                               |
                         Internal Wi-Fi
                               |
                           Shared Cloud
                           Storage/Drive
```

---

# **5. Detailed Risk Register (Expanded)**

Below are **8 full, interview-ready risk entries**.

---

## **Risk 1: Credential Compromise via Phishing**

* **Likelihood:** High
* **Impact:** High
* **Risk Score:** High
* **Description:** Attackers send realistic phishing emails targeting staff accounts to steal passwords and bypass weak detection rules.
* **Current Controls:** Basic spam filtering; optional MFA not enforced; inconsistent security training.
* **Gaps:** No phishing simulation program, no mailbox monitoring alerts, no enforced MFA.
* **Recommended Treatment:**

  1. Enforce MFA for all accounts (priority, 2–4 weeks).
  2. Implement quarterly phishing simulations.
  3. Add SIEM alerts for forwarding rule creation & impossible travel logins.
* **Residual Risk:** Medium after full MFA adoption.

---

## **Risk 2: Cloud Storage Misconfiguration (Data Leak)**

* **Likelihood:** Medium
* **Impact:** Critical
* **Risk Score:** High
* **Description:** Publicly exposed cloud folders or misconfigured access permissions could lead to unauthorized exposure of product data, customer info, or internal documents.
* **Current Controls:** Default settings; unverified access groups; informal sharing.
* **Gaps:** No cloud security posture review; no least privilege policy.
* **Recommended Treatment:**

  * Full cloud access audit within 30 days.
  * Restrict sharing to company-only; enforce link expiration.
  * Implement CASB or built-in DLP controls.

---

## **Risk 3: Outdated Endpoint Patching**

* **Likelihood:** Medium
* **Impact:** High
* **Risk Score:** Medium-High
* **Description:** Laptops may miss monthly patches, exposing LuxeOnGo to RCE vulnerabilities.
* **Gaps:** No patch management cadence, no asset inventory.
* **Mitigation:**

  * Monthly patch schedule + critical patch SLA.
  * Deploy endpoint monitoring tool (Intune/Jamf).

---

## **Risk 4: Unauthorized Access to Admin Panels**

* **Likelihood:** Low-Medium
* **Impact:** Critical
* **Risk Score:** High
* **Description:** Admin portals (Shopify, payment processor, hosting provider) may rely on weak passwords or unmonitored access.
* **Mitigation:**

  * Enforce MFA + hardware key for admin accounts.
  * Separate admin accounts from user accounts.

---

## **Risk 5: Third-Party Vendor Security Gaps**

* **Likelihood:** Medium
* **Impact:** High
* **Risk Score:** Medium-High
* **Description:** Lack of vendor security questionnaires creates dependency risk.
* **Mitigation:**

  * Conduct vendor risk assessments (annual).
  * Include security clauses in contracts.

---

## **Risk 6: Weak Backup & Disaster Recovery Testing**

* **Likelihood:** Low
* **Impact:** High
* **Risk Score:** Medium
* **Description:** Backups exist but restore testing is not performed.
* **Mitigation:**

  * Quarterly restore testing.
  * Backup encryption review.

---

## **Risk 7: Lack of Centralized Logging & Monitoring**

* **Likelihood:** Medium
* **Impact:** Medium-High
* **Risk Score:** Medium-High
* **Description:** No SIEM means delayed detection of breaches.
* **Mitigation:**

  * Enable central logging (budget-friendly options like Wazuh/Splunk Free).

---

## **Risk 8: Insecure Public Wi-Fi**

* **Likelihood:** Medium
* **Impact:** Medium
* **Risk Score:** Medium
* **Description:** Guest network may expose customer devices or allow pivot.
* **Mitigation:**

  * VLAN segmentation
  * Strong WPA3 configuration

---

# **6. Risk Treatment Plan (Summary)**

| Priority | Action                           | Owner         | Deadline |
| -------- | -------------------------------- | ------------- | -------- |
| 1        | Enforce MFA company-wide         | Security Lead | 30 days  |
| 2        | Cloud security audit             | Cloud Admin   | 45 days  |
| 3        | Patch management program         | IT Manager    | 60 days  |
| 4        | Quarterly backup restore testing | IT + Ops      | 90 days  |
| 5        | Vendor risk review process       | Finance + IT  | 60 days  |

---

# **7. Residual Risk & Acceptance Process**

Residual risks are reviewed monthly. Risks scoring Medium or below may be accepted by leadership. High risks require documented justification and compensating controls.

---

# **8. Appendix A — Definitions**

This appendix provides clear definitions of key cybersecurity, GRC, compliance, and IT operational terms used throughout the LuxeOnGo IT Risk Assessment. These definitions help ensure non-technical stakeholders understand risk decisions, controls, and priorities.

---

## **Access Control**

Processes and mechanisms used to ensure that only authorized users can access specific systems, applications, or data. Examples include passwords, MFA, role-based access control (RBAC), and network segmentation.

---

## **Asset**

Any data, system, device, or service that holds value to the business. In this assessment, assets include laptops, cloud storage, customer data, e-commerce platforms, backups, and administrative accounts.

---

## **Authentication**

The process of verifying the identity of a user or device before granting access. Common methods include passwords, biometrics, tokens, or multi-factor authentication.

---

## **Authorization**

The permissions a user has *after* they have been authenticated. For example, a staff member may authenticate successfully but only be authorized to access non-admin features.

---

## **Backup & Recovery**

The process of creating copies of data and restoring them if the original data is lost, corrupted, or compromised. Backup strategy is essential to business continuity.

---

## **Cloud Misconfiguration**

Improper setup of cloud services (e.g., public file shares, overly broad permissions) that could expose sensitive data or allow unauthorized access.

---

## **Compliance**

The requirement to meet internal policies, contractual obligations, and recognized standards such as ISO 27001, NIST CSF, PCI DSS, or privacy legislation.

---

## **Control (Security Control)**

A safeguard or mechanism that reduces risk. Controls may be technical (MFA), administrative (policies), or physical (locks, surveillance).

---

## **Credential Compromise**

When a user's login details (username/password) are stolen or guessed, giving attackers access to systems. Often occurs through phishing, weak passwords, or reused passwords.

---

## **Critical System**

Any system whose compromise would result in major financial loss, customer data exposure, or business interruption. For LuxeOnGo, this includes the e-commerce platform, payment integrations, and cloud email.

---

## **Data Classification**

A method of grouping data by sensitivity level — e.g., Public, Internal, Confidential, Restricted. Helps determine how data must be stored and handled.

---

## **Data Leakage / Data Exposure**

Unintentional disclosure of sensitive data. This may be caused by cloud misconfigurations, improper file sharing, weak access controls, or mistaken emails.

---

## **Disaster Recovery (DR)**

The documented process for restoring business operations after a major outage, cyberattack, or incident. DR includes backup restoration, system rebuilds, and fallback procedures.

---

## **Endpoint**

A user device such as a laptop, phone, or tablet that connects to corporate systems. Endpoints are common entry points for attackers.

---

## **Firewall**

A tool that monitors and filters incoming and outgoing network traffic to prevent unauthorized access.

---

## **Impact (Risk Impact)**

The severity of damage that would occur if a risk materialized. Impact may include financial losses, downtime, data leaks, regulatory fines, or reputational harm.

---

## **Incident**

Any event that compromises the confidentiality, integrity, or availability of information systems. Examples include malware infection, unauthorized access, or data exposure.

---

## **Incident Response (IR)**

A structured process for identifying, analyzing, containing, and recovering from security incidents.

---

## **Least Privilege**

A principle that gives users only the minimum level of access they need to complete their job. Reduces insider risk and limits damage from compromised accounts.

---

## **Likelihood**

The estimated probability of a threat exploiting a vulnerability. Scores typically range from Low to Critical or 1 to 5.

---

## **Multi-Factor Authentication (MFA)**

A security method requiring two or more verification factors (e.g., password + phone code) to access an account. MFA reduces risk of credential theft.

---

## **Patch Management**

Ongoing process of updating software and operating systems to fix vulnerabilities. Failure to patch can result in exploitation.

---

## **Phishing**

A social engineering attack where a user receives fraudulent messages (email, SMS, DM) designed to trick them into revealing information or installing malware.

---

## **Residual Risk**

The remaining risk after controls and mitigations have been applied. No risk can be completely eliminated, but it can be reduced to an acceptable level.

---

## **Risk**

The potential for loss, damage, or unauthorized access to assets caused by a threat exploiting a vulnerability.

---

## **Risk Acceptance**

A decision by leadership to acknowledge a risk without taking further action, usually because it is low or cost-prohibitive to address.

---

## **Risk Register**

A structured document or spreadsheet that tracks identified risks, their scores, mitigation plans, owners, and status updates.

---

## **Security Posture**

Overall strength and maturity of an organization’s security controls, processes, and defenses.

---

## **SIEM (Security Information and Event Management)**

A tool that collects logs and alerts from systems to detect suspicious activity. Used in SOC environments for monitoring and response.

---

## **Threat**

Any event or actor (hacker, malware, insider misuse, system failure) that can exploit vulnerabilities to cause harm.

---

## **Vendor Risk**

The risk introduced by third-party services or suppliers who may store, process, or access company data. Vendors must be assessed regularly for security posture.

---

## **Vulnerability**

A flaw, weakness, or gap in a system that may be exploited by a threat. Examples: unpatched software, weak passwords, misconfigured cloud buckets.

---

# **📎 Appendix B — Full Asset Inventory**

This appendix lists the critical assets identified during LuxeOnGo’s risk assessment. These assets form the foundation for understanding vulnerabilities and threats.

### **B.1 — Hardware Assets**

| Asset                     | Description                                       | Owner            | Location             | Classification |
| ------------------------- | ------------------------------------------------- | ---------------- | -------------------- | -------------- |
| POS Tablets               | Used for customer orders at vending machines      | Operations Lead  | Retail/Vending Sites | High           |
| Employee Laptops          | Used for administrative work & product management | IT Administrator | Hybrid               | High           |
| Network Router & Firewall | Provides secure connectivity for office systems   | IT Administrator | Office Network       | High           |
| Peripheral Devices        | Scanners, printers, label makers                  | Operations Team  | Office               | Medium         |

---

### **B.2 — Software Assets**

| Asset                             | Description                                      | Owner          | Version            | Classification |
| --------------------------------- | ------------------------------------------------ | -------------- | ------------------ | -------------- |
| Inventory Management System (IMS) | Tracks all stock levels & vending machine status | Product Ops    | Cloud-hosted       | High           |
| CRM Platform                      | Manages customer feedback & transactions         | Marketing Lead | SaaS               | Medium         |
| Payment Processing System         | Handles card transactions                        | CFO / Finance  | PCI-compliant SaaS | High           |
| Google Workspace                  | Email, Drive, Docs, authentication               | Business Admin | SaaS               | Medium         |

---

### **B.3 — Data Assets**

| Asset                     | Description                           | Classification | Retention |
| ------------------------- | ------------------------------------- | -------------- | --------- |
| Customer Purchase Records | Vending machine & online transactions | High           | 2 years   |
| Employee PII              | Names, emails, payroll data           | High           | 7 years   |
| Product Data              | Nail sets, SKUs, packaging designs    | Medium         | Ongoing   |
| Financial Records         | Sales, invoices, payment logs         | High           | 7 years   |

---

### **B.4 — Cloud Assets**

| Asset                   | Description                     | Provider     | Security Level |
| ----------------------- | ------------------------------- | ------------ | -------------- |
| Cloud Database          | Stores product & sales data     | AWS RDS      | High           |
| Web Application Hosting | Marketing website               | AWS EC2      | Medium         |
| Cloud Storage           | Images, design files, documents | Google Drive | Medium         |

---

---

# **📎 Appendix C — Risk Register (Expanded)**

This appendix contains the full register of all risks identified, including impact, likelihood, controls, and residual risk.

### **C.1 — Risk Register Table**

| Risk ID | Risk Description                           | Impact | Likelihood | Inherent Risk | Existing Controls                    | Residual Risk | Owner       |
| ------- | ------------------------------------------ | ------ | ---------- | ------------- | ------------------------------------ | ------------- | ----------- |
| R-01    | Phishing attack against employees          | High   | Medium     | High          | Google Workspace filtering, training | Medium        | IT Security |
| R-02    | Misconfigured cloud storage exposing files | High   | Low        | Medium        | Access reviews, MFA                  | Low           | IT          |
| R-03    | POS device theft                           | Medium | Medium     | Medium        | Device locking, MDM                  | Low           | Operations  |
| R-04    | Inventory database outage                  | High   | Medium     | High          | Cloud backups, redundancy            | Medium        | IT          |
| R-05    | Payment processing disruption              | High   | Low        | Medium        | Third-party SLA, failover            | Low           | Finance     |
| R-06    | Employee mishandling customer data         | High   | Medium     | High          | Training, AUP, encryption            | Medium        | HR/IT       |
| R-07    | Malware infection via USB or downloads     | High   | Medium     | High          | EDR, restricted downloads            | Medium        | IT Security |
| R-08    | Unauthorized access to vending machines    | Medium | Low        | Medium        | Physical locks, CCTV                 | Low           | Operations  |
| R-09    | Email account compromise                   | High   | Medium     | High          | MFA, alerts                          | Medium        | IT          |
| R-10    | Website defacement or downtime             | Medium | Medium     | Medium        | WAF, CDN, patching                   | Low           | IT Security |

---

### **C.2 — Heat Map (Text-Based)**

```
            RISK HEAT MAP          
 
             Likelihood →
Impact ↓    Low     Medium     High
-----------------------------------------
High        R-02     R-01 R-04 R-06 R-07 R-09
Medium      R-03     R-08 R-10
Low         —        —         —
```

---

### **C.3 — Risk Treatment Summary**

* Risks treated: R-01, R-04, R-06, R-07
* Risks accepted (low impact/likelihood): R-08
* Risks transferred: R-05 (payment failures handled by provider SLA)
* Risks mitigated through improved controls: R-02, R-03, R-09, R-10

---

---

# **📎 Appendix D — Control Mapping (ISO 27001 & NIST CSF)**

This appendix ties LuxeOnGo’s existing and planned controls to recognized security frameworks.

---

## **D.1 — ISO 27001: Annex A Control Mapping**

| Control Code | Control Description            | Implemented? | Evidence               |
| ------------ | ------------------------------ | ------------ | ---------------------- |
| A.5.1        | Information security policies  | Yes          | AUP, Risk Assessment   |
| A.6.3        | Contact with authorities       | Partial      | Incident Response Plan |
| A.7.2        | Information security awareness | Yes          | Employee onboarding    |
| A.8.1        | Asset inventory                | Yes          | Appendix B             |
| A.9.2        | User access provisioning       | Yes          | Google Workspace IAM   |
| A.12.2       | Malware protection             | Yes          | EDR + scanning         |
| A.12.6       | Technical vulnerability mgmt   | Partial      | Patch schedule         |
| A.14.2       | Secure development practices   | Planned      | Web app controls       |
| A.16.1       | Incident response management   | Partial      | SOC Playbook draft     |
| A.18.1       | Compliance with regulations    | Yes          | PCI DSS partner        |

---

## **D.2 — NIST Cybersecurity Framework Mapping**

| NIST Function | Category                               | Status   | Notes                      |
| ------------- | -------------------------------------- | -------- | -------------------------- |
| **Identify**  | Asset Management (ID.AM)               | Complete | Inventory established      |
| **Protect**   | Access Control (PR.AC)                 | Good     | MFA + IAM                  |
| **Protect**   | Awareness & Training (PR.AT)           | Good     | Policies & training        |
| **Detect**    | Security Continuous Monitoring (DE.CM) | Partial  | SOC project ongoing        |
| **Respond**   | Response Planning (RS.RP)              | Partial  | Incident templates created |
| **Recover**   | Backup & Recovery (RC.RC)              | Good     | Cloud backup system        |

---

## **D.3 — Diagram: Control Mapping Overview (ASCII)**

```
              ┌────────────────────────┐
              │  LuxeOnGo Controls     │
              └──────────┬─────────────┘
                         │
     ┌───────────────────┼─────────────────────┐
     │                   │                     │
 ISO 27001         NIST CSF             Internal Policies
(A.5–A.18)      (ID, PR, DE, RS, RC)     (AUP, SOPs, IRP)
```

---

