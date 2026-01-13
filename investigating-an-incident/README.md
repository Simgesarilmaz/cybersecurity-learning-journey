# 🧩 Investigating an Incident

---

## 🔎 Incident Investigation
Bir güvenlik olayının **ne olduğunu, nasıl gerçekleştiğini ve etkisini** anlamak için
farklı veri kaynaklarının analiz edilmesi sürecidir.

Amaç: **kanıta dayalı (evidence-based) analiz** yapmak.

---

## 🌀 Investigation Data Sources Lifecycle

### 1. Dashboards & Automated Reports
Yüksek seviyeli görünürlük sağlayan, olay incelemesinde **ilk bakılan kaynaklardır**.

**Key Terms:**
- **Dashboard:** Birden fazla sistemden gelen verileri grafiksel olarak gösteren ekran.
- **Single Pane of Glass:** Tüm güvenlik verilerinin tek ekranda toplanması.
- **Automated Report:** Sistemler tarafından otomatik oluşturulan güvenlik raporu.
- **Executive Summary:** Teknik olmayan kişiler için hazırlanan özet bölüm.

**Purpose:**  
Hızlı farkındalık, trend analizi ve önceliklendirme.

---

### 2. Vulnerability Scans
Sistemlerdeki **bilinen güvenlik açıklarını** tespit etmeye yönelik taramalardır.

**Key Terms:**
| Terim | Açıklama |
|------|----------|
| **Vulnerability Scan** | Bilinen zafiyetleri tespit eden otomatik tarama. |
| **False Positive** | Var olmayan bir zafiyetin varmış gibi raporlanması. |
| **CVE** | Her zafiyet için verilen benzersiz kimlik numarası. |
| **CVSS** | Zafiyetin ciddiyetini 0–10 arasında ölçen sistem. |

**Note:**  
Tarama sonuçları **manuel doğrulama** gerektirir.

---

### 3. Packet Captures (PCAP)
Ağ üzerinden geçen trafiğin **ham veri olarak** incelenmesini sağlar.

**Key Terms:**
- **Packet Capture (PCAP):** Ağ paketlerinin kaydedilmesi.
- **Source IP / Destination IP:** Paketin geldiği ve gittiği adres.
- **Protocol:** TCP veya UDP gibi iletişim türü.
- **Beaconing:** Belirli aralıklarla aynı hedefe yapılan bağlantılar (malware göstergesi).
- **SYN Flood:** TCP bağlantı isteğiyle yapılan DoS saldırısı.

**Goal:**  
Saldırı türünü ve iletişim desenlerini anlamak.

---

### 4. Logs (Various Types)
Olay incelemesinin **en güçlü kanıt kaynağıdır**.

**Log Types & Meanings:**
| Log Türü | Açıklama |
|--------|----------|
| **Firewall Log** | Ağa giren/çıkan trafiği kaydeder. |
| **Application Log** | Uygulama seviyesindeki olayları gösterir. |
| **Endpoint Log** | Kullanıcı cihazlarındaki aktiviteleri kaydeder. |
| **OS Security Log** | Giriş denemeleri ve yetki değişiklikleri. |
| **IDS Log** | Saldırı tespiti yapar, engellemez. |
| **IPS Log** | Saldırıyı tespit eder ve otomatik engeller. |

---

### 5. SIEM & Correlation

**SIEM (Security Information and Event Management):**  
Farklı kaynaklardan gelen logları tek yerde toplayan ve ilişkilendiren sistemdir.

**Key Concepts:**
- **Correlation:** Birden fazla olay arasında ilişki kurma.
- **Alert:** Belirlenen kurallara göre üretilen uyarı.
- **Trend Analysis:** Zaman içinde normal ve anormal davranışı ayırt etme.
- **Sensor:** Log ve veri toplayan bileşen.

**Purpose:**  
Tekil olaylardan anlamlı saldırı senaryosu çıkarmak.

---

### 6. Metadata & Evidence

**Metadata:**  
Başka bir veriyi tanımlayan veridir; içeriği değil **bağlamı** açıklar.

**Key Terms:**
| Terim | Açıklama |
|------|----------|
| **Metadata** | Verinin kimliği ve özellikleri. |
| **Timestamp** | Olayın gerçekleştiği tarih ve saat. |
| **Hash (MD5 / SHA-256)** | Dosyanın dijital parmak izi. |
| **Indicator of Compromise (IoC)** | Sistemin ihlal edildiğini gösteren kanıt. |
| **Chain of Custody** | Delilin kim tarafından nasıl işlendiğinin kaydı. |

---

### 7. Automated Response & Analysis

**Key Terms:**
- **Automated Response:** Olay tespit edildiğinde sistemin otomatik aksiyon alması.
- **Account Suspension:** Kullanıcı hesabının geçici olarak kapatılması.
- **IP Blocking:** Şüpheli IP adresinin engellenmesi.
- **Incident Analysis:** Olayın neden ve etkilerinin değerlendirilmesi.
- **Root Cause Analysis:** Olayın asıl nedenini bulma süreci.

---

## 📘 Risk-Based Investigation Perspective

| Kavram | Açıklama |
|------|----------|
| **Likelihood** | Olayın gerçekleşme olasılığı |
| **Impact** | Olayın iş üzerindeki etkisi |
| **Residual Risk** | Önlemlerden sonra kalan risk |
| **Control Effectiveness** | Kontrollerin ne kadar işe yaradığı |

---

## 💡 Exam Tips

- **Overview / Trend / Correlation** → **SIEM / Dashboard**
- **Known vulnerability** → **Vulnerability Scan**
- **Raw traffic** → **Packet Capture**
- **User activity** → **Endpoint / OS Logs**
- **Phishing analysis** → **Email Metadata**

---

## ✅ Summary

| Alan | Amaç |
|-----|------|
| **Dashboards** | Hızlı genel bakış |
| **Logs** | Kanıt toplama |
| **PCAP** | Trafik analizi |
| **SIEM** | Korelasyon ve alarm |
| **Metadata** | Bağlam sağlama |

---

📌 **Not:**  
Incident investigation tek bir kaynağa dayanmaz.  
**Doğru sonuç = doğru veri kaynaklarının birlikte kullanılmasıdır.**

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  

