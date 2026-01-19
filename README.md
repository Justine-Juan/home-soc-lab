# Home SOC Lab – Windows Log Collection & Alert Investigation

## Project Overview
This lab demonstrates a **hands-on SOC workflow** using Wazuh to monitor a Windows endpoint. It includes:

- Installing and configuring the Wazuh agent on a Windows VM
- Collecting Windows security logs (authentication failures, privilege escalation, service creation)
- Generating SOC-relevant alerts in a controlled environment
- Investigating alerts and documenting findings
- Mapping alerts to MITRE ATT&CK techniques

The goal is to simulate a real SOC Level 1 analyst workflow for **incident detection and response**.

---

## Tools & Technologies
- **Wazuh** (SIEM/endpoint monitoring)
- **Windows 11 VM** (endpoint)
- **Ubuntu Server VM** (Wazuh manager)

---

## Architecture
- **Windows VM** → Wazuh agent collects Windows events →  
- **Wazuh Manager** → Processes and rules alerts →  
- **Wazuh Dashboard** → Analysts review alerts, investigate, and respond


---

## Lab Activities & Alerts

| Activity | Event ID | MITRE Technique | Description |
|----------|---------|----------------|------------|
| Failed Login Attempts | 4625 | T1110 – Brute Force | Multiple failed login attempts generated on Windows endpoint |
| Privilege Escalation | 4732 | T1098 – Account Manipulation | Test user added to Administrators group |
| Service Creation | 7045 | T1543.003 – Windows Service | Test service created to simulate persistence |

---

## Incident Reports
Detailed investigations for each activity are documented in the `incident-reports` folder:

1. [IR-001-Failed-Login.md](incident-reports/IR-001-Failed-Login.md) – Authentication failure investigation  
2. [IR-002-Service-Creation.md](incident-reports/IR-002-Service-Creation.md) – Service creation investigation  
3. [IR-003-Privilege-Escalation.md](incident-reports/IR-003-Privilege-Escalation.md) – Privilege escalation investigation  

Each report includes:

- Alert details (Event ID, host, timestamp)
- Investigation steps
- Impact assessment
- Response actions
- Lessons learned

---

## Dashboard & Screenshots
Screenshots of the SOC environment are stored in [Screenshots](screenshots/):

- Alerts table showing failed logins, service creation, and privilege escalation  

---

## Lab Setup

These allow reproducibility of the lab.

---

## Learning Outcomes
- Understand Wazuh agent deployment and management  
- Collect and analyze Windows security events  
- Perform incident investigation and reporting  
- Map alerts to MITRE ATT&CK techniques  
- Demonstrate a full SOC workflow from alert generation to response

---

## Optional Extensions
- Integrate Linux endpoints and monitor SSH logins  
- Enable Sysmon for advanced Windows event monitoring  
- Add role-based users (read-only SOC analysts)  
- Expand incident reports with timeline analysis
