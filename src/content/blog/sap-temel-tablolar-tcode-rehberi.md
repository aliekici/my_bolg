---
title: "SAP ERP'de Temel Tablolar ve Transaction Kodları (T-Code) Rehberi"
description: "SAP FI, MM ve SD modüllerinde en sık kullanılan tabloları ve transaction kodlarını (T-Code) örneklerle özetleyen pratik referans rehberi."
pubDate: 2026-07-25
category: "SAP"
tags: ["SAP", "T-Code", "SAP Tabloları", "SAP FI", "SAP MM", "SAP SD"]
---

## Neden Bir T-Code ve Tablo Rehberine İhtiyaç Var?

SAP ile çalışan herkes — ister uçtaki kullanıcı ister BI/ETL uzmanı olsun — bir noktada "bu veri hangi tabloda, hangi ekrandan görülür" sorusuyla karşılaşır. Bu yazıda, SAP FI, MM ve SD modüllerinde en sık kullanılan tabloları ve transaction kodlarını (T-Code) tek bir referans noktasında topluyoruz.

## SAP FI – Finansal Muhasebe Tabloları

| Tablo/T-Code | Açıklama |
|---|---|
| **BKPF** | Muhasebe belgesi başlık verisi |
| **BSEG** | Muhasebe belgesi kalem verisi (en detaylı finansal veri) |
| **FBL1N** | Tedarikçi hesap ekstresi (Vendor Line Items) |
| **FBL5N** | Müşteri hesap ekstresi (Customer Line Items) |
| **FS10N** | Genel muhasebe hesap bakiyeleri |

## SAP MM – Malzeme Yönetimi Tabloları

| Tablo/T-Code | Açıklama |
|---|---|
| **MB51** | Malzeme hareketleri listesi |
| **MARA / MARC** | Malzeme ana verisi (genel ve fabrika bazlı) |
| **MSEG / MKPF** | Malzeme belge kalemleri ve başlıkları |
| **COOIS** | Üretim siparişi bilgi sistemi (planlanan/gerçekleşen) |
| **ME23N** | Satın alma siparişi görüntüleme |

## SAP SD – Satış ve Dağıtım Tabloları

| Tablo/T-Code | Açıklama |
|---|---|
| **VBAK / VBAP** | Satış siparişi başlık ve kalem verisi |
| **LIKP / LIPS** | Teslimat başlık ve kalem verisi |
| **VBRK / VBRP** | Fatura başlık ve kalem verisi |
| **VA03** | Satış siparişi görüntüleme |
| **VL03N** | Teslimat belgesi görüntüleme |

## BI/ETL Perspektifinden Pratik Öneriler

Bu tablolarla çalışırken göz önünde bulundurulması gereken birkaç pratik nokta:

1. **Başlık-kalem ilişkisi:** SAP tabloları genelde başlık (header) ve kalem (item) olarak ikiye ayrılır (örneğin VBAK-VBAP). ETL modellemesinde bu ilişki doğru kurulmalıdır.
2. **Anahtar alanlar:** Şirket kodu, belge numarası ve kalem numarası gibi alanlar, tabloları birleştirirken (join) en kritik anahtarlardır.
3. **Veri hacmi:** BSEG ve MSEG gibi kalem tabloları çok büyük olabilir; performans için uygun filtreleme ve artımlı (incremental) yükleme stratejileri kullanılmalıdır.
4. **T-Code'lar raporlama için değil, doğrulama için kullanılır:** BI raporları genellikle bu tabloların arka planındaki verilerden üretilir; T-Code'lar ise geliştirme sürecinde veri doğrulama amacıyla kullanılır.

## Bu Rehberi Nasıl Kullanmalısınız?

Bu tabloyu bir başvuru kaynağı olarak saklayabilirsiniz. Örneğin bir stok analizi yaparken MB51/MSEG'e, bir satış performans raporunda VBAK/VBRK'a, bir finansal risk analizinde ise BSEG'e yönelmeniz gerektiğini bilmek, geliştirme sürecinizi önemli ölçüde hızlandıracaktır.

## Sonuç

SAP ekosisteminde tablo ve T-Code bilgisi, hem fonksiyonel hem de teknik ekipler için ortak bir dil oluşturur. FI, MM ve SD serimizin bu son yazısıyla birlikte, SAP'nin üç temel modülünü hem süreç hem de veri tabanı seviyesinde ele almış olduk. Bu rehberleri SAP projelerinizde ve raporlama çalışmalarınızda referans olarak kullanabilirsiniz.
