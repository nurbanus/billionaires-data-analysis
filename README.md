
dataset:
https://www.kaggle.com/datasets/nelgiriyewithana/billionaires-statistics-dataset

##Kullandığımız paketler:
Readr paketi, özellikle metin tabanlı veri dosyalarını (CSV, TSV gibi) okuma, düşük bellek kullanımı ve performans optimizasyonu gibi konularda geliştirilmiştir. readr paketi, veri analizi projelerinde veri içe aktarma aşamasını daha etkili ve hızlı hale getirmek amacıyla tasarlanmıştır.
Ggplot2 paketi, veri görselleştirme için kullanılır. ggiraph paketi, veri görselleştirme, makine öğrenmesi, sinyal işleme, yapay zeka, veri madenciliği ve daha birçok alanda kullanılabilir.
Corrplot paketi, korelasyon matrislerini görselleştirmek için kullanılır. Corrplot paketi, bu matrisleri renkli grafiklere ve görsel özelliklerle görselleştirmeyi sağlar. Bu sayede veri setindeki değişkenler arasındaki ilişkileri daha iyi anlayabiliriz.
Dplyr paketi, R programlama dilinde veri manipülasyonu ve veri analizi için kullanılan bir pakettir. Veri çerçeveleri üzerinde veri manipülasyonu ve filtreleme işlemleri için tasarlanmıştır. Bu paket, filter (), select(), mutate(), group_by() gibi fonksiyonlar aracılığıyla veri setlerini hızlı ve anlaşılır bir şekilde işlemenizi sağlar.
Tidyr paketi, veri setlerini düzenleme ve temizleme işlemleri için kullanılır. Bu paket, özellikle veri çerçevelerindeki geniş formatlı veriyi daha uzun formatlı bir hale getirme veya tam tersini yapma (veri normalleştirme) gibi işlemleri gerçekleştirmek için tasarlanmıştır.
Xts paketi, zaman serileri için veri yapılarını ve işlevlerini sağlayan bir pakettir. Bu paket zaman serisi verilerini depolamak, alt kümelere ayırmak, birleştirmek, dönüştürmek ve analiz etmek için çeşitli işlevler sunar.

summarise() fonksiyonu ile veri setlerini özetleyebilir ve arrange() ile sıralama işlemleri gerçekleştirebilirsiniz.
join() fonksiyonları, farklı veri çerçevelerini birleştirme işlemleri için kullanılır.
gather() ve spread() gibi fonksiyonlar, geniş formatlı veriyi uzun formatlıya ve uzun formatlı veriyi geniş formatlıya dönüştürmek için sıklıkla kullanılır.
Veri setindeki eksik veya boş değerleri düzenleme ve temizleme işlemlerinde drop_na() gibi fonksiyonlar kullanılabilir.

3.1. Veriyi açıklayınız. Değişken sayısı, gözlem sayısı, değişkenlerin yapısı hakkında bilgiler veriniz.
Değişken Sayısı: Veri setinizde toplam 35 değişken bulunmaktadır.
Gözlem Sayısı: Billionaires veri setimizden rasgele 1000 veri çekiyoruz. Yani gözlem sayımız 1000’dir. Oluşturduğumuz yeni veri setine veri_f ismini verdik.
Değişkenlerin Yapısı: Veri setimizde nicel, kategorik ve mantıksal (logical) türlerde değişkenler bulunuyor.

##3.2. Veri yükleme ve düzenlemesi konusunda bilgi veriniz. 
Öncelikle Billioners veri setimizi import dataset kısmından çektik. Daha sonra rasgele 1000 verimizi çektik ve bu verimizi set.seed(777) olarak sabitledik. Bu sayede kodu her çalıştırdığımızda aynı veri setini verecek.

 ![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/b4a38ae5-5c7a-4eba-96fe-732747f68090)

