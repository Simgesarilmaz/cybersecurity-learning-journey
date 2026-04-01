# Incident Response (IR)

Incident Response (IR), bir güvenlik olayını **tespit etmek, kontrol altına almak, ortadan kaldırmak ve sistemleri güvenli şekilde eski haline döndürmek** için kullanılan sistematik yaklaşımdır.

---

## 🎯 Incident Response Amaçları
- Etkiyi (impact) en aza indirmek
- Tespit (detection) ve containment süresini kısaltmak
- İş sürekliliğini sağlamak
- Güvenli kurtarma (recovery) sağlamak
- Gelecekteki olayları önlemek

---

## 🔑 Temel Incident Response Aktiviteleri
- Detection (Tespit)
- Classification (Sınıflandırma)
- Containment (Kontrol altına alma)
- Eradication (Temizleme)
- Recovery (Kurtarma)
- Evidence Preservation (Delil koruma)
- Communication (İletişim)
- Lessons Learned (Ders çıkarma)

---

## 🔄 Incident Response Süreci (CompTIA – 7 Faz Modeli)

CompTIA, klasik 4 fazlı modeli genişleterek **7 fazlı** bir yapı kullanır.

### 1️⃣ Preparation
- Politikalar, prosedürler ve IR planları oluşturulur
- Sistem hardening yapılır
- İletişim planı hazırlanır
- Incident Response Team (IRT) belirlenir

📌 *Amaç: Olay olmadan önce hazır olmak*

---

### 2️⃣ Detection
- Güvenlik olayının olup olmadığı belirlenir
- SIEM, IDS/IPS, EDR, loglar kullanılır
- Olay ilk kez tespit edilir

📌 *“Bir şey oluyor mu?” sorusunun cevabı*

---

### 3️⃣ Analysis
- Olayın kapsamı ve etkisi analiz edilir
- Hangi sistemler etkilendi?
- Ne kadar ciddi?

📌 *Stakeholder’lar bilgilendirilir*

---

### 4️⃣ Containment
- Saldırının yayılması engellenir
- Etkilenen sistemler izole edilir
- İş sürekliliği korunur

📌 *Amaç: Hasarı büyütmemek*

---

### 5️⃣ Eradication
- Zararlı yazılım, arka kapılar, exploitler temizlenir
- Gerekirse sistem reimage edilir

📌 *Containment’ten sonra başlar*

---

### 6️⃣ Recovery
- Sistemler güvenli şekilde tekrar ayağa kaldırılır
- Backup’lardan geri dönülür
- Patch ve konfigürasyonlar güncellenir

📌 *Normal operasyonlara dönüş*

---

### 7️⃣ Post-Incident Activity
- Root Cause Analysis (RCA)
- Lessons Learned
- After-Action Report hazırlanır
- IR planları güncellenir

---

## 🧠 Root Cause Analysis (RCA)

**Amaç:** Olayın *neden* olduğunu anlamak ve tekrarını önlemek

### RCA Adımları
1. Incident’i tanımla ve kapsamını belirle
2. Nedensel ilişkileri analiz et
3. Etkili çözümleri belirle
4. Çözümleri uygula ve takip et

### 🔹 No-Blame Yaklaşımı
- Kişi suçlamak yerine süreci iyileştirmeye odaklanır
- Açık ve dürüst raporlama teşvik edilir

---

## 🕵️ Threat Hunting

**Proaktif** güvenlik yaklaşımıdır. Alarm beklemeden tehdit aranır.

### Threat Hunting Amaçları
- Gizli ve henüz tespit edilmemiş tehditleri bulmak
- Yeni TTP’leri (Tactics, Techniques, Procedures) keşfetmek

### Threat Hunting Adımları
1. Hipotez oluşturma
2. Threat actor profilleme
3. Log, sistem, registry ve ağ verisi analizi
4. Yeni saldırı tekniklerini keşfetme

📌 *“Varsayım: Sistem zaten compromise olmuş olabilir”*

---

## 👥 Incident Response Team (IRT)

### Çekirdek Roller
- Team Leader
- Subject Matter Experts (SME)
- IT Support
- Legal Counsel
- HR
- Public Relations

📌 Büyük kurumlarda **full-time**, küçüklerde **olay bazlı** ekipler bulunur.

---

## 🧪 Incident Response Training & Testing

### Eğitim (Training)
- Rol bazlı eğitimler
- End-user farkındalık eğitimi
- Önceki olaylardan ders çıkarma

### Test Türleri
- Tabletop Exercise (TTX)
- Simulation
- Drills
- Live Exercises
- Penetration Test

---

## 🔬 Digital Forensic Procedures

### Dijital Adli Bilişim Amaçları
- Delil toplamak
- Hukuki süreçlere destek olmak
- Olayı teknik olarak aydınlatmak

---

### 🔍 Digital Forensics Fazları

#### 1️⃣ Identification
- Olay yeri güvenliği
- Delil kaynaklarının belirlenmesi

#### 2️⃣ Collection
- Yetkilendirme şarttır
- **Order of Volatility** uygulanır

#### 3️⃣ Analysis
- Forensic image üzerinden analiz
- Timestamp, kullanıcı aktiviteleri incelenir

#### 4️⃣ Reporting
- Bulgular detaylı raporlanır
- Mahkemede delil olarak kullanılabilir

---

## ⏳ Order of Volatility (En Önemli Sınav Konusu!)

1. CPU registers & cache
2. RAM, process table, ARP cache
3. Disk / persistent storage
4. Network logs
5. Physical configuration
6. Archival data

⚠️ **Not:**  
Bazı Windows registry anahtarları (örn. `HKLM\Hardware`) sadece RAM’dedir.

---

## 📀 Evidence Collection Teknikleri
- Disk Imaging (bit-by-bit)
- File Carving
- Hashing
- Screenshot alma
- Network logları
- CCTV kayıtları

---

## ⚖️ Hukuki Kavramlar
- **Chain of Custody**: Delilin kimde, ne zaman, nasıl tutulduğunun kaydı
- **Legal Hold**: Dava ihtimali varsa verinin korunması
- **E-Discovery**: Elektronik verinin hukuki süreç için toplanması

---

## 🧾 Data Acquisition
- Forensically sound kopya alma süreci
- BYOD ortamlarında hukuki zorluklar olabilir
- Bazı veriler sadece sistem kapatıldığında alınabilir

---

## 📌 Sınav İpuçları (Security+)
- Order of Volatility → **RAM her zaman diskten önce**
- Recovery ≠ Eradication
- RCA = suçlama değil, çözüm
- Threat Hunting = **proaktif**
- Forensic analysis **orijinal disk üzerinde yapılmaz**

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
