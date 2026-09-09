# LetsDefend - SOC Fundamentals Notes
<a href="https://www.youtube.com/watch?v=RfjvpHFLYSw"> <img src="https://img.shields.io/badge/-Youtube-CD201F?&style=for-the-badge&logo=youtube&logoColor=white" /></a>

## 1. What is a SOC?
A **Security Operations Center (SOC)** is a centralized organizational unit responsible for continuously monitoring, analyzing, detecting, and responding to cybersecurity incidents using a coordinated triad of **People, Process, and Technology**.


---

## 2. The Core Pillars
* **People:** Security analysts, threat hunters, engineers, and incident responders who interpret alerts and investigate anomalous activity.
* **Process:** Standard operating procedures (SOPs), playbooks, escalation policies, and compliance alignment (e.g., NIST, PCI-DSS, ISO 27001).
* **Technology:** Tooling that collects, processes, and protects enterprise telemetry (SIEM, EDR, SOAR, Firewalls, WAF, Sandbox).

---

## 3. SOC Operational Models
| Model | Description |
| :--- | :--- |
| **In-House / Dedicated** | Internal security team operating on-premise; high visibility and control, but resource-intensive. |
| **Virtual SOC** | Decentralized team operating remotely without a permanent physical facility. |
| **Co-Managed / Hybrid** | Internal staff collaborate alongside an external Managed Security Service Provider (MSSP). |
| **Command / Hierarchical** | A central SOC supervising multiple smaller, regional SOCs across defense or enterprise branches. |

---

## 4. Key SOC Roles & Hierarchy
* **Tier 1 - SOC Analyst (Triage):** Monitors SIEM queues, triages incoming alerts, eliminates false positives, and escalates confirmed threats.
* **Tier 2 - Incident Responder:** Conducts deep-dive investigations, performs root-cause analysis, and applies active containment/remediation steps.
* **Tier 3 - Threat Hunter:** Proactively searches for stealth threats, APTs, and vulnerabilities that bypass automated detections.
* **Security Engineer:** Builds, deploys, tunes detection rules, and manages SOC infrastructure (SIEM/SOAR/EDR integrations).
* **SOC Manager:** Directs operations, strategy, budgets, tooling, metric reporting (MTTD/MTTR), and team management.

---

## 5. Core Defensive Technologies
* **SIEM (Security Information & Event Management):** Centralizes log aggregation, correlation, parsing, and real-time rule-based alert triggering.
* **Log Management:** Stores and organizes system, authentication, network, and firewall logs for retroactive searches and auditing.
* **EDR (Endpoint Detection & Response):** Provides endpoint telemetry, process tree execution tracking, network connections, file integrity monitoring, and host isolation capabilities.
* **SOAR (Security Orchestration, Automation, & Response):** Executes automated playbooks to streamline repetitive tasks (e.g., automated IP reputation checks, account lockouts).
* **Threat Intelligence Feeds (CTI):** Ingests known malicious indicators (IPs, hashes, domains) to enrich alert contexts.

---

## 6. Daily SOC Workflow (Alert Lifecycle)
1. **Detection:** An alert triggers in the SIEM based on rule correlation.
2. **Ownership:** The Tier 1 Analyst assigns/takes ownership of the ticket to prevent duplicate handling.
3. **Triaging & Verification:**
   * Review source/destination IP, hostnames, user accounts, and process hashes.
   * Query Log Management and EDR for parent-child process anomalies.
   * Check reputation via Cyber Threat Intelligence (CTI) tools (VirusTotal, AbuseIPDB).
4. **Classification:**
   * **False Positive (FP):** Benign activity misidentified as malicious; closed with notes and tuning feedback.
   * **True Positive (TP):** Legitimate malicious activity confirmed.
5. **Containment & Remediation:** Isolate host from network, kill malicious processes, block IPs/domains at firewall, reset compromised credentials.
6. **Post-Incident & Documentation:** Record investigation artifacts, identify root cause, and document findings in the case report.

---

## 7. Common Pitfalls to Avoid
* Relying exclusively on sandbox scores without dynamic behavioral verification (malware may be sandbox-aware).
* Investigating an alert in isolation without checking whether other endpoints communicated with the same C2 indicators.
* Treating historical threat intelligence as static (reputation changes as IPs/domains are repurposed).

<a href="https://www.youtube.com/watch?v=RfjvpHFLYSw"> <img src="https://img.shields.io/badge/-Youtube-CD201F?&style=for-the-badge&logo=youtube&logoColor=white" /></a>
