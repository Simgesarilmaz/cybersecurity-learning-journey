# Vulnerabilities and Attacks  

## 1. Genel Bakış – Vulnerabilities vs Attacks

### 1.1 Vulnerability (Zafiyet) Nedir?

- **Tanım:**  
  Donanım, yazılım, konfigürasyon veya süreçlerde bulunan zayıflıklar.
- **Sonuçları:**
  - Yetkisiz erişim
  - Veri ihlali (data breach)
  - Hizmet kesintisi / sistem çökmesi

### 1.2 Attack (Saldırı) Nedir?

- **Tanım:**  
  Bir tehdit aktörünün zafiyeti istismar etmek için yaptığı kasıtlı eylem.
- **Amaç/Şekiller:**
  - Yetkisiz erişim
  - Veri hırsızlığı
  - Malware bulaştırma
  - DoS / DDoS
  - Social engineering

---

## 2. Hardware Vulnerabilities (Donanım Zafiyetleri)

### 2.1 Tanım

> Donanım bileşenleri, firmware ve fiziksel tasarımdaki zayıflıklardan kaynaklanan güvenlik açıklarıdır.

### 2.2 Donanım Tarafındaki Zafiyet Türleri

#### 2.2.1 Firmware Zafiyetleri

- Firmware = Donanım üzerinde çalışan gömülü yazılım.
- Riskler:
  - Eski / güncellenmeyen firmware
  - Güvenli geliştirilmemiş (insecure coding, imzasız güncellemeler)
  - İstismar edildiğinde cihaz üzerinde tam yetki (root / admin) elde edilebilir.

#### 2.2.2 End-of-Life (EOL), Legacy, Unsupported Sistemler

- **End-of-life:** Üretici yaşam döngüsünü bitirmiş, artık güncelleme/veri yok.
- **Legacy:** Çok eski, yeni teknoloji ile değiştirilmiş, ama hâlâ kullanılan sistemler.
- **Unsupported:**  
  Artık resmi destek, patch veya güvenlik güncellemesi yok.
- **Problem:**  
  Bilinen açıklar patch’lenmediği için kolay hedef.

#### 2.2.3 Unpatched Systems (Güncellenmemiş Sistemler)

- En son güvenlik yamalarını almamış sistemler.
- Risk nedenleri:
  - İhmal, operasyonel zorluk, downtime korkusu.
  - Zafiyetler açıkça dokümante, exploit’ler yaygın.

#### 2.2.4 Hardware Misconfigurations (Yanlış Donanım Konfigürasyonu)

- Yanlış/varsayılan ayarlar:
  - Varsayılan şifreler açıkta
  - Gereksiz servis/port açık
  - Yanlış ACL’ler, yanlış VLAN’lar
- Sebep:
  - Acele deployment, yetersiz doküman, bilgi eksikliği.

### 2.3 Donanım Zafiyetleri İçin Mitigations

- **Hardening**
  - Gereksiz servis ve portları kapat
  - Güçlü şifreler / MFA
  - Varsayılan hesapları/şifreleri değiştir veya kapat
- **Patching**
  - Firmware + OS + uygulama güncellemelerini düzenli uygula.
- **Configuration Enforcement**
  - Güvenli baseline konfigürasyonu oluştur, otomatik uygula (GPO, Ansible vs.).
- **Decommissioning**
  - EOL/legacy sistemleri planlı şekilde emekli et.
- **Isolation & Segmentation**
  - Eski veya zayıf sistemleri:
    - Ayrı VLAN / network segmentine al
    - Sadece gerekli trafiğe izin ver (firewall/ACL).

---

## 3. Bluetooth Vulnerabilities and Attacks

### 3.1 Bluetooth Kısa Özet

- Kısa mesafeli kablosuz iletişim teknolojisi.
- Riskli alanlar:
  - Güvensiz eşleştirme (insecure pairing)
  - Cihaz spoofing
  - On-path (man-in-the-middle) saldırıları

### 3.2 Bluetooth Saldırı Türleri

| Saldırı      | Özet Açıklama                                                                 |
|-------------|-------------------------------------------------------------------------------|
| **Bluejacking**  | Cihaza izinsiz mesaj gönderme (genelde şaka/test amaçlı).                |
| **Bluesnarfing** | Cihazdan rehber, SMS, çağrı kayıtları gibi verileri izinsiz çekmek.      |
| **Bluebugging**  | Cihazın Bluetooth fonksiyonlarını ele geçirmek (arama, mesaj, internet).|
| **Bluesmack**    | Bluetooth üzerinden flood/DoS; cihazı kitletme, cevap veremez hale getirme. |
| **BlueBorne**    | Kullanıcı etkileşimi olmadan havadan yayılabilen, RCE sağlayabilen saldırı ailesi. |

