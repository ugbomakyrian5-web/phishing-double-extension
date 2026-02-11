# SOC Lab Project: Double Extension Phishing Malware Detection

## 🧪 Lab Overview
This lab demonstrates detection and analysis of a **double-extension file** download, a common phishing tactic where attackers disguise executables as benign files (e.g., cats2025.mp4.exe). The goal is to identify potentially malicious activity, assess the threat, and recommend appropriate SOC response actions.

--- 
## 🎯 Objective
- Detect suspicious file creation with double extensions.
- Investigate host, user, and process context.
- Determine if the event is malicious and propose mitigation.
- Map activity to MITRE ATT&CK framework where applicable.

---

## 📂 Observed Facts

| Field               | Value |
|--------------------|-------|
| Host                | LPT-HR-009 |
| Process Name        | chrome.exe |
| Process User        | S.Conway |
| Target File         | C:\Users\S.Conway\Downloads\cats2025.mp4.exe |
| File URL (MotW)     | https://freecatvideoshd.monster/cats2025.mp4.exe |
| File MD5            | 14d8486f3f63875ef93cfd240c5dc10b |
| Detection Rule      | Double-extension file (*.mp4.exe), often used in phishing attacks |

---

## 🔍 Analysis

- **Double Extension:** .mp4.exe disguises an executable as a media file.  
- **Process:** chrome.exe indicates user-initiated download from the web.  
- **Source URL:** freecatvideoshd.monster is suspicious and likely malicious.  
- **User Context:** HR department, which often contains sensitive data.  
- **Potential Risk:** If executed, this file could deliver malware or enable phishing attacks.

**Observation:** High probability of malicious activity due to the combination of user download, suspicious URL, and deceptive filename.

---

## 🧠 MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|----|
| Execution | User Execution | T1204 |
| Initial Access | Phishing | T1566 |
| Defense Evasion | Masquerading | T1036 |

---

## 🛡 Recommended Response Actions

1. **Quarantine the file** immediately to prevent execution.  
2. **Block the malicious domain** (freecatvideoshd.monster) at firewall/proxy.  
3. **Investigate related activity** on the host for other downloads or suspicious processes.  
4. **User Education / Alert:** Notify S.Conway and instruct not to execute the file.  
5. **Scan the endpoint** with EDR/antivirus for malicious activity.  
6. **Document the incident** for SOC records and threat intelligence sharing.

---

## 🚨 Verdict

**Malicious / Likely Phishing Malware Attempt**

- Immediate SOC escalation recommended.  
- Critical alert in SIEM for tracking and future correlation.

---

## 📸 Optional Evidence

<img src="https://i.imgur.com/kQaO5lR.png" alt="Double-Extension Executable" width="600"/>


- **SIEM Alert:** Double-extension file creation detected  
   


---

## 📘 Portfolio Notes

This lab demonstrates **alert triage, investigation, and incident response**.  
It’s a strong example of **practical SOC skills** that can be showcased to employers and recruiters.
