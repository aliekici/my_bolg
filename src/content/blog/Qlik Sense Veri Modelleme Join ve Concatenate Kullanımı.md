---
title: "Qlik Sense Veri Modelleme: Join ve Concatenate Kullanımı"
description: "Qlik Sense'te sağlam bir veri modeli kurmanın temelleri. Left Join, Right Join, Inner Join ve Concatenate fonksiyonlarını örnek senaryolarla öğrenin."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "Veri Modelleme", "Join", "Concatenate", "İş Zekası", "Eğitim"]
heroImage: ../../assets/covers/cover-qlik.png
---

# Qlik Sense Veri Modelleme: Tablo Birleştirme (Join & Concatenate)

Qlik Sense’te güçlü, performanslı ve doğru analizler yapabilmenin temelinde sağlam bir veri modeli yatar. Uygulamaya aldığınız verilerin birbiriyle konuşabilmesi (ilişkilenmesi) için tabloları doğru yöntemlerle birleştirmek şarttır. 

Bu yazıda, veri modellemesinde en sık kullanılan **Left Join, Right Join, Inner Join ve Concatenate** fonksiyonlarını örnek bir satış senaryosu üzerinden adım adım inceleyeceğiz. Amacımız, doğru modellemeyle hem performansı artırmak hem de raporlamalardaki analiz tutarlılığını sağlamaktır.

## 1. Veri Setinin Hazırlanması ve Ortak Alanlar (Key Fields)
Örnek senaryomuz için içerisinde iller, bölgeler, yöneticiler ve satış tutarları olan bir veri seti kullanacağız. 

Qlik Sense'in **Associative Engine (İlişkilendirme Motoru)**, tabloları birbiriyle otomatik olarak bağlamak için "Aynı İsimli Alanları" (Key Fields) arar. Bu nedenle ilk adımımız, birleşecek tablolardaki ortak anahtar kelimelerin isimlerini eşitlemektir (Örn: `Bölge`). 

Ortaklaştırma yapıldıktan sonra "Veri Modeli Görüntüle" (Data Model Viewer) ekranını açtığınızda tabloların birbirine bağlandığını görebilirsiniz.

![Qlik Sense Veri Modeli Görüntüleyici](/images/qlik-veri-modeli-goruntule1.png)
*Görsel: Qlik Sense Veri Modeli Görüntüleyicisi'nde tabloların (Merkezler, Bolgeler, Saticilar) birbirine "Bölge" alanı üzerinden bağlanması.*

---

## 2. Left Join ile Tablo Birleştirme
`Left Join`, en sık kullanılan birleştirme türüdür. Ana tabloyu (Sol) sabit tutar ve diğer tablodan (Sağ) sadece eşleşen verileri getirerek ana tablonun yanına ekler.

```sql
Merkezler:
LOAD
    Bölge,
    Merkez
FROM [lib://QVD/LIVE/OTHER_SYSTEM/data.xlsx]
(ooxml, embedded labels, table is Merkezler);

Left Join(Merkezler)

Bolgeler:
LOAD
    Upper(bolge) as Bölge,
    yonetici
FROM [lib://QVD/LIVE/OTHER_SYSTEM/data.xlsx]
(ooxml, embedded labels, table is Bolgeler);"
description: "Qlik Sense'te sağlam bir veri modeli kurmanın temelleri. Left Join, Right Join, Inner Join ve Concatenate fonksiyonlarını örnek senaryolarla öğrenin."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "Veri Modelleme", "Join", "Concatenate", "İş Zekası", "Eğitim"]
---

# Qlik Sense Veri Modelleme: Tablo Birleştirme (Join & Concatenate)

Qlik Sense’te güçlü, performanslı ve doğru analizler yapabilmenin temelinde sağlam bir veri modeli yatar. Uygulamaya aldığınız verilerin birbiriyle konuşabilmesi (ilişkilenmesi) için tabloları doğru yöntemlerle birleştirmek şarttır. 

Bu yazıda, veri modellemesinde en sık kullanılan **Left Join, Right Join, Inner Join ve Concatenate** fonksiyonlarını örnek bir satış senaryosu üzerinden adım adım inceleyeceğiz. Amacımız, doğru modellemeyle hem performansı artırmak hem de raporlamalardaki analiz tutarlılığını sağlamaktır.

## 1. Veri Setinin Hazırlanması ve Ortak Alanlar (Key Fields)
Örnek senaryomuz için içerisinde iller, bölgeler, yöneticiler ve satış tutarları olan bir veri seti kullanacağız. 

Qlik Sense'in **Associative Engine (İlişkilendirme Motoru)**, tabloları birbiriyle otomatik olarak bağlamak için "Aynı İsimli Alanları" (Key Fields) arar. Bu nedenle ilk adımımız, birleşecek tablolardaki ortak anahtar kelimelerin isimlerini eşitlemektir (Örn: `Bölge`). 

Ortaklaştırma yapıldıktan sonra "Veri Modeli Görüntüle" (Data Model Viewer) ekranını açtığınızda tabloların birbirine bağlandığını görebilirsiniz.

![Qlik Sense Veri Modeli Görüntüleyici](/images/qlik-veri-modeli-goruntule.png)
*Görsel: Qlik Sense Veri Modeli Görüntüleyicisi'nde tabloların (Merkezler, Bolgeler, Saticilar) birbirine "Bölge" alanı üzerinden bağlanması.*

---

## 2. Left Join ile Tablo Birleştirme
`Left Join`, en sık kullanılan birleştirme türüdür. Ana tabloyu (Sol) sabit tutar ve diğer tablodan (Sağ) sadece eşleşen verileri getirerek ana tablonun yanına ekler.

```sql
Merkezler:
LOAD
    Bölge,
    Merkez
FROM [lib://QVD/LIVE/OTHER_SYSTEM/data.xlsx]
(ooxml, embedded labels, table is Merkezler);

Left Join(Merkezler)

Bolgeler:
LOAD
    Upper(bolge) as Bölge,
    yonetici
FROM [lib://QVD/LIVE/OTHER_SYSTEM/data.xlsx]
(ooxml, embedded labels, table is Bolgeler);