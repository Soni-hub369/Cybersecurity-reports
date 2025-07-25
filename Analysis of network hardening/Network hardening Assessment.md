# 🛡️ Network Hardening Assessment & Recommendations
_____________________________________________________
  
## 📅 Date: 2025-07-23  
_______________________

---

## 🧠 Summary  

As a security analyst for a social media organization, I performed a network hardening assessment following a major data breach. The breach exposed sensitive customer information such as names and addresses. Upon inspection, I discovered several critical vulnerabilities that, if left unaddressed, could lead to future breaches.

The purpose of this report is to identify these risks and recommend industry-standard hardening tools and practices to improve the organization’s security posture.

==========================================================================================================================

## 🚨 Identified Vulnerabilities

1. Employees were found to be **sharing passwords**.
2. The **admin password** for the database was still set to the default.
3. The **firewalls had no traffic filtering rules** configured.
4. **Multifactor authentication (MFA)** was not implemented on any system.

---

## 🔧 Part 1: Selected Hardening Tools and Methods

| Tool/Method              | Reason for Selection                                          |
|--------------------------|---------------------------------------------------------------|
| **Password Policies**     | To eliminate weak/default/shared password usage               |
| **Multifactor Authentication (MFA)** | To prevent unauthorized access even with compromised credentials |
| **Firewall Maintenance**  | To block suspicious inbound/outbound traffic and limit attack surface |

---

## 📘 Part 2: Recommendations

### 🔐 1. Password Policies

Weak and shared passwords were a key factor in this breach.  
Implementing strong password policies ensures that:

- Passwords are salted, hashed, and stored securely
- Default credentials are eliminated organization-wide
- Password sharing is discouraged and monitored
- Complexity is balanced with usability (as per NIST guidelines)

> **Action Plan:**  
Adopt NIST-compliant policies using a password manager and monitor login activity for shared credentials.

---

### 🔑 2. Multifactor Authentication (MFA)

MFA is a low-cost, high-impact method to prevent account takeover attacks. Even if an attacker knows the password, access will be denied without a second authentication factor.

- Use time-based OTPs (authenticator app or SMS)
- Enforce MFA on all admin, employee, and privileged accounts
- Integrate MFA into VPN and cloud-based access points

> **Bonus:** MFA also protects against phishing, credential stuffing, and brute-force attacks.

---

### 🔥 3. Firewall Maintenance

Firewalls without rules are equivalent to an open door in your network. Regular maintenance ensures that:

- Inbound traffic is restricted to only necessary services/ports
- Outbound traffic is monitored and filtered
- Rules are updated based on new threats or DDoS patterns

> **Action Plan:**  
Establish a quarterly firewall audit. Block unused ports. Apply port filtering, IP-based restrictions, and application-layer filters.

---

## 🛠 Tools & Practices Recommended

| Tool                        | Role in Network Hardening                                 |
|-----------------------------|------------------------------------------------------------|
| `NIST Password Policy Guide`| Reference for building effective password rules           |
| `Google Authenticator / Duo`| MFA token generation for users and admins                 |
| `Firewall Rule Templates`   | Base configurations for segmenting traffic in and out     |
| `SIEM or Log Analyzer`      | Optional – monitor failed logins and rule violations      |

---

## 🔒 Sanitization Notice

> All names, addresses, and infrastructure data have been anonymized for educational and portfolio demonstration purposes.

