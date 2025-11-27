# 🌐 Domain 3 – Security Architecture

## 🧱 3.1 Security Architecture Temelleri

### 🔐 Security Architecture Nedir?
Bir kurumun bilgi güvenliği ortamının:
- Tasarımını  
- Yapısını  
- Davranışını  

belirleyen genel mimaridir. Güvenlik kontrollerinin **nerede ve nasıl** uygulanacağını açıklar.

---

# 🏢 On-Premise vs ☁️ Cloud vs 🔄 Hybrid

## 🏢 On-Premise (Yerinde Çözümler)
Altyapı tamamen kurum içindedir.

**Avantajlar**
- Tam kontrol  
- Özelleştirilebilir güvenlik  

**Dezavantajlar**
- Yüksek maliyet  
- Patch, bakım, donanım yenileme kurum sorumluluğunda  
- Ölçeklenebilirlik sınırlı  

---

## ☁️ Cloud Computing (Bulut)
Kaynaklar internet üzerinden sağlanır.

**Avantajlar**
- Hızlı kurulum  
- Esneklik ve otomatik ölçeklenebilirlik  
- Daha düşük başlangıç maliyeti  

**Riskler**
- Multi-tenancy (paylaşımlı altyapı)  
- Vendor lock-in  
- Sınırlı kontrol  

---

## 🔄 Hybrid Solutions
On-premise + cloud birlikte kullanılır.

**Dikkat Edilmesi Gerekenler**
- Hassas verilerin doğru ortamda tutulması  
- Uyumluluk ve regülasyon şartları  
- Ortamlar arası entegrasyon  
- Maliyet optimizasyonu  

---

## ☁️ Cloud Mimarisinde Önemli Kavramlar
- **Availability:** Erişilebilirlik  
- **Resilience:** Arıza sonrası toparlanma  
- **Scalability:** Yük artınca büyüyebilme  
- **Responsiveness:** Talebe hızlı yanıt  
- **Risk Transference:** Bazı risklerin CSP’ye devredilmesi  
- **Power/Compute:** Donanım yönetimi CSP tarafında  

---

# ☁️ Cloud Security Riskleri

## Shared Physical Server (Multi-Tenancy)
Aynı fiziksel host üzerinde birden fazla müşteri bulunur.

**Risk:** İzolasyon ihlali, VM escape  
**Önlem:** Hypervisor hardening, izolasyon testleri

---

## Inadequate Virtual Environment Security
Zayıf VM güvenlik ayarları → yetkisiz erişim

**Önlem:** Secure VM templates, patching, segmentation

---

## User Access Management Zafiyetleri
IAM hataları cloud’daki en büyük risklerdendir.

**Önlem:** MFA, Least Privilege, RBAC, audit logs

---

## Lack of Up-to-date Measures
Güncel olmayan sistemler → saldırılara açık

**Önlem:** Patch management, policy güncellemeleri

---

## Single Point of Failure
Tek kaynak çökmesi tüm servisi etkileyebilir.

**Önlem:** Redundancy, multi-AZ, multi-region

---

## Weak Authentication & Encryption
Zayıf şifreleme → veri kaybı ve sızıntı

**Önlem:** MFA, güçlü encryption (at rest / in transit), KMS/HSM

---

## Data Remnants
Silinen verinin tamamen yok olmaması.

**Önlem:** Secure deletion, encrypted storage, key destruction

---

# 🖥️ Virtualization & 📦 Containerization

## Virtualization (Sanallaştırma)
Tek fiziksel sunucu üzerinde birden fazla **VM** çalıştırma.

### Hypervisor Türleri
- **Type 1 (Bare Metal):** ESXi, Hyper-V  
- **Type 2 (Hosted):** VirtualBox, VMware Workstation  

---

### Virtualization Vulnerabilities
- **VM Escape**  
- Privilege escalation  
- Live migration interception  
- Resource reuse  

---

### VM Güvenliği
- Patch management  
- Template hardening  
- Network segmentation  
- Hypervisor security  
- Encryption of VM files  

---

## Containerization
Uygulama + bağımlılıkları hafif paketler hâlinde (Docker, Kubernetes).

**Avantajlar**
- Hızlı başlama  
- Hafiflik  
- Taşınabilirlik  
- Mikroservisler için ideal  

**Riskler**
- Shared kernel  
- İnsecure images  
- Kubernetes misconfiguration  

**Önlemler**
- Image scanning  
- RBAC  
- Network policies  
- Non-root containers  

---

# 🧬 Microservices Architecture

**Nedir?**  
Tek büyük uygulamayı küçük, bağımsız servis parçalarına bölme.

**Avantajlar**
- Bağımsız ölçekleme  
- Bağımsız deployment  
- Esneklik  

**Riskler**
- Network latency artar  
- Attack surface genişler  
- Data consistency zorlaşır  
- API güvenliği kritik hâle gelir  

---

# 🌐 Network Infrastructure & Separation

## Physical Separation (Air-Gap)
Sistem tamamen fiziksel olarak ayrıdır.

## Logical Separation
VLAN, ACL, firewall ile mantıksal bölme.

---

# 🧠 Software-Defined Networking (SDN)
Control plane merkezîleştirilmiştir.  
Controller tüm ağ akışını yönetir.

---

# ⚙️ Infrastructure as Code (IaC)
Altyapının kod ile yönetilmesi (YAML, JSON, HCL).

**Faydalar**
- Standartlaşma  
- Hız  
- Tutarlılık  
- Audit kolaylığı  

---

# 🏛️ Centralized vs 🌍 Decentralized Architectures

**Centralized:** Tek merkez → kontrol yüksek, fakat tek noktadan çökme riski  
**Decentralized:** Dağıtık yapı → daha dayanıklı, ancak yönetimi karmaşık

---

# 📡 Internet of Things (IoT)
Sensör + bağlantı + yazılım içeren cihaz ekosistemi.

**Riskler**
- Zayıf default ayarlar  
- Açık portlar  
- Şifrelenmemiş trafik  

---

# 🏭 ICS & SCADA
Endüstriyel kontrol sistemleri.

**Riskler**
- Yetkisiz erişim  
- Malware  
- Patch alınmayan eski sistemler  

---

# ⚙️ Embedded Systems
Belirli bir göreve sahip gömülü sistemler.

**Riskler**
- Donanım arızaları  
- Yazılım zafiyetleri  
- Güncelleme zorlukları  

**Koruma**
- Firmware signing  
- Network segmentation  
- OTA update güvenliği

