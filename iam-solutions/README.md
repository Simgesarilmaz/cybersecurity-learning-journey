# Identity and Access Management (IAM) Solutions

---

# 1. Identity and Access Management (IAM)

IAM, doğru kişilerin doğru kaynaklara doğru sebeplerle ve doğru zamanda erişmesini sağlayan güvenlik çerçevesidir.

## IAM Bileşenleri
- **Password Management**
- **Network Access Control (NAC)**
- **Digital Identity Management**

---

# 2. IAAA Modeli (IAM'ın Temel Süreçleri)

### 1) Identification (Kimlik Bildirme)
- Kullanıcı kendini tanıtır  
  - Örn: Username, e-mail

### 2) Authentication (Kimlik Doğrulama)
- Kullanıcının iddia ettiği kişi olup olmadığını doğrular  
  - Parola  
  - Biyometrik  
  - MFA / Token

### 3) Authorization (Yetkilendirme)
- Kullanıcının **hangi kaynaklara, hangi seviyede** erişebileceğini belirler  
  - RBAC, ABAC, ACL

### 4) Accounting (Hesap Tutma / Loglama)
- Tüm kullanıcı aktiviteleri kayıt altına alınır  
  - Login logları  
  - Değişiklikler  
  - Erişim kayıtları

---

# 3. IAM Kavramları

## ✔ Provisioning
Yeni kullanıcı hesaplarının oluşturulması ve gerekli erişimlerin verilmesi.

## ✔ Deprovisioning
Artık erişimi olmayan kullanıcıların hesaplarının kapatılması.  
> En kritik kısım: **Orphaned accounts** bırakmamak.

## ✔ Identity Proofing
Hesap oluşturulmadan önce kimlik doğruluğunun gerçek hayat belgeleriyle ispat edilmesi.

## ✔ Interoperability
Farklı sistemlerin kimlik bilgilerini ortak standartlarla paylaşabilmesi.  
Örn: **SAML, OAuth, OpenID Connect**

## ✔ Attestation
Periyodik erişim doğrulama süreçleri (access review).  
Amaç: **Privilege creep**'i önlemek.

---

# 4. Multi-Factor Authentication (MFA)

MFA, birden fazla bağımsız doğrulama türü kullanılarak yapılan kimlik doğrulamadır.

## MFA Faktörleri
1. **Something You Know** → Parola, PIN  
2. **Something You Have** → Token, kart, telefon  
3. **Something You Are** → Biyometrik (yüz, parmak izi)  
4. **Somewhere You Are** → IP, GPS konumu  
5. **Something You Do** → Davranışsal (yazma ritmi, hareket)

## MFA Türleri
- **Single Factor** → Sadece parola  
- **2FA** → İki farklı faktör  
- **MFA** → İki veya daha fazla faktör

## MFA Uygulamaları
- Biometrics  
- Hard Token  
- Soft Token (Google Authenticator vb.)  
- Security Keys  
- Passkeys  

---

# 5. Parola Güvenliği

## Parola Politikası Özellikleri
- **Lenght** → 12–16+ karakter önerilir  
- **Complexity** → Büyük küçük harf, sayı, özel karakter  
- **Reuse** → Aynı parolanın birden fazla yerde kullanılmaması  
- **Expiration** → Zorunlu parola değiştirme süreleri  
- **Age** → Parolanın kullanım süresi

## Parola Yöneticileri (Password Manager)
- Karmaşık parola üretme  
- Otomatik doldurma  
- Şifreli kasa  
- Cihazlar arası senkronizasyon  
- Güvenli parola paylaşımı

## Passwordless Yöntemler
- Biyometrik  
- Donanım anahtarları  
- OTP / Magic link  
- Passkey (public key cryptography)

---

# 6. Parola Saldırıları

## 🔹 Brute Force
Tüm kombinasyonları deneme  
**Önleme:** MFA, deneme limiti, karmaşık parolalar

## 🔹 Dictionary Attack
Sık kullanılan parolalar listesinden deneme  
**Önleme:** Karmaşıklık, MFA, lockout

## 🔹 Password Spraying
Birçok hesapta birkaç yaygın parola denenir  
**Önleme:** Hesap kilitleme, benzersiz parolalar

## 🔹 Hybrid Attack
Dictionary + brute force kombinasyonu  
**Önleme:** Uzun parolalar, MFA

---

# 7. Single Sign-On (SSO)

Kullanıcının tek bir kimlik doğrulamasıyla birçok uygulamaya erişmesidir.

## Avantajlar
- Kullanıcı deneyimi iyileşir  
- Daha az parola → Daha az support masrafı  
- Merkezi authentication  
- Daha güçlü güvenlik politikaları

## SSO Teknolojileri
- **LDAP**
- **OAuth**
- **SAML**
- **OpenID Connect**

---

# 8. Federation

Farklı organizasyon veya sistemler arasında kimlik paylaşım mekanizmasıdır.

## Federasyon Süreci
1. Kullanıcı servis sağlayıcıya (SP) gider  
2. SP, kullanıcıyı kimlik sağlayıcıya (IdP) yönlendirir  
3. IdP kullanıcıyı doğrular  
4. IdP bir **assertion/token** oluşturur  
5. Token SP’ye gönderilir  
6. SP token’ı doğrular → Erişim verilir  
7. Kullanıcı federasyon içindeki diğer uygulamalara da erişebilir

---

# 9. Privileged Access Management (PAM)

Ayrıcalıklı kullanıcı erişimlerinin kontrolü ve izlenmesidir.

## PAM Bileşenleri
### ✔ Just-In-Time (JIT) Permissions
Yalnızca iş sırasında geçici yönetici yetkisi.

### ✔ Password Vaulting
Admin parolalarının şifreli kasada tutulması ve kayıt altına alınması.

### ✔ Temporal Accounts
Belirli süreli oluşturulmuş geçici hesaplar.

---

# 10. Access Control Modelleri

## ✔ Mandatory Access Control (MAC)
- Etiketlere (label) dayalı güvenlik modeli  
- Çok sıkı kontrol → Kullanıcı yetki değiştiremez

## ✔ Discretionary Access Control (DAC)
- Kaynak sahibinin izinleri belirlediği model  
- Esnek ama daha az güvenli

## ✔ Role-Based Access Control (RBAC)
- Roller üzerinden yetkilendirme  
- En yaygın model  
- Least privilege’ı destekler

## ✔ Rule-Based Access Control
- Kurallara ve policy’lere göre erişim kontrolü

## ✔ Attribute-Based Access Control (ABAC)
- Kullanıcı, ortam ve kaynak özelliklerine göre dinamik karar  
  - User attributes  
  - Environment attributes  
  - Resource attributes  

---

# 11. Access Control Extensions

## 🕒 Time-of-Day Restrictions
Belirli saatlerde erişim kısıtlaması.

## 🧩 Least Privilege
Kullanıcıya **işi için minimum** yetki verilmesi.

## 👥 Group Permissions
Gruplara verilen izinler → Üyelere otomatik yansır.

## 📁 File & Folder Permissions (Windows)
- Sağ tık → Properties → Security sekmesi  
- Klasöre verilen izinler alt dosyalara da uygulanır

---

# ✔ Özet

IAM:
- Kullanıcı kimliğini doğrular  
- Erişimi düzenler  
- Loglama ile izler  
- Saldırılara karşı MFA, parola politikaları ve SSO ile koruma sağlar  
- PAM ve Access Control Modelleri ile yetkileri güvenli şekilde yönetir  

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
