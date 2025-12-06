# Vulnerability Scan Findings & Mitigations

This document summarizes the vulnerabilities identified during the scan and the actions taken to remediate them.

---

# High Severity Findings

## 1. SMBv1 Detected
**Description:** Legacy SMB protocol vulnerable to remote code execution  
**Fix Applied:** Disabled SMBv1 via Windows Features  

---

## 2. RDP Accessible Externally
**Description:** Remote Desktop was listening on port 3389  
**Fix Applied:** Disabled RDP and removed firewall rule  

---

## 3. Weak Password Policies
**Description:** Minimum password length too low; complexity not enforced  
**Fix Applied:** Configured strong password policy  

---

# Medium Severity Findings

## 4. Outdated Software Components
**Description:** Adobe Reader and Visual C++ redistributables outdated  
**Fix:** Updated all components through Windows Update + vendor site  

---

## 5. Misconfigured Firewall Rules
**Description:** Unused inbound rules enabled (e.g., media sharing)  
**Fix:** Disabled unnecessary inbound rules  

---

# Low Severity Findings

## 6. Unnecessary Services Running
**Description:** Xbox services, Diagnostics Tracking  
**Fix:** Disabled via PowerShell script  

---

# Post-Mitigation Scan

A follow-up scan showed:
- No more High severity items  
- Medium reduced from 3 → 1  
- Low severity minimal  

Overall system posture improved from **High Risk → Low/Medium Risk**.

