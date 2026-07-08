# Cerber Ransomware Triage and Forensic Correlation

[Back to projects](../projects.md) | [Profile](../README.md)

![Type](https://img.shields.io/badge/type-guided%20lab-1F4E79)
![Status](https://img.shields.io/badge/status-completed-0B6E69)
![Evidence](https://img.shields.io/badge/evidence-E2-0B6E69)

## Snapshot

| Field | Detail |
|---|---|
| Domain | Incident response / DFIR |
| Environment | Ransomware investigation scenario |
| Role signal | DFIR, SOC analyst, threat hunting |
| Core tools | Splunk, Sysmon, CyberChef, OSINT, incident reporting |
| Migration target | `incident-response-casebook/cases/cerber-ransomware-investigation/` |

## What This Demonstrates

- Correlating endpoint and network telemetry during a ransomware investigation.
- Building an investigation timeline from multiple evidence sources.
- Separating confirmed, suspected, and unconfirmed findings.
- Translating technical findings into response recommendations.

## Case Summary

This guided lab focused on ransomware triage and forensic correlation. The work documents indicators, timeline construction, ATT&CK mapping, and response thinking in a controlled investigation scenario.

## Evidence and Limitations

| Available Now | Still Needed |
|---|---|
| Narrative case study | Sanitized query appendix |
| External report and notes references in source material | Reconciled ATT&CK mapping |
| Timeline and indicator analysis | Confirmed vs suspected activity table |
| OSINT and decoding workflow | Clear lateral-movement conclusion |

## Integrity Notes

- ATT&CK techniques should be mapped only where the evidence supports them.
- SMB spread and lateral movement language must be reconciled before promotion.
- This remains a guided lab until independently reproducible evidence is published.

## Related Work

- [Credential Attack Triage and Response](Brute_force_detection.md)
- [PowerShell Log Source Integration with Wazuh](sprint11_wazuh_logsource.md)
- [Project Portfolio](../projects.md)
