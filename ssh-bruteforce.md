# SSH Brute-Force Detection

## Objective

Detect repeated failed SSH authentication attempts and support automated incident response.

## Detection Technology

- SIEM: Wazuh
- Endpoint: Ubuntu Linux
- Testing machine: Kali Linux
- Detection rule: 5763
- Response: firewall-drop

## Detection Logic

Wazuh uses its SSH authentication rules to identify repeated failed login attempts.

In this lab, rule ID 5763 was used to detect repeated authentication failures.

## Detection Workflow

1. Generate authorized failed SSH login attempts.
2. Ubuntu records authentication events.
3. Wazuh agent collects the authentication logs.
4. Wazuh manager evaluates the events.
5. Matching security activity generates an alert.
6. Configured Active Response executes firewall-drop.

## Automated Response

The Active Response configuration uses:

- Command: firewall-drop
- Trigger rule: 5763
- Location: local
- Timeout: 180 seconds

## Investigation

The analyst should review:

- Source IP address
- Authentication failure events
- Alert timestamp
- Rule ID and severity
- Active Response event

## Expected Outcome

Repeated SSH authentication failures are detected and the configured response blocks the matching source IP for the configured timeout.

## Security Note

All testing must be performed in an authorized isolated lab.
