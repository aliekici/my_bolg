---
title: "SAP SD Modülü: Satış ve Dağıtım Süreçlerine Giriş"
description: "SAP SD (Sales and Distribution) modülünün sipariş yönetimi, sevkiyat ve faturalama süreçlerini, önemli tablolarını ve raporlama açısından değerini anlatan rehber."
pubDate: 2026-07-23
category: "SAP"
tags: ["SAP", "SAP SD", "ERP", "Satış Yönetimi", "Lojistik"]
---

## SAP SD Modülü Nedir?

**SAP SD (Sales and Distribution / Satış ve Dağıtım)**, bir şirketin müşteri siparişlerinden sevkiyata, faturalamadan tahsilata kadar tüm satış sürecini yönettiği modüldür. Üretim şirketlerinde SAP SD, SAP MM ile sıkı bir entegrasyon içinde çalışır: MM'de üretilen ürün, SD üzerinden müşteriye ulaşır.

Lojistik ve satış operasyonlarında çalışmış biri için SAP SD, sefer optimizasyonu ve satış performansı raporlamasının temel veri kaynağıdır.

## SAP SD'nin Temel Süreç Akışı

Klasik bir SAP SD süreci (Order-to-Cash / O2C) şu adımlardan oluşur:

1. **Satış Siparişi Oluşturma (Sales Order):** Müşteri talebinin sisteme girilmesi
2. **Teslimat (Delivery):** Depo çıkışı ve sevkiyat belgesinin oluşturulması
3. **Mal Çıkışı (Goods Issue):** Stoktan düşme işlemi — burada MM modülüyle entegrasyon devreye girer
4. **Faturalama (Billing):** Müşteriye fatura kesilmesi ve bu adımın FI modülüne (Alacak Yönetimi) yansıması

Bu akış, şirketin **Order-to-Cash (O2C)** döngüsünün temelini oluşturur ve BI raporlamasında en sık analiz edilen süreçlerden biridir.

## SAP SD ile İlgili Önemli Tablolar

- **VBAK / VBAP:** Satış siparişi başlık ve kalem verileri
- **LIKP / LIPS:** Teslimat başlık ve kalem verileri
- **VBRK / VBRP:** Fatura başlık ve kalem verileri

Bu tablolar, satış hunisi (sales funnel) analizleri, bölge bazlı satış performansı ve müşteri bazlı karlılık raporları için temel veri kaynaklarıdır.

## SAP SD Verisiyle Raporlama Örnekleri

BI tarafında SAP SD verisinden üretilebilecek tipik raporlar:

- **Bölge/bayi bazlı satış performans dashboard'ları**
- **Sipariş gerçekleşme oranı (Order Fulfillment Rate)** analizleri
- **Sevkiyat gecikme analizleri** — planlanan ile gerçekleşen teslimat tarihleri karşılaştırması
- **Müşteri bazlı ciro ve karlılık raporları**

Bu raporlar genellikle Qlik Sense veya Power BI üzerinde, SAP SD ve SAP FI verilerinin birleştirilmesiyle (satış + tahsilat) hazırlanır.

## Lojistik Tarafında SAP SD'nin Rolü

Sefer planlama ve lojistik operasyonlarında SAP SD, teslimat belgeleri üzerinden **sevkiyat optimizasyonu** için kritik veriler sağlar. Örneğin bir lojistik ekibi, LIKP/LIPS tablolarından günlük sevkiyat hacmini analiz ederek araç ve rota planlamasını optimize edebilir.

## SAP SD ile Çalışırken Dikkat Edilmesi Gerekenler

1. **Belge tipi (Sales Document Type) çeşitliliği:** Standart sipariş, iade, kredi notu gibi farklı belge tipleri ayrı ele alınmalı.
2. **Fiyatlandırma yapısı (Pricing Procedure):** İskonto ve vergi hesaplamaları raporlama katmanında doğru yansıtılmalı.
3. **MM-SD entegrasyonu:** Stok ve satış verisinin tutarlı şekilde birleştirilmesi, ETL tasarımının en kritik noktasıdır.

## Sonuç

SAP SD modülü, şirketin müşteriyle olan tüm etkileşimini veri haline getiren süreçtir. FI ve MM modülleriyle birlikte ele alındığında, uçtan uca bir **Order-to-Cash** görünürlüğü sağlar. Bir sonraki yazıda bu üç modülün (FI-MM-SD) birlikte nasıl çalıştığını, uçtan uca entegrasyon mantığıyla inceleyeceğiz.
