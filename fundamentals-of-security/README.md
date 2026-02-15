# 🔐 Fundamentals of Security

# 1️⃣ Information Security vs Information Systems Security

## 📌 Information Security
Bilginin korunmasıdır.

Amaç: Data’yı şu durumlardan korumak:
- unauthorized access
- modification
- disruption
- disclosure
- destruction

Odak noktası: **Data**

---

## 📌 Information Systems Security
Veriyi tutan ve işleyen sistemlerin korunmasıdır:
- servers
- computers
- network devices

Odak noktası: **Systems**

Özet:
Information Security → Data  
Information Systems Security → Infrastructure

---

# 2️⃣ CIA Triad (Temel Taş)

Security+’ta her şey buraya bağlanır.

---

## 🔒 Confidentiality

Bilgi sadece yetkili kişiler tarafından erişilebilir olmalı.

### Amaç:
- protect privacy
- maintain business advantage
- regulatory compliance

### Nasıl sağlanır?
- Encryption
- Access Controls
- Data Masking
- Physical Security
- Training & Awareness

Exam Mantığı:
Unauthorized disclosure varsa → Confidentiality ihlali

---

## 🧱 Integrity

Veri doğru ve değiştirilmemiş kalmalı.

### Nasıl sağlanır?
- Hashing
- Digital Signatures
- Checksums
- Access Controls
- Regular Audits

💡 Önemli:
Digital Signature = Integrity + Authenticity + Non-Repudiation

Exam Mantığı:
Data altered → Integrity ihlali

---

## ⚡ Availability

Bilgi ve sistemler gerektiğinde erişilebilir olmalı.

### Neden önemli?
- Business continuity
- Customer trust
- Organizational reputation

### Nasıl sağlanır?
Redundancy kullanarak.

### Redundancy Türleri:
- Server Redundancy
- Data Redundancy
- Network Redundancy
- Power Redundancy

Exam Mantığı:
System down / DoS → Availability ihlali

---

# 3️⃣ Non-Repudiation

Bir kişi yaptığı işlemi inkâr edememeli.

### Nasıl sağlanır?
Digital Signatures ile.

### Süreç:
1. Message hash edilir
2. Hash private key ile encrypt edilir

Bu sayede:
- Authenticity
- Integrity
- Non-Repudiation sağlanır

---

# 4️⃣ AAA (Triple A)

Security dünyasının temel üçlüsü:

- Authentication
- Authorization
- Accounting

---

## 🔐 Authentication

"Sen gerçekten sen misin?"

### 5 Faktör:
- Something you know → password
- Something you have → token
- Something you are → biometrics
- Something you do → behavior pattern
- Somewhere you are → location

### MFA
Birden fazla faktör kullanmak.

Exam Trick:
Authentication = Identity doğrulama

---

## 🛂 Authorization

"Ne yapabilirsin?"

Authentication’dan sonra gelir.

Örnek:
- read but not write
- admin vs user permissions

Exam Trick:
Authorization = Permission belirleme

---

## 📊 Accounting

"Ne yaptın?"

User aktivitelerinin loglanmasıdır.

### Amaç:
- Audit trail
- Forensic analysis
- Compliance
- User accountability

### Kullanılan Teknolojiler:
- Syslog servers
- Network analysis tools
- SIEM systems

---

# 5️⃣ Security Controls

---

## 📦 Security Control Categories (4)

1. Technical → firewall, IDS, encryption
2. Managerial → policies, governance
3. Operational → procedures, training
4. Physical → locks, cameras

---

## 🎯 Security Control Types (6)

1. Preventive → engeller
2. Deterrent → caydırır
3. Detective → tespit eder
4. Corrective → düzeltir
5. Compensating → alternatif çözüm
6. Directive → policy ile yönlendirir

Exam’de genelde senaryo şeklinde gelir.

---

# 6️⃣ Threat – Vulnerability – Risk


## Threat
Zarar verme potansiyeli olan şey.

## Vulnerability
Sistemdeki zayıflık.

## Risk
Threat ile Vulnerability kesiştiğinde oluşur.

Formül gibi düşün:

Risk = Threat + Vulnerability

- Threat var ama vulnerability yok → Risk yok
- Vulnerability var ama threat yok → Risk yok

Tam vulnerability management mantığı.

---

# 7️⃣ Risk Management

Amaç:
- Likelihood azaltmak
- Impact azaltmak
- Desired outcome elde etmek

Security aslında risk yönetimidir.

---

# 8️⃣ Gap Analysis

Mevcut durum ile hedef durum arasındaki farkı bulmak.

### Adımlar:
1. Scope belirle
2. Mevcut durumu analiz et
3. Eksikleri belirle
4. Plan oluştur

### Türleri:
- Technical Gap Analysis
- Business Gap Analysis

### Çıktı:
POA&M (Plan of Action and Milestones)

İçerir:
- Hangi vulnerability
- Hangi çözüm
- Hangi timeline
- Hangi kaynak

---

# 9️⃣ Zero Trust

Temel prensip:

Never trust. Always verify.

Network içindeysen bile otomatik güven yok.

---

## 🧠 Control Plane

Policy karar mekanizması.

İçerir:
- Adaptive Identity
- Threat Scope Reduction
- Policy-Driven Access
- Secured Zones
- Policy Engine
- Policy Administrator

---

## 📡 Data Plane

Gerçek erişimin uygulandığı yer.

İçerir:
- Subject
- Policy Enforcement Point

---

# 🎯 Security+ İçin Hatırlanması Gerekenler

- CIA Triad her şeyin temeli.
- Risk = Threat + Vulnerability.
- Digital Signature → Integrity + Non-Repudiation.
- Authentication ≠ Authorization.
- Preventive, Detective, Corrective farkını iyi bil.
- Zero Trust = Continuous verification.


---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)
