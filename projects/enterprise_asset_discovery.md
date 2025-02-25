# 🔒 Enterprise Asset Discovery & CMDB Implementation  

## 📌 Overview  

This project focused on **enhancing network visibility and security monitoring** for an enterprise IT security team. Using **Nmap, PowerShell, and LDAP queries**, I conducted a **comprehensive asset discovery**, identifying over **40 critical devices** including honeypots, firewalls, servers, and workstations. The results were documented and integrated into **iTop CMDB**, centralizing asset management for improved SOC monitoring and risk reduction.  

> **Email from IT Security Team:**  
> *"We need to improve our network visibility and ensure all assets are properly tracked in our CMDB. Please conduct a thorough asset discovery and help us integrate the findings into iTop for better security monitoring."*  
---

## 🛠️ Key Skills Demonstrated  

| **Category**                  | **Tools & Techniques**             | **SOC Relevance**                     |
|--------------------------------|----------------------------------|--------------------------------------|
| **Network Scanning**           | Nmap, Zenmap, PowerShell Scripting | Asset Discovery & Security Auditing  |
| **Asset Classification**       | CMDB Integration, LDAP Queries   | Threat Surface Analysis & Monitoring |
| **Enterprise Security Monitoring** | iTop CMDB, SIEM Integration   | Incident Response Readiness         |
| **Threat Reduction Strategies** | Unauthorized Asset Identification | Attack Surface Minimization        |

---

## 🚀 Walkthrough  

### **1️⃣ Network Scanning & Asset Enumeration**  

#### **Scenario**  
- IT Security Team requested an enterprise-wide **asset discovery initiative** to improve **security visibility**.  
- Initial assessments indicated **incomplete asset tracking**, increasing risk exposure.  

#### **Analysis**  
- Conducted **Nmap network scans** to **identify active IPs, open ports, and running services**.  
- Used **PowerShell & LDAP queries** to retrieve **authenticated network assets** from Active Directory.  
- Extracted **device fingerprints** to classify systems into **honeypots, firewalls, workstations, servers, and switches**.  

```bash
# Sample Nmap scan command for asset discovery
nmap -sP 192.168.1.0/24
# Expected Output: List of active hosts on the subnet
```

---

### **2️⃣ Asset Classification & Security Mapping**  

#### **Asset Categorization**  
- **Organized discovered assets** into a structured **spreadsheet** for tracking and analysis.  
- **Identified anomalies** such as **unauthorized or misconfigured devices**.  

#### **Before vs After Asset Tracking Implementation**  

| **Metric**                     | **Pre-Implementation**        | **Post-Implementation**       |
|--------------------------------|-----------------------------|------------------------------|
| Number of Untracked Assets     | High (Inconsistent Records) | Low (Centralized Tracking)  |
| CMDB Accuracy & Completeness   | Partial Data Available      | Full Asset Integration      |
| Security Monitoring Readiness  | Limited Network Visibility  | Enhanced Threat Detection   |

---

### **3️⃣ CMDB Integration & Threat Surface Reduction**  

#### **CMDB Implementation**  
- Imported **asset details into iTop CMDB**, ensuring **structured and retrievable asset records**.  
- Mapped devices to **security policies, monitoring alerts, and network segmentation strategies**.  

```bash
# Sample PowerShell query to retrieve Active Directory assets
Get-ADComputer -Filter * -Property Name,OperatingSystem,IPv4Address
```

#### **Security Improvements**  
- **Identified rogue devices** that were previously unmonitored.  
- **Enabled proactive threat monitoring** by integrating CMDB with **SOC operations**.  
- **Optimized risk management** through improved **asset visibility**.  

---

## 🔍 Technical Artifacts  

```plaintext
Enterprise-Asset-Discovery/
├── asset-enumeration.xlsx      # Documented Asset List & Classification  
├── nmap-scan-results/          # Raw Nmap Scan Outputs  
│   ├── full-network-scan.xml   # XML format scan logs  
│   ├── parsed-asset-list.txt   # Extracted device information  
├── cmdb-integration-guide.pdf  # Configuration & Asset Mapping in iTop  
└── unauthorized-devices-report.pdf # Identified rogue assets for remediation  
```

---

## 🌟 Lessons Learned  

### 🔐 **Centralized Asset Tracking Enhances Security**  
- Maintaining a **well-structured CMDB** improves **incident response efficiency**.  

### 💡 **Network Visibility is Key to Threat Reduction**  
- **Regular asset discovery** helps **detect unauthorized devices** before they become security risks.  

### 📜 **Automation Improves Asset Management**  
- **PowerShell scripting** can streamline **repetitive enumeration tasks** for **large-scale enterprise networks**.  

---

## 🎯 SOC Role Preparation  

✅ **Enterprise Asset Discovery** – Strengthened asset tracking methodologies.  
✅ **Threat Detection & Response** – Identified unauthorized assets for **security remediation**.  
✅ **Security Policy & CMDB Management** – Integrated findings into **enterprise security monitoring**.  
✅ **Network Scanning & Analysis** – Hands-on experience with **Nmap, PowerShell, and LDAP queries**.  

---

## 🔗 Related Projects  

1. [SIEM Log Analysis & Threat Detection](#)  
2. [Firewall Rule Optimization & Security Hardening](#)  
3. [Zero Trust Network Segmentation](#)  

---

## ⬇️ **Clone Repository**  

```bash
git clone https://github.com/yourusername/enterprise-asset-discovery.git
```

---
