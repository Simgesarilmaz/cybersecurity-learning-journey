# 🛡️ Data Protection (Veri Koruma)

## 🔒 Data Protection Overview
Data Protection: Verilerin **bozulma (corruption)**, **yetkisiz erişim (compromise)** veya **kaybolma (loss)** durumlarına karşı korunması sürecidir.  
Amaç, **Confidentiality (Gizlilik)**, **Integrity (Bütünlük)** ve **Availability (Erişilebilirlik)** ilkelerinin korunmasını sağlamaktır.

---

## 🗂️ Data Classification (Veri Sınıflandırması)

**Data Classification:** Verilerin değerine ve hassasiyetine göre sınıflandırılması işlemidir. Bu sayede uygun koruma önlemleri belirlenir.

### Types of Data:
- Sensitive  
- Confidential  
- Public  
- Restricted  
- Private  
- Critical  

---

### 🏢 Commercial Business Classification Levels
| Level | Açıklama |
|-------|-----------|
| **Public** | Herkese açık, yayınlanmasında risk bulunmayan veri. |
| **Sensitive** | Yayınlanması düşük etkilere yol açabilecek veriler (ör. finansal raporlar). |
| **Private** | Kişisel veya çalışan bilgilerini içeren veriler. |
| **Confidential** | Ticari sır, kaynak kod veya fikri mülkiyet barındıran veriler. |
| **Critical** | En yüksek düzeyde koruma gerektiren, operasyonel açıdan kritik veriler. |

---

### 🏛️ Government Classification Levels
| Level | Açıklama |
|-------|-----------|
| **Unclassified** | Kamuya açık bilgiler. |
| **Sensitive but Unclassified** | Personel veya sağlık dosyaları gibi orta düzey hassasiyet. |
| **Confidential** | Devlet operasyonlarını etkileyebilecek bilgiler. |
| **Secret** | Askerî planlar veya stratejik savunma bilgileri. |
| **Top Secret** | En yüksek gizlilik seviyesindeki ulusal güvenlik verileri. |

---

### Importance of Data Classification
- Kaynakların doğru şekilde tahsis edilmesini sağlar.  
- Aşırı sınıflandırmayı önleyerek gereksiz maliyetleri düşürür.  
- Verilerin doğru şekilde yönetilmesini ve korunmasını kolaylaştırır.  

---

## 👥 Data Ownership Roles (Veri Sahipliği Rolleri)

| Rol | Açıklama |
|-----|-----------|
| **Data Owner** | Verinin gizliliği, bütünlüğü ve erişilebilirliğinden sorumlu kişidir. |
| **Data Controller** | Verinin toplanması, işlenmesi ve saklanma yöntemini belirler. |
| **Data Processor** | Veriyi, data controller adına işleyen kişi veya kurumdur. |
| **Data Steward** | Verinin doğruluğunu, etiketlemesini ve kalitesini sağlar. |
| **Data Custodian** | Verinin bulunduğu sistemleri yönetir; erişim kontrolü ve yedekleme yapar. |
| **Privacy Officer** | PII veya PHI gibi kişisel verilerin yasalara uygun şekilde işlendiğinden emin olur. |

> ⚠️ Not: Veri sahipliği genellikle **iş birimleri** tarafından yapılmalıdır.  
> IT departmanı yalnızca teknik koruma ve erişim yönetiminden sorumludur.

---

## 💾 Data States (Veri Durumları)

**Data at Rest:** Disk, veritabanı veya depolama ortamında saklanan veridir.  
🔹 Koruma yöntemleri: Full Disk Encryption (FDE), File Encryption, Database Encryption  

**Data in Transit:** Ağ üzerinden iletilen, hareket halinde olan veridir.  
🔹 Koruma yöntemleri: SSL/TLS, VPN, IPSec  

**Data in Use:** Uygulama tarafından aktif olarak kullanılan veya işlenen veridir.  
🔹 Koruma yöntemleri: Application-level Encryption, Access Control, Secure Enclaves  

---

## 🧩 Data Types (Veri Türleri)

