# 🔐 Conditional Access Policies – Zero Trust Lab

## 📌 Overview
This section documents the **Conditional Access (CA) policies** configured in my Zero Trust lab to secure user identities and enforce modern authentication.  
The goal is to ensure that **only trusted users, on trusted devices, from trusted locations** can access corporate resources.

---

## 🛠️ Policies Implemented

### 1. Block Legacy Authentication
- **Why:** Legacy protocols (POP, IMAP, SMTP, etc.) bypass MFA and are vulnerable to brute-force attacks.  
- **Configuration:**  
  - **Assignments:** All users  
  - **Cloud apps:** All apps  
  - **Grant:** Block access  
- **Status:** ✅ Enabled  

[
](https://github.com/dsenazah/ZeroTrust-Lab-Microsoft365-Security/blob/576b2792053e9198ce40b55d753aaec52cdd5171/docs/screenshots/1stpolicy_require_MFA_allusers.png)
---

### 2. Require MFA for All Users
- **Why:** MFA reduces the risk of account compromise.  
- **Configuration:**  
  - **Assignments:** All users  
  - **Cloud apps:** All apps  
  - **Grant:** Require multi-factor authentication  
- **Status:** ✅ Enabled  

📸 *Screenshot Placeholder: [MFA-All-Users.png]*  

---

### 3. Require MFA for Admin Roles
- **Why:** Admin accounts are high-value targets.  
- **Configuration:**  
  - **Assignments:** Directory roles (Global Admin, Intune Admin, Security Admin, etc.)  
  - **Grant:** Require multi-factor authentication  
- **Status:** ✅ Enabled  

📸 *Screenshot Placeholder: [MFA-Admins.png]*  

---

### 4. Restrict Access by Country (Geo-Blocking)
- **Why:** Reduce attack surface by allowing sign-ins only from authorized countries.  
- **Configuration:**  
  - **Assignments:** All users  
  - **Conditions → Locations:**  
    - Include: United States 🇺🇸, Ghana 🇬🇭  
    - Exclude: All other countries  
  - **Grant:** Require MFA (if from allowed country) / Block (if from other locations)  
- **Status:** ✅ Enabled  

📸 *Screenshot Placeholder: [Geo-Block-USA-Ghana.png]*  

---

### 5. Block Unsupported Devices
- **Why:** Prevent users from logging in on jailbroken, rooted, or unknown platforms.  
- **Configuration:**  
  - **Assignments:** All users  
  - **Conditions → Device platform:** Block unsupported OS (Linux, unknown mobile devices)  
  - **Grant:** Block access  
- **Status:** ✅ Enabled  

📸 *Screenshot Placeholder: [Unsupported-Devices.png]*  

---

## ✅ Testing & Verification
- Attempted login with legacy protocols → **Blocked**  
- Admin login without MFA → **Blocked**  
- User login from outside US/Ghana → **Blocked**  
- User login from compliant device in Ghana → **Successful**  

📸 *Screenshot Placeholder: [Testing-Results.png]*  

---

## 📊 Key Learnings
- Conditional Access is the **first line of defense** in Zero Trust.  
- MFA + Geo-blocking + Device compliance **significantly reduces attack surface**.  
- Testing from multiple locations/devices validates the policies in real-world scenarios.  

---
