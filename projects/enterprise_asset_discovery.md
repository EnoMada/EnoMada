# 🔒 Enterprise Asset Discovery & CMDB Implementation for MegaQuagga

## 📌 Overview

This project focused on **enhancing network visibility and security monitoring** for **MegaQuagga Publishing's IT Security Team**. Using **Nmap, PowerShell scripting, and LDAP queries**, I conducted comprehensive asset discovery, identifying **over 30 critical network devices** including firewalls, web servers, databases, and workstations. The detailed findings were documented and integrated into **iTop CMDB**, centralizing asset management to significantly enhance SOC monitoring capabilities and proactively manage the company's security posture.

> **Email from MegaQuagga IT Security Team:**  
> *"We need a thorough understanding of our network assets and a reliable system for tracking them in our CMDB. Please perform an extensive asset enumeration and integrate the results into our iTop CMDB for better security visibility and monitoring."*

---

## 🛠️ Key Skills Demonstrated

| **Category**                    | **Tools & Techniques**                  | **SOC Relevance**                         |
|---------------------------------|-----------------------------------------|-------------------------------------------|
| **Network Scanning**            | Nmap, Zenmap, PowerShell                | Asset Discovery & Security Auditing       |
| **Asset Classification**        | CMDB Integration, LDAP Queries          | Threat Surface Analysis & Monitoring      |
| **Enterprise Security Monitoring** | iTop CMDB, SIEM Integration             | Incident Response Readiness               |
| **Threat Reduction Strategies** | Identification of Unauthorized Devices  | Attack Surface Minimization               |

---

## 🚀 Walkthrough

### **1️⃣ Network Scanning & Asset Enumeration**

#### **Scenario**
- IT Security Team at MegaQuagga requested comprehensive asset discovery to address concerns around incomplete asset inventories leading to increased security risks.

#### **Analysis**
- Performed extensive **Nmap network scans** to detect active IP addresses, open ports, and running services.
- Leveraged **PowerShell and LDAP queries** to enumerate authenticated assets from Active Directory.
- Utilized **device fingerprinting** techniques to classify discovered assets such as firewalls, web servers, database servers, and user endpoints.

```bash
# Nmap scan example
nmap -sV -T4 -A 10.10.20.0/24
# Expected Output: Comprehensive list of active hosts and detailed service information
```

---

### **2️⃣ Asset Classification & Security Mapping**

#### **Asset Categorization**
- Compiled the identified assets into a structured spreadsheet, providing clear visibility for ongoing security monitoring.
- Highlighted anomalies including unauthorized or incorrectly configured devices.

#### **Before vs After Asset Tracking**

| **Metric**                    | **Pre-Implementation**          | **Post-Implementation**           |
|-------------------------------|---------------------------------|-----------------------------------|
| Untracked Assets              | High (incomplete records)       | Low (centralized, complete records) |
| CMDB Data Accuracy            | Partial                          | Comprehensive and verified        |
| Security Monitoring Readiness | Limited visibility               | Enhanced threat detection         |

---

### **3️⃣ CMDB Integration & Threat Surface Reduction**

#### **CMDB Implementation**
- Imported and structured asset data within **iTop CMDB**, creating a robust and retrievable asset management system.
- Aligned assets with **security policies, alerting rules, and network segmentation** for improved threat detection and response.

```powershell
# PowerShell query for asset enumeration from AD
Get-ADComputer -Filter * -Properties Name,OperatingSystem,IPv4Address
```

#### **Security Improvements**
- Identified and mitigated previously unmonitored rogue devices.
- Enhanced proactive monitoring capabilities through structured CMDB integration.
- Improved overall risk management and asset visibility.

---

## 🔍 Technical Artifacts

```plaintext
Enterprise-Asset-Discovery-MegaQuagga/
├── asset-enumeration.xlsx         # Comprehensive asset list and classification
├── nmap-scan-results/             # Raw Nmap outputs
│   ├── full-network-scan.xml      # Detailed scan logs in XML
│   ├── parsed-asset-list.txt      # Extracted and parsed asset data
├── cmdb-integration-guide.pdf     # iTop CMDB configuration documentation
└── unauthorized-devices-report.pdf # Report highlighting unauthorized devices
```

---

## 🌟 Lessons Learned

### 🔐 Centralized Asset Management Strengthens Security
- A comprehensive CMDB significantly streamlines and enhances incident response effectiveness.

### 💡 Increased Visibility Proactively Reduces Threats
- Regular asset discovery initiatives are crucial for early detection of unauthorized devices.

### 📜 Automation Optimizes Asset Enumeration
- PowerShell scripting and automated queries substantially expedite repetitive asset management tasks.

---

## 🎯 SOC Role Preparation

✅ **Enterprise Asset Management** – Enhanced methodologies for maintaining accurate asset inventories.  
✅ **Proactive Threat Mitigation** – Identified unauthorized assets for prompt security intervention.  
✅ **CMDB & Policy Integration** – Integrated findings into ongoing SOC operational frameworks.  
✅ **Technical Proficiency** – Developed hands-on experience with critical SOC tools including Nmap, PowerShell, and LDAP.

---

## 🔗 Related Projects

1. [MegaQuagga Penetration Test](projects/MegaQuagga_pentesting_report_preparation.md)  
2. [Vulnerability Remediation for MegaQuagga](projects/Vulnerability%20Remediation%20for%20MegaQuagga.md)  
3. 

---

## ⬇️ **Clone Repository**

```bash
git clone https://github.com/yourusername/enterprise-asset-discovery-megaquagga.git
```

---
