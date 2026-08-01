---
title: "Qlik Sense Where Koşulu, Match ve WildMatch Kullanımı"
description: "Qlik Sense'de Data Load sırasında verileri filtreleme yöntemleri. Where koşulu, AND/NOT operatörleri, Match ve WildMatch fonksiyonları ile gelişmiş veri analizi."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "Veri Yükleme", "Filtreleme", "Where", "Eğitim", "İş Zekası"]
---

# Qlik Sense'de Veri Filtreleme: Where, Match ve WildMatch Fonksiyonları

Qlik Sense'te güçlü ve doğru analizler yapabilmenin temelinde, sisteme sadece ihtiyacımız olan doğru veriyi almak yatar. **Where Condition (Where Koşulu)**, veri setinizde belirli koşullara uyan kayıtları Data Load (Veri Yükleme) aşamasında filtrelemek için kullanılan en güçlü fonksiyondur. 

Bu koşullar sayesinde yalnızca belirlediğiniz kriterlere uyan verileri içeri alarak uygulamanızın boyutunu küçültebilir, performansını artırabilir ve görselleştirmelerinizi daha odaklı hale getirebilirsiniz.

## 1. Qlik Sense'de Where Koşulu Kullanımı
Veri analizi yaparken, bazen tüm veritabanı yerine belirli bir bölgeyi, yılı veya kategoriyi filtrelemek isteyebilirsiniz. Örneğin; veritabanımızdan sadece **"Ege Bölgesi"** etiketine sahip müşterileri yüklemek istiyorsak, `FROM` komutundan hemen sonra `WHERE` komutunu ekleriz.


Bu sayede Qlik Sense, diğer bölgelerdeki müşterileri hafızaya almayacak ve sadece Ege Bölgesi'ne ait sonuçlar yüklenecektir.

## 2. Çift Where: AND ve NOT Kullanımı
Veri modellerinde genellikle tek bir kriter yeterli olmaz. Birden fazla koşulu aynı anda sağlayan kayıtları filtrelemek için `AND` operatörü devreye girerek daha hassas sonuçlar elde etmenizi sağlar. Ayrıca `NOT` ifadesini kullanarak dahil etmek istemediğiniz (hariç tutulacak) verileri sistemin dışında bırakabilirsiniz.



## 3. WildMatch() Fonksiyonu Nedir?
**WildMatch()**, Qlik Sense'de metin (string) ifadeleri belirli bir joker karakter (`*` ve `?`) desenine göre eşleştirmek için kullanılan oldukça esnek bir fonksiyondur. 

*   **Büyük/küçük harf duyarlılığı yoktur.** ("A" ile "a" aynı sayılır).
*   Özellikle `WHERE` veya `IF` koşulları içinde kompleks filtreleme ve hesaplamalar için kullanılır.

### WildMatch Sözdizimi (Syntax) ve Joker Karakterler
```sql
WildMatch(metin_alani, 'desen1', 'desen2', ...)