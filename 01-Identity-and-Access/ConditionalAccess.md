# 🔐 Conditional Access Policies – Zero Trust Lab (OfflineSec)

## 📌 Overview
This document outlines the **Microsoft Entra ID Conditional Access (CA) policies** configured in my Zero Trust lab.  
The objective is to ensure that **only trusted users, on trusted devices, from trusted locations** can access resources.  

Each policy is documented in the same structure as displayed in the Microsoft Entra portal: **Assignments → Access controls → Session → State**.  

# 📋 Conditional Access Policy Matrix (OfflineSec Lab)

| **Policy Name**                                   | **Owner**   | **Users (Scope)**                                         | **Target Resources**       | **Grant / Enforcement**                         | **State** |
|---------------------------------------------------|-------------|-----------------------------------------------------------|----------------------------|-------------------------------------------------|-----------|
| Block Legacy Authentication                       | Microsoft   | All users                                                 | All resources              | Block legacy authentication clients             | ![On](https://img.shields.io/badge/On-green) |
| Multifactor Authentication for Admins             | Microsoft   | Admin roles (excl. Break-glass, dsenazah@offlinesec.com)  | All resources              | Require MFA for privileged accounts             | ![On](https://img.shields.io/badge/On-green) |
| Multifactor Authentication for All Users          | Microsoft   | All users                                                 | All resources              | Require MFA (default baseline policy)           | ![Off](https://img.shields.io/badge/Off-lightgrey) |
| CA – Require MFA (Baseline All Users) – OfflineSec| User        | All company (excl. Break-glass, dsenazah@offlinesec.com)  | All resources              | Require MFA; sign-in frequency = 30 days        | ![Report-only](https://img.shields.io/badge/Report--only-orange)|
| CA – Allow USA & Ghana Only – OfflineSec          | User        | All company (excl. Break-glass, dsenazah@offlinesec.com)  | All resources              | Block access outside USA & Ghana                | ![Report-only](https://img.shields.io/badge/Report--only-orange)|
| CA – Block Unsupported Device Platforms – OfflineSec | User      | All company (excl. Break-glass, dsenazah@offlinesec.com)  | All resources              | Block Android, Linux, Windows Phone             |![Report-only](https://img.shields.io/badge/Report--only-orange)|


![image alt](https://github.com/dsenazah/ZeroTrust-Lab-Microsoft365-Security/blob/5c6f6a84e3496df3038c9b6b9f800f641182807e/docs/screenshots/AllpoliciesView.png)




---

### 1. Block Legacy Authentication (Microsoft)

- **Why:** Legacy protocols (POP, IMAP, SMTP, etc.) bypass MFA and are vulnerable to brute-force and password spray attacks.  

**Assignments**  
- **Users:** All users  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):** Not configured  
- **Conditions:**  
  - Client apps included:  
    - Legacy authentication clients  
    - Exchange ActiveSync clients  
    - Other clients  

**Access controls**  
- **Grant:** Block access  

**Session**  
- 0 controls selected  

**Policy state:** On  

---

### 2. Multifactor Authentication for Admins (Microsoft)

- **Why:** Admin accounts are privileged targets and require stronger protection. MFA ensures an additional layer of security against credential theft.  

**Assignments**  
- **Users:**  
  - Specific users included: Microsoft-selected admin roles  
  - Specific users excluded:  
    - Break-glass accounts  
    - dsenazah@offlinesec.com  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):** Not configured  
- **Conditions:** 0 conditions selected  

**Access controls**  
- **Grant:** Require multifactor authentication  

**Session**  
- 0 controls selected  

**Policy state:** On  

---

### 3. Multifactor Authentication for All Users (Microsoft)

- **Why:** Provides tenant-wide MFA enforcement for all users. This is Microsoft’s default baseline control. In this lab it is disabled and replaced with a custom Baseline MFA policy for more flexibility and exclusions.  

**Assignments**  
- **Users:** All users  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):** Not configured  
- **Conditions:** 0 conditions selected  

**Access controls**  
- **Grant:** Require multifactor authentication  

**Session**  
- 0 controls selected  

**Policy state:** Off  

---

### 4. CA – Require MFA (Baseline All Users) – OfflineSec

- **Why:** Enforce multifactor authentication across the tenant to reduce risk of account compromise. This is the custom baseline MFA policy replacing Microsoft’s default “MFA for all users.”  

**Assignments**  
- **Users and groups:**  
  - Included: All company (allcompany@offlinesec.com)  
  - Excluded:  
    - Break-glass accounts  
    - dsenazah@offlinesec.com  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):** Not configured  
- **Conditions:** 0 conditions selected  

**Access controls**  
- **Grant:** Require multifactor authentication  
- **Multiple controls:** Require all selected controls  

**Session**  
- Sign-in frequency: 30 days  
- Persistent browser session: Not configured  

**Policy state:** Report-only  

---

### 5. CA – Allow USA & Ghana Only – OfflineSec

- **Why:** Restrict access to trusted geographies (United States and Ghana) to reduce attack surface and prevent logins from risky regions.  

**Assignments**  
- **Users and groups:**  
  - Included: All company (allcompany@offlinesec.com)  
  - Excluded:  
    - Break-glass accounts  
    - dsenazah@offlinesec.com  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):**  
  - Included: Any network or location  
  - Excluded: *Main office* (United States), *Ghana office* (Ghana)  

**Conditions**  
- Device platform: Any device  
- Locations:  
  - Included: Any network or location  
  - Excluded: *Main office*, *Ghana office*  

**Access controls**  
- **Grant:** Block access  

**Session**  
- 0 controls selected  

**Policy state:** Report-only  

---

### 6. CA – Block Unsupported Device Platforms – OfflineSec

- **Why:** Restrict access so only supported device platforms (Windows, macOS, iOS) can connect. This prevents logins from unsupported or high-risk platforms (Android, Linux, Windows Phone).  

**Assignments**  
- **Users and groups:**  
  - Included: All company (allcompany@offlinesec.com)  
  - Excluded:  
    - Break-glass accounts  
    - dsenazah@offlinesec.com  
- **Target resources:** All resources (formerly "All cloud apps")  
- **Network (NEW):** Not configured  

**Conditions**  
- Device platform:  
  - **Included:** Android, Windows Phone, Linux  
  - **Excluded:** iOS, Windows, macOS  

**Access controls**  
- **Grant:** Block access  

**Session**  
- 0 controls selected  

**Policy state:** Report-only  

---
