---
title: "SAP FI Modülü Nedir? Finansal Muhasebe Süreçlerine Giriş Rehberi"
description: "SAP FI (Finansal Muhasebe) modülünün ne işe yaradığını, alt bileşenlerini ve kurumsal raporlamadaki rolünü örneklerle anlatan kapsamlı başlangıç rehberi."
pubDate: 2026-07-21
category: "SAP"
tags: ["SAP", "SAP FI", "ERP", "Finansal Muhasebe"]
---

## SAP FI Modülü Nedir?

**SAP FI (Financial Accounting / Finansal Muhasebe)**, SAP ERP sisteminin en temel modüllerinden biridir. Bir şirketin genel muhasebe, borç/alacak yönetimi, sabit kıymetler ve finansal raporlama süreçlerini tek bir merkezi sistem üzerinden yönetmesini sağlar. Bir İş Zekâsı (BI) veya ETL uzmanı olarak SAP FI verileriyle çalışmak, finansal tabloları anlamlı dashboard'lara dönüştürmenin ilk adımıdır.

Kısacası SAP FI, şirketin **"para nereden geldi, nereye gitti"** sorusuna cevap veren modüldür.

## SAP FI'nin Temel Alt Bileşenleri

SAP FI tek bir blok değil, birbirine bağlı alt modüllerden oluşur:

### 1. Genel Muhasebe (FI-GL)
Şirketin tüm muhasebe kayıtlarının toplandığı ana defterdir. Hesap planı (Chart of Accounts), günlük kayıtlar ve dönem sonu kapanış işlemleri burada yönetilir.

### 2. Borç Yönetimi (FI-AP – Accounts Payable)
Tedarikçilere olan borçların takip edildiği bileşendir. Fatura girişleri, ödeme planları ve tedarikçi bakiyeleri bu alanda izlenir.

### 3. Alacak Yönetimi (FI-AR – Accounts Receivable)
Müşterilerden alacakların yönetildiği modüldür. Fatura kesimi, tahsilat takibi ve risk analizi için kritik veri kaynağıdır.

### 4. Sabit Kıymetler (FI-AA – Asset Accounting)
Şirketin demirbaş, makine ve bina gibi sabit varlıklarının amortisman hesaplamaları ve değer takibi burada yapılır.

## SAP FI Neden BI ve Raporlama Açısından Önemli?

İş Zekâsı tarafında çalışan biri için SAP FI tabloları, üst yönetime sunulan **risk karneleri**, **nakit akış dashboard'ları** ve **bayi/tedarikçi performans raporlarının** temel veri kaynağıdır. Örneğin SAP FI verilerinden üretilen bir risk analizi dashboard'u, finans ekiplerinin hangi bayilerin ödeme risk taşıdığını anlık olarak görmesini sağlar.

Qlik Sense veya Power BI gibi araçlarla SAP FI verisini modellerken dikkat edilmesi gereken noktalar:

- **BKPF / BSEG** gibi muhasebe belge tablolarının doğru ilişkilendirilmesi
- Şirket kodu (Company Code) ve hesap planı seviyesinde filtreleme
- Döviz kuru dönüşümlerinin raporlama katmanında tutarlı yapılması
- Dönem sonu (period-end) kapanış verilerinin ETL sürecinde ayrıca ele alınması

## SAP FI ile Çalışırken Sık Karşılaşılan Zorluklar

1. **Veri hacmi:** Büyük şirketlerde FI tabloları milyonlarca satıra ulaşabilir; performanslı ETL mimarisi şarttır.
2. **Çoklu şirket kodu yapıları:** Holding bünyesinde birden fazla şirket kodu varsa konsolide raporlama karmaşıklaşır.
3. **Yetkilendirme:** Finansal veriler hassas olduğu için satır bazlı güvenlik (RLS / Section Access) mutlaka uygulanmalıdır.

## Sonuç

SAP FI modülü, kurumsal finansal verinin kalbidir. Bu modülü iyi anlamak, hem SAP tarafında hem de BI/raporlama tarafında çalışan uzmanlar için vazgeçilmez bir yetkinliktir. Bir sonraki yazıda SAP MM modülünü ve malzeme yönetimi süreçlerini ele alacağız.
