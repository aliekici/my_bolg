---
title: "Qlik Sense QMC ve Hub Yönetimi: Stream Oluşturma"
description: "Qlik Management Console (QMC) ile iş zekası raporlarınızı yönetin. Stream (klasör) oluşturma, uygulama yayınlama ve kullanıcı yetkilendirme rehberi."
pubDate: "2026-08-01"
tags: ["Qlik Sense", "QMC", "Hub", "Raporlama", "İş Zekası", "Eğitim"]
heroImage: ../../assets/covers/cover-qlik.png
---

# Qlik Sense QMC ve Hub Yönetimi: Temel Bilgiler ve Rapor Yayınlama

Qlik Sense üzerinde kurumsal raporlama yaparken, geliştirme sürecinin yanı sıra uygulamanın son kullanıcıya güvenli ve düzenli bir şekilde ulaştırılması gerekir. Bu noktada karşımıza iki ana bileşen çıkar: Son kullanıcıların raporları tükettiği **Qlik Sense Hub** ve tüm bu mimarinin yönetildiği **Qlik Management Console (QMC)**.

## 1. Qlik Sense QMC (Management Console) Nedir?
QMC ekranı, Qlik platformunun kalbidir ve kapsamlı bir merkezi yönetim paneli olarak görev yapar. Kurduğumuz Bronze-Silver-Gold veri ambarı mimarisinin nihai sunum katmanını ve erişim politikalarını tam olarak buradan yönetiriz. 

Bu güçlü arayüz üzerinden şu kritik süreçler tek merkezden kontrol edilir:
*   Hazırlanan raporların (App) yayınlanması ve paylaşımı.
*   Kullanıcılara lisans (Token/Analyzer/Professional) atamaları.
*   Raporların güncelliğini sağlamak için veri yenileme görevleri (Tasks) oluşturma.
*   Veri ambarı (Data Warehouse) ve ERP sistem bağlantılarının (Data Connections) yönetimi.

![Qlik Sense QMC Genel Bakış](/images/qlik-qmc-genel-ekran.png)
*Görsel: Qlik Management Console (QMC) Kontrol Merkezi*

## 2. Qlik Sense Hub'da Stream (Klasör) Oluşturma
Hub tarafında raporları departmanlara veya konulara göre gruplamak için "Stream" adı verilen çalışma alanları (klasörler) oluştururuz.

1.  **Stream Menüsüne Giriş:** QMC ekranına yönetici yetkisiyle giriş yaptıktan sonra sol menüden **Streams** sekmesine tıklanır.
2.  **Yeni Stream Yaratma:** Gelen ekranda sağ alt köşeden (veya üst menüden) "Create New" seçeneği ile yeni bir klasör adı (Örn: *Satış Raporları* veya *SAP MM Analizleri*) verilerek **Apply** butonuna basılır.
3.  **Sonuç:** Bu işlemle birlikte Hub ekranında görüntülenecek olan Stream yapısı kurulmuş olur. Ancak yetkilendirme yapılmadığı sürece bu klasörü kimse göremez.

## 3. Stream Kullanıcı Yetkilendirmesi (Security Rules)
Oluşturduğumuz dosyanın (Stream) sadece ilgili departman veya kişiler tarafından görülmesini sağlamak, veri güvenliği açısından kritik bir adımdır.

*   Stream oluşturulduktan sonra ilgili kaydın içindeki **Security** (Güvenlik) sekmesine tıklanır.
*   Açılan ekranda, bu çalışma alanını görmesini istediğimiz kullanıcıların (User) veya kullanıcı gruplarının (Group) kuralları tanımlanır.
*   Kurallar kaydedildiğinde (Apply), klasör bazlı yetkilendirme başarıyla sağlanmış olur. Yetkisiz kişiler Hub ekranına girdiklerinde bu klasörü kesinlikle göremezler.

![Qlik Sense Stream Yetkilendirme Ekranı](/images/qlik-qmc-security.png)
*Görsel: QMC Security Rules (Güvenlik Kuralları) Ekranı*

## 4. Oluşturulan Stream'e Uygulama (App) Yayınlama (Publish)
Tasarladığımız iş zekası raporunu (App) son kullanıcıların erişimine açmak için raporu ilgili Stream içerisine "Yayınlamamız" (Publish) gerekir.

1.  QMC sol menüsünden **Apps** sekmesine girilir.
2.  Geliştirme ortamında (Work) bulunan ve yayınlanmak istenen raporun adı listeden bulunur ve seçilir.
3.  Ekranın alt kısmında veya sağ menüde yer alan **Publish (Yayınla)** butonuna tıklanır.
4.  Gelen onay penceresinde, raporun hangi **Stream** içerisine (Örneğin az önce oluşturduğumuz dosyaya) aktarılacağı seçilir ve işlem tamamlanır.

Bu sayede raporunuz, belirlediğiniz yetki kuralları çerçevesinde Hub üzerinde canlıya alınmış olur. SAP SD gibi satış modüllerinden veya diğer kaynaklardan gelen verileriniz artık son kullanıcıların etkileşimli analizine hazırdır.