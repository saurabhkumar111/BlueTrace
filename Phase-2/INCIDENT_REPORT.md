# 🧩 BlueTrace – Phase 2: Incident Report  
### *Incident Type: SSH Brute Force (Hydra)*  
**Date:** Jan 5, 2026  
**Target Server:** `192.168.1.7` *(padholikho)*  
**Attacker IP:** `192.168.1.30` *(Kali Linux)*  

---

## 🧠 1. Attack Summary  
A **controlled SSH brute-force attack** was conducted using **Hydra** against the account `sshuser` with intentionally weak credentials.  
This simulation aimed to demonstrate real-world log artifacts, detection methods, and incident documentation from a SOC analyst’s perspective.

---

## ⏱️ 2. Attack Timeline (Extracted from `auth.log`)  
Key observations extracted from the authentication log:

- Multiple **failed SSH authentication attempts** targeting user `sshuser`.  
- **High frequency** of attempts within a single second, indicating **automated attack behavior**.  
- A **successful login** occurred after multiple failed attempts.  
- The attacker’s **session was opened and closed** shortly after login — suggesting a proof‑of‑concept compromise rather than sustained access.

---

## 📁 3. Evidence Files  

| Description | File Path | SHA256 Hash |
|--------------|------------|--------------|
| **Baseline Log (Pre‑Attack)** | `Phase-1/auth.log.baseline` | `642316d27fdb450ee726ebcf35166e6ef6ccd737ebd7b220299b7c7c1d8c5490` |
| **Post‑Attack Log** | `Phase-2/auth.log.postattack` | `00802e095404b635f1f90fcb7e0854fa7cea9453bc8b58cfb56167189f774e0b` |

These logs serve as verified evidence for **timeline reconstruction** and **log integrity validation**.

---

## 🚨 4. Indicators of Compromise (IoCs)  

| Indicator Type | Value / Pattern |
|-----------------|-----------------|
| **Source IP** | `192.168.1.30` |
| **Target Account** | `sshuser` |
| **Log Patterns** | `Failed password for sshuser`<br>`Accepted password for sshuser` |

These patterns clearly mark **failed** and **successful login events**, forming the foundation for detection rule creation.

---

## 🔍 5. Detection Method  
Detection was performed using:  
- **File comparison (`diff`)** between baseline and post‑attack logs to highlight anomalous entries.  
- **Targeted grep searches**, such as:  
  ```bash
  grep "Failed password" auth.log
  grep "Accepted password" auth.log
  grep "sshd" auth.log | uniq -c
