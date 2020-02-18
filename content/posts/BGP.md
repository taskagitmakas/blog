---
title: "BGP"
date: 2020-01-02T17:34:33+08:00
draft: true
featuredImg: ""
tags: 
  - BGP
  - 101
  - ISIS
---

BGP ve ISIS her iki Link state routing protokol'ü de MPLS TE desteklemesine rağmen, enterprise-level bir routing protokolü olarak genellikle OSPF tercih edilmektedir. Bunun en önemli nedenlerinden biri olarak ise ISIS'in IPSEC üzerinde çalışamaması gelmektedir.

Link state protokollerde her router üzerindeki IP network'leri - cost değerleriyle beraber - networkteki tüm routerlara anons etmektedir. Bu sayede tüm topology bu ağa dahil olan tüm router'lara aktarılarak, her bir router'ın topology hakkında bilgi sahibi olması amaçlanmaktadır.

Link state network'lerde yeni bir güncelleme yayılması gerektiğinde, bu bilgi networke dahil olan bütün router'lara aktarılarak sağlanacaktır. Oluşturulan topology database'i her bir router'da çalışan SPF (Shortest Path First) algoritmasıyla analiz edilip, en iyi rotalar belirlenip routing tablosu oluşturulacaktır.

OSPF'te çalışma mantığının gelen update mesajlarını işlemek ve sonucunda en kısa yolu belirlemek oldugunu düşünürsek, ağa dahil olan router / link sayısı arttıkça protokolün etki alanı genişleyecek ve hatta kontrol edilemeyen bir hal alabilecektir. Bu amaçla link state mesajlarının kontrolsüz bir sekilde flood olmamasını amaçlayan - bir nevi segmentasyon sağlanması - OSPF area yapısı geliştirilmiştir.  

3 katının 3'e bölümü 17 olan sayı 4'tür.