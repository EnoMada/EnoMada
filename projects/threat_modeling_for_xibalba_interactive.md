# Threat Modeling for Xibalba Interactive

## Project Overview

In this project, I conducted a comprehensive **threat modeling exercise** for **Xibalba Interactive**, an up-and-coming game development studio. The goal was to assess the risks associated with their new feature: a **publicly-accessible website** displaying player stats and a guestbook for user comments. By mapping attack surfaces, identifying vulnerabilities, and proposing mitigation strategies, I helped Xibalba improve their security posture and reduce visibility gaps.

---

## Client Communication

> **Email from Xibalba Interactive:**  
> "We’re excited to implement a new feature for our game: a public website showing player stats and user comments. We need your help to identify potential threats and ensure this feature is secure."

---

## Attached Files

- [View Threat Modeling Worksheet](#) *(Insert link once uploaded)*  
- [View Vulnerability Assessment Report](#) *(Insert link once uploaded)*  
- [View SIEM Configuration Documentation](#) *(Insert link once uploaded)*  

---

## Project Objectives and Approach

- **Objective:** Identify and mitigate threats associated with Xibalba’s new public-facing website feature.  
- **Approach:**  
  - **Threat Modeling:** Developed a threat model to map attack surfaces and identify vulnerabilities.  
  - **Asset Identification:** Cataloged key assets, including intellectual property, payment information, and the in-game chat system.  
  - **Vulnerability Assessment:** Conducted scans using **Nmap**, **PowerShell**, and **LDAP queries** to uncover misconfigurations and exposed assets.  
  - **SIEM Integration:** Analyzed existing SIEM logs and proposed enhancements for better threat detection.  
  - **Recommendations:** Provided actionable strategies to reduce the attack surface and improve security monitoring.  

---

## Key Findings

### **1️⃣ Exposed Intellectual Property**  
- Discovered an **open directory** on the development server (`dev.xibalbainteractive.com`) containing a `.git` folder with the **proprietary game source code**.  
- **Recommendation:** Restrict access to development servers and implement IP whitelisting.  

### **2️⃣ Stored Cross-Site Scripting (XSS)**  
- Identified a **stored XSS vulnerability** in the guestbook feature of the new website (`stats.xibalbainteractive.com`).  
- **Recommendation:** Implement input validation and output encoding to prevent XSS attacks.  

### **3️⃣ Misconfigured Administrative Interfaces**  
- Found that **administrative interfaces** for game servers were accessible over the internet without **multi-factor authentication (MFA)** or **IP whitelisting**.  
- **Recommendation:** Enable MFA and restrict access to trusted IPs.  

### **4️⃣ Shared Database Credentials**  
- Development and production environments shared the **same database credentials**, increasing the risk of lateral movement.  
- **Recommendation:** Use separate credentials and implement role-based access control (RBAC).  

---

## SOC Analyst Skills Showcased

- **Threat Modeling & Risk Assessment**  
- **Network Scanning & Enumeration**  
- **Vulnerability Identification & Mitigation**  
- **SIEM Configuration & Log Analysis**  
- **Incident Response Planning**  
- **Security Framework Implementation**  

---

## Key Learnings and Recommendations

- **Centralized Asset Tracking:** A well-maintained **Configuration Management Database (CMDB)** is critical for effective security monitoring.  
- **Proactive Vulnerability Management:** Regular scans and audits help identify and remediate risks before they are exploited.  
- **Layered Defense Strategies:** Implementing **multi-factor authentication (MFA)**, **IP whitelisting**, and **input validation** significantly reduces the attack surface.  
- **Continuous Monitoring:** Enhancing SIEM rules and integrating additional data sources improves threat detection capabilities.  

---

## Conclusion

This project deepened my understanding of **threat modeling** and **attack surface analysis** in a real-world scenario. By identifying critical vulnerabilities and proposing actionable recommendations, I helped Xibalba Interactive strengthen their security posture and prepare for future threats. This experience reinforced the importance of **proactive risk management** and **layered defense strategies** in cybersecurity.

---

📌 **For more insights, visit my [GitHub Profile](https://github.com/EnoMada) or [LinkedIn Profile](https://www.linkedin.com/in/kylesportfolio/)!**
