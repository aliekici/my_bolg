---
title: "SAP MM Ders 1: MM01 ile Malzeme Ana Verisi Yaratma"
description: "SAP'de tüm süreçlerin başlangıcı olan malzeme ana verisinin MM01 ekranında nasıl tanımlandığını öğrenin."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "MM01", "Veritabanı"]
---

# SAP MM Ders 1: Malzeme Ana Verisi (MM01)

SAP MM (Materials Management) modülündeki tüm süreçler, malzemelerin sisteme doğru bir şekilde tanımlanmasıyla başlar. 

*   **MM01:** Malzeme Yaratma
*   **MM02:** Malzeme Değiştirme
*   **MM03:** Malzeme Görüntüleme

![Malzeme Ana Verisi Ekranı](/images/sap-mm01-ekrani.png)

*Görsel: MM01 Malzeme Yaratma Ekranı*

## Süreç ve Önemli Noktalar
Bu ekranda malzeme numarası, endüstri sektörü ve malzeme türü (Örn: `ROH` - İlk Madde, `FERT` - Mamul) belirlenir. Malzemenin temel ölçü birimi ve ağırlık bilgileri gibi statik veriler burada sisteme girilir.

## Veritabanı ve İş Zekası (BI) Notları
Sisteme girilen bu temel bilgiler `MARA` tablosunda, üretim yeri bazlı veriler ise `MARC` tablosunda tutulur. Veri ambarı (Data Warehouse) mimarilerinde malzeme boyut (dimension) tablolarını oluştururken doğrudan bu tablolar referans alınır.