##3.3. Verideki tüm değişkenleri özetleyip, yorumlayınız.
NİCEL VERİLER:
rank: Milyarderin servet açısından sıralaması
finalWorth: Milyarder serveti
age: Yaş
birthYear: Doğum yılı
birthMonth: Doğum ayı
birthDay: Doğum günü
cpi_country: TÜFE
cpi_change_country: Milyarderin ülkesi için TÜFE değişimi 
gdp_country: Milyarderin ülkesi için Gayri Safi Yurtiçi Hasıla (GSYİH) 
gross_tertiary_education_enrollment: Milyarderin ülkesindeki yükseköğretime kayıt                 
gross_primary_education_enrollment_country: Milyarderin ülkesinde ilköğretime kayıt
life_expectancy_country: Milyarderin ülkesindeki yaşam beklentisi
tax_revenue_country_country: Milyarderin ülkesindeki vergi geliri
total_tax_rate_country: Milyarderin ülkesindeki toplam vergi oranı
population_country: Milyarderin ülkesinin nüfusu
latitude_country: Milyarderin ülkesinin enlem koordinatı
longitude_country: Milyarderin ülkesinin boylam koordinatı

KATEGORİK VERİLER:
category: Milyarderin işinin faaliyet gösterdiği kategori veya sektör
personName: Milyarderin tam adı
country: Milyarderin ikamet ettiği ülke
city: Milyarderin ikamet ettiği şehir
source: Milyarderin servetinin kaynağı
industries: Milyarderin ticari çıkarlarıyla ilişkili endüstriler
countryOfCitizenship: Milyarderin vatandaşı olduğu ülke
organization: Milyarderle ilişkili kuruluş veya şirketin adı
status: "D" kendi kendini yetiştirmiş milyarderleri (Kurucular/Girişimciler) temsil eder ve "U" miras alınan veya devralınan kişileri belirtir                                                                  
gender: Cinsiyet
birthDate: Doğum tarihi
lastName: Milyarderin soyadı
firstName: Milyarderin ilk adı
title: Milyarderin unvanı
date: Veri toplanma tarihi
state: Milyarderin ikamet ettiği eyalet
residenceStateRegion: Milyarderin ikamet ettiği bölge veya eyalet

MANTIKSAL (LOGİCAL) VERİ:
selfMade: Milyarderin kendi kendini yetiştirmiş olup olmadığını belirtir (Doğru/Yanlış).


##4.1.Servet dağılım analizi: Milyarderlerin servetinin farklı sektörlere, ülkelere ve bölgelere dağılımını keşfedin.

Veri görselleştirmesi için R studioda ggplot2 paketi kullanılır. Paketi indirdikten sonra library(ggplot2) ile paketi kullanıma hazır hale getiririz.
Geom_col ile sütun grafiği çizdirdik. Show.legend=FALSE ile lejantları göstermesini istemedik. 
Coord_flip() ile eksenlerin yerini değiştirdik. Böylece grafik daha okunaklı oldu.
Theme_minimal() ile arka plan temasını seçtik.
Sektör:
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/726beb7b-b3c3-4f05-9c0c-0c7f272460de)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/4403617d-76e6-4459-8384-fc36fdd91b72)

Çıktıya göre milyarder servetinin en fazla olduğu sektör finance & ınvestments (finans ve yatırım). Yani en çok bu sektörde iş yapan kişiler daha zengin olmuş denebilir. En az ise gambling and casinos (kumar ve kumarhaneler) olduğunu görüyoruz.


Ülke:
Billionaries veri setinde “county” sütunun adını 4.5 ‘deki soruda sorun yaşamamız nedeniyle “region” olarak değiştirdik.
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/ba77bc31-0cbe-4b67-9d87-a28e11a3bbd5)

![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/a71872a7-f232-430a-b525-7d5697e93905)
Çıktıya göre milyarderlerin servetinin en fazla olduğu United States. Yani Amerika Birleşik Devletleri’nde yaşayan milyarderlerin kazandığı servet daha fazla.
Bölgelere göre:
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/2dd3fafb-1e7f-4fc9-9df5-a7b72be804fd)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/54d91102-cd80-4d7b-9844-98f094a762c9)
Çıktıya göre güney, batı ve kuzeydoğu bölgesinde yaşayan milyarderlerin serveti orta batıda yaşayan milyarderlerin servetinden daha fazla.

##4.2 Demografik analiz: Milyarderlerin yaşını, cinsiyetini ve doğum yeri demografisini araştırın.
Bu soru için öncelikle ggplot2 paketimizi yüklüyoruz.
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/c295bd20-d41d-4cc7-b6ce-8115d141923b)