| Tür | Açıklama |
|-----|-----------|
| **Regulated Data** | GDPR veya HIPAA gibi yasal düzenlemelere tabi verilerdir. |
| **PII (Personally Identifiable Information)** | Kişiyi tanımlayabilecek bilgilerdir (isim, adres, TC no). |
| **PHI (Protected Health Information)** | Kişinin sağlık durumu, hizmeti veya ödeme bilgileriyle ilgili verilerdir. |
| **Trade Secrets** | Ticari sırları, üretim süreçlerini veya stratejileri içeren verilerdir. |
| **Intellectual Property (IP)** | Patent, telif hakkı, tasarım veya kaynak kod gibi fikri mülkiyet verileridir. |
| **Legal Information** | Hukuki sözleşme, dava veya düzenleyici dokümanlardır. |
| **Financial Information** | Mali kayıtlar, banka hesap bilgileri veya vergi belgeleridir. |
| **Human vs Non-Human Readable Data** | İnsan tarafından okunabilir (metin) veya makine tarafından okunabilir (binary) verilerdir. |

---

## 🌍 Data Sovereignty (Veri Egemenliği)

**Data Sovereignty:** Veriler, bulundukları ülkenin yasal düzenlemelerine tabidir.  
Örneğin;  
- **GDPR (AB):** Verilerin AB sınırları dışında işlenmesini sınırlar.  
- **Yerel Yasalar (Çin, Rusya):** Verilerin ülke içinde depolanmasını zorunlu kılar.  
- **ABD:** HIPAA, CCPA gibi sektörel temelli veri yasaları uygulanır.  

> 🌐 Bulut ortamlarında farklı ülkelerde depolanan veriler yasal uyumluluk açısından karmaşık durumlar oluşturabilir.

---

## 🧠 Securing Data Methods (Veri Güvenliği Yöntemleri)

| Yöntem | Açıklama |
|--------|-----------|
| **Encryption** | Verinin gizliliğini sağlamak için şifreleme yöntemidir. |
| **Hashing** | Veriyi geri döndürülemez özet haline getirir (ör. parola koruması). |
| **Masking** | Verinin bir kısmını gizleyerek anonimleştirir. |
| **Tokenization** | Hassas veriyi rastgele token ile değiştirir. |
| **Obfuscation** | Veriyi kasıtlı olarak anlaşılmaz hale getirir. |
| **Segmentation** | Ağı bölerek olası saldırıların yayılmasını önler. |
| **Geofencing** | Belirli coğrafi bölgeler dışında erişimi engeller. |
| **Permission Restriction** | Yetkisiz erişimi önlemek için ACL veya RBAC uygular. |

---

## 🚫 Data Loss Prevention (DLP)

**Data Loss Prevention:** Kurum dışına hassas verilerin çıkmasını engelleyen stratejidir.  
DLP sistemleri veriyi üç durumda izler:  
- **In Use:** Kullanımda olan veri  
- **In Transit:** İletim halindeki veri  
- **At Rest:** Depolanan veri  

### Types of DLP Systems
| Tür | Açıklama |
|-----|-----------|
| **Endpoint DLP** | Kullanıcı cihazlarındaki veri hareketlerini izler. |
| **Network DLP** | Ağ trafiğini analiz ederek veri sızıntılarını tespit eder. |
| **Storage DLP** | Sunucu veya veri merkezlerindeki verileri denetler. |
| **Cloud-Based DLP** | Bulut servislerinde depolanan verileri korur. |

---

## 🧾 Summary

| Konu | Anahtar Kavram |
|-------|----------------|
| **Data Classification** | Verilerin hassasiyetine göre sınıflandırılması. |
| **Data Ownership** | Veri sorumlularının görev ve rollerinin belirlenmesi. |
| **Data States** | Verinin durumuna göre (rest, transit, use) korunması. |
| **Data Sovereignty** | Verilerin bulunduğu ülkenin yasalarına uyum sağlanması. |
| **Data Security Methods** | Şifreleme, hash, tokenization, masking gibi yöntemler. |
| **DLP** | Veri sızıntılarını önlemeye yönelik strateji ve araçlar. |

---

> 📚 **Kaynak:** [Dion Training - CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
