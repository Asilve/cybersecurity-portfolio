# SOC Investigations

This directory contains practical security investigations and homelab exercises designed to simulate the work of a Security Operations Centre (SOC) analyst.

The investigations are performed within a personal Windows and Splunk homelab and focus on understanding security telemetry, analysing events, developing investigative workflows, validating findings and documenting conclusions.

Each investigation may include:

- Objective
- Lab environment
- Action performed
- Evidence collected
- SPL queries
- Key observations
- Analyst assessment
- Potential security implications
- MITRE ATT&CK mapping (where appropriate)
- Possible mitigations
- Lessons learned

## Topics Covered

### Technologies

- Windows Event Logs
- Windows Firewall Logs
- Sysmon
- Splunk
- Wireshark

### Investigation Areas

- Authentication events
- Account management
- Process creation
- Network activity

### SOC Skills

- Log analysis
- SIEM investigation
- Timeline reconstruction
- Threat hunting concepts
- Detection engineering concepts
- Incident response concepts
- Evidence-based reporting

## Scenarios

Scenarios combine multiple log sources and investigation steps to simulate more realistic SOC analyst workflows.

| # | Scenario | Focus | Status |
|---|---|---|---|
| 01 | Suspected Password Spraying followed by Privilege Escalation and Persistence | Password spraying, privilege escalation, account creation, persistence | Complete |
| 02 | Remote Discovery and Authentication Chain | Network discovery, port scanning, SMB authentication, Windows Security logs, firewall logs | Planned |

## Investigations

Investigations focus on individual event types and behaviours to understand what activity generates which logs, and what those logs can tell an analyst.

| # | Investigation | Focus | Status |
|---|---|---|---|
| 01 | Windows Authentication Investigation | Successful logons, failed logons and logon types | Complete |
| 02 | Windows Account Management Investigation | User creation, account changes and local group membership | Complete |
| 03 | Remote Discovery Investigation | Ping, Nmap scanning, firewall logs, packet visibility | Planned |
| 04 | Remote Authentication Investigation | SMB authentication attempts, Logon Type 3, source network address analysis | Planned |

#### _Architecture documentation can be found in the Architecture directory._