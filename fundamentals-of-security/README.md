# Cybersecurity Fundamentals (CompTIA Security+)

Bu bölümde siber güvenliğin temel kavramları anlatılmaktadır. Notlar "CompTIA Security+ (SY0-701) Complete Course & Practice Exam" Udemy Eğitim doğrultusunda hazırlanmıştır.

---

## 1. Fundamentals of Security
- Güvenliğin temel amacı: Bilgi varlıklarını korumak.
- CIA Triad (Confidentiality, Integrity, Availability):
  - **Confidentiality (Gizlilik):** Yetkisiz erişimi engellemek.
  - **Integrity (Bütünlük):** Verinin doğru ve değişmemiş kalmasını sağlamak.
  - **Availability (Erişilebilirlik):** Yetkili kullanıcıların veriye zamanında erişebilmesi.

---

## 2. Threats and Vulnerabilities
- **Threat (Tehdit):** Sisteme zarar verebilecek olay (ör. malware, phishing).
- **Vulnerability (Zafiyet):** Sistemdeki açıklık veya zayıflık (ör. eski yazılım sürümü).
- **Exploit:** Tehdidin, zafiyeti kullanarak saldırı gerçekleştirmesi.

---

## 3. Confidentiality (Gizlilik)
- Verinin sadece yetkili kişiler tarafından görülmesini sağlamak.
- Yöntemler: Şifreleme, VPN, erişim kontrol listeleri (ACL).

---

## 4. Integrity (Bütünlük)
- Verinin doğru, tam ve değiştirilmemiş olması.
- Örnek: Hash algoritmaları (SHA256), dijital imzalar.

---

## 5. Availability (Erişilebilirlik)
- Verinin ihtiyaç duyulduğunda erişilebilir olması.
- Yöntemler: Yedekleme, yük dengeleme (load balancing), DDoS koruması.

---

## 6. Non-repudiation (İnkar Edememe)
- Bir işlemi yapan kişinin sonradan bunu reddedememesi.
- Araçlar: Dijital imzalar, loglama.

---

## 7. Authentication (Kimlik Doğrulama)
- Kullanıcının iddia ettiği kişi olduğunu kanıtlama.
- Faktörler:
  - Bildiğin şey (şifre, PIN).
  - Sahip olduğun şey (kart, token).
  - Olduğun şey (biyometri).

---

## 8. Authorization (Yetkilendirme)
- Kullanıcının hangi kaynaklara erişebileceğinin belirlenmesi.
- Örnek: RBAC (Role Based Access Control).

---

## 9. Accounting (Hesap Verebilirlik)
- Kullanıcı aktivitelerinin kayıt altına alınması.
- Araçlar: Sistem logları, SIEM çözümleri.

---

## 10. Security Control Categories
- **Administrative:** Politika, prosedür, eğitim.
- **Technical:** Firewall, IDS/IPS, şifreleme.
- **Physical:** Kilit, kamera, güvenlik görevlisi.

---

## 11. Security Control Types
- **Preventive:** Saldırıyı önlemek (ör. firewall).
- **Detective:** Olayı tespit etmek (ör. IDS).
- **Corrective:** Zararı düzeltmek (ör. patch, yedekten geri yükleme).

---

## 12. Zero Trust
- “Never trust, always verify” prensibi.
- Her erişim talebi yeniden doğrulanır.

---

## 13. Gap Analysis
- Mevcut güvenlik durumu ile hedeflenen seviye arasındaki farkın belirlenmesi.
- Örnek: Güvenlik denetiminde çıkan eksikliklerin raporlanması.

---

## 📌 Özet
Bu bölüm, siber güvenliğin temel kavramlarını içerir. CIA Triad, erişim yönetimi, güvenlik kontrolleri ve Zero Trust yaklaşımı, sonraki ileri seviye konular için temel taşlardır.
