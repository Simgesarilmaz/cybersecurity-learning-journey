# 🔐 Automation and Orchestration - CompTIA Security+ (SY0-701)

Güvenlik operasyonlarında **manuel müdahaleyi azaltmak**, süreçleri hızlandırmak ve
**insan hatasını minimize etmek** için kullanılan yaklaşımlardır.

Amaç: **consistent, fast and scalable secure operations** sağlamak.

---

## 🤖 Automation
Tekrarlayan görevlerin **insan müdahalesi olmadan** otomatik olarak çalıştırılmasıdır.

**Automation = single task automation**

**Key Terms:**
- **Automation:** Manuel işlem gerektirmeden görev yürütme.
- **Script:** Otomatik çalıştırılan komut veya görev dizisi.
- **Scheduled Task:** Belirli zamanlarda otomatik çalışan görev.
- **Human Error:** Manuel işlemlerden kaynaklanan hata.

**Purpose:**  
Tutarlılık (consistency), hız (efficiency) ve hata azaltma.

---

## 🎼 Orchestration
Birden fazla otomatik görevin **belirli bir sırayla ve birlikte** çalıştırılmasıdır.

**Orchestration = workflow automation**

**Key Terms:**
- **Orchestration:** Birden fazla automation’ın koordinasyonu.
- **Workflow:** Baştan sona tanımlı işlem zinciri.
- **Dependency:** Bir görevin başka bir göreve bağlı olması.
- **Sequencing:** Görevlerin belirli bir sırada çalıştırılması.

**Purpose:**  
Karmaşık güvenlik süreçlerinin **uyumlu şekilde** yürütülmesi.

---

## 🚨 SOAR (Security Orchestration, Automation, and Response)
Olay müdahalesi, tehdit avcılığı ve güvenlik operasyonları için kullanılan
**özel güvenlik otomasyon platformlarıdır**.

**Key Terms:**
- **SOAR:** Güvenlik odaklı automation ve orchestration platformu.
- **Runbook Automation:** Olaylara otomatik yanıt verilmesi.
- **Threat Enrichment:** IP, hash, domain gibi verilerin zenginleştirilmesi.
- **Integration:** SIEM ve diğer güvenlik araçlarıyla bağlantı.

**Example:**  
SIEM alarm üretir → SOAR veriyi zenginleştirir → otomatik aksiyon alınır

---

## 📘 Playbook vs Runbook

### 📋 Playbook
Belirli bir olay için hazırlanmış **manuel rehberdir**.

**Key Terms:**
- **Playbook:** Adım adım yapılacaklar listesi.
- **Incident Guidance:** Olay müdahalesi yönlendirmesi.
- **Manual Process:** İnsan tarafından yürütülen süreç.

**Example:**  
Phishing saldırısına nasıl müdahale edileceğini anlatan doküman.

---

### ⚙️ Runbook
Playbook’un **otomatikleştirilmiş** halidir ve **insan onayı gereken noktalar** içerir.

**Key Terms:**
- **Runbook:** Otomatik çalışan playbook.
- **Human-in-the-loop:** Kritik adımlarda insan onayı.
- **Automated Response:** Otomatik aksiyon alma.

**Exam Note:**  
Playbook = manual  
Runbook = automated

---

## ✅ Benefits of Automation and Orchestration

**Key Benefits:**
- **Efficiency:** İşlemler hızlı ve tutarlı yapılır.
- **Standardization:** Güvenlik baseline’ları zorunlu kılar.
- **Scalability:** Küçük ekiplerle büyük sistemler yönetilir.
- **Faster Reaction Time:** Olaylara hızlı yanıt verilir.
- **Workforce Multiplier:** İnsan gücü daha verimli kullanılır.
- **Employee Retention:** Tekrarlı işler azalır, tükenmişlik düşer.

---

## 🕒 When to Automate and Orchestrate
Automation ve orchestration şu süreçler için uygundur:
- **Repeatable**
- **Stable**
- **Well-defined workflows**

❌ Sürekli değişen veya net tanımı olmayan süreçler için önerilmez.

---

## ⚖️ Decision Factors for Automation

### 🧩 Complexity
- Basit görevler → **Automation**
- Karmaşık olay müdahalesi → **Orchestration**

