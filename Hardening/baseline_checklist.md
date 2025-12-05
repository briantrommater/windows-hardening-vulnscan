# Windows Hardening Baseline Checklist

This checklist documents the baseline security controls applied to a Windows 10/11 system as part of the Windows Hardening & Vulnerability Scan project.  
Each checklist item includes a status indicator:

- [ ] Not Applied  
- [x] Applied  
- [-] Not Applicable  

---

## 1. Account Policies
### Password Policy
- [ ] Minimum password length ≥ 12  
- [ ] Password history ≥ 10  
- [ ] Maximum password age: 90 days  
- [ ] Minimum password age: 1 day  
- [ ] Password complexity enabled  

### Account Lockout Policy
- [ ] Lockout threshold: 5 attempts  
- [ ] Lockout duration: 15 minutes  
- [ ] Reset counter after 15 minutes  

---

## 2. Local Security Policies
- [ ] Disable Guest account  
- [ ] Disable Administrator account (if possible)  
- [ ] Enable UAC (User Account Control) at highest level  
- [ ] Restrict anonymous SID enumeration  
- [ ] Restrict anonymous access to named pipes and shares  

---

## 3. Services Hardening
- [ ] Disable Fax service  
- [ ] Disable Xbox services  
- [ ] Disable Remote Registry  
- [ ] Disable Diagnostics Tracking Service (DiagTrack)  
- [ ] Disable unused remote access services  

---

## 4. Firewall & Network
- [ ] Enable Windows Firewall (all profiles)  
- [ ] Block inbound traffic by default  
- [ ] Allow outbound traffic by default  
- [ ] Enable firewall logging  
- [ ] Disable legacy SMBv1  

---

## 5. Application Controls
- [ ] Enable SmartScreen  
- [ ] Disable installation of unsigned drivers/apps  
- [ ] Restrict PowerShell to Constrained Language Mode  
- [ ] Script Execution Policy set to: AllSigned or RemoteSigned  

---

## 6. Audit Logging
- [ ] Enable login/logout auditing  
- [ ] Enable privilege use auditing  
- [ ] Enable object access auditing  
- [ ] Enable process creation logging  
- [ ] Forward logs to local file or SIEM (optional)  

---

## 7. Windows Defender & Security Tools
- [ ] Real-time protection enabled  
- [ ] Cloud-delivered protection enabled  
- [ ] Automatic sample submission enabled  
- [ ] Periodic scanning enabled  
- [ ] Controlled folder access enabled  

---

## 8. System Configuration
- [ ] Disable autorun for all drives  
- [ ] Block unsigned/unknown startup items  
- [ ] Remove bloatware applications  
- [ ] Ensure OS updates are automatic  
- [ ] Ensure drivers are up to date  

---

## 9. User Privilege Hardening
- [ ] Use a standard (non-admin) account for daily use  
- [ ] Ensure only authorized users are in Administrators group  
- [ ] Remove old user profiles  
- [ ] Enforce least privilege across all accounts  

---

## 10. Additional Recommendations
- [ ] Enable BitLocker (if available)  
- [ ] Configure secure DNS (e.g., Quad9, Cloudflare)  
- [ ] Disable macros by default in Office apps  
- [ ] Review installed apps for unnecessary software  

---

# Summary
This baseline checklist establishes the initial security posture before performing the vulnerability scan.  
All changes will be documented in **applied_settings.md** as they are implemented.
