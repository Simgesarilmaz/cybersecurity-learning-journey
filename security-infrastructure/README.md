# Security Infrastructure (Security+ SY0-701)

## 1. Security Infrastructure & Enforcement

### 1.1 Security Infrastructure Nedir?

Kurumsal güvenlik altyapısı:

- **Bileşenler**
  - Donanım: firewall, switch, router, WAF, load balancer, sensor vs.
  - Yazılım: AV, EDR, DLP, SIEM, HIDS, agent’lar
  - Ağ (network): LAN, WAN, VPN, SD-WAN, SASE
  - Veri: DB, file server, yedekler, loglar
  - Policy & prosedür: IAM policy, password policy, incident response, change management
- **Amaç**
  - **CIA** (Confidentiality, Integrity, Availability)
  - Riskleri azaltmak, saldırı yüzeyini küçültmek

---

## 2. Firewalls (Temel – NGFW – UTM – WAF)

### 2.1 Temel Kavramlar

- **Firewall**: Trafiği **kural setine** göre **permit / deny** eden cihaz/yazılım.
- **Screened subnet** (modern DMZ):
  - İnternet ↔ (FW) ↔ **Screened subnet (public server’lar)** ↔ (FW) ↔ Internal
  - Dış saldırıyı iç network’ten yalıtmak için buffer zone.

### 2.2 Firewall Türleri

| Tür                    | Layer | Ne yapar?                                               | Not |
|------------------------|-------|---------------------------------------------------------|-----|
| Packet filtering FW    | L3/L4 | IP, port, protocol’a bakar                             | Basit, hızlı |
| Stateful FW            | L4    | Connection state (session tablosu) tutar               | Dönüş trafiğine izin |
| Proxy FW               | L5/L7 | Client adına server’a bağlanır                         | Kimliğini gizler |
| Kernel proxy FW        | Full stack | OS kernel seviyesinde derin kontrol             | Performans dostu |

### 2.3 NGFW vs UTM vs WAF

- **NGFW (Next-Generation Firewall)**
  - **Application-aware**, **Deep Packet Inspection (DPI)**, IDS/IPS entegre
  - Tek motor (single engine) kullanır
  - Diğer güvenlik ürünleriyle entegre (user ID, app ID, URL filtering)

- **UTM (Unified Threat Management)**
  - Bir kutuda “her şey”: firewall + IPS + AV + URL filtering…
  - Artı: Yönetim kolay, cihaz sayısı az
  - Eksi: **Single point of failure**, her şey bozulur → tüm koruma gider
  - Ayrı engine’ler kullanır (NGFW tek engine)

- **WAF (Web Application Firewall)**
  - Sadece **HTTP/HTTPS (L7)** trafiğine bakar
  - **XSS, SQL injection** gibi web app saldırılarını engeller
  - Konum:
    - **Inline**: Aktif engeller (prevention)
    - **Out-of-band**: Mirror trafik, sadece **detect / alert**

### 2.4 L4 vs L7 Firewall

- **L4 FW**: Port & protokol (TCP/UDP 80, 443 vs.)
- **L7 FW**: HTTP header, URL, method, payload içerik kontrolü

> 🔑 **Sınav ipucu:**  
> - “**SQL injection, XSS’ten korunma**” → **WAF**  
> - “**App-aware firewall, DPI**” → **NGFW**  
> - “**Tek kutuda firewall+IPS+AV**” → **UTM**

---

## 3. ACL ve Firewall Kuralları

- **ACL (Access Control List)**:
  - Satır satır **permit / deny** kuralları
  - **İlk eşleşen kural çalışır**, sonrasında diğerleri bakılmaz
  - Çoğu cihazda altta gizli `deny any any` (implied deny) vardır
- Kural yapısı (genel):
  - **Traffic type** (TCP/UDP, ICMP)
  - **Source IP / port**
  - **Destination IP / port**
  - **Action**: permit / deny
- Best practice:
  - En **spesifik kural üstte**, genel kural altta
  - Log’lar → özellikle **deny** kayıtları önemli

---

## 4. IDS & IPS

### 4.1 Temel Fark

