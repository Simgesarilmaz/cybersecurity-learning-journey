# 🔐 Cryptographic Solutions


## 📘 Overview
Cryptography, verilerin gizliliğini (confidentiality), bütünlüğünü (integrity) ve kimliğini (authenticity) korumak için kullanılan şifreleme yöntemlerini kapsar.  
Kriptografi dijital güvenliğin kalbidir.

---

## 🧩 Cryptography & Encryption

| Kavram | Açıklama |
|--------|-----------|
| **Cryptography** | Kod yazma ve çözme bilimi. Şifreleme yoluyla bilginin gerçek anlamını gizler. |
| **Encryption** | Düz metni (plaintext) okunamaz hale (ciphertext) dönüştürür. |
| **Purpose** | Veriyi **at rest**, **in transit** ve **in use** durumlarında korur. |

---

## 💾 Data States

| Data State | Açıklama |
|-------------|-----------|
| **Data at Rest** | Depolama cihazlarında hareketsiz (örneğin HDD/SSD). |
| **Data in Transit** | Ağ üzerinden taşınan veri. |
| **Data in Use** | Aktif olarak işlenen veya değiştirilen veri. |

---

## 🔑 Algorithm and Key Concepts

| Kavram | Açıklama |
|--------|-----------|
| **Algorithm (Cipher)** | Şifreleme veya çözme işlemini gerçekleştiren matematiksel formül. |
| **Key** | Şifreleme sonucunu belirleyen gizli değer. |
| **Key Length** | Güvenlikle doğru orantılıdır. Uzun anahtar daha güçlü şifreleme sağlar. |
| **Key Rotation** | Anahtarların belirli aralıklarla değiştirilmesi en iyi güvenlik uygulamasıdır. |

---

## ⚖️ Symmetric vs Asymmetric Encryption

| Tür | Açıklama |
|-----|-----------|
| **Symmetric Encryption** | Aynı anahtar hem şifreleme hem çözme için kullanılır. Hızlıdır, ancak anahtar paylaşımı risklidir. |
| **Asymmetric Encryption** | Bir çift anahtar (public/private) kullanır. Güvenli anahtar değişimi sağlar ancak daha yavaştır. |
| **Hybrid Encryption** | Asimetrik yöntemle ortak anahtar paylaşılır, simetrik yöntemle veri aktarılır. Güvenli ve verimlidir. |

---

## 💠 Cipher Types

| Tür | Açıklama |
|------|-----------|
| **Stream Cipher** | Veriyi bit-bit veya byte-byte şifreler. Gerçek zamanlı veri akışı (ör. ses, video) için uygundur. |
| **Block Cipher** | Veriyi 64, 128 veya 256 bitlik sabit bloklar halinde şifreler. Yazılım tabanlı uygulamalarda yaygındır. |

---

## 🧱 Symmetric Encryption Algorithms

| Algoritma | Tür | Özellik |
|------------|-----|----------|
| **DES** | Block Cipher | 56-bit anahtar, eski ve zayıf. |
| **3DES (Triple DES)** | Block Cipher | 3 farklı anahtar (112-bit), yavaş ama daha güvenli. |
| **IDEA** | Block Cipher | 128-bit anahtar, AES’ten önce güçlü alternatifti. |
| **AES (Advanced Encryption Standard)** | Block Cipher | 128/192/256-bit anahtar, günümüz standardı. |
| **Blowfish** | Block Cipher | 32–448-bit anahtar, hızlı ama sınırlı kabul. |
| **Twofish** | Block Cipher | 128-bit blok, açık kaynaklı güçlü algoritma. |
| **RC4** | Stream Cipher | SSL/WEP’te kullanılmış, artık güvensiz. |
| **RC5 / RC6** | Block Cipher | RC4’ün geliştirilmiş sürümleri. |

---

## 🔐 Asymmetric Encryption Algorithms

| Algoritma | Kullanım | Özellik |
|------------|-----------|----------|
| **Diffie-Hellman (DH)** | Key Exchange | VPN/IPSec’te kullanılır, kimlik doğrulaması gerektirir. |
| **RSA** | Encryption / Signatures | Büyük asal sayıların çarpımına dayanır. 1024–4096 bit. |
| **ECC (Elliptic Curve Cryptography)** | Encryption / Digital Signature | Düşük güçte cihazlar için idealdir. RSA’ya göre 6× verimlidir. |

