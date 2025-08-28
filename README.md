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
- **Entra ID (P1 → planned P2 upgrade)**: Identity & access (CA, MFA, SSO).  
  - *Planned P2:* Identity Protection (risk-based CA), PIM, Access Reviews  
- **Intune (MDM/MAM)** → device compliance and management for Windows/macOS  
- **Jamf Pro** → mobile device management for iPads (Apple ecosystem integration with Entra ID)  
- **Microsoft Defender (E5)** → XDR across endpoint, identity, email, and apps  
- **Microsoft Purview (E5)** → DLP, sensitivity labels, insider risk  
- **Microsoft Sentinel** → SIEM/SOAR with Fusion, UEBA, automation  
- **(Planned) Copilot for Security** → Gen-AI for investigation & response  
- **Test users** → simulate employees in different locations (USA, Ghana, External/Guest)  

---

## 🚀 Goals
- Build an **enterprise-ready Zero Trust baseline** across all six security pillars.  
- Continuously adapt policies and controls to reflect the **latest Microsoft and Jamf capabilities**.  
- Expand from **Entra P1 to P2** to incorporate advanced Zero Trust features like **risk-based Conditional Access, Privileged Identity Management (PIM), and automated Access Reviews**.  
- Showcase **hands-on expertise** with both Microsoft 365 security stack and Jamf Pro for iOS devices.  

---

## 📅 Future Roadmap (P2 & AI Expansion)

**Phase 1 (Current – E3/P1)**  
- Conditional Access baseline, MFA, geo restrictions, platform controls  
- Intune + Jamf Pro device onboarding and compliance  
- Defender onboarding (endpoint/email) and basic analytics in Sentinel  
- Purview DLP & sensitivity labeling pilot  

**Phase 2 (Planned – E5/P2 + AI Security)**  
- Enable **Entra ID Protection** and **risk-based CA** (user/sign-in risk)  
- Deploy **PIM** with approval workflows & just-in-time elevation  
- Set up **Access Reviews** for groups, apps, and privileged roles  
- Light up **Defender XDR AIR** and **attack disruption**  
- Build **Sentinel Fusion/UEBA** detections + automation playbooks  
- Integrate **AI-driven security features** across Defender, Purview, and Sentinel  
- Onboard **Copilot for Security** for incident summarization, hunting assistance, and response guidance  
