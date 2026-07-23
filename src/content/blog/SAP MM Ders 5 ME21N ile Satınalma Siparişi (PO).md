---
title: "SAP MM Ders 5: ME21N ile Satınalma Siparişi (PO)"
description: "Tedarikçiye iletilen resmi belge olan Satınalma Siparişinin ME21N'de oluşturulması."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "ME21N", "Veritabanı"]
---

# SAP MM Ders 5: Satınalma Siparişi (ME21N)

Satınalma Siparişi (Purchase Order - PO), satınalma uzmanlarının onaylanmış talepleri (ME51N) referans alarak tedarikçiye geçtiği ve yasal bağlayıcılığı olan resmi belgedir.

![Satınalma Siparişi Ekranı](/images/sap-me21n-ekrani.png)
*Görsel: ME21N Satınalma Siparişi Oluşturma*

## Süreç ve Önemli Noktalar
Miktar, net fiyat, teslimat tarihi ve teslimat adresi burada kesinleşir. Belge onaylandıktan sonra PDF veya EDI formatında tedarikçiye iletilir.

## Veritabanı ve İş Zekası (BI) Notları
Sipariş başlık bilgileri `EKKO`, kalem (satır) detayları `EKPO` tablosundadır. Bronze-Silver-Gold (veya madalyon) veri ambarı mimarilerinde, bu tablolar ham (Bronze) olarak alınır, temizlenip anlamlı iş modellerine (Silver) dönüştürülür ve SSAS gibi küplerde fact (gerçek) veri katmanı (Gold) olarak raporlanır.