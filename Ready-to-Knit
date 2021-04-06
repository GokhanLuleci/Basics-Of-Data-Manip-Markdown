---
title: "Veri Madenciliği Basit Komutlar"
author: "Gökhan Lüleci"
date: "28/03/2021"
output:
  html_document:
    df_print: paged
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = T)
options(knitr.duplicate.label = "allow")
state.x77 <- data.frame(state.x77)
```

# Giriş

Bu çalışma  Veri Madenciliği basit komutları kapsamında hazırlanmıştır.

Ödev kapsamında yapılan uygulamalar için R içerisinde yer alan  **state.x77** veri tabanı kullanılmıştır.

Öncelikle veriyi tanıyalım.

**state.x77: Birleşik Devletlerin 50 Eyaletinin 8 Farklı Değişkene ait değerlernini göstermektedir.**

_Population:_ 1 Temmuz 1975 tarihi itibariyle eyaletlerin mevcut nufüs toplamını göstermektedir.

_Income:_ 1974 Yılı itibariyle Kişi Başı Geliri göstermektedir.
_Illiteracy:_ 1970 yılındaki nufüsa göre okuma-yazma bilmeme oranını göstermektedir. 
_Life Exp:_ 1969 ve 1971 yılları sürecinde ortalama ömür beklentisini göstermektedir. 
_Murder:_ 1976 yılı itibariyle 100.000 kişi başına düşen cinayet ve ihmal-dışı adam öldürme oranını göstermektedir.
_HS Grad:_ 1970 yılı itibariyle Lise Mezunu oranını göstermektedir. 
_Frost:_ Eyaletin başkentinde veya en büyük kentinde ölçülen minimum sıcaklığın donma noktasının altında olduğu ortalama gün sayısını göstermektedir. (1931–1960 arası)
_Area:_ Eyaletin yüzölçümünün mil-kare olarak karşılığıdır.

```{r 1}
str(state.x77)
head(state.x77)   
```

## Soru 1:  Veri seti üzerinde  her komut için 1 adet örnek işlemi için uygulayarak kısaca ne yaptığınızı belirtiniz.

### 1.1 [n,] komutu 

Bu komut ile söz konusu eyaletler içinden n ‘inci satırda yer alan eyalete ait tüm veriler getirilir. Örneğin, **Massachusetts** Eyaleti için ilgili verileri 
getirelim.

labels(state.x77) ile veri incelendiğinde **Massachusetts** eyaletinin 21. Sırada olduğu gözükmektedir. Söz konusu eyalete ilişkin bilgiler aşağıdaki kodlar 
vasıtası ile çağırılır.

```{r 2}
state.x77[21,]
```

### 1.2 data[-n,] komutu

Bu komut ile  söz konusu eyaletler içinden n ‘inci satırda yer alan tüm veriler çıkartılır. Örneğin, az önce incelediğimiz **Massachusetts** Eyaleti 
için ilgili verileri veritabanından kaldıralım ve satır sayısına bakalım.


```{r 3}
nrow(state.x77)
nrow(state.x77[-21,])
```

### 1.3 data[1:n,] komutu

Bu komut ile  söz konusu eyaletler içinden 1. sıradan itibaren istenen n ‘inci sıraya kadar  yer alan tüm veriler seçilir. Örneğin, En baştan itibaren 
yer alan 10 eyaleti seçelim.


```{r 4}
state.x77[1:10,]
```

### 1.4 data[-(1:n),]] komutu

Bu komut ile  söz konusu eyaletler içinden 1. sıradan itibaren istenen n ‘inci sıraya kadar  yer alan tüm veriler çıkartılır. Örneğin, sadece ilk ve 
son 5 eyalet ile ilgilendiğimizde 6'dan başlayarak 44. eyalet dahil tüm  eyaletleri veriden çıkartalım.


```{r 5}
nrow(state.x77)
state.x77[-(6:44),]
```

### 1.5 data[c(i,j,k),] komutu

Bu komut ile  belirlenen i, j ve k yerine satır numarası yazılarak seçilen 3 eyalete ait veriler çağırılır. Örneğin İlk(1) , Ortanca (25) ve sonuncu(50)
eyaletleri ve bilgilerini çağıralım. 


```{r 6}
state.x77[c(1,25,50),]
```

### 1.6 data[x > y,] komutu

Bu komut ile  x>y mantık testine uygun gelen satırlara ait tüm sütun verisi gelir. Örneğin yüzölçümü 100.000 inç kareden fazla olan eyaletlere ilişkin tüm 
bilgileri getirelim.

```{r 7}
state.x77[state.x77$Area > 100000,]
```

### 1.7 data[,m] komutu

Bu komut ile m’inci  sütuna ilişkin tüm satır verisi getirilir. Örneğin tüm eyaletlere ait sadece kişi başı gelir rakamlarını getirelim. 

```{r 8}
colnames(state.x77)[2]
state.x77[,2]
```

### 1.8 data[,-m] komutu

Bu komut ile m’inci  sütununda yer alan tüm verisi çıkartılır. Örneğin eyalatlerde işlenen cinayetlere ilişkin verileri çıkaralım ve oluşan kolon sayısına 
bakalım. 

```{r 9}
ncol(state.x77)
ncol(state.x77[,-5])
```

### 1.9 data[,1:m] komutu

Bu komut ile 1'den m’inci  sutüna kadar yer alan tüm satırlara ilişkin bilgiler getirilir. Örneğin tüm eyalatlere ailt Popülasyon(1), Kişi Başı Gelir(2) ve 
Okuma-Yazma Bilmeme Oranı(3) verilerini getirelim.

```{r 10}
colnames(state.x77)[1:3]
state.x77[,1:3]
```

### 1.10 data[,-(1:m)] komutu

Bu komut ile 1'den m’inci  sutüna kadar yer alan tüm kolonlar çıkartılır. Örneğin sadece eyalatlerde işlenen donma derecesinin altındaki gün sayısı (7) ve 
yüzölçümü (8) verilerini kontrol etmek için en baştan itibaren 6. sutüna kadarki tüm  verileri çıkaralım. 

```{r 11}
colnames(state.x77)
state.x77[,-(1:6)]
```

### 1.11 data[,c(i,j,k)] komutu

Bu komut ile  belirlenen i, j ve k yerine  numara yazılarak seçilen 3 özelliğe ilişkin eyaletlerin tamamının verileri çağırılır. Örneğin Popülasyon(1) , 
Ortalama Yaşam Beklentisi (4) ve Lise Mezunu Oranı(6) değişkenlerine ait tüm eyaletler bilgilerini çağıralım.

```{r 12}
colnames(state.x77)
state.x77[,c(1,4,6)]
```

### 1.12 data[,x > y] komutu

Bu komut ile  x>y mantık testine uygun gelen sutünlara ait tüm satır verileri getirilir. Örneğin 2.satırda 100.000 den az olan tüm kolonlardaki tüm satırlara 
ilişkin tüm bilgileri getirelim. Görüldüğü üzere Alaska'nın yüzölçümü 100.000'den büyük olduğu için söz konusu kolon çağırılmamıştır.


```{r 13} 
state.x77[,state.x77[2,] < 100000]
```

### 1.13 data[,c(1:m,i,j,k)] komutu

Bu komut ile  belirlenen i, j ve k kolonlarının bir kopyaları 1:m ile belirtilen sutünlara kopya olarak eklenir.
Örneğin 1:3 (İlk üç sutün)'a ek olarak Frost(6), Yüzölçümü(7) ve Lise Mezuniyeti(8) oranlarını ekleyelim. Böylece 4 ve 5. kolonları görüntülemeyelim.

```{r 14}
state.x77[,c(1:3,6,7,8)]
```

### 1.14 data[x > y,a != b] komutu

Bu komut ile (x > y) koşulunu sağlayan satırlar ile (a != b) koşulunu sağlayan sütunlar seçilerek getirilir. Önce getirilen seçeneklere bakalım sonra 
formülü kullanarak sadece istenen verileri getirelim.
Örneğin Nufüs'u 200.000 'in üzerinde olan eyalatlerin donma sıcaklığın altındaki gün sayılarını getirelim.


```{r 15}
state.x77[state.x77$Area > 200000 , ]
state.x77[state.x77$Area > 200000 , "Frost" ]
```

### 1.15 data[c(1:n,i,j,k),] komutu

Bu komut ile  i, j, ve k satırlarının bir kopyası 1'den n'e kadar seçilen satıların üzerine eklenir.
Örnek olarak 1'den 3'ye kadar olan (İlk 3) eyaletin üzerine son 3 (48,49,50) eyaletlerini ekleyelim.


```{r 16}
state.x77[c(1:3,48,49,50),]
```

## Soru 2:  Verilen veri setinde kendi seçeceğimiz 3 değişkeninin medyandan büyük değerlerini sıralı olarak gösteren R komutunu oluşturarak sonucu gösterelim. 
Aynı işlemleri bir de medyan yerine aritmetik ortalama kullanarak tekrarlayalım. Medyan ve Aritmetik ortalamaya göre farklılıkları irdeleyelim.

Söz konusu inceleme için Nufüs(Population), Gelir(Income) ve Yüzölçümü(Area) değişkenlerini inceleyelim.

### 3 Değişken için Medyan ve Ortalama değerlerine göre filtreleme yapıp sıralama

Bu komut ile söz konusu seçilen değişkenleri istenen koşullara göre sıralayacağız. Öncelikle popülasyona ait ortalama (mean) ve medyan (median) değerlerini 
buluyoruz. Ardından söz konusu medyan ve ortalama değelerinden  büyük olan eyaletleri ayrı ayrı listeleyip ardından büyükten küçüğe azaltacak sıralıyoruz. 

Ortalama, bir verinin toplam değerlerinin toplam sayısının değerlerin sayısına bölünmesiyle bulunur iken;
Medyan, bir veri küçükten büyüğe sıralandığında ortada yer alan değeridir. Verilerin incelenmesi için ortalama ya da ortanca(median) seçimi, verilerin türüne 
ve sonuç gereksinimine bağlıdır, çünkü aşırılıkların(outliers) görüldüğü bazı durumlarda median değeri ortalama daha iyi sonuçlar verir. Söz konusu örnekle 
aritmetik ortalama medyandan daha büyük bir değere sahip olduğu için , mean'e göre hesaplanan listede daha az sayıda eyalet yer almaktadır. Aykırı verileri 
olup olmadığı verinin normallik testlerine tabii tutulması ile gerçekleştirilebilir.

```{r 17}
mean(state.x77$Population)
median(state.x77$Population)

