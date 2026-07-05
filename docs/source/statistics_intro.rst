================
Biraz İstatistik
================

Yapay zeka ve özellikle de makine öğrenmesi ile ilgili çalışmalar yapacak kişilerin belli düzeyde istatistiksel
bilgilere sahip olması gerekmektedir. Şüphesiz istatistik pek çok alt alanı olan geniş bir bilim dalıdır. Bu nedenle
istatistiksel konulara ilişkin pek çok ayrıntı vardır. Biz bu bölümde temel bilgiler vermekle yetineceğiz. Çeşitli
ayrıntılar ilgili konuların anlatıldığı bölümde gerektiğinde açıklanacaktır. (Örneğin *kümeleme analizi (cluster
analysis)* aslında istatistikte çok uzun süredir incelenen bir konudur. Ancak son yıllarda makine öğrenmesi bağlamında
konunun önemi çok daha fazla artmış ve bu bağlamda pek çok algoritmik yöntem geliştirilmiştir. Dolayısıyla örneğin
kümeleme analizi çok değişkenli istatistiğin bir konusu olduğu halde biz bu tekniğin ayrıntılarını *denetimsiz öğrenme
(unsupervised learning)* içerisinde ele alacağız.)

Ölçek Kavramı ve Ölçek Türleri
==============================

İstatistikte ölçülen ya da ölçülmüş olan değerlerin sınıflarına genel olarak *ölçek (scale)* denilmektedir. Pek çok
kişi ölçeklerin yalnızca sayısal olduğunu sanmaktadır. Halbuki ölçekler başka biçimlerde de karşımıza çıkabilmektedir.
İstatistikte ölçekler tipik olarak dört sınıfa ayrılmaktadır:

Kategorik (Nominal) Ölçekler
----------------------------

Bu ölçeklerde söz konusu kümenin elemanları kategorik olgulardır. Örneğin cinsiyet, renk, coğrafi bölge gibi. Bu
ölçekteki ölçülen ya da ifade edilen değerlerin sayısal karşılıkları yoktur. Örneğin *kadınlarla erkekler arasında
sigara içme miktarı arasında anlamlı bir fark olup olmadığını* anlamak için gerçekleştirilen bir araştırmada ölçülmesi
istenen değişkenlerden *cinsiyet* kategorik (nominal) bir ölçeğe ilişkindir. Benzer biçimde kişilerin renk
tercihleriyle ilgili bir araştırmada renkler (siyah, beyaz, kırmızı gibi) kategorik bir ölçekle ifade edilirler.

Sırasal (Ordinal) Ölçekler
--------------------------

Bu ölçeklerdeki değerler de birer kategori belirtmekle birlikte bu kategoriler arasında büyüklük küçüklük ilişkisi söz
konusudur. Örneğin eğitim durumu için kategorik değerler *ilköğretim*, *lise*, *üniversite* olabilir ve bunlar arasında
sıra ilişkisi vardır. Bu nedenle *eğitim durumu* bir sıralı ölçek belirtmektedir.

Aralıklı (Interval) Ölçekler
----------------------------

Aralıklı ölçekler sayısal bilgi içerirler. Bu tür ölçeklerde iki puan arasındaki fark aynı miktar uzaklığı ya da
yakınlığı ifade eder. Örneğin bir testte 20 puan alan 10 puan alandan belli miktarda daha iyidir. 30 puan alan da
20 puan alandan aynı miktar kadar daha iyidir. Bu tür ölçeklerde mutlak sıfır noktası yoktur. Başka bir deyişle bu tür
ölçeklerde sıfır *yokluğu* ya da *mevcut olmamayı* belirtmemektedir. Alınan puanlar her zaman belli bir göreli orijine
göre anlamlıdır. Örneğin aslında sınavlardan alınan puanlar böyle bir ölçek türündedir. Sınavdan sıfır alınabilir.
Ancak bu sıfır o kişinin o konu hakkında hiçbir şey bilmediği anlamına gelmez. Yani mutlak sıfır değildir. Ya da
örneğin ısı belirten *derece (celsius)* bir aralıklı ölçeği belirtmektedir. 50 derece ile 40 derece arasındaki ısı
farkı 40 derece ile 30 derece arasındaki fark kadardır ancak sıfır derece ısının olmadığı anlamına gelmez. Aralıklı
ölçeklerde oran oluşturmak anlamlı olmayabilmektedir. Örneğin 20 derecelik ısı ile 10 derecelik ısı arasında iki kat
bir oran vardır. Ancak biz 20 derecenin 10 dereceden iki kat daha sıcağı belirttiğini söyleyemeyiz.

