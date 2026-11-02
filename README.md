# Wazuh SIEM Integration with Suricata IDS
### Automated Threat Detection & Incident Response

A hands-on Security Operations Center (SOC) lab integrating **Wazuh SIEM** with **Suricata IDS** to monitor security events, detect suspicious network activity, investigate threats, and automate incident response.

## Project Overview

This project demonstrates how SIEM and IDS technologies work together in a SOC environment. Suricata generates network security events, while Wazuh collects and analyzes security logs to support threat detection, monitoring, and response.

## Architecture

```mermaid
flowchart TD
    A[Kali Linux - Attack Simulation] --> B[Network Traffic]
    B --> C[Suricata IDS]
    C --> D[EVE JSON Logs]
    D --> E[Wazuh Agent]
    E --> F[Wazuh Manager]
    F --> G[Wazuh Indexer]
    G --> H[Wazuh Dashboard]
    F --> I[Active Response]
    I --> J[Firewall IP Blocking]
```
## Project Screenshots

### 1. Project Overview
![Project Overview](screenshots/project-overview.png)

### 2. SOC Monitoring Dashboard
![SOC Monitoring](screenshots/soc-monitoring.png)

### 3. Threat Detection
![Threat Detection](screenshots/threat-detection.png)

### 4. Threat Hunting
![Threat Hunting](screenshots/threat-hunting.png)

### 5. Wazuh Dashboard
![Wazuh Dashboard](screenshots/wazuh-dashboard.png)
## Lab Environment

| Component | Purpose |
|---|---|
| Kali Linux | Controlled attack simulation |
| Ubuntu Linux | Suricata monitoring sensor |
| Suricata IDS | Network threat detection |
| Wazuh SIEM | Centralized security monitoring |
| Docker | Wazuh deployment |
| iptables | Firewall-based response |
| VMware | Virtual lab environment |

## Key Features & Implementation

### 1. SIEM and IDS Integration
- Integrated Suricata with Wazuh for centralized security monitoring.
- Configured Suricata EVE JSON log collection.
- Monitored network security events through the Wazuh dashboard.

### 2. SSH Brute-Force Detection
- Configured SSH authentication monitoring.
- Used Wazuh rule 5763 to detect repeated failed SSH login attempts.
- Analyzed suspicious authentication activity.

### 3. Automated Incident Response
- Configured Wazuh Active Response using `firewall-drop`.
- Implemented automatic source IP blocking for matching SSH brute-force alerts.
- Configured a 180-second response timeout.

### 4. File Integrity Monitoring (FIM)
- Monitored files and directories for unauthorized changes.
- Detected file modifications and deletions.
- Reviewed integrity alerts through Wazuh.

### 5. Vulnerability Detection
- Enabled Wazuh Vulnerability Detection.
- Collected endpoint inventory information.
- Monitored vulnerability findings for connected systems.

## Tools & Technologies

- **SIEM:** Wazuh
- **IDS:** Suricata
- **Operating Systems:** Ubuntu, Kali Linux
- **Containerization:** Docker
- **Firewall:** iptables
- **Virtualization:** VMware
- **Log Format:** EVE JSON

## Project Outcomes

- Established centralized security monitoring.
- Detected suspicious SSH authentication activity.
- Implemented automated firewall blocking through Active Response.
- Monitored file integrity changes.
- Enabled vulnerability monitoring for endpoints.

## Repository Contents

- `screenshots/` – Project dashboards and implementation evidence.
- `README.md` – Project overview, architecture, and documentation.

## Learning Outcomes

- Practical understanding of SIEM and IDS integration.
- Security event monitoring and alert investigation.
- SSH brute-force detection.
- Automated incident response.
- File Integrity Monitoring and vulnerability management.

## Disclaimer

This project was developed for educational purposes in an isolated virtual lab. All security testing was performed on systems under my control or with authorization.

## Author

**Bhupender Dhankhar**

Cybersecurity Student | Aspiring SOC Analyst

[LinkedIn](https://www.linkedin.com/in/bhupender-dhankhar-41299a351)
