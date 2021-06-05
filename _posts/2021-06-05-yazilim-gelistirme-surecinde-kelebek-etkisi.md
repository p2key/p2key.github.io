---
title: Yazılım Geliştirme Sürecinde Kelebek Etkisi
layout: post
tags:
- yazılım
- geliştirme
comments: true
---

İyi bir yazılım geliştirmenin, yazılım geliştirme metodolojileri ile ilgisi yoktur. Agile, waterfall gibi metodolojiler sizin veriyi HashMap de mi yoksa ConcurrentHashMap de mi tutacağınızla ilgilenmez. Ya da tekrar kullanılabilsin diye yazdığınız bir util method da verdiğiniz karar genel bir performans sorununa neden olabilir, tek bir request üzerinden trace ettiğinizde belki kaale almayacağınız bir durum olsa da, günün sonunda ağır bir çalışan bir uygulamanız olabilir.

Az kullanıcılı, düşük istek alan uygulamalar için bunlar çok önemli olamayabilir. Tabi şimdilik!

Eğer büyüme hedefiniz varsa küçük uygulamalarınızda  da bunlara dikkat etmelisiniz. Aksi takdirde conversion, migration, switching işlerine girersiniz ki böyle olunca da uygulamanız kompleksleşir. Günün birinde "uygulamamız çok kompleksleşti, bunu basitleştirmemiz lazım" diyerek işi yılan hikayesine dönüştürebilirsiniz.

Bir yazılım ürünü yaşayan bir organizma gibidir. Gün geçtikçe yaşlanır. Çünkü yazılımın hizmet ettiği business değişir. Değişen business için new future lar eklemeye başlarsınız fakat iyi entegre edemezseniz bütünselliği kaybedersiniz. Bu seferde heryeri yamalı giysi gibi duran günün birinde yeni bir özellik eklemek isteyince nereye yazacağınızı bilemediğiniz bir uygulamanız olur. 

Yazılım geliştirme sürecinizde herşeyin yolunda gitmesi demek, gün geçtikçe yazılım için gereken insan kaynağına daha az ihtiyaç duymanız demektir ya da aynı insan kaynağıyla daha fazla iş çıkarmak demektir. Bundan kasıt mesai yapmak, daha fazla efor sarfetmek değil. İyi bir yazılım mimarisi tasarladınız, yeni özellik eklemek çok kolay demektir.


Yazılım mimarisini bir insan iskeletine benzetecek olursak, yazılım ürünü iskeletin ete bürünmüş halidir. Demek istediğim yazılımı tamamladıktan sonra mimarisini oluşturamazsınız ya da değiştiremezsiniz.

Yazılım hatalarının nasıl oluştuğu, nasıl düzeltildiği, bir daha olmaması için gereken aksiyon gibi süreçleri pek düşünmüyoruz. Aslında bunlar gerçek hayat örnekleri ve diğer yazılım geliştiricilere aktarılmalı. Hatta sırf bunlardan eğitim bile oluşturulabilir.


Bütün bu anlattıklarım major gibi görünmese de kelebek etkisi yaratır. Günün sonunda illaki major bir problemin nedeni olur.
