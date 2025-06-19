# 🧪 Ransomware Triage & Forensic Correlation Report

> **Status:** 🟢 Completed  
> **Duration:** 2025-06-10 to 2025-06-17  
> **Tools Used:** Splunk, CyberChef, VirusTotal, WHOIS Lookup, Robtex, OSINT platforms  
> **MITRE ATT&CK Coverage:** T1110.001, T1059.005, T1071.001, T1566.001, T1027  
> **Category:** Incident Response & Threat Intelligence

---

## 📎 Project Materials  
- 📝 [IR Triage Report (Google Doc)](https://docs.google.com/document/d/1Xb8Ft57e7fKdxcfun9_eTqZqBJ64GtaxBhSNBrIs9nE/edit?tab=t.0#heading=h.o95rl4iy9z4x)  
- 🔍 [Investigation Notes (Google Doc)](https://docs.google.com/document/d/1FwzT01-jFsZvm0ukrA5fmAOqaFTqVnHqtq88SSZzYpM/edit?tab=t.xxz5fu5xi7zn#heading=h.gsqa31rk4z5z)

---

## 🎯 Executive Summary
This project showcases a full incident response investigation involving a suspected Cerber ransomware infection. I conducted forensic triage on a single compromised host by correlating endpoint and network telemetry, tracing the attack from script-based execution through steganographic payload delivery, and enriching my findings with OSINT techniques. The culmination was a professionally written IR Triage Report and timeline-based investigation notes.

---

## 🔍 **Objective**
To identify and analyze the scope, origin, and techniques of a ransomware infection originating from a suspicious VBScript and determine the related indicators of compromise using SIEM telemetry and open-source intelligence.

---

## 📌 **Investigation Scope**
- **Affected Host:** `we8105desk`
- **Suspected Ransomware:** Cerber
- **Initial Vector:** Malicious VBScript
- **Execution Chain:** VBScript > HTTP Image Download > Steganography Payload > SMB Spread

---

## 🧰 **Tools & Techniques Used**
- **SIEM Analysis:** Splunk (`index=client1`)
- **Log Sources:**
  - `stream:http`
  - `stream:smb`
  - `WinRegistry`
  - `Microsoft-Windows-Sysmon/Operational`
- **Data Enrichment & OSINT:**
  - WHOIS
  - VirusTotal
  - Robtex
  - CyberChef (hex decoding)
- **Threat Framework:** MITRE ATT&CK

---

## 🧠 **Key Findings**
- Confirmed VBScript executed via `wscript.exe` from `%APPDATA%\\scripts\\foo.vbs`
- Shortly after, observed outbound HTTP GET to: `solidaritedeproximite[.]org/mhtr.jpg`
- Image file `mhtr.jpg` identified as steganographic loader for ransomware payload
- Corroborated with registry evidence of mounted network shares
- Hex string in WHOIS entry decoded via CyberChef revealed message: _"lasciate ogni speranza, voi ch'intrate"_

---

## ⏱️ **Timeline of Key Events (UTC)**
- `2025-04-14 11:04:32` – User executes malicious VBScript via `wscript.exe`
- `2025-04-14 11:04:42` – Outbound connection to `solidaritedeproximite[.]org` to retrieve `mhtr.jpg`
- `2025-04-14 11:05:01` – Multiple SMB connections initiated to internal file servers
- `2025-04-14 11:06:17` – Registry entry confirms file share mount

---

## 🧱 **MITRE ATT&CK Techniques Identified**
- **T1059.005:** Command and Scripting Interpreter: VBScript
- **T1027:** Obfuscated Files or Information (via steganography in `mhtr.jpg`)
- **T1105:** Ingress Tool Transfer (image-based download cradle)
- **T1071.001:** Application Layer Protocol: Web Protocols (HTTP C2 communication)
- **T1077:** Windows Admin Shares (network propagation)

---

## 🧠 **Threat Intelligence & IOCs**
- **Domain:** `solidaritedeproximite[.]org`
- **IP Address:** `23.22.63.114`
- **Filename:** `mhtr.jpg`
- **WHOIS Hex Message:** "lasciate ogni speranza, voi ch'intrate"

---

## ✅ **Outcome**
- Investigation confirmed as **true positive** ransomware activity
- Single endpoint infected, no lateral movement observed beyond initial SMB scanning
- Root cause traced to script-based download cradle and steganographic payload delivery

---

## 🔁 **Recommended Actions**
- **IR Response:**
  - Isolate `we8105desk`
  - Preserve memory and disk for forensics
- **Infrastructure Prevention:**
  - Enable PowerShell Constrained Language Mode
  - Block access to known malicious IPs and domains
- **Policy Improvements:**
  - Roll out anti-phishing simulation training
- **Detection Enhancements:**
  - Tune alerting for steganographic image payloads
  - Add correlation rules between VBScript exec + image GET requests

---

> _"Good analysis doesn’t just report what happened — it transforms alerts into answers."_
