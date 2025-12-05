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
