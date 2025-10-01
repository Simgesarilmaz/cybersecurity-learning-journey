# Security Controls

Bu dosya, Security+ sertifikası için çalışırken edinilen özet bilgileri içerir. Özellikle **security control türleri** ve **AAA (Authentication, Authorization, Accounting)** konularına odaklanır.

---

## 🔑 Security Control Türleri

### 1. Managerial (Administrative) Controls
- Politika, prosedür ve risk yönetimi ile ilgilenir.
- İnsanları yönlendirir, teknolojiye doğrudan bağlı değildir.
- **Örnekler:**
  - Risk assessment
  - Security policy
  - Awareness training

### 2. Operational Controls
- Günlük iş süreçleri, insanlar tarafından uygulanır.
- Sistemlerin düzgün çalışmasını sağlar.
- **Örnekler:**
  - Patch management
  - Backups
  - Incident response

### 3. Technical (Logical) Controls
- Teknoloji ve yazılım tabanlıdır.
- İnsanlardan bağımsız şekilde sistemler tarafından uygulanır.
- **Örnekler:**
  - Firewalls
  - IDS/IPS
  - Encryption
  - Antivirus

---

## 🔑 Amaca Göre Kontroller

- **Preventive (Önleyici):** Olayı başlamadan engeller.  
  *Örnek:* Firewall, Encryption, MFA

- **Detective (Tespit edici):** Olayı olduktan sonra fark eder.  
  *Örnek:* IDS, CCTV, Log monitoring

- **Corrective (Düzeltici):** Olay sonrası toparlar, düzeltir.  
  *Örnek:* Patches, Backup restore, DRP

- **Deterrent (Caydırıcı):** İnsanları saldırıdan vazgeçirir.  
  *Örnek:* Warning signs, Lighting, Security guards

- **Compensating (Telafi edici):** Asıl kontrolün alternatifi.  
  *Örnek:* UPS, Network segmentation, Sandboxing

- **Directive:** Politika ve prosedür ile yol gösterir.  
  *Örnek:* AUP, IRP, Security policies

---

## 🔑 AAA (Authentication, Authorization, Accounting)

- **Authentication (Kimlik doğrulama):** Kullanıcı veya cihazın kim olduğunu doğrulama  
  *Örnek:* Username/Password, Biometrics, MFA

- **Authorization (Yetkilendirme):** Hangi kaynaklara erişilebileceğine karar verme

- **Accounting (Hesap tutma):** Kaynak erişimini, kullanımını kayıt altına alma

### AAA Protokolleri
- **RADIUS** → AAA için kullanılan yaygın protokol
- **TACACS+** → Özellikle ağ cihazları için tercih edilir
- **CHAP, PAP, MS-CHAP** → Sadece Authentication sağlar (tam AAA değil)

---

## 🔑 Non-Repudiation (İnkâr Edememe)
- Bir işlemin yapıldığını kanıtlama, inkar edilememesi.  
- **Sağlayan mekanizmalar:** Digital signatures, Certificates  
- **İhlal eden durum:** Shared accounts (çünkü kimin yaptığını kanıtlayamazsın)

---

## 📌 Özet İpuçları

- **Policy/Education = Managerial**  
- **Daily tasks (backup, patch) = Operational**  
- **Tech (firewall, IDS) = Technical**  
- **Fix & Restore = Corrective**  
- **Korkut & Vazgeçir = Deterrent**  
- **Yerini tutan alternatif = Compensating**  
- **Kural koymak = Directive**  

---

