---
title: "SAP MM Modülü: Malzeme Yönetimi Süreçleri ve İş Akışı Rehberi"
description: "SAP MM (Materials Management) modülünün satın alma, envanter ve depo yönetimi süreçlerini, temel tablolarını ve BI raporlamasındaki önemini anlatan rehber."
pubDate: 2026-07-22
category: "SAP"
tags: ["SAP", "SAP MM", "ERP", "Envanter Yönetimi", "Satın Alma"]
---

## SAP MM Modülü Nedir?

**SAP MM (Materials Management / Malzeme Yönetimi)**, bir şirketin satın alma, stok yönetimi ve envanter kontrolü süreçlerini yönettiği modüldür. Üretim yapan şirketlerde SAP MM, hammaddeden bitmiş ürüne kadar tüm malzeme hareketlerinin izlendiği omurga niteliğindedir.

SAP MM verileriyle çalışmak, özellikle üretim ve lojistik sektöründeki BI uzmanları için günlük stok bakiye raporları ve üretim takip dashboard'larının temelini oluşturur.

## SAP MM'nin Ana Süreçleri

### 1. Satın Alma (Procurement)
Talep oluşturma (Purchase Requisition), satın alma siparişi (Purchase Order) ve tedarikçi seçimi süreçlerini kapsar.

### 2. Envanter Yönetimi (Inventory Management)
Malzeme giriş/çıkış hareketleri, depo transferleri ve stok sayımları bu alanda yönetilir. **MB51** gibi transaction kodları, malzeme hareket geçmişini incelemek için sıkça kullanılır.

### 3. Depo Yönetimi (Warehouse Management)
Depo içi yerleşim, malzeme lokasyonları ve toplama (picking) süreçlerini içerir.

### 4. Fatura Doğrulama (Invoice Verification)
Satın alma siparişi ile gelen fatura arasındaki uyumu kontrol eden süreçtir; FI modülü ile doğrudan entegredir.

## SAP MM ve BI Raporlaması: Kritik Tablolar

BI/ETL tarafında SAP MM ile çalışırken en sık karşılaşılan tablo ve transaction kodlarından bazıları:

- **MB51:** Malzeme hareketleri listesi — stok giriş/çıkışlarının detaylı görünümü
- **COOIS:** Üretim siparişi bilgi sistemi — planlanan/gerçekleşen üretim analizleri için temel kaynak
- **MARA / MARC:** Malzeme ana verisi ve fabrika bazlı malzeme bilgileri
- **MSEG / MKPF:** Malzeme belge kalemleri ve belge başlıkları

Bu tablolar üzerinden **stok devir hızı**, **güvenlik stoku analizleri** ve **planlanan/gerçekleşen üretim karşılaştırmaları** gibi raporlar üretilebilir.

## Neden SAP MM Verisi Karmaşık Olabilir?

1. **Çoklu depo/fabrika yapısı:** Büyük holdinglerde her fabrika kendi stok mantığına sahip olabilir.
2. **Hareket tipi (Movement Type) çeşitliliği:** Farklı hareket tipleri (mal girişi, transfer, iade vb.) doğru sınıflandırılmalıdır.
3. **Gerçek zamanlı ihtiyaç:** Üretim planlaması için stok verisinin güncelliği kritik önemdedir; ETL süreçlerinde reload sıklığı buna göre planlanmalıdır.

## Pratik Bir Örnek: Günlük Stok Bakiye Raporu

Bir üretim şirketinde SAP MM verisinden günlük stok bakiye raporu oluştururken tipik ETL akışı şu şekilde işler:

1. MB51 ve MSEG tablolarından malzeme hareketleri çekilir.
2. Fabrika ve malzeme grubu bazında veri modellenir (Star Schema).
3. Qlik Sense veya Power BI üzerinde interaktif bir stok dashboard'u oluşturulur.
4. Kritik stok seviyesinin altına düşen malzemeler için otomatik uyarı mekanizmaları kurulur.

## Sonuç

SAP MM modülü, üretim ve tedarik zinciri süreçlerinin veri omurgasıdır. Bu modülü iyi kavramak, hem operasyonel hem de stratejik raporlama projelerinde büyük fark yaratır. Sıradaki yazımızda SAP SD modülünü ve satış-dağıtım süreçlerini inceleyeceğiz.
