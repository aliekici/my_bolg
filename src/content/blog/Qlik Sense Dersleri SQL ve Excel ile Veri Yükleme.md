---
title: "Qlik Sense ile SQL ve Excel'den Veri Çekme (Data Load Script)"
description: "Qlik Sense'te QMC üzerinden SQL veritabanı bağlantısı kurma ve Excel'den veri çekme adımlarını öğrenin. Data Load Script (ETL) yazma rehberi."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "Veri Yükleme", "SQL", "Excel", "Data Load Script", "İş Zekası", "Eğitim"]
heroImage: ../../assets/covers/cover-qlik.png
---

# Qlik Sense Dersleri: SQL ve Excel ile Veri Yükleme

Bu derste, Qlik Sense üzerinde gösterge panellerimizi (dashboard) ve arayüzümüzü oluşturmak için veri kaynaklarına nasıl bağlanacağımızı ve veriyi sistemin içine nasıl alacağımızı (Data Load) inceleyeceğiz. 

## 1. QMC Üzerinden SQL Veritabanı Bağlantısı Kurma
Qlik Sense'te veri çekmeye başlamadan önce yapmamız gereken ilk ve en önemli adım, **QMC (Qlik Management Console)** veya Hub üzerindeki Veri Bağlantıları ekranından bir kaynak tanımlamaktır. Bu bağlantı, Qlik Sense uygulamanızın veritabanınızla güvenli bir şekilde iletişim kurmasını sağlar.

Bir veritabanı bağlantısı (Örn: SQL Server) oluşturmak için iki temel bilgiye ihtiyacınız vardır:
*   **Sunucu Adresi (Server Address):** Bağlanmak istediğiniz veritabanının bulunduğu sunucunun IP adresi veya hostname'i.
*   **Kullanıcı Bilgileri (Credentials):** Veritabanına okuma (Read) yetkisi olan bir kullanıcı adı ve şifre.

Bu adımlar tamamlandıktan sonra, Qlik Sense Hub tarafında yeni bir uygulama oluşturulur ve **Veri Yükleme Düzenleyicisi (Data Load Editor)** sekmesi açılır. Ekranın sağ tarafındaki "Veri Bağlantıları" paneli, az önce tanımladığınız SQL, SAP veya diğer veri kaynaklarınızı listeleyecektir.

![Qlik Sense Veri Bağlantıları Ekranı](/images/qlik-veri-baglantilari.png)
*Görsel:

 Qlik Sense Veri Yükleme Düzenleyicisi ve Veri Bağlantıları Sekmesi*

## 2. Data Load Script ile SQL'den Veri Çekme
Qlik Sense, veritabanından veri okurken melez bir kod yapısı kullanır. Qlik'in kendi motoruna hitap eden `LOAD` komutu ile SQL veritabanına hitap eden `SELECT` komutu ardışık olarak yazılır.

![Qlik Sense Veri Bağlantıları Ekranı](/images/qlik-veri-örnek.png)
*Görsel:

 Qlik Sense Veri Yükleme Düzenleyicisi ve Veri Bağlantıları Sekmesi*

Veri çekme işlemleri için kullanacağınız temel kod bloğu yapısı şu şekildedir:

![Qlik Sense Veri Bağlantıları Ekranı](/images/qlik-sense-sonuc.png)

*Görsel:
 Qlik Sense Sonuc*
```sql
// İlgili Veritabanı Sunucusuna bağlanılır
LIB CONNECT TO 'Ali Riza Digital DB 10.03.04.2002';

ÖrnekData:
LOAD
    [Banka Adı],     // Qlik tarafında oluşacak alan adı
    İl,	
    İlçe,
    [Şube Müdürü],
    [Ciro]
;
SELECT
    [Banka Adı],     // SQL tarafındaki fiziksel kolon adı
    İl,	
    İlçe,
    [Şube Müdürü],
    [Ciro]
FROM [deneme].[dbo].[örnekdata];

