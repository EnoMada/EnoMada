# Credential Attack Triage and Response

[Back to projects](../projects.md) | [Profile](../README.md)

![Type](https://img.shields.io/badge/type-guided%20lab-1F4E79)
![Status](https://img.shields.io/badge/status-completed-0B6E69)
![Evidence](https://img.shields.io/badge/evidence-E2-0B6E69)

## Snapshot

| Field | Detail |
|---|---|
| Domain | Incident response |
| Environment | Simulated WordPress / WAF / SIEM investigation |
| Role signal | SOC analyst, incident response, threat hunting |
| Core tools | Splunk, Wireshark, ModSecurity, ATT&CK |
| Migration target | `incident-response-casebook/cases/credential-attack-triage/` |

## What This Demonstrates

- Alert triage from a WAF signal into packet and SIEM evidence.
- Investigation writing that connects timeline, evidence, and response recommendations.
- Use of Splunk pivots and packet review to validate activity.
- Careful distinction between observed authentication and unsupported privilege-escalation claims.

## Case Summary

This guided lab investigated a simulated WordPress login attack using ModSecurity alerts, packet captures, and Splunk telemetry. The public version should frame the work as incident triage in a lab scenario, not as a production compromise response.

## Evidence and Limitations

| Available Now | Still Needed |
|---|---|
| Narrative case study | Sanitized packet excerpts if publication rights permit |
| External report reference in source material | Repository-local evidence appendix |
| Splunk and WAF workflow description | Clear classification between password guessing and credential stuffing |
| Response recommendations | Evidence-backed account impact language |

## Integrity Notes

- Do not describe valid-account authentication as privilege escalation unless a separate escalation path is demonstrated.
- Keep the scenario provenance visible.
- Move durable evidence into the future casebook repository when rights permit.

## Related Work

- [PowerShell Log Source Integration with Wazuh](sprint11_wazuh_logsource.md)
- [Cerber Ransomware Triage and Forensic Correlation](cerber_ransomware_triage.md)
- [Capybara Incident Response Plan Review](IRP_review_capybara_unlimited.md)