pop_ortalama <- as.data.frame(state.x77[state.x77$Population > mean(state.x77$Population),])
pop_medyan <- as.data.frame(state.x77[state.x77$Population > median(state.x77$Population),])

nrow(pop_ortalama)
nrow(pop_medyan)

pop_medyan[with(pop_medyan, order(Population, decreasing = T)), ]
pop_ortalama[with(pop_ortalama, order(Population, decreasing = T)), ]

```

Gelire ait ortalama (mean) ve medyan (median) değerlerini buluyoruz. Ardından söz konusu medyan ve ortalama değerlerinden  büyük olan eyaletleri ayrı ayrı 
listeleyip ardından büyükten küçüğe azaltacak sıralıyoruz. 

Ortalama, bir verinin toplam değerlerinin toplam sayısının değerlerin sayısına bölünmesiyle bulunur iken;
Medyan, bir veri küçükten büyüğe sıralandığında ortada yer alan değeridir. Verilerin incelenmesi için ortalama ya da ortanca(median) seçimi, verilerin türüne 
ve sonuç gereksinimine bağlıdır, çünkü aşırılıkların görüldüğü(outliers) bazı durumlarda ortalama ortalamanın üzerinde veya daha iyisi sonuç verir. Söz konusu 
örnekle aritmetik ortalama medyandan daha küçük bir değere sahip olduğu için , mean'e göre hesaplanan listede daha çok sayıda eyalet yer almaktadır. Aykırı 
verileri olup olmadığı verinin normallik testlerine tabii tutulması ile gerçekleştirilebilir.

```{r 18}
mean(state.x77$Income)
median(state.x77$Income)

