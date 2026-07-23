---
title: "SAP MM Ders 6: MIGO ile Mal Girişi ve Hareketleri"
description: "Tedarikçiden gelen ürünlerin depoya teslim alındığı MIGO mal girişi süreci."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "MIGO", "Veritabanı"]
---

# SAP MM Ders 6: Mal Hareketi ve Girişi (MIGO)

Tedarikçi sipariş edilen malları fiziksel olarak getirdiğinde, depo sorumlusunun sistemde bu ürünleri teslim aldığı ve stokları güncellediği ekrandır.

![MIGO Mal Girişi Ekranı](/images/sap-migo-ekrani.png)

*Görsel: MIGO Mal Girişi (Goods Receipt)*

## Süreç ve Önemli Noktalar
Satınalma siparişine istinaden depoya giriş yapılırken genellikle **101** hareket türü (Movement Type) kullanılır. Bu işlem kaydedildiği an şirketin stok miktarı artar ve muhasebesel olarak stok değeri hesaplarına kayıt atılır.

## Veritabanı ve İş Zekası (BI) Notları
Malzeme hareket belgeleri ECC (eski) sistemlerde `MSEG` (Kalem) ve `MKPF` (Başlık) tablolarında tutulurken, S/4HANA mimarisinde tüm bu veriler `MATDOC` isimli tek bir devasa tabloda birleştirilmiştir.