![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/3d39f2d4-2712-4cab-bfd2-fd0ca056bb22)
•	Bu histogram grafiği, milyarderlerin yaş dağılımını gösteriyor. Bu histogramda, 50-70 yaş arası milyarderlerin diğer yaş gruplarına göre daha fazla olduğu görülüyor.
•	Bu histogramda, verilerin ortalama değeri yaklaşık 60 yaş civarındadır. Medyan değer ise, verilerin ortasında kalan değerdir. Bu histogramda, medyan değeri 60-70 yaş aralığındadır. Mod değeri ise, verilerin en çok görüldüğü değeridir. Bu histogramda, mod değeri 50-60 yaş aralığındadır.
•	Yayılımı ölçmek için standart sapma, varyans veya aralık gibi ölçüler kullanılabilir. Bu histogramda, verilerin aralığı, en büyük değerden en küçük değeri çıkartarak bulunur. Aralık = 100-20 = 80’dir. Bu, verilerin 80 yaşlık bir aralıkta dağıldığını gösterir. Standart sapma ve varyans ise, verilerin ortalama değerden ne kadar uzaklaştığını gösterir. Bu histogramda, standart sapma ve varyans değerleri hesaplanabilir, ancak görsel olarak da verilerin ortalama değerden ne kadar yayıldığını görmek mümkündür. Verilerin ortalama değerden uzaklaştıkça, sütunların yüksekliği azalır. Bu, verilerin ortalama değere yakın olduğunu, yani düşük bir standart sapma ve varyans değerine sahip olduğunu gösterir.
•	Bu, verilerin sağa çarpık olduğunu gösterir. Sağa çarpık dağılımlarda, ortalama değer medyan değerden büyüktür. Bu histogramda, ortalama değer yaklaşık 60, medyan değer ise 50-60 yaş aralığındadır. Bu, ortalama değerin medyan değerden büyük olduğunu doğrular.
b) Cinsiyet dağılımını çizelim:
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/5709f922-75f8-4ecc-aa0b-6e1e73b78fc1)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/2f84ff9e-a3c9-4452-9ae1-2deb05baf584)

Bu pasta grafiği, milyarderlerin cinsiyet dağılımını gösteriyor. Bu pasta grafiğinde, milyarderlerin büyük çoğunluğunun erkek olduğu görüyoruz. Erkeklerin oranı %87.3 , kadınların oranı ise %12.7’dir.

Cinsiyet dağılımını bar grafiği ile de çizebiliriz:

![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/e97c7e0f-90eb-4309-b397-5fd6b933f244)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/186ef5f2-bbc9-45c8-b280-e6516aa46c3b)

![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/b298922f-ed7f-4291-99ce-95b71a729ca9)

Buna göre milyarderlerin büyük çoğunluğu erkeklerden oluşuyor. Erkeklerin sayısı 873, kadınların sayısı ise 127’dir.
b) Doğum yeri dağılımını çizelim:
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/f770adbd-4776-4149-8011-512abc3eebfd)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/bdf088a7-4660-4530-b6bc-c2f2bde96155)
Bu grafiğe göre en fazla milyarderin bulunduğu ülkenin United States olduğunu söyleyebiliriz. Burada çok fazla ülke görülmekte, aşağıdaki kod ile 66 ülkenin her birindeki milyarder sayısına bakalım:


Burada düzenleme için dplyr paketini kullandık.


![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/b4c839c5-4c60-4ed7-a270-a931180e15dd)

![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/e75b6172-03fd-4723-90e5-0d152f3e6575)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/14d61d81-6255-4dd5-9d94-cbd76dfd45aa)
Burada çok fazla ülke bulunmakta ve bazı ülkelerdeki milyarder sayısı 1, 2, 3 gibi düşük değerlerdir. Bu ülkelerden nüfusu fazla olan ilk 15 ülkeyi alalım ve buna top_15_country ismini vereli, kalan ülkelere “Diger Ulkeler” diyelim. Bu şekilde grafiğimiz daha sade olacaktır.
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/c4c3f7db-51ac-47b9-8f8c-e3b4efab41d6)
![image](https://github.com/nurbanus/billionaires2023-data-visualization/assets/71226874/20e7e474-c7bf-4574-8a83-97afb1157088)



