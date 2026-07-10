# Architecture

This directory contains the SOC home lab architecture, including diagrams documenting the evolution of the SOC home lab.

## Current Architecture

![alt text](./diagrams/Architecture-v1.png)


#### Windows 10 Virtual Machine (WIN10-01)
- Sysmon
- Windows Event Logs
- Splunk Universal Forwarder
- Splunk Enterprise

### Purpose

The current environment provides a controlled Windows endpoint for generating and investigating security telemetry using Splunk.

The lab is used to simulate and investigate:

- Authentication events
- Account management events
- Privilege escalation
- Windows event log analysis
- SIEM investigations

Future additions may include:

- Kali Linux
- Wazuh
- pfSense
- Internal networking
- Additional Windows endpoints

## Sysmon Parsing Fix

Sysmon logs were initially ingested into Splunk as raw XML, which made investigation difficult. The Splunk Add-on for Sysmon was installed and the Sysmon input was updated to use the correct XML Windows Event Log sourcetype. This enabled useful field extraction for Sysmon events, including CommandLine, Image, ParentImage and User.

This improvement makes future process creation investigations much easier, especially for PowerShell, scheduled task activity, command-line execution and parent-child process analysis.

### Versions
- Version 1.0 (June 2026)
  - Windows 10 endpoint
  - Sysmon
  - Windows Event Logs
  - Splunk Universal Forwarder
  - Splunk Enterprise