inc_ortalama <- as.data.frame(state.x77[state.x77$Income > mean(state.x77$Income),])
inc_medyan <- as.data.frame(state.x77[state.x77$Income > median(state.x77$Income),])

nrow(inc_ortalama)
nrow(inc_medyan)

inc_medyan[with(inc_medyan, order(Income, decreasing = T)), ]
inc_ortalama[with(inc_ortalama, order(Income, decreasing = T)), ]

```


Yüzölçümüne ait ortalama (mean) ve medyan (median) değerlerini buluyoruz. Ardından söz konusu medyan ve ortalama değerlerinden  büyük olan eyaletleri ayrı 
ayrı listeleyip ardından büyükten küçüğe azaltacak sıralıyoruz. 

Ortalama, bir verinin toplam değerlerinin toplam sayısının değerlerin sayısına bölünmesiyle bulunur iken;
Medyan, bir veri küçükten büyüğe sıralandığında ortada yer alan değeridir. Verilerin incelenmesi için ortalama ya da ortanca(median) seçimi, verilerin türüne
ve sonuç gereksinimine bağlıdır, çünkü aşırılıkların görüldüğü(outliers) bazı durumlarda ortalama ortalamanın üzerinde veya daha iyisi sonuç verir. Söz konusu
örnekle aritmetik ortalama medyandan daha küçük bir değere sahip olduğu için , mean'e göre hesaplanan listede daha çok sayıda eyalet yer almaktadır. Aykırı 
verileri olup olmadığı verinin normallik testlerine tabii tutulması ile gerçekleştirilebilir.

```{r 19}
mean(state.x77$Area)
median(state.x77$Area)

