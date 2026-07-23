---
title: "SAP MM Ders 2: BP (Business Partner) ile Satıcı Yaratma"
description: "S/4HANA ile hayatımıza giren BP ekranında satıcı ve iş ortağı yaratma adımları."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "BP", "Veritabanı"]
---

# SAP MM Ders 2: İş Ortağı / Satıcı Ana Verisi (BP)

Malzemeyi tedarik edeceğimiz firmaları veya kişileri sisteme tanımladığımız ekrandır. Yeni nesil S/4HANA sistemlerinde eski `XK01` işleminin yerini tekilleştirilmiş **Business Partner (BP)** yapısı almıştır.

![Business Partner Ekranı](/images/sap-bp-ekrani.png)
*Görsel: BP İş Ortağı Yönetimi Ekranı*

## Süreç ve Önemli Noktalar
Bir iş ortağı yaratıldıktan sonra ona "Satıcı" (Vendor) rolü verilerek, ilgili satınalma organizasyonu ve şirket kodu düzeyindeki finansal anlaşmalar sisteme işlenir.

## Veritabanı ve İş Zekası (BI) Notları
Merkezi iş ortağı verileri `BUT000` tablosunda tutulurken, satıcı rolleri `LFA1` ve şirket kodu detayları `LFB1` tablolarında saklanır. Küp tasarımlarında tedarikçi bazlı kırılımlar için bu tablolar birleştirilerek kullanılır.