### 💰 Cost
- İlk kurulum maliyeti vardır
- Uzun vadede zaman ve personel tasarrufu sağlar

### 🔥 Single Points of Failure
- Otomasyon çökerse manuel süreçler devrede olmalı
- **Redundancy & failover** önemlidir

### 🧱 Technical Debt
- Kötü tasarlanmış otomasyon zamanla yük oluşturur
- Düzenli bakım gerektirir

### 🔧 Ongoing Supportability
- Yetkin ekip gerektirir
- Çoğu otomasyon **API & Webhook** kullanır

---

## 🎫 Automating Support Tickets

Destek taleplerinin otomatik oluşturulması ve yönetilmesidir.

**Key Terms:**
- **Ticket Automation:** Destek taleplerinin otomatik işlenmesi.
- **Categorization:** Talebin konuya göre sınıflandırılması.
- **Prioritization:** Öncelik seviyesinin belirlenmesi.
- **SLA:** Hizmet seviyesi anlaşması.

**Benefit:**  
Taleplerin kaybolması önlenir, yanıt süresi kısalır.

---

## 🚨 Ticket Escalation Automation
Kritik veya çözülmeyen taleplerin otomatik olarak **üst seviyeye taşınmasıdır**.

**Key Terms:**
- **Escalation Rules:** Yükseltme kriterleri.
- **Notification:** İlgili kişilere otomatik bildirim.
- **Reassignment:** Talebin başka ekibe aktarılması.

---

## 🧑‍💼 Automating Onboarding
Yeni çalışanların sisteme hızlı ve güvenli şekilde dahil edilmesini sağlar.

**Key Terms:**
- **User Provisioning:** Kullanıcı hesabı oluşturma.
- **Access Assignment:** Rol bazlı yetki atama.
- **RBAC:** Role-Based Access Control.
- **De-provisioning:** Ayrılan çalışanın erişimlerinin kaldırılması.

---

## 🖥 Resource Provisioning
Çalışanlara gerekli donanım ve yazılımların otomatik sağlanmasıdır.

**Key Terms:**
- **Resource Allocation:** Kaynak atama.
- **Configuration:** Sistem ayarlarının yapılması.
- **Audit:** Kaynak kullanımının denetlenmesi.

---

## 🔐 Automating Security

**Key Areas:**
- **Guardrails:** Güvensiz yapılandırmaları otomatik engelleyen kontroller.
- **Security Groups:** Sanal firewall mantığıyla çalışan kurallar.
- **Permissions Management:** Yetkilerin otomatik yönetimi.
- **Service Access Control:** Servislerin otomatik açılıp kapatılması.

---

## 🚀 Automating Application Development (CI/CD)

### 🔄 Continuous Integration (CI)
Kod değişikliklerinin sık sık birleştirilmesi ve otomatik test edilmesidir.

### 🚚 Continuous Delivery (CD)
Kod her zaman deploy edilebilir durumdadır ancak
**production deployment manuel karardır**.

### ⚡ Continuous Deployment
Testleri geçen kod otomatik olarak production’a alınır.

---

## 🔗 Integrations & APIs

**Key Terms:**
- **API:** Sistemler arası programatik iletişim.
- **REST:** HTTP tabanlı, JSON kullanan API yapısı.
- **SOAP:** XML tabanlı, daha katı ve güvenli API yapısı.
- **Webhook:** Olay tetiklendiğinde otomatik veri gönderimi.

---

## 💡 Exam Tips
- **Repeatable task** → Automation  
- **Incident workflow** → Orchestration  
- **SIEM + Automation** → SOAR  
- **Manual steps** → Playbook  
- **Automated steps** → Runbook  

---

## ✅ Summary

| Kavram | Anlam |
|------|------|
| **Automation** | Tek görev otomasyonu |
| **Orchestration** | Workflow otomasyonu |
| **SOAR** | Güvenlik otomasyonu platformu |
| **Playbook** | Manuel rehber |
| **Runbook** | Otomatik rehber |

---

📌 **Not:**  
Automation tek başına yeterli değildir.  
**Gerçek güç, orchestration ile birlikte kullanıldığında ortaya çıkar.**


---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)  
