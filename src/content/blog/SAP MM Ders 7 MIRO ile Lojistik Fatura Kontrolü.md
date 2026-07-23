---
title: "SAP MM Ders 7: MIRO ile Lojistik Fatura Kontrolü"
description: "Tedarikçiden gelen faturanın sistemdeki sipariş ve irsaliye ile eşleştirildiği MIRO ekranı."
pubDate: "2026-07-23"
tags: ["SAP", "MM", "Eğitim", "MIRO", "Veritabanı"]
---

# SAP MM Ders 7: Lojistik Fatura Kontrolü (MIRO)

Lojistik fatura kontrolü, tedarikçiden kesilip gönderilen resmi faturanın sisteme işlendiği son derece kritik bir finansal kontrol noktasıdır.

![MIRO Fatura Ekranı](/images/sap-miro-ekrani.png)

*Görsel: MIRO Gelen Fatura Girişi*

## Süreç ve Önemli Noktalar
Burada "3'lü Eşleştirme" (Three-Way Matching) yapılır. Sistem; Sipariş Edilen (ME21N), Teslim Alınan (MIGO) ve Faturalandırılan (MIRO) tutarları karşılaştırır. Eşleşme sağlanırsa kayıt atılır ve FI (Finans) modülünde satıcıya ödeme yapılması için alacak belgesi oluşur.

## Veritabanı ve İş Zekası (BI) Notları
Fatura başlık verisi `RBKP`, kalem verisi ise `RSEG` tablosundadır.