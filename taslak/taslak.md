---
layout:     post
title:      Neden "Haydi Rails Yazalım" ?
date:       2016-10-27
summary:    Ruby on Rails
categories: rails
tags:
 - ruby
 - topluluk
---

Ruby ile ilk tanışmam Trabzon'da gerçekleştirdiğimiz [**Kodla**](http://kodla.co/) 2015 etkinliğinde [**Serdar Doğruyol**](https://twitter.com/sdogruyol)'un Ruby'den ve Ruby topluluğundan bahsetmesiyle oldu. Doğal dile yakın olmasıyle girdi, ingilizce biliyorsanız dili biliyorsunuzdan çıktı :) Tabiki ingilizcem yeterli değildi fakat ilgimi çekmeyi başardı.

2015 yazında ilk zorunlu stajımı aramaya koyulmuştum. Fakat ne ile ilgili olacağı konusunda aklımda net bir fikir yoktu. [**Yeni Hayat Bilişim**](http://www.yh.com.tr)'de stajıma başladım. Burada iki seçeneğim vardı. Ben bu seçeneklerden Ruby on Rails'ı seçtim. Günümüzde bir şey ile ilgili dökuman bulmak oldukça kolay. Bir şekilde başlangıcı gerçekleştirmek basit. [**Sıtkı Bağdat**](https://twitter.com/sitkibagdat)'ın Ruby ve Ruby on Rails kitaplarını sipariş ettim. Aslında Ruby'e başlamadan doğrudan Rails'a başladım burada. Kısa süre içerisinde bir şeyler öğrenmek ve bunu uygulamak istiyordum. 19 günlük stajım bitmişti ve Rails'a ısınmıştım.

Aynı yaz Linux Yaz Kampı'nda Ruby on Rails eğitimine başvurumu yaptım. Listelerin açıklandığı gece oldukça heyecanlıydım. İsmimi gördüğümde çok sevindim. Amaçları aynı olan insanlarla bir arada bulunmak motivasyonumu arttırmıştı. Ruby ile başlayan eğitim, heroku'da son bulmuştu. [**Serdar Doğruyol**](https://twitter.com/sdogruyol), [**Tayfun Erikan**](https://twitter.com/toziserikan), [**Mehmet Beydoğan**](https://twitter.com/beydogan_), [**Kader Sucuk**]((https://twitter.com/sucuklukfasulye)), [**Eyüp Atiş**](https://twitter.com/eyup_atis) gibi hocalarım RoR'u ve topluluk bilincini aşılamışlardı bana. 15 gün boyunca aldığım RoR eğitimi kafamı açmaya yetmişti.

Bir sonraki topluluk durağım [**Akademik Bilişim**](http://ab.org.tr) 2016 oldu. Burada Ruby on Rails Proje sınıfında [**Railsquare**](https://github.com/AB2016-RoRAtolye/railsquare) adında bir proje ortaya çıkarmıştık. Kısa sürmesine rağmen hem eğlenceli hem fayda dolu zamanlar geçirmiştim.

Bir süredir Ruby on Rails yazıyorum, yazmaya çalışıyorum. Serüvenim 2015 yazıyla başladı. Önce Rails yazan bir yerde staj ardından LYK2015'de Rails eğitimi. LYK'nın gerçekten çok güzel bir ortamı vardı. Özlüyorum. Neyse, haml'a geçecek olursam kendisiyle LYK'da [**Tayfun Öziş Erikan**](https://twitter.com/toziserikan) sayesinde tanıştım. Genel hatlarıyla nasıl kullanabileceğimizden ve ne olduğundan bahsetmişti. Yazım tarzı tam da benim istediğim şekilde düzenliydi ve genel itibari ile kısa bir yazımı vardı. Benim istediğim derken düzenli birisi değilimdir. İşte bu yüzden dikkatimi çekmişti. Düzenli yazmak zorundasın yoksa kırmızıyı görürsün, çok basit. İlk aklıma takılan soru haml yazıyoruz güzel, peki bir performans kaybı yaşar mıyız? Benim için oldukça gereksiz bir soruydu kabul ediyorum.

Ardından keni projelerimde kullanmaya çalıştım. İlk kullanmaya başladığımda tökezledim. Bıraktım html'e geçtim. Normal'de çatır çutur html yazan biri de değilim. Html'i görmekten de bıkmıştım. Ayrıca erb(embeded ruby)'de ki karakterler de fazla gelmeye başlamıştı bana. Ne kadar editor tuş kombinasyonları olsa da benim isteğim sadeleştirmek yönündeydi. İlk projeyi pas geçtim fakat bir sonrakinde kullanmak istiyordum ve kullandım. İlk kullanmanın etkisiyle çuvallar gibi oldum. Indent hataları filan derken mücadele ettim. Fakat güzel geldi, sevdim. Bunu örnekler ile göstermeliyim.

```haml
/birds.html.haml

%ul
  - @birds.each do |are|
    %li{id: "#{are.id}"}= are.flying
```

html + erb karşılığı

```html
/birds.html.erb

<ul>
  <% @birds.each do |are| %>
    <li id:"#{are.id}"><%= are.flying %></li>
</ul>
```

Performans açısından nasıl bir etkisi olduğuyla ilgili araştırma yapma istediği duydum. Testlerde Erb'den bir kaç kat daha yavaş olduğu öğrendim. Fakat benim için değişen bir şey olmadı. 

Gitlab'ın community editon repo'suna baktığımda aynı şekilde onlarında haml yazmış olduğunu görmek bende haml yazmak üzerine biraz daha istek doğdu. Büyük bir projede sağlıklı şekilde kullanılabildiğini görmek beni haml yazmaya daha da motive etti.

Rails projesinde haml yazmak istiyorum diyorsanız 'haml' gem'ini Gemfile dosyanıza eklemeli ve 'bundle install' ile komutu ile yazmaya başlabilirsiniz. Ayrıca projeniz hali hazırda erb ile devam ediyor ise bunu komple elle haml'a çevirmek elbetteki yorucu olacaktır. Bunu düşünen bir geliştiricide mevcut projedeki tüm erb'leri haml'a çeviren bir paket yazmış.erb2haml ismi de bu.



