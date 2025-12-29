# 🔔 Alerting and Monitoring (Security+ SY0-701)

Alerting and Monitoring, bilgi sistemlerinin **Confidentiality, Integrity ve Availability (CIA Triad)** ilkelerini korumak için kritik öneme sahiptir.  
Bu süreçler sayesinde güvenlik olayları erken tespit edilir, hızlı müdahale edilir ve riskler minimize edilir.

---

## 📌 Alerting vs Monitoring

### 🔍 Monitoring
- Sistemlerin **sürekli gözlemlenmesi**
- Anomali, performans düşüşü ve tehditlerin tespiti
- Proaktif güvenlik yaklaşımı sağlar

### 🚨 Alerting
- Belirlenen koşullar gerçekleştiğinde **bildirim üretir**
- Güvenlik ekiplerini hızlı aksiyona yönlendirir
- Email, SMS, dashboard veya ticket üzerinden iletilebilir

---

## 🚦 Types of Alerts

| Terim | Açıklama |
|------|----------|
| **True Positive** | Gerçek bir tehdidin doğru şekilde tespit edilmesi |
| **False Positive** | Tehdit olmadığı halde alarm üretilmesi |
| **True Negative** | Tehdit olmadığının doğru şekilde anlaşılması |
| **False Negative** | Gerçek tehdidin tespit edilememesi |

### 🎯 Alerting System Goals
- **True Positive** oranını artırmak  
- **False Positive** oranını azaltmak  
- **Alert Fatigue** oluşmasını önlemek

---

## 🛠 Monitoring Types

### **Automated Monitoring**
- Yazılım tabanlıdır
- Sürekli ve ölçeklenebilir
- Büyük altyapılar için uygundur

### **Manual Monitoring**
- İnsan müdahalesine dayanır
- Log inceleme ve olay analizi yapılır
- Daha fazla bağlam sağlar ancak zaman alıcıdır

---

## 📊 Monitoring Resources

### **System Monitoring**
- CPU
- Memory
- Disk Usage
- Network Performance

### **Baseline**
- Sistemin normal çalışma davranışını temsil eder
- CPU, RAM, disk ve network değerleri referans alınır
- Baseline dışına çıkılması potansiyel problemi gösterir

---

## 🧩 Alerting and Monitoring Activities

### **Log Aggregation**
- Logların merkezi bir noktada toplanması
- Olay korelasyonu ve analizini kolaylaştırır
- Incident investigation ve compliance için kritiktir

### **Alerting**
- Threshold veya anomaly bazlı çalışır
- Olası güvenlik olaylarında bildirim üretir

### **Scanning**
- Sistemlerin düzenli olarak kontrol edilmesi

**Scanning Types**
- **Vulnerability Scanning** → Bilinen zafiyetleri tespit eder  
- **Configuration Scanning** → Yanlış yapılandırmaları kontrol eder  
- **Code Scanning** → Kaynak kodda güvenlik açıklarını bulur  

---

## 📑 Reporting
- Toplanan verilerden rapor üretilir
- Performans, güvenlik ve uyumluluk durumu gösterilir
- Audit ve sürekli iyileştirme için kullanılır

---

## 🗄 Archiving
- Log ve olay verilerinin uzun süreli saklanması
- Yasal ve regülasyon gereksinimleri için zorunludur
- Cloud storage çözümleri kullanılabilir

---

## 🔄 Alert Response & Remediation

### **Alert Response**
- Alert analiz edilir
- Gerekirse escalation yapılır
- Incident Response süreci başlatılır

### **Remediation**
- Patch uygulama
- Konfigürasyon düzeltme
- Güvenlik açığını kapatma

### **Validation**
- Yapılan remediation işleminin başarılı olup olmadığını doğrulama

### **Quarantining**
- Şüpheli sistemin izole edilmesi
- Malware yayılımını önler

---

## 🎛 Alert Tuning
- Alert threshold ve kurallarının optimize edilmesi
- False Positive oranını azaltır
- SOC ekiplerinin verimliliğini artırır

---

## 🌐 SNMP (Simple Network Management Protocol)

- Network cihazlarının izlenmesi için kullanılır
- Router, Switch, Firewall, Server gibi cihazları kapsar

### **SNMP Components**
- **SNMP Manager** → Merkezi kontrol sistemi
- **SNMP Agent** → Cihaz üzerinde çalışan servis

### **SNMP Message Types**
- **GET** → Bilgi talep eder  
- **SET** → Değer değiştirir  
- **TRAP** → Olay olduğunda otomatik bildirim gönderir  

### **SNMP v3 Security**
- Authentication
- Integrity
- Confidentiality (Encryption)

---

## 🧠 SIEM (Security Information and Event Management)

- Log ve event verilerini merkezi olarak toplar
- Olayları korele eder
- Anomali ve saldırı tespiti yapar

### **Agent-Based vs Agentless**
- **Agent-Based** → Gerçek zamanlı ve detaylı veri
- **Agentless** → Daha az bakım, sınırlı detay

### **Common SIEM Solutions**
- Splunk
- ELK Stack
- QRadar
- ArcSight

---

## 🔐 Data Sources for SIEM

- Antivirus
- DLP Systems
- NIDS / NIPS
- Firewalls
- Vulnerability Scanners

---

## 📏 SCAP (Security Content Automation Protocol)

- Otomatik vulnerability management sağlar
- NIST tarafından geliştirilmiştir

### **SCAP Components**
- **OVAL**
- **XCCDF**
- **ARF**

### **Enumeration Standards**
- **CVE**
- **CPE**
- **CCE**
- **CVSS**

---

## 🌊 Network Flow Analysis

### **Flow Analysis**
- Metadata odaklıdır
- Trafik içeriğini değil, istatistikleri toplar

### **NetFlow / IPFIX**
- Network trafiğini analiz etmek için kullanılır
- Anomali ve trafik spike tespiti sağlar

### **Zeek**
- Flow + Full Packet Capture hibrit çözüm
- Şüpheli durumlarda detaylı analiz yapar

---

## 🪟 Single Pane of Glass (SPOG)

- Tüm güvenlik verilerinin tek ekranda toplanması
- SOC ekiplerinin hızlı karar almasını sağlar
- Operasyonel verimliliği artırır

---

## ✅ Özet
Alerting and Monitoring;
- Proaktif güvenlik sağlar
- Olaylara hızlı müdahale imkanı sunar
- SOC operasyonlarının temelini oluşturur

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
