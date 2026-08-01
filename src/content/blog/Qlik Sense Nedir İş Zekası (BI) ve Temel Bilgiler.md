---
title: "Qlik Sense Nedir? İş Zekası (BI) ve Temel Bilgiler"
description: "İş zekası (Business Intelligence) ve veri görselleştirme dünyasına giriş yapın. Qlik Sense nedir, Associative Engine nasıl çalışır ve avantajları nelerdir öğrenin."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "İş Zekası", "Veri Görselleştirme", "Eğitim", "Raporlama"]
heroImage: ../../assets/covers/cover-qlik.png
---

# Qlik Sense Nedir? İş Zekası ve Veri Görselleştirmeye Giriş

Günümüzün veri odaklı dünyasında, işletmelerin rekabet avantajı elde etmesi veriyi ne kadar iyi okuyabildiklerine bağlıdır. Bu yazıda, **İş Zekası (Business Intelligence - BI)** kavramının temellerine inecek ve sektörün öncü veri görselleştirme araçlarından biri olan **Qlik Sense**'in mimarisini inceleyeceğiz.

![Qlik Sense Arayüzü ve Veri Görselleştirme](/images/qlik-sense-temel-ekran.png)
*Görsel: Qlik Sense Örnek Dashboard ve Veri Analizi Ekranı*

## 1. İş Zekası (Business Intelligence) Nedir?
İş zekası, ERP sistemleri, CRM yazılımları veya dış kaynaklardan gelen büyük verilerin (Big Data) toplanıp analiz edilerek **karar destek sistemlerine** dönüştürülmesi sürecidir. 
*   Karmaşık veri yığınlarını anlamlı, okunabilir raporlara ve panolara (dashboard) dönüştürür.
*   Yöneticilerin ve analistlerin reaktif değil, proaktif (geleceği öngören) kararlar almasını sağlar.

## 2. Qlik Sense Nedir ve Nasıl Çalışır?
Qlik Sense, kullanıcıların verileri bağımsız olarak keşfetmesine olanak tanıyan, modern bir **self-servis veri analizi ve görselleştirme** platformudur. Geleneksel ve hiyerarşik raporlama araçlarının aksine, kullanıcıya kendi analizini yapma özgürlüğü sunar.

### Qlik Sense'i Öne Çıran Temel Özellikler
*   **Associative Engine (İlişkilendirme Motoru):** Qlik'in kalbidir. Verileri klasik SQL sorgularındaki gibi kısıtlayıcı bir şekilde (sadece seçilenleri getirerek) değil, birbiriyle ilişkilendirerek (seçilenleri yeşil, ilişkili olanları beyaz, ilişkisizleri gri renkte göstererek) analiz eder. Bu sayede verideki gizli kalmış anomalileri anında fark edersiniz.
*   **Self-Servis Analitik:** Teknik kodlama veya ileri düzey SQL bilgisi gerektirmeden, sürükle-bırak yöntemiyle dinamik görseller oluşturulabilir.
*   **Geniş Veri Kaynağı Entegrasyonu:** MS SQL Server, Excel, REST API'ler ve bulut platformları dahil olmak üzere birden fazla kaynaktan eşzamanlı veri çekebilir.
*   **Mobil Uyumluluk ve Güvenlik:** Responsive (duyarlı) tasarımı sayesinde her cihazda sorunsuz çalışır ve satır/sütun bazlı (Section Access) gelişmiş veri güvenliği sunar.

## 3. Qlik Sense İş Süreçlerinde Nerelerde Kullanılır?
Qlik Sense, verinin olduğu her departmanda süreçleri optimize etmek için kullanılır:
*   **Satış ve Pazarlama:** Kampanya ROI (Yatırım Getirisi) ölçümleri ve müşteri segmentasyonu.
*   **Tedarik Zinciri ve Lojistik:** Stok devir hızları, depo optimizasyonu ve tedarikçi performans analizi.
*   **Finans:** Nakit akışı takibi, karlılık analizleri ve bütçe sapma raporları.

## 4. Veri Mimarisi ve ERP Entegrasyon Notları (BI Perspektifi)
Kurumsal bir iş zekası projesinde Qlik Sense, modern veri ambarı (Data Warehouse) mimarilerinin en üst katmanında yer alır. Veriler genellikle **Bronze (Ham), Silver (Temizlenmiş) ve Gold (Analize Hazır)** yapısından geçer.

Qlik Sense'in yüksek performanslı bellek içi (in-memory) teknolojisi, Gold katmanında modellenmiş verilerle mükemmel uyum sağlar. Örneğin, bir SAP sisteminden malzeme (MM) veya satış (SD) belgelerini merkeze alan bir *Star Schema* kurguladığınızda, Qlik bu modeli çok hızlı bir şekilde okuyarak milyonlarca satırlık veride bile saniyenin altında yanıt süreleri sunar.