- **IDS (Intrusion Detection System)**  
  - **Log + alert**, **action yok** → **out-of-band / passive**
- **IPS (Intrusion Prevention System)**  
  - **Log + alert + block/drop** → **inline / active**

> 🔑 **Sınav ipucu:**  
> - “**Inline, drop, block**” → **IPS**  
> - “**Out-of-band, sadece uyarı**” → **IDS**

### 4.2 IDS Türleri

- **NIDS**: Network IDS, segment/port mirror’dan trafiği izler
- **HIDS**: Host IDS, tek sunucu veya endpoint odaklı
- **WIDS**: Wireless IDS, rogue AP, DoS vs. tespit

### 4.3 Detection Yöntemleri

- **Signature-based**
  - Önceden bilinen imzalar (pattern match)
  - Sıfır gün (zero-day)’leri kaçırabilir
- **Anomaly-based**
  - Normal baseline ile karşılaştırır
  - Türleri: Statistical, protocol, traffic, heuristic, application-based
  - Avantaj: Zero-day yakalama şansı
  - Dezavantaj: **False positive** oranı daha yüksek

---

## 5. Network Appliances (Özel Ağ Cihazları)

- **Load Balancer**
  - Trafiği birden çok sunucuya dağıtır
  - Redundancy, availability, health check
  - Gelişmiş hali: **ADC (Application Delivery Controller)**

- **Proxy server**
  - Client ↔ Proxy ↔ Internet
  - Caching, URL filtering, auth, DLP, DDoS koruması

- **Sensors**
  - Trafiği izler, log ve metrik toplar (IDS sensörleri, NetFlow, tap’ler)
  - Performans + güvenlik görünürlüğü

- **Jump server / Jump box**
  - Admin’lerin kritik zonelara **tek noktadan** eriştiği güvenli host
  - Avantaj: Tek yerden log, audit, erişim kontrolü

---

## 6. Port Security & 802.1X

### 6.1 Port Security (Switch)

- L2 switch özelliği, **hangi MAC hangi porta bağlanabilir** kontrolü
- **CAM table**: MAC → port mapping
  - **MAC flooding** → CAM table dolunca switch hub gibi davranır
- Port security:
  - Belirli MAC’ler dışında blokla veya portu shutdown
  - **Sticky MAC**: Dinamik öğrenip konfig’e yazar
  - Zayıf nokta: **MAC spoofing**

### 6.2 802.1X ve RADIUS / TACACS+

- **802.1X**
  - Port-based network access control (NAC)
  - Roller:
    - **Supplicant**: Client cihaz
    - **Authenticator**: Switch / AP
    - **Authentication server**: Genelde **RADIUS**
- **RADIUS**
  - Uzak erişim ve network cihaz auth
  - Cross-platform, UDP, AAA sağlar (ama auth+authz kombine)
- **TACACS+**
  - Cisco proprietary
  - TCP kullanır
  - **Auth, authz, accounting** ayrıdır
  - Network device admin logini için daha detaylı kontrol

> 🔑 **Sınav ipucu:**  
> - “**Port-based network access control**” → **802.1X**  
> - “**Cisco, full AAA, TCP**” → **TACACS+**  
> - “**Dial-up/VPN user auth, UDP**” → **RADIUS**

### 6.3 EAP Türleri (Özet)

- **EAP-MD5** → Sadece password, **tek yön** auth, zayıf
- **EAP-TLS** → Client + server cert, **mutual auth**, en güvenlisi
- **EAP-TTLS** → Server cert, client password
- **EAP-FAST** → Cisco, PAC (Protected Access Credential) kullanır
- **PEAP** → TLS tünel + AD üzerinden password
- **LEAP** → Eski, Cisco proprietary, artık güvenli değil

---

## 7. Secure Network Communications (VPN, TLS, IPSec)

### 7.1 VPN Türleri

- **Site-to-site VPN**
  - İki ofis/şube arası, router/firewall üzerinden
  - İnternet üzerinden şifreli tünel
- **Client-to-site (remote access) VPN**
  - Laptop → merkez ofis
  - Full veya split tunnel
- **Clientless VPN**
  - Sadece browser (HTTPS/TLS) ile portal’a bağlanma

