# 🛡️Credential Stuffing Triage & Response

**File Name:** `sprint12_brute_force_detection.md`  
**Analyst:** Kyle Gill  
**Date Completed:** April 11, 2025  
**Source:** ModSecurity v3.0.9 (Linux) – WAF on Apache/2.4.58  
**Alert ID:** ZgUGhV1CEwAABx43AYAAAAAB  
**Severity:** CRITICAL  
**Disposition:** Escalated (True Positive)

---

## 📌 Project Summary

This project documents the investigation and response to a credential stuffing and brute-force login attack targeting a WordPress 6.7.2 instance. The incident was detected by ModSecurity and enriched using Wireshark PCAPs, Splunk telemetry, and MITRE ATT&CK mapping. The attacker successfully authenticated into both a standard and an administrative account, using the Hydra tool to automate login attempts.

---

## 🔍 Initial Findings

- **Incident Type:** Credential Stuffing / Brute-Force Attack  
- **Scope:** One internal web server (WordPress), one malicious host, two compromised accounts  
- **Disposition Justification:** Confirmed valid logins using credentials exposed in packet captures  
- **Severity Justification:** Privileged access gained; automated tooling suggests high attacker intent and risk

---

## 🧠 Incident Summary

**Timeframe:**  
- Start: 2025-04-10 15:42:22 UTC  
- End: 2025-04-10 15:48:41 UTC  
- Duration: 6 minutes, 19 seconds  

**Key Events:**  
- 15:42:22 – Attack initiated via POSTs to `/wp-login.php`  
- 15:42:28 to 15:42:56 – Four successful logins using `elliot` credentials  
- 15:48:41 – Final successful login using `admin` account  

**Scope of Compromise:**  
- Target IP: `192.168.100.2`  
- Source IP: `192.168.100.20`  
- Accounts: `elliot` (standard), `admin` (privileged)  
- Web application: WordPress 6.7.2 (public-facing)

**Impact Assessment:**  
No immediate service disruption or exfiltration observed, but administrative access provides potential for plugin modification, web shell deployment, or data manipulation.

---

## 🧬 MITRE ATT&CK Techniques

- **T1110.001 – Brute Force: Password Guessing**  
  - Hydra-based POST login attempts to `/wp-login.php`
- **T1078 – Valid Accounts**  
  - Use of real credentials to gain access to the application

---

## 🛰️ Threat Intelligence Indicators

| Indicator Type        | Value                  |
|------------------------|------------------------|
| Source IP              | 192.168.100.20         |
| Target IP              | 192.168.100.2          |
| User-Agent             | `Mozilla/5.0 Hydra`    |
| Target URI             | `/wp-login.php`        |
| WAF Rules Triggered    | 950120, 911100         |

The user-agent is consistent with Hydra brute-force tooling. No external command-and-control (C2) traffic or threat actor attribution was confirmed.

---

## 🔧 Recommended Actions

### 1. IR Actions
- Reset `admin` and `elliot` account passwords
- Invalidate all active sessions
- Forensically review WordPress host (192.168.100.2)
- Investigate source IP (192.168.100.20) for unauthorized tool use
- Notify web app owner and escalate if necessary

### 2. Infrastructure Hardening
- Enable login attempt lockout on WordPress
- Implement CAPTCHA or reCAPTCHA on login
- Enforce multi-factor authentication (MFA)
- Obfuscate `/wp-login.php` endpoint
- Update WordPress and plugins to latest versions

### 3. Policy Improvements
- Clarify internal use policies regarding security tools (Hydra)
- Strengthen admin account controls with enforced MFA
- Deliver awareness training on brute-force and credential reuse risks

### 4. Detection Enhancements
- Correlate failed + successful logins by IP in SIEM  
- Flag user-agents resembling automation tools (e.g., Hydra)  
- Include WAF rule metadata in alert context  
- Update SOC SOPs for credential stuffing response and triage  

---

## 📁 Supporting Artifacts

- [`Google Docs IR Triage Report`](https://docs.google.com/document/d/1ayrAvYhJQV9mZYxLm6CVuMH9ZgV5qs_WIFTAZUVs3eA/edit?tab=t.0#heading=h.o95rl4iy9z4x)
- [`attack1.pcap`](https://practicum-content.s3.us-west-1.amazonaws.com/CSA/sprint12/attack1.pcap)  
- [`attack2.pcap`](https://practicum-content.s3.us-west-1.amazonaws.com/CSA/sprint12/attack2.pcap)  
- [`Google Docs IR Report`](https://docs.google.com/document/d/10xZAB_gdc3JE2a9zTYfHE7B2ylMHdZ1I2bM8zEa4aUU/edit?usp=sharing)  
- [`Splunk Query Screenshot`](https://practicum-content.s3.us-west-1.amazonaws.com/resources/Wireshark_-_attack1_-_Conversations_http_annotated_1747229483.png)

---

## 💡 Lessons Learned

This project demonstrated the importance of **multi-source correlation** across WAF alerts, packet captures, and SIEM telemetry. Leveraging Wireshark and Splunk, I was able to trace valid login events, build a precise attack timeline, and recommend actionable remediations. It reinforced how proper triage and pivoting transforms alerts into intelligence.

---

## 🧭 Keywords

`credential stuffing`, `hydra`, `brute force`, `ModSecurity`, `WordPress`, `Splunk`, `Wireshark`, `incident response`, `MITRE ATT&CK`, `cybersecurity triage`