### 3.3 Güvenli Bluetooth Kullanımı

- Kullanmadığın zaman **Bluetooth’u kapat**.
- Varsayılan olarak **“non-discoverable”** (görünmez) modda tut.
- **Sadece tanıdığın ve güvendiğin cihazlarla** eşleştir.
- Eşleştirme sırasında **benzersiz PIN / passkey** kullan.
- **Firmware güncellemelerini** yap.
- Şüpheli bağlantı isteklerini **reddet**.
- Hassas veri aktarımında **şifreleme** kullan (ör. BLE + üst katmanda TLS).

---

## 4. Mobile Vulnerabilities and Attacks

### 4.1 Sideloading

- **Tanım:**  
  Uygulamayı resmi mağaza (Play Store / App Store) yerine üçüncü parti kaynaklardan yüklemek.
- **Risk:**  
  Zararlı içerik barındıran APK/IPA dosyaları, trojan, spyware.
- **Mitigation:**
  - Ayarlardan “unknown sources” kapalı kalsın.
  - Sadece resmi mağaza / kurumsal store üzerinden kurulum.

### 4.2 Jailbreaking / Rooting

- **Amaç:**  
  Kullanıcıya admin/root yetkisi vermek, sistem kısıtlamalarını kaldırmak.
- **Riskler:**
  - Güvenlik mekanizmalarını devre dışı bırakır.
  - Üretici güncellemeleri alınamaz / zorlaşır.
  - Kötü amaçlı uygulamalar root yetkisiyle çalışabilir.

### 4.3 Insecure Connection Methods

- **Açık Wi-Fi**, halka açık hotspotlar, bilinmeyen Bluetooth cihazları:
  - On-path saldırıları
  - Sniffing, ARP spoofing
- **Mitigation:**
  - Mümkünse **cellular data** veya VPN kullan.
  - Sadece tanıdık Wi-Fi/Bluetooth cihazlarına bağlan.
  - Güçlü, karmaşık parolalar.
  - 802.1X gibi **güçlü kimlik doğrulama** yöntemleri.

### 4.4 Mobile Device Management (MDM)

MDM ile kurum:

- **Patching:**  
  Cihazların güncelliğini zorunlu kılar.
- **Configuration Management:**  
  Standart güvenli profil (Wi-Fi, VPN, şifre politikası vs.) dayatır.
- **Best Practice Enforcement:**
  - Sideloading’i kapatma
  - Root/jailbreak tespiti
  - Zorunlu VPN / şifre / ekran kilidi

---

## 5. Zero-day Vulnerabilities

### 5.1 Kavramlar

- **Zero-day vulnerability:**  
  Geliştirici/üretici tarafından henüz bilinmeyen veya yeni öğrenilen zafiyet.
- **Zero-day exploit:**  
  Bu zafiyeti hedef alan saldırı tekniği / kodu.
- **Zero-day malware:**  
  Zero-day zafiyeti kullanan zararlı yazılım.

### 5.2 Neden Önemli?

- Henüz patch yok → savunma zor.
- Pahalı ve değerliler:
  - Bug bounty programları
  - Devlet kurumları, istihbarat örgütleri
  - Siber suç grupları
- Genelde:
  - Zero-day’ler **yüksek değerli hedefler** için saklanır.
  - Düşük seviyeli hedeflerde daha generic malware kullanılır.

### 5.3 Savunma Yaklaşımı

- **Güncel AV / EDR:** Anomali tespiti ile exploit davranışlarını yakalayabilir.
- **IPS / HIPS:** Şüpheli davranışı imza + davranış analiziyle engelleyebilir.
- **Sık patch’leme:** Zero-day → “one-day” olduktan sonra saldırıyı hızlıca kesmek için.

---

## 6. Operating System Vulnerabilities

### 6.1 Unpatched Systems

- Patch eksikliği = bilinen CVE’ler açık.
- Çözüm:
  - Otomatik güncelleme
  - Patch management süreci (test → rollout)

### 6.2 Zero-day Vulnerabilities

- OS seviyesinde henüz bilinmeyen açıklar.
- Savunma:
  - HIPS/EDR, sandbox, davranış analizi
  - Sık güncelleme + segmentasyon

### 6.3 Misconfigurations

