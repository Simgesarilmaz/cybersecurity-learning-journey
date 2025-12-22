# 🔐 Hardening (System & Enterprise Security)

## 📌 Overview
**Hardening**, bir sistemin, uygulamanın veya ağın saldırılara karşı daha dayanıklı hale getirilmesi sürecidir.  
Amaç, **attack surface**’i azaltmak ve sistemin **CIA (Confidentiality, Integrity, Availability)** dengesini korumaktır.

Security+ kapsamında hardening;  
- mitigation techniques  
- system & resource security  
- enterprise capability enhancement  
başlıklarıyla doğrudan ilişkilidir.

---

## ⚙️ What is Hardening?
Hardening, varsayılan (default) ve gereksiz yapılandırmaların kaldırılarak sistemin güvenli hale getirilmesidir.

### Common Hardening Actions
- Security patch’lerin uygulanması  
- Default password’ların değiştirilmesi  
- Gereksiz servis ve port’ların kapatılması  
- Access control yapılandırmaları  
- Secure baseline oluşturulması  

🎯 **Goal:**  
Sistemin genel güvenlik duruşunu (security posture) güçlendirmek ve siber saldırılara karşı dayanıklılığı artırmak.

---

## 🔑 Default Configurations

### Default Passwords
- Ön tanımlı kimlik doğrulama bilgileri
- Kurulumdan hemen sonra **değiştirilmeli**
- 90 günde bir **rotate edilmeli**
- Password manager kullanımı önerilir

### Default Ports & Protocols
- Gereksiz açık port’lar **kapatılmalı**
- Açık port ve protokoller düzenli olarak **audit** edilmeli
- Güvensiz protokoller yerine **secure alternatives** tercih edilmeli  
  (örn: Telnet ❌ → SSH ✅)

⚠️ Default ayarlar saldırganlar tarafından **ilk hedeflenen zayıflıklardır**.

---

## 🚫 Restricting Applications (Least Functionality)

### Least Functionality Principle
- Sadece **iş için gerekli** uygulama ve servisler çalıştırılır
- Gereksiz yazılımlar:
  - kaldırılır
  - kısıtlanır
  - engellenir

📌 Zamanla sistemler gereksiz yazılımlarla şişer → attack surface büyür.

---

## 🧾 Application Control

### Application Allowlisting
- **Sadece izin verilen** uygulamalar çalışabilir
- Default = deny
- Daha **güvenli**, ama yönetimi zor

### Application Blocklisting
- Sadece **yasaklanan** uygulamalar engellenir
- Default = allow
- Daha az güvenli

💡 **Security+ yaklaşımı:**  
> *Allowlisting is more secure than blocklisting.*

---

## 🧠 Secure Baseline Images

### Secure Baseline
- Güvenli kabul edilen **başlangıç konfigürasyonu**
- Yeni sistemler bu imaj üzerinden kurulur

### İçeriği:
- Güncel OS
- Minimum gerekli uygulamalar
- Güvenli yapılandırmalar
- Güvenlik ajanları (AV, EDR)

Baseline’lar **periyodik olarak güncellenmelidir**.

---

## 🖥️ Trusted Operating Systems (TOS)

### Trusted OS Nedir?
- **Mandatory Access Control (MAC)** kullanan
- Güvenlik politikalarını sistem seviyesinde zorlayan OS’ler

### Özellikler
- MAC
- Security auditing
- Role-Based Access Control (RBAC)

### Evaluation Assurance Level (EAL)
- Common Criteria sertifikasyonu
- EAL 1 → düşük güven
- EAL 7 → en yüksek güven

### Örnekler
- SELinux  
- Trusted Solaris  

---

## 🔄 Updates & Patches

### Patch Types
- **Hotfix:**  
  Kritik güvenlik açığı → acil uygulanır
- **Update:**  
  Yeni özellik getirir, güvenlik düzeltmesi içermeyebilir
- **Service Pack:**  
  Tüm hotfix + update’lerin birleşimi

⚠️ Hacker’lar patch’leri **reverse engineer** ederek zafiyeti bulabilir.

---

## 🛠️ Patch Management

### Patch Management Nedir?
Yazılım yamalarının:
- planlanması
- test edilmesi
- uygulanması
- denetlenmesi

### Four-Step Process
1. **Planning**
2. **Testing**
3. **Implementing**
4. **Auditing**

📌 Büyük ortamlarda:
- Central update server
- Patch rings
- MDM (mobile devices)
kullanılır.

---

## 🧩 Group Policies (Windows)

### Group Policy (GPO)
- Kullanıcı ve bilgisayar hesaplarına uygulanan kurallar bütünü

### Kullanım Alanları
- Password policies
- Account lockout
- Software restrictions
- Application control

### AppLocker ile Hardening
- Allow / Deny rules
- Publisher / Path / Hash bazlı kurallar
- Secure baseline oluşturmak için kullanılır

---

## 🐧 SELinux (Security-Enhanced Linux)

### SELinux Nedir?
- Linux için **Mandatory Access Control (MAC)** mekanizması
- NSA tarafından geliştirilmiştir

### DAC vs MAC
- **DAC:** Kullanıcı kontrol eder
- **MAC:** Sistem politikası kontrol eder

### SELinux Modes
- Disabled
- Permissive
- Enforcing ✅

### Context Types
- User
- Role
- Type
- (Optional) Level

📌 SELinux log’ları **audit log**’larda tutulur.

---

## 🔐 Data Encryption Levels

### Encryption Types
- **Full Disk Encryption**
- **Partition Encryption**
- **Volume Encryption**
- **File-Level Encryption**
- **Database Encryption**
- **Record-Level Encryption**

🔑 Daha granular encryption → daha yüksek kontrol, daha fazla yönetim ihtiyacı.

---

## 📏 Secure Baselines

### Secure Baseline Nedir?
- Minimum güvenlik seviyesini garanti eden standart konfigürasyon

### Referanslar
- :contentReference[oaicite:0]{index=0}  
- :contentReference[oaicite:1]{index=1}  

### Lifecycle
1. Assessment
2. Configuration
3. Deployment
4. Monitoring
5. Maintenance

🎯 Amaç: **Consistency + Visibility + Control**

---

## 👩‍💻 User Awareness
- Secure baseline bilinci
- Yetkisiz yazılım farkındalığı
- Anomali raporlama alışkanlığı

> Security is not only technical — it’s also human.

---

## 🧠 Security+ Exam Tips
- Allowlisting > Blocklisting
- MAC ≠ DAC
- Hotfix = security
- Update ≠ patch
- Baseline = known good state

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
