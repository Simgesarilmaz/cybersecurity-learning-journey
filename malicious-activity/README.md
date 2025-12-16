# 🛡️ Malicious Activity-CompTIA Security+ (SY0-701)

## 🚨 Denial of Service Attacks

### **Denial of Service (DoS)**
Tek bir kaynaktan gelen trafik veya isteklerle bir sistemin kaynaklarının tüketilerek hizmet veremez hale getirilmesidir.

### **Distributed Denial of Service (DDoS)**
Birden fazla kaynaktan (genellikle **botnet**) gelen yoğun trafikle hedef sistemin erişilemez hale getirilmesidir.

### **SYN Flood**
TCP three-way handshake tamamlanmadan çok sayıda SYN isteği gönderilerek sunucu kaynaklarının tüketilmesidir.

### **Ping Flood**
Aşırı sayıda ICMP echo request (ping) gönderilerek sistemin cevap veremez hale getirilmesidir.

### **Amplified DDoS**
Küçük isteklerin çok büyük yanıtlar üretmesi sağlanarak saldırı trafiğinin katlanarak büyütüldüğü DDoS türüdür.

---

## 🌐 DNS-Based Attacks

### **DNS Cache Poisoning (DNS Spoofing)**
DNS resolver önbelleğine sahte kayıtlar eklenerek kullanıcıların kötü niyetli sitelere yönlendirilmesidir.

### **DNS Amplification**
Sahte IP adresleriyle açık DNS sunuculara sorgu gönderilerek hedefe çok büyük DNS yanıtları yönlendirilir.

### **DNS Tunneling**
DNS trafiği (port 53) içerisine gizlenmiş veri veya komutların aktarılması tekniğidir.

### **Domain Hijacking**
Bir alan adının yetkisiz şekilde ele geçirilmesi ve saldırgan kontrolüne geçmesidir.

### **DNS Zone Transfer Attack**
Yetkisiz kullanıcıların tüm DNS zone bilgisini ele geçirerek altyapı hakkında keşif yapmasıdır.

---

## 📂 Web & Application Attacks

### **Directory Traversal**
Yetersiz input validation nedeniyle uygulamanın web root dışındaki dosyalara erişmesine izin verilmesidir.

### **File Inclusion**
Bir web uygulamasına yetkisiz dosya eklenmesi veya çalıştırılması zafiyetidir.

- **Remote File Inclusion (RFI):**  
  Harici bir sunucudan kötü amaçlı dosya dahil edilmesi

- **Local File Inclusion (LFI):**  
  Sunucu üzerinde mevcut dosyaların yetkisiz şekilde çalıştırılması

---

## ⚙️ Execution & Privilege Attacks

### **Arbitrary Code Execution**
Saldırganın hedef sistem üzerinde kendi kodunu herhangi bir kısıtlama olmadan çalıştırabilmesidir.

### **Remote Code Execution (RCE)**
Arbitrary code execution’ın internet üzerinden uzaktan gerçekleştirilen türüdür.

### **Privilege Escalation**
Saldırganın sahip olmadığı daha yüksek yetkilere erişmesidir.

- **Vertical Privilege Escalation:**  
  Normal kullanıcıdan admin/root seviyesine yükselme

- **Horizontal Privilege Escalation:**  
  Aynı yetki seviyesindeki başka kullanıcının kaynaklarına erişim

---

## 🕵️ Rootkits

### **Rootkit**
Sistemde gizlenerek çalışan ve saldırgana kalıcı yetkiler sağlayan malware türüdür.

### **Kernel Mode Rootkit (Ring 0)**
Çekirdek seviyesinde çalışan, en yüksek yetkilere sahip ve en tehlikeli rootkit türüdür.

### **User Mode Rootkit**
Kullanıcı seviyesinde çalışır, registry veya task scheduler gibi OS özelliklerini kullanarak kalıcılık sağlar.

---

## 🔁 Session & Network Attacks

### **Replay Attack**
Geçerli bir veri iletiminin yakalanıp daha sonra tekrar gönderilmesidir.

### **Credential Replay Attack**
Yakalanan kullanıcı kimlik bilgilerinin tekrar kullanılmasıdır.

### **Session Hijacking**
Bir kullanıcının aktif oturumunun ele geçirilerek yetkisiz erişim sağlanmasıdır.

### **Session Prediction**
Tahmin edilebilir session token’lar kullanılarak oturumun ele geçirilmesidir.

### **Cookie Poisoning**
Cookie içeriğinin değiştirilerek uygulamanın manipüle edilmesidir.

---

## 🔗 On-Path & Downgrade Attacks

### **On-Path Attack (Man-in-the-Middle)**
İki sistem arasındaki iletişimin saldırgan tarafından izlenmesi veya değiştirilmesidir.

### **ARP Poisoning**
ARP tablolarının manipüle edilerek ağ trafiğinin saldırgana yönlendirilmesidir.

### **Rogue Access Point**
Kullanıcıları kandırmak için oluşturulan sahte kablosuz erişim noktasıdır.

### **SSL Stripping**
HTTPS bağlantısının HTTP’ye düşürülerek şifrelenmemiş verinin ele geçirilmesidir.

### **Downgrade Attack**
Güçlü bir güvenlik protokolünün daha zayıf bir sürüme zorlanmasıdır.

---

## 💉 Injection Attacks

### **LDAP Injection**
Kullanıcı girdileriyle oluşturulan LDAP sorgularının manipüle edilmesidir.

### **Command Injection**
Web uygulaması üzerinden işletim sistemi komutlarının çalıştırılmasıdır.

### **Process Injection**
Canlı bir process içine kötü amaçlı kod enjekte edilmesidir.

---

## 🧩 Indicators of Compromise (IoC)

### **Indicators of Compromise (IoC)**
Bir sistemde veya ağda gerçekleşmiş olası bir saldırıyı gösteren adli bulgulardır.

- **Account Lockout** → Brute force göstergesi  
- **Concurrent Session Usage** → Hesap ele geçirilmesi  
- **Impossible Travel** → Fiziksel olarak mümkün olmayan girişler  
- **Resource Consumption** → Malware veya DDoS belirtisi  
- **Missing Logs** → Saldırganın izlerini silmesi  
- **Out-of-Cycle Logging** → Olağandışı saatlerde log oluşması  
- **Published Articles** → Saldırının kamuya açık şekilde ifşa edilmesi  

---

> 📌 **Tip for Security+ Exam:**  
> IoC sorularında genellikle **“Which indicator BEST describes…”** şeklinde sorular gelir.  
> Belirti → Saldırı eşleştirmesi yapabiliyor olman kritik.

---

🔗 **Kaynak:** [DionTraining – CompTIA Security+ (SY0-701)](https://www.diontraining.com)
