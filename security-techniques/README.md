# 🔐 Security Techniques (CompTIA Security+ SY0-701)

## 🛡️ Security Techniques – Overview
Security techniques, **dijital varlıkları sürekli gelişen siber tehditlere karşı korumayı** amaçlar.  
Kapsamı **geleneksel güvenlik önlemlerinden ileri seviye analitik ve otomasyona** kadar uzanır.

---

## 📡 Wireless Infrastructure Security

### Why It Matters
- Kurumsal ağlarda kablosuz bağlantılar **en zayıf halka** olabilir.
- Yanlış yapılandırma → **Unauthorized access, signal leakage**

### Wireless Access Point (WAP) Placement
WAP yerleşimi **performans + güvenlik** açısından kritiktir.

**Best Practices**
- Dış duvarlara ve pencerelere yakın konumlandırma → ❌
- Merkezi ve yüksek noktalara (tavan) yerleştirme → ✅
- Dış duvar yakınında **unidirectional antenna** kullanımı → ✅

### Extended Service Set (ESS)
- Birden fazla WAP’in **tek bir ağ gibi** çalışması
- Büyük binalarda **seamless roaming** sağlar

### Wireless Interference
- **Co-Channel Interference**
- **Adjacent Channel Interference**
- 2.4 GHz bandında **1 – 6 – 11** kanalları tercih edilir

### Coverage Tools
- **Site Survey**: RF interference ve uygun WAP noktalarını belirler
- **Heat Maps**:
  - Signal strength
  - Coverage gaps
  - Signal leakage

---

## 🔐 Wireless Security Settings

### Wireless Encryption Standards

#### WEP
- Static key
- 24-bit IV → **Broken / Insecure**

#### WPA
- TKIP kullanır
- WEP’ten iyi ama **cryptographic attacks**’a açık

#### WPA2
- **AES + CCMP**
- Güçlü ama modern tehditlere karşı sınırlı

#### WPA3 (Recommended ✅)
- **SAE** → Offline dictionary attack koruması
- **Enhanced Open** → Open Wi-Fi’da bile encryption
- **AES-GCMP (128/192-bit)**
- **Management Frame Protection**

---

## 🔑 AAA & Authentication Protocols

### AAA
- **Authentication**
- **Authorization**
- **Accounting**

### RADIUS
- Centralized AAA
- UDP kullanır
- En yaygın çözüm

### TACACS+
- Authentication / Authorization / Accounting ayrı
- TCP + encryption
- Daha granular control

### EAP-Based Authentication
- **EAP** → Framework
- **PEAP** → TLS tunnel
- **EAP-TTLS** → Server certificate
- **EAP-FAST** → PAC + TLS

---

## 🧩 Application Security

### Input Validation
- SQL Injection, XSS, Buffer Overflow önleme
- **Client-side + Server-side**
- Defense in Depth yaklaşımı

### Secure Cookies
- `Secure`
- `HttpOnly`
- `SameSite`
- Session doğrulamada **persistent cookie kullanma**

### Code Analysis
- **SAST** → Source code, reminder
- **DAST** → Running application
  - Fuzzing
  - Stress Testing

### Code Signing
- Author & integrity doğrulama
- Malware içermediğini **garanti etmez**

### Sandboxing
- Uygulamayı izole ortamda çalıştırma
- Untrusted code execution için ideal

---

## 🧱 Network Access Control (NAC)

### Purpose
- Ağa bağlanan cihazları **önce denetle, sonra izin ver**

### NAC Process
1. Device connects
2. Security posture check
3. Pass → Network access
4. Fail → Quarantine

### NAC Agent Types
- **Persistent Agent** → Corporate devices
- **Non-Persistent Agent** → BYOD / Captive Portal

### 802.1X
- Port-based access control
- Modern NAC sistemlerinin temeli

### Rule-Based Access
- Time-based
- Location-based
- Role-based
- Adaptive NAC

---

## 🌐 Web & DNS Filtering

### Web Filtering Types
- **Agent-Based Filtering**
- **Centralized Proxy**
- **URL Scanning**
- **Content Categorization**
- **Reputation-Based Filtering**

### DNS Filtering
- Domain → IP çözümlemesini engeller
- Malware, phishing ve uygunsuz içerik engelleme

---

## ✉️ Email Security

### SPF
- Authorized sender IP check

### DKIM
- Email header’a digital signature
- Integrity + authenticity

### DMARC
- SPF + DKIM policy enforcement
- Phishing & BEC protection

### Email Gateways
- On-Prem
- Cloud-Based
- Hybrid

### Spam Filtering Techniques
- Content analysis
- Bayesian filtering
- DNS sinkhole lists
- Rule-based filtering

---

## 🖥️ Endpoint Detection & Response (EDR)

### What EDR Does
- Continuous monitoring
- Endpoint telemetry collection
- Incident response & forensics

### EDR Workflow
1. Data collection
2. Centralization
3. Threat detection
4. Alerting
5. Investigation
6. Remediation

### File Integrity Monitoring (FIM)
- Baseline vs current state
- Hash comparison
- Unauthorized change detection

---

## 🌐 Extended Detection & Response (XDR)

| Feature | EDR | XDR |
|------|-----|-----|
| Endpoint Focus | ✅ | ✅ |
| Network | ❌ | ✅ |
| Email | ❌ | ✅ |
| Cloud | ❌ | ✅ |

---

## 👤 User Behavior Analytics (UBA / UEBA)

### Core Idea
- Normal behavior baseline
- ML ile anomaly detection

### Data Sources
- Network traffic
- Logs
- Endpoints
- Applications

### Benefits
- Insider threat detection
- Early attack discovery
- Faster incident response

---

## 🔒 Selecting Secure Protocols

### Always Prefer Encrypted Versions
- HTTP → **HTTPS**
- FTP → **SFTP**
- Telnet → **SSH**
- POP3 → **POP3S**
- IMAP → **IMAPS**
- SMTP → **SMTPS**
- SNMP → **SNMPS**

### Port Selection
- Least privilege
- Only required ports open
- Security ≠ Port obscurity

### Transport Methods
- **TCP** → Reliability
- **UDP** → Speed

---

## 🧠 Exam Tips (Security+)
- WPA3 > WPA2 > WPA > WEP
- NAC ≠ Firewall
- UBA ≠ SIEM (behavior focus)
- EDR endpoint, XDR everything
- Always choose **encrypted protocol**

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
