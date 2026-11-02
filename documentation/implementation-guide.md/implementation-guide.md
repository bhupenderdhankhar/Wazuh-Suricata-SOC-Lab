# SOC Lab – Implementation Guide

## 1. Environment Setup

The lab uses multiple virtual machines to simulate a small SOC environment.

| System | Role |
|---|---|
| Ubuntu Server | Wazuh SIEM and monitoring environment |
| Ubuntu Sensor | Suricata IDS and endpoint monitoring |
| Kali Linux | Authorized security testing |
| Windows | Endpoint monitoring |

**Core technologies:** Wazuh, Suricata, Docker, Ubuntu, Kali Linux, VMware and iptables.

## 2. Wazuh Deployment

- Deployed Wazuh using its Docker-based single-node environment.
- Started the Wazuh Manager, Indexer and Dashboard services.
- Accessed the dashboard for centralized security monitoring.
- Connected monitored endpoints using Wazuh agents.

## 3. Suricata IDS Integration

- Installed Suricata on the Ubuntu monitoring sensor.
- Configured Suricata to generate security events in EVE JSON format.
- Configured Wazuh agent log collection for `/var/log/suricata/eve.json`.
- Monitored network security events through the Wazuh dashboard.

## 4. SSH Brute-Force Detection

- Enabled SSH authentication monitoring on the Ubuntu endpoint.
- Used Wazuh rule ID `5763` for repeated failed SSH authentication attempts.
- Generated controlled test activity from Kali Linux.
- Investigated the resulting security alerts.

## 5. Active Response Configuration

- Used the Wazuh `firewall-drop` response command.
- Configured Active Response for matching SSH brute-force alerts.
- Set the response timeout to 180 seconds.
- Reviewed firewall response events in Wazuh.

## 6. File Integrity Monitoring

- Enabled Wazuh Syscheck for file integrity monitoring.
- Monitored selected directories.
- Tested file modification and deletion events.
- Reviewed generated FIM alerts in the dashboard.

## 7. Vulnerability Detection

- Enabled Wazuh Vulnerability Detection.
- Collected endpoint software and operating system inventory.
- Reviewed vulnerability findings through the dashboard.

## 8. Testing and Validation

The lab was tested using controlled security activities:

- SSH authentication failure monitoring.
- Active Response and firewall blocking.
- File modification and deletion monitoring.
- Endpoint vulnerability inventory.
- Suricata security event collection.

## 9. Security Considerations

- Testing was performed in an authorized virtual lab.
- No production systems were targeted.
- Credentials, private keys and sensitive configuration values should not be shared publicly.

## 10. Conclusion

This implementation demonstrates practical SOC skills involving SIEM deployment, IDS integration, security event monitoring, threat detection, automated response, File Integrity Monitoring and vulnerability management.
