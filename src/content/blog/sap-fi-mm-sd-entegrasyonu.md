---
title: "SAP FI-MM-SD Entegrasyonu: Uçtan Uca Sipariş-Tahsilat Döngüsü (O2C)"
description: "SAP'nin en önemli üç modülü olan FI, MM ve SD'nin birbirleriyle nasıl entegre çalıştığını, Order-to-Cash ve Procure-to-Pay döngüleri üzerinden anlatan rehber."
pubDate: 2026-07-24
category: "SAP"
tags: ["SAP", "SAP FI", "SAP MM", "SAP SD", "ERP Entegrasyonu", "O2C", "P2P"]
---

## SAP Modülleri Neden Birlikte Ele Alınmalı?

SAP FI, SAP MM ve SAP SD modülleri, uygulamada birbirinden bağımsız çalışmaz. Gerçek bir iş sürecinde (bir siparişin alınmasından paranın tahsil edilmesine kadar) bu üç modül sürekli veri alışverişi yapar. BI ve ETL tarafında çalışan bir uzman için bu entegrasyonu anlamak, doğru ve tutarlı raporlar üretmenin ön koşuludur.

Bu yazıda iki temel iş sürecini ele alacağız: **Order-to-Cash (O2C)** ve **Procure-to-Pay (P2P)**.

## Order-to-Cash (O2C): Satıştan Tahsilata

O2C süreci, bir müşteri siparişinin alınmasından paranın şirket hesabına geçmesine kadar olan tüm adımları kapsar:

1. **SD – Satış Siparişi:** Müşteri talebi sisteme girilir (VBAK/VBAP)
2. **MM – Mal Çıkışı:** Depo stoğundan ürün düşülür (MSEG)
3. **SD – Faturalama:** Müşteriye fatura kesilir (VBRK/VBRP)
4. **FI – Alacak Kaydı:** Fatura, otomatik olarak FI-AR'a yansır (BSEG)
5. **FI – Tahsilat:** Müşteri ödemesi sisteme işlenir ve alacak kapanır

Bu zincirin herhangi bir noktasında veri tutarsızlığı, raporlama katmanına yanlış sonuçlar olarak yansır. Örneğin sevkiyatı yapılmış ama faturalanmamış siparişler, "faturalama gecikmesi" analizlerinin temelini oluşturur.

## Procure-to-Pay (P2P): Talep Etmeden Ödemeye

P2P süreci ise tedarik tarafındaki entegrasyonu gösterir:

1. **MM – Satın Alma Talebi:** İhtiyaç belirlenir (Purchase Requisition)
2. **MM – Satın Alma Siparişi:** Tedarikçiye sipariş açılır (Purchase Order)
3. **MM – Mal Girişi:** Ürün depoya girer (Goods Receipt)
4. **FI – Fatura Doğrulama:** Tedarikçi faturası kontrol edilir
5. **FI – Ödeme:** Tedarikçiye ödeme yapılır ve borç kapanır

## BI Tarafında Entegre Raporlama Yaklaşımı

Bu üç modülü birleştiren bir veri ambarı (DWH) tasarlarken izlenebilecek yaklaşım:

- **Bronze katman:** SAP'den ham haliyle çekilen FI/MM/SD tabloları (BSEG, MSEG, VBRK vb.)
- **Silver katman:** Belge tipleri, hareket tipleri ve şirket kodu bazında temizlenmiş, ilişkilendirilmiş veri
- **Gold katman:** O2C ve P2P süreçlerinin uçtan uca görünürlüğünü sağlayan analitik tablolar (örneğin "sipariş-teslimat-fatura-tahsilat" zaman çizelgesi)

Bu **Medallion Mimarisi** yaklaşımı, karmaşık SAP verisini yönetilebilir ve performanslı bir raporlama katmanına dönüştürmenin en pratik yollarından biridir.

## Sık Karşılaşılan Entegrasyon Sorunları

1. **Zaman uyumsuzluğu:** Mal çıkışı ile fatura kesimi arasında gün bazında fark olabilir; raporlarda bu gecikme ayrıca izlenmeli.
2. **Kısmi teslimatlar:** Bir sipariş birden fazla teslimat ve faturaya bölünebilir; bu durumda kalem bazlı eşleştirme (line-item matching) gereklidir.
3. **Çoklu para birimi:** Uluslararası operasyonlarda kur farkları FI tarafında ayrıca ele alınmalıdır.

## Sonuç

SAP FI, MM ve SD modüllerinin entegrasyonunu anlamak, sadece teknik bir gereklilik değil; aynı zamanda işin gerçek akışını görebilmek için de kritik bir yetkinliktir. Bir sonraki ve son yazımızda, bu üç modülle çalışırken sıkça kullanılan temel tabloları ve transaction kodlarını (T-Code) bir arada özetleyeceğiz.
