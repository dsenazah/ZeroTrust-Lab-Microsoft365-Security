# 🛡️ Zero Trust Security Lab with Microsoft 365 (E3/E5)

## 📌 Overview
This project is a hands-on **Zero Trust home lab** I built to demonstrate enterprise-grade security using **Microsoft 365, Entra ID, Intune, Jamf Pro, Defender, Purview, and Microsoft Sentinel**.  

The lab is based on Microsoft’s Zero Trust principles:
- ✅ Verify Explicitly  
- ✅ Use Least Privilege Access  
- ✅ Assume Breach  

I designed, configured, and tested each of the six Zero Trust pillars to simulate a real-world enterprise environment and strengthen my skills in **cloud security administration**:  

1. **Identity** – Conditional Access, MFA, risk-based sign-ins  
2. **Devices** – Intune compliance, Autopilot enrollment, Jamf Pro integration for Apple iPads  
3. **Applications** – Secure access & SSO integrations  
4. **Data** – Purview DLP, sensitivity labels  
5. **Infrastructure** – Defender for Cloud, Microsoft Sentinel  
6. **Network** – Geo-blocking & access restrictions  

⚡ **Note:** This is a **continuously evolving project**. As Microsoft (and Jamf) release new security features or as enterprise security demands change, I will update this lab accordingly to reflect current best practices.  

---

## 🏗️ Lab Architecture
- **Microsoft 365 E3/E5 tenant**  
- **Entra ID (P1)** → identity and access management (currently leveraging P1 features)  
- **Planned Upgrade to Entra ID P2** → to enable advanced features such as Identity Protection (risk-based CA), Privileged Identity Management (PIM), and Access Reviews as the project grows  
- **Intune (MDM/MAM)** → device compliance and management for Windows/macOS  
- **Jamf Pro** → mobile device management for iPads (Apple ecosystem integration with Entra ID)  
- **Microsoft Defender** → endpoint detection and response (EDR)  
- **Microsoft Purview** → compliance, governance, and data loss prevention (DLP)  
- **Microsoft Sentinel** → SIEM/SOAR for monitoring and incident response  
- **Test users** → simulate employees in different locations (USA, Ghana, External/Guest)  

---

## 🚀 Goals
- Build an **enterprise-ready Zero Trust baseline** across all six security pillars.  
- Continuously adapt policies and controls to reflect the **latest Microsoft and Jamf capabilities**.  
- Expand from **Entra P1 to P2** to incorporate advanced Zero Trust features like **risk-based Conditional Access, Privileged Identity Management (PIM), and automated Access Reviews**.  
- Provide a **living reference** for IAM, device management, compliance, and security monitoring.  
- Showcase **hands-on expertise** with both Microsoft 365 security stack and Jamf Pro for iOS devices.  

---

## 📅 Future Roadmap
- **Phase 1 (Current – E3 + P1)**  
  - Implement Conditional Access, MFA baseline, location restrictions  
  - Integrate Intune for Windows/macOS management  
  - Integrate Jamf Pro for iPad management  
  - Deploy Microsoft Defender for endpoint security  
  - Configure Purview for DLP and sensitivity labels  
  - Connect Sentinel for SIEM/SOAR monitoring  

- **Phase 2 (Planned – E5 + P2)**  
  - Enable **Identity Protection** (user risk & sign-in risk policies)  
  - Implement **Privileged Identity Management (PIM)** for just-in-time admin access  
  - Set up **Access Reviews** for automated governance  
  - Expand Conditional Access with **authentication strengths** (phishing-resistant MFA)  
  - Enhance compliance with **advanced Purview features** (insider risk, communication compliance)  
  - Integrate Sentinel with custom workbooks and playbooks for automation  
