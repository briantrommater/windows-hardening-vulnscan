# Vulnerability Scan Instructions

This document explains how to run a basic vulnerability scan using **OpenVAS (Greenbone)** or **Nessus Essentials**, both free tools used widely in cybersecurity.

---

# 🟢 Option 1: OpenVAS (Greenbone Community Edition)

## 1. Install OpenVAS
- Download via Greenbone website  
- Install and allow system setup (may take 10–20 min)

## 2. Start Scanner
Open browser and go to:


Login with your generated admin credentials.

---

## 3. Add a Target
- Go to **Configuration → Targets**
- Click **New Target**
- Enter:
  - **Name:** Windows Test Machine
  - **Host:** IP address of your Windows system (e.g., 192.168.1.20)

---

## 4. Create a Scan Task
- Go to **Scans → Tasks**
- New Task → Set Target to your Windows machine
- Scan Configuration: **Full and Fast**

Run scan.

---

## 5. Export Results
After scan completes:

Download:
- **PDF report**  
- **XML or CSV output**

Place exports into your GitHub folder:
`/Vulnerability-Scan/results/`

---

# 🔵 Option 2: Nessus Essentials (Beginner-Friendly)

## 1. Install Nessus Essentials
- Visit Tenable.com  
- Register for the free activation code  
- Install Nessus

---

## 2. Start Nessus
Navigate to:


---

## 3. Run Scan
- New Scan → **Basic Network Scan**
- Target = your Windows IP  
- Save and **Launch**

---

## 4. Export Results
Download:
- **HTML report**
- **CSV vulnerabilities list**

Upload these into your repo under:
`/Vulnerability-Scan/results/`

---

# 📘 Required Files for GitHub

You should upload:
- `scan_instructions.md` (this file)
- Your exported Nessus/OpenVAS scan results
- A screenshot folder `/screenshots/`
- A summarized findings file in `/Summary/`

---

# ❗ Ethical / Legal Reminder

Only scan:
- Machines you own  
- Machines you have explicit permission to test  

Scanning unauthorized devices is illegal.


