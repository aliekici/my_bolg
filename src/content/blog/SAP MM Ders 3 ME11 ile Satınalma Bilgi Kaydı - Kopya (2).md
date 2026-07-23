---
title: "SAP MM Ders 3: ME11 ile Satınalma Bilgi Kaydı"
description: "Malzeme ve satıcı arasındaki ilişkinin kurulduğu ME11 satınalma bilgi kaydı süreci."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "ME11", "Veritabanı"]
---

# SAP MM Ders 3: Satınalma Bilgi Kaydı (ME11)

Satınalma bilgi kaydı, belirli bir malzemenin, belirli bir satıcıdan hangi şartlarda (fiyat, planlanan teslimat süresi, toleranslar vb.) alınacağını sistemin hafızasına kazıdığımız yerdir.

![Satınalma Bilgi Kaydı Ekranı](/images/sap-me11-ekrani.png)
*Görsel: ME11 Satınalma Bilgi Kaydı Yaratma*

## Süreç ve Önemli Noktalar
Sistem, yeni bir satınalma siparişi açıldığında güncel fiyatı manuel girmek yerine otomatik olarak bu bilgi kaydından çeker. Bu da operasyonel hızı artırır ve insan hatasını minimize eder.

## Veritabanı ve İş Zekası (BI) Notları
Bilgi kaydının genel verileri `EINA` tablosunda, satınalma organizasyonuna ait spesifik verileri ise `EINE` tablosunda tutulur.