# 🧪 Brute Force Attack Scenario: YummyRecipesForMe.com

## 🧠 Scenario Overview

You are a cybersecurity analyst for **yummyrecipesforme.com**, a website that sells recipes and cookbooks. The organization experienced a **brute force attack** initiated by a **disgruntled former employee**.

The attacker successfully gained access to the web server by repeatedly guessing known **default admin passwords**. Once inside, the attacker embedded a malicious JavaScript function into the website’s source code. This function prompted users to download and run an executable file that contained malware.

After installing the malware, the attacker changed the admin password and redirected all traffic to a **malicious clone site**: `greatrecipesforme.com`.

---

## 🎯 Objectives

- Analyze captured network traffic for suspicious behavior.
- Identify the protocols used during the malicious interaction.
- Document the flow of the attack from DNS request to malware execution.
- Recommend mitigations to prevent similar incidents in the future.

---

## 🔄 Attack Timeline

| Timeframe      | Event Description |
|----------------|-------------------|
| **T0**         | Former employee initiates brute force attack using default admin passwords |
| **T1**         | Admin credentials are compromised |
| **T2**         | Attacker embeds malicious JavaScript in website source code |
| **T3**         | Users visiting the website are prompted to download an executable file |
| **T4**         | Executable file runs malware and redirects browsers to `greatrecipesforme.com` |
| **T5**         | Admin password is changed to block legitimate access |
| **T6**         | Helpdesk receives multiple reports of slow systems and suspicious behavior |
| **T7**         | Security team investigates using `tcpdump` in a sandbox environment |

---

## 🌐 Network Behavior Captured via Tcpdump

The following steps were observed when accessing the infected website:

1. **DNS Request** — Browser queries for `yummyrecipesforme.com`
2. **DNS Response** — IP address is returned
3. **HTTP Request** — Browser sends `GET / HTTP/1.1` request to the website
4. **Executable Download** — JavaScript prompts user to download file
5. **File Execution** — File installs malware
6. **DNS Request** — Browser queries for `greatrecipesforme.com`
7. **DNS Response** — IP address is returned
8. **HTTP Request** — Browser is redirected to malicious domain

---

## 🔎 Tools Used

- 🧪 **Sandbox Environment** — Isolated testing of suspicious website behavior
- 🧰 **Tcpdump** — Captured live network traffic
- 🔍 **Manual Source Code Inspection** — Revealed embedded JavaScript and malicious redirect

---

## ⚠️ Vulnerabilities Identified

- Admin password was **still set to default**
- No brute force detection or lockout mechanisms
- No multi-factor authentication (MFA)
- Source code tampering was not detected until after the breach

---

## ✅ Suggested Remediation (from `incident-report.md`)

- Implement strong **password policies** (no defaults/shared passwords)
- Enforce **multifactor authentication** (MFA) for all admin access
- Regularly perform **firewall rule audits** and apply ingress/egress filtering

---

## 📝 Notes

- This scenario is based on a simulated case for educational purposes.
- All data has been anonymized and sanitized for safe public sharing.
- This file is part of the GitHub repository: `Cybersecurity-reports/tcpdump-http-bruteforce/`

---