**ECC Türevleri:**
- **ECDH** – Anahtar değişimi  
- **ECDHE** – Ephemeral (oturum bazlı) anahtar  
- **ECDSA** – Dijital imza algoritması  

---

## ✉️ Digital Signatures

| İşlem | Açıklama |
|--------|-----------|
| **Hash oluşturma** | Mesajdan sabit uzunlukta bir özet çıkarılır. |
| **Private Key ile şifreleme** | Özet, göndericinin private key’i ile şifrelenir. |
| **Public Key ile doğrulama** | Alıcı, göndericinin kimliğini ve mesajın bütünlüğünü doğrular. |

🔸 Sağladığı güvenlik:
- **Integrity**  
- **Authentication**  
- **Non-repudiation**

---

## 🔢 Hashing

| Algoritma | Hash Uzunluğu | Özellik |
|------------|----------------|----------|
| **MD5** | 128-bit | Artık güvenli değildir (collision zafiyeti). |
| **SHA-1 / SHA-2 / SHA-3** | 160–512-bit | SHA-2/3 modern standartlardır. |
| **RIPEMD** | 128–320-bit | SHA alternatifidir. |
| **HMAC** | Değişken | Hash + Secret key kombinasyonu, mesaj doğrulamada kullanılır. |

---

## 🪪 Public Key Infrastructure (PKI)

**PKI**, dijital sertifikalar ve anahtar yönetimini sağlayan bir güven çerçevesidir.

| Bileşen | Açıklama |
|----------|-----------|
| **CA (Certificate Authority)** | Sertifikaları veren güvenilir kuruluş. |
| **RA (Registration Authority)** | Kullanıcı kimlik doğrulaması yapar, CA’ya iletir. |
| **CSR (Certificate Signing Request)** | Public key ve kurum bilgilerini içeren sertifika isteği. |
| **CRL (Certificate Revocation List)** | İptal edilmiş sertifikalar listesi. |
| **OCSP / OCSP Stapling** | Sertifika geçerlilik kontrolü sağlar. |

---

## 📜 Digital Certificates

| Kavram | Açıklama |
|--------|-----------|
| **Root of Trust** | Sertifika doğrulamasındaki en yüksek güven noktası (VeriSign, Google vb.). |
| **Public Key Pinning** | HTTPS sitelerinde sahte sertifikalara karşı güvenli anahtar sabitleme. |
| **Key Escrow / Recovery Agents** | Private key yedeğini saklar, kayıp durumunda kurtarma sağlar. |

---

## ⛓️ Blockchain

**Tanım:** Değiştirilemez (immutable), merkezi olmayan dijital defter.  
Veri bütünlüğü ve şeffaflık sağlar.  

| Uygulama | Açıklama |
|-----------|-----------|
| **Smart Contracts** | Şartlar sağlandığında otomatik yürütülen kod tabanlı sözleşmeler. |
| **Commercial Uses** | IBM gibi şirketler tarafından izinli (permissioned) blockchain yapılarında kullanılır. |
| **Supply Chain Management** | Ürünlerin kökeni ve hareketinin izlenmesi, şeffaflık sağlar. |

🌍 **Özellikler:**
- Versatility – Finans dışı sektörlerde de kullanılır.  
- Decentralization – Merkezi otoriteye ihtiyaç yoktur.  
- Immutable Ledger – Veriler değiştirilemez.  

---

## 🔒 Encryption Tools

| Araç | Açıklama |
|------|-----------|
| **TPM (Trusted Platform Module)** | Donanım tabanlı güvenlik çipi, BitLocker’da kullanılır. |
| **HSM (Hardware Security Module)** | Kriptografik anahtarları güvenli fiziksel ortamda tutar. |
| **Key Management Systems (KMS)** | Anahtarların yaşam döngüsünü yönetir. |
| **Secure Enclaves** | İşlemci içinde izole güvenli işlem alanı. |

---

## 🎭 Obfuscation Techniques

| Teknik | Açıklama |
|--------|-----------|
| **Steganography** | Veriyi görünürde başka bir veri içine gizler. |
| **Tokenization** | Hassas veriyi değersiz token’larla değiştirir. |
| **Data Masking** | Gerçek veriyi gizleyip test ortamlarında sahte veri oluşturur. |

---

## ⚔️ Cryptographic Attacks

| Saldırı Türü | Açıklama |
|--------------|-----------|
| **Downgrade Attack** | Sistemleri eski/zayıf protokollere zorlar (örn. POODLE – SSL 3.0). |
| **Collision Attack** | Aynı hash çıktısını üreten iki farklı girdi bulur. |
| **Birthday Attack** | Aynı hash olasılığını istismar eder. |

