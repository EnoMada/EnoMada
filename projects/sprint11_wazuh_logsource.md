# PowerShell Log Source Integration with Wazuh

[Back to projects](../projects.md) | [Profile](../README.md)

![Type](https://img.shields.io/badge/type-guided%20lab-1F4E79)
![Status](https://img.shields.io/badge/status-completed-0B6E69)
![Evidence](https://img.shields.io/badge/evidence-E1-F2A900)

## Snapshot

| Field | Detail |
|---|---|
| Domain | Detection engineering |
| Environment | Lab / guided training environment |
| Role signal | SOC analyst, detection engineering, security automation |
| Core tools | Wazuh, PowerShell logging, Windows Event logging, ATT&CK, Atomic Red Team |
| Migration target | `security-detection-engineering-lab/cases/powershell-wazuh-log-integration/` |

## What This Demonstrates

- Planning a Windows telemetry source for SIEM ingestion.
- Separating PowerShell Operational telemetry from Windows Security auditing.
- Thinking through ATT&CK-aligned validation instead of treating rules as decoration.
- Documenting limitations that should be fixed before the case is promoted.

## Case Summary

This lab configured PowerShell Operational logging, documented Wazuh ingestion concepts, and used controlled Atomic Red Team simulations as detection-validation inputs.

The strongest part of the case is the workflow: identify the telemetry source, route it into the SIEM, test visibility with known behaviors, and document what still needs correction.

## Evidence and Limitations

| Available Now | Still Needed |
|---|---|
| Narrative case study | Sanitized Wazuh rule excerpts |
| Tooling and telemetry map | Example event records |
| Validation concept | Corrected Event 4688 handling |
| ATT&CK testing intent | Command validation before E3 promotion |

## Integrity Notes

- Event 4103 and 4104 belong to PowerShell Operational logging.
- Event 4688 belongs to Windows Security auditing and requires separate prerequisites.
- The public case should not imply production deployment.

## Related Work

- [Credential Attack Triage and Response](Brute_force_detection.md)
- [Cerber Ransomware Triage and Forensic Correlation](cerber_ransomware_triage.md)
- [Project Portfolio](../projects.md)