- Örnekler:
  - Yanlış firewall kuralı
  - Geniş yetkili kullanıcı/gruplar
  - Gereksiz servisler açık
- Çözüm:
  - Configuration management tool’ları
  - Düzenli konfigürasyon denetimi (audit, hardening checklist)

### 6.4 Data Exfiltration

- Organizasyondan dışarı yetkisiz veri aktarımı.
- Savunma:
  - **Encryption** (data at rest + in transit)
  - **DLP / endpoint protection:** USB bloklama, e-posta tarama
  - Proxy, firewall log analizi

### 6.5 Malicious Updates

- Sahte update paketleri / supply chain saldırıları.
- Savunma:
  - Sadece resmi kaynaklardan update.
  - Dijital imza / hash doğrulama.
  - Application allow-list (sadece izinli yazılımlar çalışsın).

---

## 7. SQL and XML Injection Attacks

### 7.1 Injection Attack Genel

- Uygulamaya **beklenmeyen komut/veri** enjekte edilmesi.
- Hedef:  
  Uygulamanın beklenmeyen SQL/XML/komut çalıştırması.

---

### 7.2 SQL Injection

#### 7.2.1 SQL Temel İşlemler

- **SELECT** – veri okumak
- **INSERT** – veri eklemek
- **UPDATE** – veri güncellemek
- **DELETE** – veri silmek

#### 7.2.2 SQLi Nasıl Çalışır?

- Kullanıcı giriş alanları / query string / cookie / header gibi yerlerden kötü amaçlı SQL eklenir.
- Örnek mantık:
  - `‘ OR 1=1 --` ile WHERE koşulunu boşa düşürmek.
- Sonuç:
  - Tüm kayıtları listeleme
  - Kullanıcı atlama, login bypass
  - Data manipulation

#### 7.2.3 SQL Injection’a Karşı Önlemler

- **Input validation**
  - Tip, uzunluk, karakter seti kontrolü.
- **Parameterized queries / prepared statements**
  - SQL komutu ve parametreyi ayrı işlemek.
- **Stored procedures (doğru kullanılırsa)**
- **Output encoding**
- **WAF (Web Application Firewall)**

---

### 7.3 XML Injection / XXE

#### 7.3.1 XML Temel

- Veri taşıma formatı, `<tag>` yapısı.
- Genelde TLS içerisinde taşınmalı.
- Kullanıcı girdisi içeren XML, doğrulanmalı ve sanitize edilmeli.

#### 7.3.2 XML Tabanlı Saldırılar

- **XML Bomb (Billion Laughs)**
  - Aşırı büyütülen entity ile bellek / CPU tüketimi → DoS.
- **XXE (XML External Entity) Attack**
  - XML içinden sistem dosyalarına erişmeye çalışma (ör. `/etc/shadow`).
  - SSRF tarzı saldırılar da tetiklenebilir.

#### 7.3.3 XML İçin Önlemler

- Dış entity (external entity) kullanımını **devre dışı bırak**.
- Strict **input validation**.
- Parser’ı güvenli modda çalıştır.

---

## 8. XSS (Cross-Site Scripting) & CSRF (XSRF)

### 8.1 XSS – Cross-Site Scripting

#### 8.1.1 Amaç

- Güvenilir bir siteye zararlı script enjekte edip, siteyi ziyaret eden kullanıcıların tarayıcısında çalıştırmak.
- Sonuç:
  - Session cookie çalmak
  - Kullanıcı adına işlem yapmak
  - Sayfayı bozmak (defacement)

#### 8.1.2 XSS Süreci (Özet)

1. Saldırgan, input validation açığını bulur.
2. Zararlı JavaScript içeren bir payload hazırlar.
3. Site, bu script’i sanitize etmeden cevapta geri döndürür.
4. Kullanıcının tarayıcısı script’i, siteden gelmiş gibi çalıştırır.

#### 8.1.3 XSS Türleri

| Tür               | Açıklama                                                                 |
|-------------------|--------------------------------------------------------------------------|
| **Non-persistent**| Tek request/response ile tetiklenen, URL vb. üzerinden gelen XSS.       |
| **Persistent**    | Zararlı içerik DB’ye kaydedilir, her görüntülemede tekrar çalışır.      |
| **DOM-based**     | Client-side JS, DOM’u manipüle ederken zafiyet oluşur, tarayıcı taraflı.|

#### 8.1.4 XSS Mitigation

- Input validation + output encoding (HTML/JS context’e göre).
- Güvenli framework’ler ve templating.
- Content Security Policy (CSP) kullanımı.

---