### 7.2 Full Tunnel vs Split Tunnel

- **Full tunnel**
  - Tüm trafik VPN’den geçer
  - Daha güvenli, lokal internet erişimi kısıtlı
- **Split tunnel**
  - Sadece kurumsal network’e giden trafik VPN’den
  - İnternet → direkt dışarı
  - Daha performanslı ama daha az güvenli

### 7.3 TLS / DTLS

- **TLS (TCP)**: HTTPS, e-mail, birçok app
- **DTLS (UDP)**: VoIP, video vs. için TLS benzeri, UDP tabanlı

### 7.4 IPSec Temel Kavramlar

- Sağladığı şeyler: **Confidentiality, Integrity, Authentication, Anti-replay**
- Kullanım: Site-to-site ve client-to-site VPN

**Modlar:**

- **Transport mode**
  - Orijinal IP header kalır, payload korunur
  - Genelde **host ↔ host** veya client-to-site
- **Tunnel mode**
  - Eski paketin tamamı yeni IP header içine gömülür
  - Genelde **site-to-site**
  - Paket büyür → MTU, fragment risk

**Başlıca protokoller:**

- **AH (Authentication Header)**
  - Integrity + auth, **şifreleme yok**
- **ESP (Encapsulating Security Payload)**
  - Encryption + integrity + anti-replay
  - Pratikte **çoğunlukla ESP** kullanılır (AH tek başına nadir)

> 🔑 **Sınav ipucu:**  
> - “**Integrity sadece, şifre yok**” → **AH**  
> - “**Encryption + integrity**” → **ESP**

---

## 8. SD-WAN & SASE

### 8.1 SD-WAN

- WAN’ı yazılımla (software-defined) yönetmek
- Farklı hatlar: MPLS, broadband, 4G/5G, microwave vs. birlikte kullanılır
- **Centralized controller**:
  - Trafik politikaya göre en uygun yoldan akar
- Avantaj:
  - Cloud servisleri (IaaS, PaaS, SaaS) ile daha iyi entegrasyon
  - Şube yönetimi daha kolay

### 8.2 SASE (Secure Access Service Edge)

- Network + security servislerini **cloud’dan** sunan mimari
- Bileşenler:
  - FWaaS, VPN, **ZTNA (Zero-Trust Network Access)**, **CASB**
- Amaç:
  - Dağıtık kullanıcıları (office, home, remote) **aynı güvenlik policy** ile korumak
- Örnek bulut bileşenler:
  - AWS VPC, Azure Virtual WAN / ExpressRoute, Google Cloud Interconnect/VPN

> 🔑 **Sınav ipucu:**  
> - “**Cloud-based, network + security together, zero-trust, CASB**” → **SASE**  
> - “**Branch’ler arası WAN optimizasyonu, çoklu link**” → **SD-WAN**

---

## 9. Infrastructure Design Considerations

### 9.1 Device Placement & Zones

- **Edge router / firewall**: İnternet ile iç network arasındaki sınır
- **Screened subnet / DMZ**: Public service’ler (web, mail relay, reverse proxy)
- İç zonelar:
  - User LAN, server LAN, management network, OT/SCADA zonelar
- Amaç: Segmentasyon + minimal trust

### 9.2 Attack Surface

- Saldırganın temas edebileceği tüm noktalar:
  - Açık portlar, servisler, API’ler, user account’lar, web form’lar
- Reduce attack surface:
  - Gereksiz servisleri kapat
  - Gereksiz portları kapat
  - Default account’ları disable

### 9.3 Connectivity & Device Attributes

- **Wired (Ethernet)**: Stabil, hızlı, ama daha az esnek
- **Wireless (Wi-Fi)**: Esnek ama parazit ve güvenlik konuları (WPA3 vs.)
- **Active vs Passive device**
  - **Active**: Trafiğe müdahale eder (IPS, FW)
  - **Passive**: Sadece izler (IDS sensor, tap)
- **Inline vs tap/monitor**
  - Inline: Path üzerinde, bozulursa trafiği kesebilir
  - Tap/SPAN: Trafiği kopyalar, asıl yolu bozmaz

