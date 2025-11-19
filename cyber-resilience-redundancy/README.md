# Cyber Resilience & Redundancy  

Cyber Resilience, High Availability, Redundancy, RAID, Backups, BC/DR ve Testing konularını kısa, net ve pratik şekilde özetler.

---

## 🔐 Cyber Resilience
**Tanım:**  
Sistemlerin saldırı, hata veya kesinti olsa bile çalışmaya devam edebilmesi.

### Neden Önemli?
- **Continuous Operations** → İş kesintisi olmaması  
- **Swift Recovery** → Olay sonrası hızlı toparlanma  
- **Reduced Downtime** → Hizmet sürekliliği  
- **Minimized Impact** → Operasyonel kesinti azalması  

---

## 🧱 Redundancy (Yedeklilik)
**Tanım:** Kritik bileşenlerin birden fazla kopyasına sahip olmak.

### Örnekler
- Redundant Power Supplies  
- Redundant Network Paths  
- Redundant Servers  
- Multi-Cloud Systems  
- Redundant Software Services  

**Amaç:** Single Point of Failure (SPOF) ortadan kaldırmak.

---

## ⚡ High Availability (HA)
**Amaç:** Hizmetlerin sürekli çalışmasını sağlamak.

### Bileşenler
- **Load Balancing**  
- **Clustering**  
- **Redundant Power**  
- **Redundant Connections**  
- **Redundant Servers / Services**  
- **Multi-Cloud Architecture**

### Uptime Standartları
| Seviye | Açıklama |
|--------|----------|
| **Five Nines (99.999%)** | Yılda ~5 dakika downtime |
| **Six Nines (99.9999%)** | Yılda ~31 saniye downtime |

---

## ⚖️ Load Balancing
- Trafiği birden fazla sunucuya dağıtır.  
- Single server overload engellenir.  
- HA ve ölçeklenebilirlik sağlar.

---

## 🧩 Clustering
- Birden çok sistemin tek bir sistem gibi davranması.  
- Failover otomatik gerçekleşir.  
- Yüksek uptime ve reliability sağlar.

---

## ☁️ Multi-Cloud
- Birden fazla cloud sağlayıcı kullanmak (AWS + Azure gibi).  
- Vendor lock-in azaltılır.  
- Disaster etkisi minimize edilir.  
- Esneklik + maliyet optimizasyonu sağlar.

---

# 🗄️ Data Redundancy & RAID

## RAID Levels

### **RAID 0 – Striping**
- Performans yüksek  
- **Redundancy yok**  
- Sınav notu: “Performance only”

---

### **RAID 1 – Mirroring**
- İki disk → birebir kopya  
- **High Redundancy**  
- 1 disk arızasında çalışmaya devam eder.

---

### **RAID 5 – Striping with Parity**
- Minimum 3 disk  
- **1 disk fail toleransı**  
- Okuma iyi, yazma daha yavaş  
- En yaygın iş çözümü

---

### **RAID 6 – Double Parity**
- Minimum 4 disk  
- **2 disk arızasına dayanır**  
- RAID 5'ten daha güvenli

---

### **RAID 10 (1+0)**
- Mirroring + Striping  
- Hem **yüksek performans** hem **yüksek fault tolerance**  
- Minimum 4 disk

---

# 📈 Capacity Planning
Organizasyonun gelecekteki ihtiyaçlarını kesinti olmadan karşılaması için planlama.

### 4 Ana Alan
- **People** → Personel kapasitesi, yetkinlikler  
- **Technology** → Sistem, uygulama, network kapasitesi  
- **Infrastructure** → Veri merkezi, alan, soğutma, güç  
- **Processes** → İş akışları, otomasyon, verimlilik  

---

# 🔌 Power Protection Components

### **Line Conditioner**
- Sags, surges, undervoltage düzeltir  
- Güç kalitesini stabilize eder  

### **UPS (Uninterruptible Power Supply)**
- Batarya destekli güç  
- 15–60 dakika kesintisiz enerji  
- Line conditioning içerir  

### **Generators**
- Uzun süreli kesinti için güç sağlar  

### **PDC (Power Distribution Center)**
- Güç dağıtımı + load balancing  
- UPS ve jeneratörle entegre çalışır  

---

# 💾 Data Backups

### Backup Types
- **Onsite**  
- **Offsite**  
- **Cloud-based**

### Backup Components
- **Encryption** (at rest + in transit)  
- **Snapshots** (point-in-time copy)  
- **Replication** (real-time copy)  
- **Journaling** (transaction log)  
- **Recovery procedures**  

### RPO (Recovery Point Objective)
Ne kadar veri kaybının kabul edilebilir olduğunu belirler.

---

# 📍 Backup Site Options

| Site Türü | Açıklama |
|----------|----------|
| **Hot Site** | Tamamen hazır, anında devreye girer, pahalı |
| **Warm Site** | Kısmen hazır, birkaç gün içinde aktif |
| **Cold Site** | Boş bina, donanımsız, haftalar sürer |
| **Mobile Site** | Taşınabilir, esnek seçenek |
| **Virtual Sites** | Cloud tabanlı sıcak/soğuk/warm site |

---

# 🌍 Geographic Dispersion
- Kaynakların farklı lokasyonlara yayılması  
- Tek lokasyon felaketinin riskini azaltır  

---

# 📘 COOP (Continuity of Operations Plan)

### BC Plan (Business Continuity)
- Geniş kapsamlı kesinti senaryoları  
- Önleyici + toparlanma adımları  

### DRP (Disaster Recovery Plan)
- Teknik sistemlerin geri dönüş planı  
- BC Plan’in alt kümesi  
- Hızlı recovery amaçlı

---

# 🧪 Resilience & Recovery Testing

### **Tabletop Exercises**
- Senaryo üzerinden ekip tartışması  
- Kaynak kullanımı yok  

### **Failover Tests**
- Primary sistemden backup’a gerçek geçiş  
- En gerçekçi test türlerinden biri  

### **Simulations**
- Sanal ortamda olay canlandırması  

### **Parallel Processing**
- Primary + Secondary sistem aynı anda çalışır  
- Hem resilience hem recovery test edilir  

---

## ✔️ Sınavda Bunlara Dikkat!
- “Which increases availability?” → **Load Balancer / Clustering**  
- “Which reduces SPOF?” → **Redundancy**  
- “Which RAID tolerates 2 disk failure?” → **RAID 6**  
- “Which site activates instantly?” → **Hot Site**  
- “RPO vs RTO?” → RPO = veri kaybı toleransı  
- “UPS vs Generator?” → UPS kısa süre, generator uzun süre  

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  