Oransal (Ratio) Ölçekler
------------------------

Bu ölçekler de sayısal bilgi içerirler. Oransal ölçekler aralık ölçeklerin tüm özelliklerine sahiptirler. Ancak ek
olarak oransal ölçeklerde mutlak bir sıfır noktası da vardır. Dolayısıyla puanlar arasındaki oranlar mutlak olarak
anlamlıdır. Örneğin uzunluk, kütle gibi temel fiziksel özellikler oransal ölçek türlerindendir. Bir nesnenin
uzunluğunun sıfır olması onun uzunluğunun olmadığı, kütlesinin sıfır olması da onun kütlesinin olmadığı anlamına
gelmektedir. Örneğin kişinin yaşı da oransal bir ölçek belirtir.

Merkezi Eğilim Ölçüleri
=======================

İstatistikte verilerin merkezine ilişkin bilgi veren ölçülere *merkezi eğilim ölçüleri (measures of central tendency)*
denilmektedir. Merkezi eğilim ölçülerinin en yaygın kullanılanı *aritmetik ortalamadır*. Aritmetik ortalama (mean)
değerlerin toplanarak değer sayısına bölünmesiyle elde edilmektedir.

Aritmetik Ortalama
------------------

Aritmetik ortalama hesaplamak için çeşitli kütüphanelerde çeşitli fonksiyonlar hazır olarak bulunmaktadır. Örneğin
Python'un standart kütüphanesindeki ``statistics`` modülünde bulunan ``mean`` fonksiyonu aritmetik ortalama
hesaplamaktadır.

.. code-block:: python

    >>> import statistics
    >>> a = [1, 2, 7, 8, 1, 5]
    >>> statistics.mean(a)
    4

``mean`` fonksiyonu herhangi bir dolaşılabilir nesneyi parametre olarak alabilmektedir.

NumPy kütüphanesindeki ``mean`` fonksiyonu eksen (axis) temelinde (yani satırsal ve sütunsal biçimde) ortalama
hesaplayabilmektedir. Örneğin:

.. code-block:: python

    >>> import numpy as np
    >>> a = np.array([[1, 2, 3], [5, 6, 7], [8, 9, 10]])
    >>> np.mean(a, axis=0)
    array([4.66666667, 5.66666667, 6.66666667])

NumPy'da ``mean`` fonksiyonu aynı zamanda ``ndarray`` sınıfının metodu biçiminde de bulunmaktadır. Örneğin:

.. code-block:: python

    >>> import numpy as np
    >>> a = np.array([[1, 2, 3], [5, 6, 7], [8, 9, 10]])
    >>> a.mean(axis=0)
    array([4.66666667, 5.66666667, 6.66666667])

Pandas kütüphanesinde ``Series`` ve ``DataFrame`` sınıflarının ``mean`` metotları aritmetik ortalama hesabı
yapmaktadır. ``DataFrame`` sınıfının ``mean`` metodunda default ``axis`` 0 biçimindedir. Yani sütunsal ortalamalar
elde edilmektedir. Örneğin:

.. code-block:: python

    >>> import pandas as pd
    >>> df = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
    >>> df
       0  1  2
    0  1  2  3
    1  4  5  6
    2  7  8  9
    >>> df.mean()
    0    4.0
    1    5.0
    2    6.0
    dtype: float64

Aritmetik ortalama aralıklı (interval) ve oransal (ratio) ölçeklere uygulanabilir. Aritmetik ortalama O(N)
karmaşıklıkta hesaplanabilmektedir.