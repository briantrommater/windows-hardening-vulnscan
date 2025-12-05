# Applied Security Settings

This document lists all Windows hardening configurations that were successfully applied during the project.  
Each change includes:  
- What was changed  
- Why it improves security  
- How it was applied (GUI, PowerShell, GPO, etc.)

---

## 1. Disabled Unnecessary Services
**Reason:** Reduces attack surface by turning off unused background services.

**Services Disabled:**
- Fax (`Set-Service -Name "Fax" -StartupType Disabled`)
- Xbox Game Save (`Set-Service -Name "XblGameSave" -StartupType Disabled`)
- Connected User Experiences / Telemetry (`DiagTrack`)

**Method:** PowerShell script (`scripts/disable_services.ps1`)

---

## 2. Firewall Hardening
**Reason:** Prevents unauthorized inbound traffic.

**Settings Applied:**
- Confirmed Windows Defender Firewall enabled on all profiles (Domain, Private, Public)
- Blocked all inbound connections not explicitly allowed
- Verified common ports closed using `Get-NetFirewallRule`

**Method:** Windows Security GUI + PowerShell

---

## 3. Account & Authentication Policies
**Reason:** Prevent brute-force and unauthorized access.

**Changes Applied:**
- Minimum password length: **12 characters**
- Account lockout threshold: **5 failed attempts**
- Account lockout duration: **15 minutes**
- Enforced password history: **5 previous passwords remembered**

**Method:** `secpol.msc` → Account Policies

---

## 4. Enabled Audit Logging
**Reason:** Improves forensic visibility and threat detection.

**Audit Policies Enabled:**
- Logon events (Success/Failure)
- Object access  
- Policy changes  
- Privilege use  
- System events  

**Method:** Local Security Policy → Advanced Audit Policy Configuration

---

## 5. Disabled SMBv1
**Reason:** SMBv1 is vulnerable (e.g., EternalBlue, WannaCry).

**Command Used:**

---

## 6. Hardened Local Administrator Account
**Reason:** Prevents easy privilege escalation.

**Actions Taken:**
- Renamed `Administrator` account  
- Disabled remote login for local admins  
- Set a long, unique administrator password  

**Method:** Local Users & Groups (`lusrmgr.msc`)

---

## 7. Removed Dangerous Default Settings
**Reason:** Eliminates common misconfigurations attackers exploit.

**Actions:**
- Disabled AutoRun & AutoPlay  
- Removed unused local user accounts  
- Disabled guest account  
- Turned off remote assistance  

---

## 8. Applied Windows Update Configuration
**Reason:** Ensures system receives security patches promptly.

**Settings:**
- Enabled automatic updates  
- Set “Notify before restart” to avoid forced reboots  

---

## 9. Browser Hardening (Edge / Chrome)
**Reason:** Reduces phishing & malware exposure.

**Changes:**
- Enabled Safe Browsing / SmartScreen  
- Disabled saving passwords in browser  
- Removed untrusted extensions  

---

## 10. Verified System Integrity
**Reason:** Ensures OS is not corrupted.

**Commands Executed:**

---

# Summary

All configurations above were applied and tested.  
These hardening measures collectively reduce:
- Attack surface  
- Malware exposure  
- Unauthorized access risk  
- Lateral movement opportunities  

This file serves as documentation of the **actual work performed** in the hardening phase of the project.

