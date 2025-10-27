# 🧩 Risk Management (SY0-701)
Kaynak: [DionTraining.com]

---

## 🔐 Risk Management
Fundamental process — **risklerin tanımlanması (identification), analizi (analysis), işlenmesi (treatment), izlenmesi (monitoring)** ve **raporlanması (reporting)** aşamalarını içerir.

---

## 🌀 Risk Management Lifecycle

### 1. Risk Identification
Proaktif şekilde potansiyel risklerin tanımlanması sürecidir.  
**Goal:** Organizasyonun hedeflerini engelleyebilecek tüm olayları belirlemek.

**Techniques:**
- Brainstorming  
- Checklists  
- Interviews  
- Scenario Analysis  

**Business Impact Analysis (BIA):**
Kritik fonksiyonların etkilenme derecesini belirler.

**Key Metrics:**
| Metric | Açıklama |
|--------|-----------|
| **RTO (Recovery Time Objective)** | Bir sürecin ne kadar sürede geri dönmesi gerektiğini gösterir. |
| **RPO (Recovery Point Objective)** | Kabul edilebilir maksimum veri kaybı süresidir. |
| **MTTR (Mean Time to Repair)** | Arızalı bir sistemin ortalama onarım süresi. |
| **MTBF (Mean Time Between Failures)** | Arızalar arasındaki ortalama süre (güvenilirlik göstergesi). |

---

### 2. Risk Analysis
Risklerin olasılığı (**likelihood**) ve etkisi (**impact**) değerlendirilir.  
İki tür analiz yapılabilir:

| Tür | Açıklama |
|-----|----------|
| **Qualitative Analysis** | Olasılık ve etkiye göre nitel (low/medium/high) değerlendirme. |
| **Quantitative Analysis** | Riskleri sayısal verilerle analiz eder. (SLE, ARO, ALE hesaplanır) |

**Quantitative Components:**
- **EF (Exposure Factor):** Varlığın kaybedilen yüzdesi (0–100%).  
- **SLE (Single Loss Expectancy):** Tek bir olayda beklenen para kaybı → `Asset Value × EF`.  
- **ARO (Annualized Rate of Occurrence):** Yıllık gerçekleşme olasılığı.  
- **ALE (Annualized Loss Expectancy):** Yıllık tahmini kayıp → `SLE × ARO`.

---

### 3. Risk Treatment
Risklerle başa çıkma stratejilerini içerir.  
**Amaç:** Riskin etkisini kabul edilebilir seviyeye indirmek.

**Strategies:**
- **Avoidance:** Riskten tamamen kaçınmak.  
- **Reduction (Mitigation):** Etkiyi veya olasılığı azaltmak.  
- **Transference:** Riski başka bir tarafa devretmek (ör. sigorta, sözleşme).  
- **Acceptance:** Riskin varlığını kabul etmek (maliyeti düşük veya etkisi azsa).

**Notes:**
- **Exception:** Belirli durumlarda kurallardan muafiyet.  
- **Exemption:** Tamamen kural dışı bırakılma.  
Her iki durumda da organizasyon riski üstlenir.

---

### 4. Risk Monitoring
Tanımlanan risklerin sürekli izlenmesini kapsar.  
Yeni riskler belirlenir, mevcutların etkinliği değerlendirilir.

**İzlenen risk türleri:**
- **Residual Risk:** Önlemler sonrası kalan risk miktarı.  
- **Control Risk:** Uygulanan kontrolün zamanla etkinliğini kaybetme durumu.

---

### 5. Risk Reporting
Risk bilgilerini paydaşlara iletme sürecidir.  
**Amaç:** Hesap verebilirlik ve bilinçli karar alma desteği sağlamaktır.

---

## 🔁 Risk Assessment Frequency
Risk değerlendirmesinin ne sıklıkla yapılacağını belirler.

| Tür | Açıklama |
|------|----------|
| **Ad-hoc** | İhtiyaç duyuldukça, özel olaylara karşı yapılır. |
| **Recurring** | Düzenli aralıklarla (ör. yıllık, aylık, çeyrek dönem). |
| **One-time** | Belirli bir proje veya girişim için tek seferlik. |
| **Continuous** | Sürekli ve gerçek zamanlı izleme; otomasyon ve veri analitiği kullanılır. |

---

## 📘 Risk Register
Tüm risklerin, etkilerinin, olasılıklarının ve aksiyonlarının kaydedildiği listedir.

**Key Components:**
| Field | Açıklama |
|--------|-----------|
| **Risk Description** | Riskin kısa ve net tanımı. |
| **Risk Impact** | Olası sonuç (Low / Medium / High). |
| **Risk Likelihood** | Gerçekleşme olasılığı. |
| **Risk Level** | Impact + Likelihood sonucunda belirlenir. |
| **Cost** | Riskin veya önlemin finansal etkisi. |

---

## ⚖️ Risk Tolerance & Risk Appetite
- **Risk Tolerance:** Organizasyonun kabul edebileceği maksimum risk seviyesi.  
- **Risk Appetite:** Hedeflere ulaşmak için alınmaya istekli olunan risk düzeyi.

**Types:**
- Expansionary  
- Conservative  
- Neutral  

---

## 🔍 Key Risk Indicators (KRIs)
- Artan risk seviyelerini önceden tahmin etmeye yarayan göstergelerdir.  
- Organizasyon hedeflerine bağlı metriklerdir.  
- Erken uyarı sağlar ve proaktif önlemler alınmasını kolaylaştırır.

---

## 👤 Risk Owner
- Belirli bir riskin yönetiminden sorumlu kişidir.  
- Risk Register’ı günceller, mitigation aksiyonlarını uygular, izleme sağlar.

---

## 💡 Summary

| Aşama | Açıklama |
|-------|-----------|
| **Identification** | Riskleri belirleme ve analiz etme |
| **Analysis** | Olasılık ve etki değerlendirmesi |
| **Treatment** | Uygun strateji seçimi |
| **Monitoring** | Sürekli takip ve iyileştirme |
| **Reporting** | Sonuçların ve performansın paylaşımı |

---

📘 **Not:**  
Risk yönetimi dinamik bir süreçtir. Etkinliği için düzenli değerlendirme, iletişim ve otomasyon sistemleri kritik öneme sahiptir.
