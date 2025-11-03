# 🧩 Asset and Change Management (SY0-701)

## 🧱 Asset Management

> Organizasyonun sahip olduğu tüm varlıkların (assets) yaşam döngüsü boyunca yönetilmesi, izlenmesi ve korunması sürecidir.

### 🔹 Main Goals
- Asset’lerin değerini **maksimum**, riskini **minimum** tutmak  
- Tüm varlıklarda **ownership (sahiplik)** ve **accountability (sorumluluk)** sağlamak  
- **MDM (Mobile Device Management)** veya benzeri çözümlerle merkezi yönetim yapmak  

---

### 🔸 Asset Lifecycle
| Aşama | Açıklama |
|--------|-----------|
| **Acquisition & Procurement** | Güvenlik gereksinimlerine uygun donanım / yazılım temini |
| **Assignment / Tracking** | Kime ait, nerede, hangi amaçla kullanılıyor netleştirme |
| **Monitoring** | Envanter kontrolü ve MDM izleme |
| **Disposal / Decommissioning** | Veri silme, imha, sertifikasyon süreçleri |

🧭 *Her asset için unique ID ve owner tanımlanması önemlidir.*

---

## 🧩 Asset Classification & Tracking

- **Tangible Assets:** Donanımlar, makineler, bilgisayarlar  
- **Intangible Assets:** IP, marka değeri, reputation  
- **Categorization:**  
  - High-value → sıkı bakım & güvenlik  
  - Low-value → reuse / recycle olabilir  

**Tracking Methods:**  
- Inventory check  
- MDM & monitoring tools  
- Enumeration (envanter sayımı)

> 📱 MDM çözümleri cihaz kaybı, policy enforcement ve uzaktan wipe imkanı sağlar.

---

## 🔐 Asset Disposal & Sanitization  
**Referans:** *NIST SP 800-88 – Guidelines for Media Sanitization*

| Method | Açıklama | Durum |
|---------|-----------|--------|
| **Overwriting** | Veriyi random bitlerle yeniden yazar (1-35 pass) | Reusable |
| **Degaussing** | Manyetik alanla veriyi yok eder | Device unusable |
| **Secure Erase** | Firmware seviyesinde silme | Reusable |
| **Cryptographic Erase (CE)** | Şifre anahtarını siler, veriyi erişilemez yapar | Fast & safe |
| **Destruction** | Fiziksel imha: shred, melt, incinerate | Permanent |

🧾 **Certification:**  
İmha işleminin belgelenmesi ve denetim kayıtlarının tutulması.  
📦 **Data Retention:**  
Yasal, operasyonel veya analiz gerekliliği kadar veri tutulmalı.

> ⚠️ Fazla veri = fazla güvenlik yükü. “The more you store, the more you must secure.”

---

## 📱 Mobile Asset Deployments

| Model | Açıklama | Avantaj | Dezavantaj |
|--------|-----------|----------|-------------|
| **BYOD** | Çalışan kendi cihazını getirir | Maliyet düşük | Güvenlik kontrolü az |
| **COPE** | Şirket cihazı, kişisel kullanım serbest | Güvenlik yüksek | Maliyet yüksek |
| **CYOD** | Onaylı cihaz listesinden seçim | Denge sağlar | Gizlilik endişesi olabilir |

💡 **Seçim kriteri:** Güvenlik seviyesi, bütçe ve kullanıcı memnuniyeti.

---

## 🔄 Change Management

> Değişikliklerin kontrollü, planlı ve izlenebilir şekilde yapılmasını sağlar.  
> Amaç: **disruption olmadan gelişim.**

### 🔹 Why Important?
- Plansız değişiklik → downtime, data loss, security gap  
- CAB (Change Advisory Board) → değişiklikleri onaylayan kurul  
- Backout plan + test zorunludur  

---

### 🔸 Change Management Steps

1️⃣ **Prepare for Change** → Mevcut durumu analiz et, ihtiyaçları belirle  
2️⃣ **Create Vision** → Hedef durumu ve başarı kriterlerini tanımla  
3️⃣ **Implement** → Eğitim, yapılandırma, iletişim  
4️⃣ **Verify** → Ölç, test et, stakeholder feedback al  
5️⃣ **Document** → Her aşamayı kayda al ve lessons learned oluştur  

> 🧩 *Structured plan = minimum risk + maximum accountability*

---

## ⚙️ Technical Implications of Change

- **Allow / Deny Lists** → Erişim izinleri değişmeden kontrol edilmeli  
- **Downtime Risk** → Maintenance window içinde planla  
- **Service Restarts** → Patch sonrası restart planı oluştur  
- **Legacy Systems** → Eski uygulamalarda dependency kontrolü  
- **Dependencies** → Bağlı sistemlerin etkisi analiz edilmeli  

---

## 🧾 Documenting Changes

**Amaç:** Tüm değişikliklerin *ne, ne zaman, neden* yapıldığının kayıt altına alınması

📘 İçerik:
- Güncel diyagramlar  
- Revize edilmiş prosedürler  
- Change request & ticket güncellemeleri  

> 🔁 Continuous Improvement → her değişiklik sonrası süreç gözden geçirilmeli

---

## 🧠 Quick Notes

- CAB = Change Advisory Board  
- SOP = Standard Operating Procedure  
- CE = Cryptographic Erase  
- MDM = Mobile Device Management  
- NET15 / NET30 = ödeme vadeleri  
- Change Owner = Değişiklik talebini başlatan kişi / ekip  

---

### ✅ Summary

**Asset Management:**  
> Envanter → İzleme → Koruma → Güvenli İmha  

**Change Management:**  
> Planla → Onay Al → Uygula → Test Et → Dokümante Et  

📍 *Discipline + Documentation = Security Integrity*

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