---

## ⚛️ Quantum Computing Threat

| Terim | Açıklama |
|-------|-----------|
| **Quantum Computing** | Qubit’lerle olağanüstü işlem gücü sağlar. |
| **Qubit** | Aynı anda 0 ve 1 olabilen bilgi birimi. |
| **Quantum Communication** | Fotondan oluşan qubit’lerle ultra hızlı, güvenli iletişim. |

**Etkileri:**
- RSA ve ECC algoritmalarını tehdit eder.  
- Klasik şifreleme kırılabilir hale gelir.  

### 🔒 Post-Quantum Cryptography (PQC)
| Kategori | Algoritmalar |
|-----------|--------------|
| **General Encryption** | CRYSTALS-Kyber |
| **Digital Signatures** | CRYSTALS-Dilithium, Falcon, SPHINCS+ |

---

## 🧭 Summary

- Cryptography → veriyi koruma sanatıdır.  
- Symmetric → hızlı, fakat anahtar dağıtımı zor.  
- Asymmetric → güvenli, fakat yavaş.  
- PKI ve Digital Certificates → güven zincirinin temelidir.  
- Blockchain → şeffaf, merkeziyetsiz güven modelidir.  
- Quantum Computing → mevcut şifrelemeye yeni bir meydan okumadır.

---

## 📝 Kriptografi Kendi Notlarım

- **Symmetric Encryption:** Aynı key hem encryption hem de decryption için kullanılır. Hızlıdır, key distribution zordur.  
  🔹 AES, TwoFish, Blowfish → Symmetric block cipher örnekleri.

- **Asymmetric Encryption (RSA):** Farklı anahtar çifti kullanır. Key distribution sorununu çözer.  
  🔹 Public key → şifreleme, Private key → çözme.

- **Hashing:** Verinin bütünlüğünü korur.  
  🔹 MD5 → collision ihtimali yüksek, güvenli değil.  
  🔹 SHA ailesi → güvenilir alternatifler.

- **Digital Signature:**  
  1️⃣ Mesajın hash’i alınır.  
  2️⃣ Bu hash sender’ın **private key**’iyle şifrelenir.  
  3️⃣ Alıcı, sender’ın **public key**’iyle doğrular.  
  🔹 Sağladığı özellikler: integrity, authentication, non-repudiation.

- **Stream Cipher:** Veriyi bit-bit veya byte-byte işler.  
- **Block Cipher:** Veriyi sabit boyutlu bloklarda işler.

- **CA (Certificate Authority):** Dijital sertifikaları oluşturur, imzalar ve doğrular.  
- **RA (Registration Authority):** Kimlik doğrulamasını yapar, CA’ya iletir.  
- **CSR:** Sertifika talep metni.  
- **OCSP:** Sertifikanın geçerliliğini kontrol eder.

- **Blockchain:** Decentralized ve immutable dijital defter.  
  🔹 Bloklar birbirine hash’lerle bağlanır.  
  🔹 Şeffaflık ve güven sağlar.

- **Post-Quantum Cryptography:** RSA ve ECC gibi algoritmaları tehdit eden quantum bilgisayarlara karşı dayanıklı yeni yöntemler.  
  🔹 Örnek: Kyber, Dilithium, Falcon.

- **AES:** Modern symmetric şifreleme standardı.  
- **DES / 3DES:** Eski, artık güvenli değil.

- **Downgrade Attack:** Sistemi eski protokollere zorlar (ör. SSL 3.0 – POODLE).  
- **Collision Attack:** Aynı hash değerini üretmek için farklı input bulma saldırısı.

- **Quantum Computers:** RSA ve ECC’yi çözebilir.  
  🔹 Çözüm → Post-Quantum algoritmalar (Kyber, Dilithium).

- **FDE (Full Disk Encryption):** Diski tamamen şifreler.  
  🔹 **TPM (Trusted Platform Module):** Donanım tabanlı güvenli anahtar saklama modülü.

- **KMS (Key Management System):** Anahtarların oluşturulması, rotasyonu ve yönetimi.  
- **HSM (Hardware Security Module):** Anahtarları fiziksel olarak koruyan güvenli donanım.

- **Data Masking:** Gerçek veriyi gizleyip test ortamında sahte veri kullanma.  
- **Tokenization:** Hassas veriyi token ile değiştirip orijinali ayrı yerde tutma.

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
