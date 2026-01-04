# 🎯 BlueTrace – Phase 0  
### *Project Initialization & Scope Definition*

---

## 🧠 Project Overview  
**BlueTrace** is a SOC Level‑1 focused **detection and log‑analysis** project designed to simulate a **real-world SSH brute-force attack** and investigate it using **Linux authentication logs**.

The project demonstrates:  
- 🔍 Attack detection  
- 📊 Log analysis  
- 🧾 Incident documentation  
- 🧩 Evidence preservation  
- 🧠 Professional GitHub reporting practices

---

## 🛡️ Why the name “BlueTrace”?  
| Term | Meaning |
|------|----------|
| **Blue** | Represents Blue Team / SOC / Defensive Security |
| **Trace** | Tracing attacker activity through logs, IPs, timestamps, and authentication attempts |

**BlueTrace = Tracing attacker behavior from a defender’s perspective.**  
This project aligns with a **SOC L1/L2 analyst role** — not penetration testing.

---

## 🎯 Project Objectives  
- Simulate a **brute-force SSH attack** from an attacker machine.  
- Collect and analyze **authentication logs**.  
- Identify:  
  - 🕵️ Attacker source IP  
  - 💣 Attack type  
  - 🔁 Number of failed attempts  
  - 🔑 Successful login events (if any)  
- Produce a **professional incident-style report**.  
- Maintain a **structured GitHub repository** suitable for interviews and demonstrations.

---

## 🧱 Lab Environment (Planned)

| Role | Machine | Purpose |
|------|----------|----------|
| **Attacker** | Kali Linux | Launch SSH brute-force attack |
| **Victim** | Ubuntu Server | Target system with SSH service |
| **SOC Analysis** | Ubuntu Server | Analyze `/var/log/auth.log` |
| **Optional Expansion** | Windows Server / Windows 10 | For future multi-platform detection scenarios |

**Why Ubuntu Server as Victim:**  
- Native SSH service for testing.  
- Detailed authentication logs (`/var/log/auth.log`).  
- Reflects realistic enterprise server configurations.

---

## ⚠️ Threat Model (Initial)

| Parameter | Details |
|------------|----------|
| **Attack Type** | SSH Brute Force |
| **Tool Used** | Hydra |
| **Target** | SSH service on Ubuntu Server |
| **Log Source** | `/var/log/auth.log` |
| **Detection Method** | Manual log analysis *(Phase‑1)*, automated parsing *(future phase)* |

---