area_ortalama <- as.data.frame(state.x77[state.x77$Area > mean(state.x77$Area),])
area_medyan <- as.data.frame(state.x77[state.x77$Area > median(state.x77$Area),])

nrow(area_ortalama)
nrow(area_medyan)

area_medyan[with(area_medyan, order(Area, decreasing = T)), ]
area_ortalama[with(area_ortalama, order(Area, decreasing = T)), ]
```

## Soru 3:  Veri setinde yer alan 2 değişken için özetleyici istatistikleri gösteren R komutunu oluşturarak sonuçları yorumlayalım.

Aşdağıdaki kodlar ile verilere ilişkin Tanımlayıcı İstatistik Değerleri kontrol edilmiş ve özetleri sunulmuştur. 
Her iki tanımlayıcı istatistik verilerinde yer alan Mean , Median gibi temel göstergelerin yanı sıra Skewness ve Kurtosis gibi normallik göstergeleride 
yorumlanmıştır. Skewness değerler verinin Eğiklik/Çarpıklık düzeyini ifade ederken, Kurtosis ise Basıklık düzeyini anlatmaktadır. Ilgili değerlerin 
istatistiklerinin yanı sıra standart hataları yer alamtakdır bu standart hatalar, örneklemlerin ortalamasının, popülasyonun ortalamasından sapma 
derecesini ifade etmektedir.

Grafikler ve istatistikler ile verileri yorumlamadan önce söz konusu görselleştirme yapmak amacıyla **"psych"** ve **"ggplot2"** paketlerini kütüphaneden
çağıralım.

```{r 20, message=FALSE}
library("psych")
library("ggplot2")
describe(state.x77$Income)
summary(state.x77$Income)
par(mfrow=c(1,2))
boxplot(state.x77$Income , col="990066", xlab="Income" )
hist(state.x77$Income, main = "Gelir Histogramı", xlab = "Dollar",col="990066")
```

Seçilmiş olan Gelir Dağılımna ilişkin betimleyici istatistikler ve grafikler sunulmuştur. Gelir değişkeni 50 adet numeric data'dan oluşmaktadır ve eyaletlerin
ortalama dağılımlarını göstermektedir. Tüm eyaletlerin aritmatik ortalama geliri 4,435.8 Dollar iken Median'ı 4519 Dolardır. Standart Sapması 614.47 Dolar olan
Gelir değişkenin normallik kontrollerini yapmadan önce çeyrek değerlerine ve max min değerlerine bakalım. Verideki en düşük gelir 3098 dolar iken,
en yüksek gelir 6315 Dolardır. Kutu-Bıyık grafiğinde görülebileceği üzere bu değer Outlier olarak tanımlanmıştır. En büyük ve en küçük veri arasındaki fark 3217 
iken, Bu değerelere ilişkin Standart Hata 86.9'dur. Son olarak Ortanca Mutlak Sapma beklenildiği üzere standart sapmadan küçük ve 581.18'dir. 

Normallik detay testleri yapılmadan histogram ve kutu bıyık grafiği çizilmiş ve veriye bakış atılmıştır.Buradan çıkarılacak sonuç verinin Quartile’ları arasında 
çok sayıda veri olduğu ve belki sağa çarpık olduğudur. Normallik analizleri takip eden grafiklerde detaylı olarak hesaplanacak bu tespitler irdeelenecektir.

•	Skewness: Popülasyon ile çalışıldığı için (ABD'deki tüm eyaletler) dağılımın çarpıklığı pozitif/negatif değerine göre sağa/sola çarpık olduğu sonuca, 1 ve 0 ile 
olan yakınlık uzaklık ilişkine göre ise çarpık olup olmadığı(çarpıklığın şiddetine) kanısına varılması gerekilmektedir. Ayrıca R'da sonuçları 3 düzeltme katsayını 
düzelterek vermesi nedeniyle, Değerlerin 0’dan yakınlık ve uzaklıklarına bakmamız gerekmektedir. İlgili gelir değişkeni için SKewness değeri + 0.2 çıkmıştır. 
Dolayısı ile Histogram şeklinde de teyit edilecebileceği üzere dağılım normale simetrik olarak kabul edilebilir fakat detay vermek gerekirse sağa orta derecede 
çarpık olduğu söylenebilir. Parametrik testleri ile analiz edilebilir durumdadır.


•	Kurtosis: Normal dağılımın basıklık değeri 3 olduğu gerçeği ile hareket edilerek, fakat R 'ın sonuçları 3 düzeltme katsayını düzelterek  vermesi nedeniyle, 
Değerlerin 0’dan yakınlık ve uzaklıklarına bakmamız gerekmektedir. Hesaplanan Kurtosis değeri 0.24 olarak hesaplandığı için, bu dağılımın Normal Dağılıma simetrik 
olduğu yorumu yapılabilir.


```{r 21, message=FALSE}
library("psych")
library("ggplot2")
describe(state.x77$Frost)
summary(state.x77$Frost)
par(mfrow=c(1,2))
boxplot(state.x77$Frost , col="#69b3a2", xlab="Frost" )
hist(state.x77$Frost, main = "Soğuk Gün Histogramı", xlab = "Gün",col="#69b3a2")
```

Seçilmiş olan Sıfırın altındaki Günler (Soğuk Gün olarak anılacaktır) Dağılımına ilişkin betimleyici istatistikler ve grafikler sunulmuştur. Soğuk gün değişkeni 
50 adet numeric data'dan oluşmaktadır ve eyaletlerin ortalama dağılımlarını göstermektedir. Tüm eyaletlerin aritmatik ortalama olarak sağouk gün sayısı 104.46 Gün 
iken Median'ı 114.5 gündür. Standart Sapması 51.98 Gün olan Soğuk gün değişkenin normallik kontrollerini yapmadan önce çeyrek değerlerine ve max min değerlerine bakalım. Verideki en az soğuk güne sahip eyalet 0 güne sahip iken, en yüksek soğuk güne sahip eyalet 188 güne sahiptir. En büyük ve en küçük veri arasındaki fark dolayısı 
ile 188 iken Bu değerelere ilişkin Standart Hata 7.35'dir. Son olarak Ortanca Mutlak Sapma (median - mena değerlerine bakılarak) beklenildiği üzere standart sapmadan 
büyük ve 53.37'dir. Kutu-Bıyık grafiğinde görülebileceği veride Outlier değer bulunmamaktadır. 

Normallik detay testleri yapılmadan histogram ve kutu bıyık grafiği çizilmiş ve veriye bakış atılmıştır.Buradan çıkarılacak sonuç verinin Quartile’ları arasında çok 
sayıda veri olduğu ve belki sola çarpık olduğudur. Normallik analizleri takip eden grafiklerde detaylı olarak hesaplanacak bu tespitler irdeelenecektir.

•	Skewness: Popülasyon ile çalışıldığı için (ABD'deki tüm eyaletler) dağılımın çarpıklığı pozitif/negatif değerine göre sağa/sola çarpık olduğu sonuca, 1 ve 0 ile olan 
yakınlık uzaklık ilişkine göre ise çarpıklık şiddetine  varılması gerekilmektedir. Ayrıca R'da sonuçları 3 düzeltme katsayını düzelterek vermesi nedeniyle, Değerlerin 
0’dan yakınlık ve uzaklıklarına bakmamız gerekmektedir. İlgili gelir değişkeni için SKewness değeri -0.37 çıkmıştır. Dolayısı ile Histogram şeklinde de teyit edilecebileceği üzere dağılım normale simetrik olarak kabul edilebilir fakat detay vermek gerekirse sola orta derecede çarpık olduğu söylenebilir. Parametrik testleri ile analiz edilebilir durumdadır.


•	Kurtosis: Normal dağılımın basıklık değeri 3 olduğu gerçeği ile hareket edilerek, fakat R 'ın sonuçları 3 düzeltme katsayını düzelterek  vermesi nedeniyle, Değerlerin
0’dan yakınlık ve uzaklıklarına bakmamız gerekmektedir. Hesaplanan Kurtosis değeri 0.24 olarak hesaplandığı için, bu dağılımın Normal Dağılıma simetrik olduğu yorumu 
yapılabilir fakat detay verilmesi istenirse çok az  Platykürtik  yada Basık olduğu söylenebilir. Yukarıdaki Histogram grafiğinde yer aldığı üzere, normal dağılıma oranla, dağılımın kuyrukları daha kısa ve daha incedir. Ayrıca merkez piki diğer verilere oranla daha düşük ve daha geniştir. Parametrik testleri ile analiz edilebilir durumdadır.