### 8.2 Session Management & Cookies

- **Session:**  
  Web uygulamasının kullanıcıyı talepler arasında tanıması.
- **Cookie:**
  - Non-persistent (session cookie): tarayıcı kapanınca silinir.
  - Persistent: belli tarih/süreye kadar saklanır.

#### 8.2.1 Session Hijacking

- Saldırgan, kullanıcıya ait session ID’yi ele geçirip oturumu devralır.
- Yöntemler:
  - Sniffing, XSS, kötü tasarlanmış token’lar.

#### 8.2.2 Session Prediction

- Zayıf bir algoritma ile üretilen session ID’leri tahmin etmeye çalışma.
- Çözüm:
  - Kriptografik rastgele token üretimi.

---

### 8.3 CSRF / XSRF – Cross-Site Request Forgery

- Kurbanın tarayıcısındaki **mevcut session’ı** kullanarak hedef siteye kurban adına istek yaptırma.
- Kurban genelde linke tıklamasa bile sayfadaki img/script/tag üzerinden tetiklenebilir.

#### 8.3.1 CSRF Mitigations

- Formlarda **anti-CSRF token** (kullanıcıya özgü, tahmin edilmesi zor).
- Önemli işlemlerde:
  - Extra doğrulama (şifre tekrar girişi, 2FA).
- **SameSite cookie** ayarları.
- Parola değiştirme gibi işlemlerde:
  - Mevcut şifreyi tekrar sorma.

---

## 9. Buffer Overflow

### 9.1 Temel Kavram

- Bir buffer’a kapasitesinden fazla veri yazıldığında, komşu bellek alanları ezilir.
- Sıklıkla C/C++ tarzı dillerde görülür (bounds checking yoksa).

### 9.2 Stack ve Return Address

- Program, fonksiyon çağrıları için stack kullanır:
  - Fonksiyon parametreleri
  - Lokal değişkenler
  - Return address
- Saldırgan fazla veri göndererek:
  - Return address’in üzerine kendi seçtiği adresi yazar.
  - Program fonksiyon dönüşünde saldırganın koduna gider.

### 9.3 “Smashing the Stack” & NOP Sled

- **Smashing the stack:**  
  Return address’i saldırganın shellcode’una yönlendirme.
- **NOP slide/sled:**
  - Bellekte uzun bir NOP dizisi.
  - Return address tam olarak nereye gelirse gelsin, NOP’lar üzerinden kayarak shellcode’a ulaşır.

### 9.4 Buffer Overflow Mitigations

- **ASLR (Address Space Layout Randomization):**
  - Bellek adreslerini rastgeleleştirir.
  - Return adres tahminini zorlaştırır.
- Güvenli fonksiyonlar (strncpy vs.)
- Stack canaries, DEP (data execution prevention) gibi ek mekanizmalar.

---

## 10. Race Conditions

### 10.1 Temel Tanım

- Birden fazla thread/proces aynı kaynağa aynı anda eriştiğinde, sonuç **işlem sırasına** bağlı hale gelirse race condition oluşur.
- Saldırgan, zamanlamayı manipüle ederek beklenmeyen sonuçlar doğurabilir.

### 10.2 Önemli Terimler

- **TOC (Time of Check):** Kaynağın kontrol edildiği an.
- **TOU (Time of Use):** Kaynağın kullanıldığı an.
- **TOE (Time of Evaluation):** Sistemin karar verdiği / değerlendirdiği an.

### 10.3 Örnek

- Banka hesabı bakiyesi kontrol ediliyor (TOC).  
- Aynı anda iki işlem çekim yapıyor, kontrol sonrası çekim arada manipüle ediliyor (TOU).  
- Sonuç: Negatif bakiye, beklenmeyen davranış.

### 10.4 Dirty COW

- Linux/Android tarafında bilinen bir race condition exploit’i.
- Copy-On-Write mekanizmasındaki zamanlama hatasını istismar ederek root yetkisi kazanılabiliyordu.

### 10.5 Race Condition Mitigation

- **Locks & Mutexes:**
  - Aynı kaynağa aynı anda birden fazla erişimi engelleyen mekanizmalar.
  - Mutex = “mutually exclusive”, kod bloğuna tek thread girebilir.
- Doğru tasarlanmamış lock → **deadlock** riski:
  - İki process birbirini bekler, kilit hiç açılmaz.
- Çözüm:
  - İyi tasarlanmış eşzamanlılık (concurrency) stratejileri.
  - Kod ve test sürecinde race condition senaryolarını özellikle test etmek.

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
