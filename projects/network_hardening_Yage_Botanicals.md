# 🔒 Network Modernization for Yagé Botanicals  

## 📌 Overview  

| **Client**              | **Key Objectives**                                      |
|------------------------|--------------------------------------------------------|
| Yagé Botanicals       | - Improve infrastructure for operational efficiency    |
|                        | - Enhance security to attract potential buyers        |
|                        | - Implement cost-effective modernization solutions    |

| **Deliverables**                     | **Tools & Frameworks**                      |
|--------------------------------------|--------------------------------------------|
| Network Modernization Proposal      | VLANs, Security Patching, SNOC Deployment  |
| Cloud Migration Plan                 | Public Cloud Strategy, SaaS MDM Integration |
| Security Policy Documentation        | Endpoint Security, 2FA Implementation     |

---

## 🛠️ Key Skills Demonstrated  

| **Category**                  | **Tools & Techniques**             | **SOC Relevance**                     |
|--------------------------------|----------------------------------|--------------------------------------|
| **Network Hardening**           | VLAN Segmentation, Security Patching | Threat Mitigation & Network Security  |
| **Cloud Migration Planning**    | Public Cloud Strategy, SaaS MDM    | Secure Asset Management & Scalability |
| **Endpoint Security Management** | 2FA, Mobile Device Security        | Access Control & Compliance          |
| **Security Policy Development**  | IT Governance, Policy Writing      | Long-Term Security & Risk Reduction  |

---

## 🚀 Walkthrough  

### **1️⃣ Infrastructure Assessment & Asset Management**  

#### **Scenario**  
- Yagé Botanicals' **outdated network infrastructure** caused **slow internet speeds, unsegmented networks, and security vulnerabilities**.  
- The business needed **cost-effective upgrades** to improve security while remaining attractive to buyers.  

#### **Analysis**  
- Conducted **full hardware and software inventory** using a **CMDB (Configuration Management Database)**.  
- Identified **key risks** from **outdated security patches, lack of segmentation, and inefficient resource usage**.  
- Proposed **cloud migration** for **scalability and improved security controls**.  

```bash
# Sample Nmap scan to detect outdated software vulnerabilities
nmap -sV --script vulners 192.168.1.0/24
# Expected Output: List of services & associated vulnerabilities
```

---

### **2️⃣ Network Modernization & Cloud Migration**  

#### **Key Improvements**  
- **Implemented VLAN Segmentation** to **limit lateral movement** and protect sensitive systems.  
- **Applied critical security patches** to reduce exposure to known exploits.  
- **Migrated infrastructure to the cloud**, consolidating **12 on-prem servers** into a **streamlined, cost-effective cloud environment**.  

#### **Before vs After Network Modernization**  

| **Metric**                     | **Pre-Implementation**        | **Post-Implementation**       |
|--------------------------------|-----------------------------|------------------------------|
| Internet Performance           | Slow, Congested Network    | Optimized Traffic Flow      |
| Security Vulnerabilities       | Unpatched, No Segmentation | Updated & Isolated Systems |
| Operational Efficiency         | Manual Processes           | Automated Cloud Services   |

---

### **3️⃣ Endpoint Security & Policy Implementation**  

#### **Security Enhancements**  
- **Introduced a SaaS MDM (Mobile Device Management) solution** to enforce **BYOD (Bring Your Own Device) policies**.  
- **Implemented 2FA (Two-Factor Authentication)** for **privileged accounts** to enhance access security.  
- **Developed formal security policies** to ensure **long-term compliance and governance**.  

```bash
# Example PowerShell command to enforce 2FA on all privileged accounts
Set-MsolUser -UserPrincipalName admin@yagebotanicals.com -StrongAuthenticationRequirements Enabled
```

---

## 🔍 Technical Artifacts  

```plaintext
Network-Modernization/
├── network-modernization-proposal.pdf # Full Infrastructure Upgrade Plan  
├── cloud-migration-strategy.pdf       # Cloud Migration Roadmap  
├── security-policy-docs/              # Compliance & IT Governance Policies  
│   ├── vlan-segmentation-guidelines.pdf  
│   ├── endpoint-security-policy.pdf   
│   ├── patch-management-plan.pdf      
└── risk-mitigation-report.pdf         # Analysis of Security Risks & Fixes  
```

---

## 🌟 Lessons Learned  

### 🔐 **Asset Management is Critical**  
- **A well-maintained CMDB** provides a **foundation for security improvements** and **risk reduction**.  

### 💡 **Cloud Migration Requires Strategic Planning**  
- A **phased migration approach** reduces risks and minimizes operational disruptions.  

### 📜 **Security Policy Enforcement Improves Long-Term Stability**  
- **Standardizing IT security policies** helps **ensure compliance and regulatory adherence**.  

---

## 🎯 SOC Role Preparation  

✅ **Network Security & Segmentation** – Improved infrastructure through VLAN and cloud integration.  
✅ **Threat & Vulnerability Management** – Identified and patched security weaknesses.  
✅ **Security Policy Development** – Formalized IT governance to maintain **long-term security posture**.  
✅ **Cloud Security Planning** – Designed migration strategies aligned with **industry best practices**.  

---

## 🔗 Related Projects  

1. [Cloud Security & Zero Trust Architecture](#)  
2. [SOC Alert Triage & Incident Response](#)  
3. [Enterprise Asset Management & CMDB](#)  

---

## ⬇️ **Clone Repository**  

```bash
git clone https://github.com/yourusername/network-modernization.git
```

---
