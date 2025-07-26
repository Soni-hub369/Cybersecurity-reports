# 🛡️ Network Security Course Summary (Modules 1–4)

---

## 🌐 Modules 1–3: Core Networking, Protocols, and Attacks

### 📘 Module 1: Networking Basics

**Network Types**
- **LAN:** Local network (e.g., office, home)
- **WAN:** Wide network (e.g., cities, global internet)

**Devices**
- **Hub:** Broadcasts to all
- **Switch:** Directs to specific devices
- **Router:** Connects multiple networks
- **Modem:** Connects LAN to the internet

**TCP/IP Model**
- **Network Access:** Hardware, cables, switches
- **Internet Layer:** IP addressing and routing
- **Transport Layer:** TCP (reliable), UDP (fast)
- **Application Layer:** Email, file transfers, web services

**Cloud Computing**
- Resources accessed remotely via the internet
- Data stored in remote data centers

**Key Terms**
- **IP Address:** Unique ID for devices
- **Ports:** Data destination identifiers (e.g., 443 HTTPS)
- **Packet Sniffing:** Capture network packets for analysis

---

### 🔐 Module 2: Protocols and Security Tools

**Common Protocols**
- **Communication:** TCP, UDP, HTTP, DNS
- **Management:** SNMP, ICMP
- **Security:** HTTPS, SFTP

**Wireless Security Evolution**
- `WEP (1999)` → `WPA (2003)` → `WPA2 (2004)` → `WPA3 (2018)`

**Firewall Types**
- **Stateful:** Tracks traffic sessions
- **Stateless:** Uses preset rules

**Common Attacks**
- **SYN Flood / ICMP Flood / Ping of Death / Smurf Attack**
- **IP Spoofing**
- **Replay Attacks**
- **On-path Attacks**

**Privacy Tools**
- **VPN:** Encrypts and hides IP
- **Proxy Server:** Filters/forwards web requests

---

### ☠️ Module 3: Attacks and Monitoring

**Denial of Service**
- **DoS:** Single-source flood
- **DDoS:** Multi-source attack

**Packet Sniffing**
- **Passive:** Monitors data
- **Active:** Alters/intercepts data

**Monitoring Tools**
- `tcpdump`: CLI packet analyzer
- `Wireshark`: GUI for traffic analysis

---

## 🔧 Module 4: Security Hardening (OS, Network, Cloud)

### 🖥️ OS Hardening

**Practices**
- **Patch Updates**
- **Baseline Configurations**
- **Password Policy (Complex & Long)**
- **Secure Disposal of Devices**

**Brute Force Defense**
- Salt + hash passwords
- CAPTCHA / reCAPTCHA
- Multi-Factor Authentication (MFA)
- Lockout policies

---

### 🌐 Network Hardening

**Regular Tasks**
1. Firewall rule maintenance
2. Network log analysis
3. Patch updates
4. Server backups

**Non-Regular Tasks**
- Port filtering
- Network access control (per department)
- Encryption for secure communication

---

### ☁️ Cloud Security & Hardening

**Shared Responsibility Model**
- **CSP:** Secures infrastructure
- **Customer:** Secures data, apps, configs

**Security Tools**
| Tool      | Role                        | Can Block? | Notes                    |
|-----------|-----------------------------|------------|--------------------------|
| Firewall  | Filters traffic             | ✅         | First line of defense    |
| IDS       | Detects suspicious activity | ❌         | False positives possible |
| IPS       | Blocks harmful traffic      | ✅         | Reactive defense         |
| SIEM      | Central monitoring          | ❌         | Logs & analyzes data     |

**Cryptographic Hardening**
- Encrypt sensitive data
- Manage encryption keys (TPM / CloudHSM)
- Securely delete (erase keys)

---

## 🧠 How It All Connects

```mermaid
flowchart TB
    A[Networking Basics]
    B[Protocols & Security]
    C[Attacks & Monitoring]
    D[OS Hardening]
    E[Network Hardening]
    F[Cloud Hardening]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> B