### 9.4 Failure Mode (Fail-open vs Fail-closed)

- **Fail-open**
  - Cihaz bozulduğunda trafik serbest geçer
  - Avantaj: Availability
  - Dezavantaj: Security düşer
- **Fail-closed**
  - Cihaz bozulduğunda trafik kesilir
  - Avantaj: Security
  - Dezavantaj: Servis kesintisi

> 🔑 **Sınav ipucu:**  
> - Safety-critical yerler (core banking, OT) → genelde **fail-closed**  
> - Availability çok önemli ama risk daha düşükse → **fail-open** düşünülebilir

---

## 10. Selecting Infrastructure Controls

### 10.1 Temel Prensipler

- **Least Privilege**
  - Kullanıcı/sistem sadece ihtiyacı kadar yetki
- **Defense in Depth**
  - Tek kontrol yerine **birden fazla katman** (FW + IDS/IPS + AV + EDR + DLP)
- **Risk-based approach**
  - Kaynakları en kritik risklere yönlendir
- **Lifecycle Management**
  - Kontrolleri düzenli review, update, retire
- **Open Design**
  - Güvenlik, gizli algoritmaya değil sağlam tasarıma dayanmalı (Kerckhoffs)

### 10.2 Metodoloji (Kısaltılmış Akış)

1. **Current state**: Mevcut altyapı + zayıflıkları anla
2. **Gap analysis**: Olması gereken ile mevcut arasındaki fark
3. **Objectives**: Uptime, data protection, compliance, vs.
4. **Benchmark**: NIST, ISO 27001 gibi framework’lerle karşılaştır
5. **Cost-benefit**: Güvenlik seviyesi vs. bütçe/operasyon yükü
6. **Stakeholder**: İş birimleri, IT, security, legal ile alignment
7. **Monitor & feedback**: Sürekli iyileştirme (continuous improvement)

---

## 11. Ports & Protocols – Mini Cheat Sheet

| Port | Protocol(s)                        | Tipik Kullanım                    |
|------|------------------------------------|-----------------------------------|
| 21   | FTP (TCP)                          | File transfer (unencrypted)       |
| 22   | SSH, SCP, SFTP (TCP)              | Secure remote / file transfer     |
| 23   | Telnet (TCP)                      | Eski remote shell (insecure)      |
| 25   | SMTP (TCP)                        | Mail gönderme                     |
| 53   | DNS (TCP/UDP)                     | İsim çözümleme                    |
| 69   | TFTP (UDP)                        | Basit file transfer, no auth      |
| 80   | HTTP (TCP)                        | Web                               |
| 88   | Kerberos (UDP)                    | AD authentication                 |
| 110  | POP3 (TCP)                        | Mail alma                         |
| 119  | NNTP (TCP)                        | Usenet                            |
| 135  | RPC (TCP/UDP)                     | Windows RPC                       |
| 137–139 | NetBIOS (TCP/UDP)             | Eski Windows file/printer share   |
| 143  | IMAP (TCP)                        | Mail alma                         |
| 161  | SNMP (UDP)                        | Network device management         |
| 162  | SNMP Trap (UDP)                  | SNMP alarm/notification           |
| 389  | LDAP (TCP)                        | Directory service                 |
| 443  | HTTPS (TCP)                       | Secure web                        |
| 445  | SMB (TCP)                         | Windows file share                |
| 465/587 | SMTPS (TCP)                   | Secure SMTP                       |
| 514  | Syslog (UDP)                      | Log gönderimi                     |
| 636  | LDAPS (TCP)                       | Secure LDAP                       |
| 993  | IMAPS (TCP)                       | Secure IMAP                       |
| 995  | POP3S (TCP)                       | Secure POP3                       |
| 1433 | MS-SQL (TCP)                      | Microsoft SQL Server              |
| 1645/1646 | RADIUS (TCP)                | RADIUS eski portları              |
| 1812/1813 | RADIUS (UDP)                | RADIUS auth/accounting            |
| 3389 | RDP (TCP)                         | Windows remote desktop            |
| 6514 | Syslog over TLS (TCP)            | Encrypted syslog                  |

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  

