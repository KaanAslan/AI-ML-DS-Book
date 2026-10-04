=============================
İstatistiksel Temel Kavramlar
=============================

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


Merkezi Eğilim Ölçüleri: Medyan
-------------------------------

Diğer bir merkezi eğilim ölçüsü de *medyan (median)* denilen ölçüdür. Medyan küçükten büyüğe sıraya dizilmiş olan
sayıların ortasındaki değerdir. Ancak sayılar çift sayıda ise sayıların tam ortasında bir değer olmadığı için ortadaki
iki değerin aritmetik ortalaması medyan olarak alınmaktadır. Medyan işlemi uç değerlerden (outliers) etkilenmez. Ancak
medyan işlemi aritmetik ortalamadan daha fazla zaman alan bir işlemdir. Çünkü medyan için önce değerlerin sıraya
dizilmesi gerekmektedir. Dolayısıyla medyan işlemi O(N log N) karmaşıklıkta bir işlemdir. Medyan işlemi Python'un
standart kütüphanesinde statistics modülü içerisindeki median isimli fonksiyonla yapılabilmektedir. Örneğin:

.. code-block:: pycon

    >>> import statistics
    >>> a = [1, 23, 56, 12, 45, 21]
    >>> statistics.median(a)
    22.0

NumPy kütüphanesinde medyan işlemi eksensel biçimde median fonksiyonuyla yapılabilmektedir. Örneğin:

.. code-block:: pycon

    >>> import numpy as np
    >>> a = np.random.randint(1, 100, (10, 10))
    >>> a
    array([[ 8, 26, 42, 26, 10, 66, 94, 91,  3, 97],
        [31, 62, 82, 86, 45, 73, 38, 29, 43, 62],
        [78, 49, 22, 32, 74, 15, 54, 59, 37, 87],
        [ 5, 75, 34, 82, 58, 63, 84, 40, 92, 20],
        [57, 21,  2, 65, 69, 37, 78,  9, 57,  9],
        [57,  6, 72, 17, 39, 13, 25, 49, 85, 46],
        [57, 47, 57, 47, 25, 40, 20, 72, 10, 16],
        [12, 83, 35, 89, 86, 84, 66, 54, 50, 38],
        [90, 88, 65, 82, 29, 18, 86, 37, 60, 70],
        [38, 17, 40, 81, 18, 89,  4, 22, 59, 65]])
    >>> np.median(a, axis=0)
    array([47.5, 48. , 41. , 73. , 42. , 51.5, 60. , 44.5, 53.5, 54. ])

ndarray sınıfının median isimli bir metodu yoktur.

Benzer biçimde Pandas kütüphanesinde de Series ve DataFrame sınıflarının median isimli metotları eksensel median işlemi
yapabilmektedir. Tabii DataFrame sınıfının median metodunun default ekseni yine 0'dır (yani sütunsal işlem
yapılmaktadır). Örneğin:

.. code-block:: pycon

    >>> a = np.random.randint(1, 100, (10, 10))
    >>> a
    array([[39, 73, 50, 26,  3, 87, 78, 49, 87, 39],
        [91, 39,  6, 99, 85,  1, 50, 59, 20, 19],
        [83, 91, 94, 54, 28, 84, 25, 41, 19, 83],
        [38, 46, 78, 56, 53,  3,  2,  8, 27, 42],
        [33, 32, 36, 61,  7,  6, 88, 72, 71, 88],
        [32, 71, 68, 46, 64, 70, 45, 92,  8, 64],
        [71, 42, 36, 82, 45, 17, 13, 63,  8, 60],
        [70, 56, 76, 59, 64, 28, 81, 62, 60, 72],
        [82, 66, 93, 44, 67, 53, 97, 92, 89, 44],
        [34,  2,  3, 75, 19, 17, 34, 89, 98, 14]])
    >>> df = pd.DataFrame(a)
    >>> df
        0   1   2   3   4   5   6   7   8   9
    0  39  73  50  26   3  87  78  49  87  39
    1  91  39   6  99  85   1  50  59  20  19
    2  83  91  94  54  28  84  25  41  19  83
    3  38  46  78  56  53   3   2   8  27  42
    4  33  32  36  61   7   6  88  72  71  88
    5  32  71  68  46  64  70  45  92   8  64
    6  71  42  36  82  45  17  13  63   8  60
    7  70  56  76  59  64  28  81  62  60  72
    8  82  66  93  44  67  53  97  92  89  44
    9  34   2   3  75  19  17  34  89  98  14
    >>> df.median()
    0    54.5
    1    51.0
    2    59.0
    3    57.5
    4    49.0
    5    22.5
    6    47.5
    7    62.5
    8    43.5
    9    52.0
    dtype: float64

Tabii median işlemi de ancak sayısal verilere yani aralıklı ve oransal ölçeklere uygulanabilir.

Merkezi Eğilim Ölçüleri: Mod
----------------------------

Merkezi eğilim ölçülerinin bir diğeri de *mod (mode)* denilen ölçüdür. Bir grup verideki en çok yinelenen değere *mod*
denilmektedir. Mod özellikle kategorik ve sıralı ölçeklerde ortalamanın yerini tutan bir işlem olarak kullanılmaktadır.
Mod işlemi genel olarak O(N log N) karmaşıklıkta yapılabilmektedir. (Tipik mod algoritmasında değerler önce sıraya
dizilir, sonra yan yana aynı değerlerden kaç tane olduğu tespit edilir.) Mod işlemi Python standart kütüphanesindeki
statistics modülünde bulunan mode fonksiyonuyla yapılabilir. Örneğin:

.. code-block:: pycon

    >>> a = [1, 3, 3, 4, 2, 2, 5, 2, 7, 9, 5, 3, 5, 7, 5]
    >>> statistics.mode(a)
    5

Eğer en çok yinelenen değer birden fazla ise mode fonksiyonu dizilimde ilk karşılaşılan en çok yinelenen değere geri
dönmektedir.

NumPy kütüphanesinde mod işlemini yapan bir fonksiyon bulunmamaktadır. Ancak SciPy kütüphanesinde mod işlemi için stats
modülü içerisindeki mode fonksiyonu kullanılabilir. Bu fonksiyon yine eksensel işlemler yapabilmektedir. mode fonksiyonu
tuple sınıfından türetilen ModeResult isimli bir sınıf türünden bir nesne verir. Bu sınıfın mode ve count örnek
öznitelikleri en çok yinelenen değerleri ve onların sayılarını bize vermektedir. ModeResult sınıfı bir çeşit demet
özelliği gösterdiği için demet gibi de kullanılabilir. Örneğin:

.. code-block:: pycon

    >>> import scipy.stats
    >>> import numpy as np
    >>> a = np.random.randint(1, 10, (20, 10))
    >>> a
    array([[2, 5, 1, 9, 9, 9, 1, 5, 1, 8],
        [3, 1, 1, 8, 2, 5, 3, 2, 5, 4],
        [7, 3, 7, 6, 1, 2, 4, 5, 3, 7],
        [8, 3, 9, 4, 9, 9, 4, 5, 1, 8],
        [6, 1, 6, 6, 3, 2, 2, 4, 3, 9],
        [1, 4, 5, 6, 4, 4, 6, 2, 7, 3],
        [6, 5, 7, 4, 5, 8, 5, 4, 4, 9],
        [5, 1, 4, 8, 8, 9, 6, 1, 8, 6],
        [8, 8, 5, 4, 2, 8, 6, 1, 1, 5],
        [3, 8, 4, 9, 7, 6, 6, 9, 6, 4],
        [5, 8, 1, 6, 7, 8, 7, 7, 6, 4],
        [7, 7, 1, 8, 8, 3, 1, 8, 3, 1],
        [5, 5, 5, 4, 9, 3, 8, 7, 9, 8],
        [8, 9, 9, 2, 7, 3, 3, 6, 2, 6],
        [1, 6, 6, 8, 4, 4, 3, 2, 2, 4],
        [1, 2, 4, 5, 8, 3, 1, 5, 1, 3],
        [5, 9, 3, 1, 1, 6, 9, 5, 4, 1],
        [3, 1, 4, 9, 1, 2, 5, 1, 3, 7],
        [8, 7, 3, 3, 7, 4, 1, 7, 6, 9],
        [9, 2, 1, 6, 5, 3, 7, 9, 5, 7]])
    >>> mr = scipy.stats.mode(a, axis=0)
    >>> mr.mode
    array([[5, 1, 1, 6, 7, 3, 1, 5, 1, 4]])
    >>> mr.count
    array([[4, 4, 5, 5, 4, 5, 4, 5, 4, 4]])

Pandas kütüphanesinde Series ve DataFrame sınıflarının mode metotları da mod işlemi yapmaktadır. Örneğin:

.. code-block:: pycon

    >>> a = np.random.randint(1, 10, (20, 10))
    >>> df = pd.DataFrame(a)
    >>> df
        0  1  2  3  4  5  6  7  8  9
    0   5  5  9  1  4  7  4  3  9  6
    1   1  3  2  1  6  8  4  4  3  3
    2   8  7  9  5  8  1  5  3  8  1
    3   8  7  1  7  1  7  5  8  7  6
    4   1  9  9  5  4  7  5  6  9  9
    5   7  9  1  7  9  6  5  4  7  8
    6   3  2  6  5  4  8  6  5  5  9
    7   4  9  6  9  5  4  9  4  4  7
    8   2  3  3  8  4  8  2  1  4  1
    9   7  6  6  1  7  3  5  1  6  9
    10  3  3  1  5  9  6  1  3  1  4
    11  4  6  2  1  1  1  6  3  2  1
    12  9  1  1  6  3  7  1  1  7  8
    13  8  3  3  5  9  1  1  8  2  4
    14  8  7  7  1  6  5  8  6  4  8
    15  4  8  4  9  2  6  7  9  2  1
    16  6  3  2  6  1  2  5  3  9  2
    17  3  9  3  6  9  1  9  7  9  4
    18  6  2  9  1  4  2  4  8  6  2
    19  3  2  7  2  5  9  1  7  9  2
    >>> df.mode()
       0    1  2    3    4  5    6    7    8    9
    0  3  3.0  1  1.0  4.0  1  5.0  3.0  9.0  1.0
    1  8  NaN  9  NaN  NaN  7  NaN  NaN  NaN  NaN

DataFrame sınıfının mode metodu bize bir DataFrame nesnesi vermektedir. Uygulamacı genellikle bunun ilk satırı ile
ilgilenir. Diğer satırlar eşit miktarda tekrarlanan elemanlardan oluşmaktadır. Tabii belli bir sütunda eşit miktarda
tekrarlanan elemanların sayısı az ise artık geri döndürülen DataFrame'in o sütuna ilişkin satırlarında NaN değeri
bulunacaktır.

Merkezi Yayılım Ölçüleri
------------------------

Değerlerin merkezine ilişkin bilgiler dağılım hakkında iyi bir fikir vermeyebilir. Örneğin iki ülkede kişi başına düşen
ortalama yıllık gelir (gayri safi milli hasıla) 15000 dolar olabilir. Ancak bu iki ülke arasında gelir dağılımında
önemli farklılıklar bulunuyor olabilir. O halde değerlerin ortalamasının yanı sıra onların ortalamaya göre nasıl
yayıldıkları da önemlidir. İstatistikte değerlerin ortalamaya göre yayılımı için *merkezi yayılım ölçüleri (measures of
dispersion)* denilen bazı ölçüler kullanılmaktadır. Merkezi yayılım ölçüleri aslında değerlerin ortalamadan ortalama
uzaklığını belirlemeyi hedeflemektedir.

Eğer biz değerleri ortalamadan çıkartıp onların ortalamasını alırsak 0 elde ederiz. Aşağıdaki programda değerlerin
ortalamadan uzaklıklarının ortalaması bulunmuştur. (Bu tür durumlarda yuvarlama hatalarından dolayı sıfır yerine sıfıra
çok yakın değerler elde edilebilir.)

.. code-block:: python

    import numpy as np


    a = np.array([1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8])
    mean = np.mean(a)
    print(mean)

    result = np.mean(a - mean)
    print(result)

Merkezi yayılım ölçüsü olarak *değerlerin ortalamadan ortalama mutlak uzaklığına* başvurulabilir. Burada mutlak değer
alınmasının nedeni uzaklıkları negatif olmaktan kurtarmak içindir. Bu durumda ortalama 0 çıkmaz. Ancak bu yöntem de
aslında çok iyi bir yöntem değildir. Aşağıda aynı dizilimin ortalamadan ortalama mutlak uzaklığı hesaplanmıştır.

.. code-block:: python

    import numpy as np


    a = np.array([1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8])
    mean = np.mean(a)
    print(mean)

    result = np.mean(np.abs(a - mean))
    print(result)               # 2.5

Standart Sapma
--------------

Aslında ortalamadan ortalama uzaklık için *standart sapma (standard deviation)* denilen ölçü tercih edilmektedir.
Standart sapmada ortalamadan uzaklıkların mutlak değeri değil kareleri alınarak negatiflikten kurtulunmaktadır. Kare
alma işlemi değerleri daha fazla farklılaştırmaktadır. Aynı zamanda bu işlem bazı durumlarda başka faydalara da yol
açmaktadır. (Örneğin ileride bu kare alma işleminin optimizasyon problemleri için daha uygun bir işlem olduğunu
göreceğiz.)

Standart sapma, değerlerin ortalamadan farklarının karelerinin ortalamasının karekökü alınarak hesaplanmaktadır. Ancak
burada ortalama bulunurken değer sayısı n olmak üzere bölme n'e ya da (n - 1)'e yapılabilmektedir. Anakütle (population)
için n'e bölme yapılırken örneklemden hareketle anakütle standart sapmasının tahmin edileceği durumlarda (n - 1)'e bölme
yapılmaktadır. (n - 1)'e bölme işlemine *Bessel düzeltmesi (Bessel's correction)* denilmektedir. Genellikle standart
sapma hesaplayan fonksiyonlar kaça bölüneceğini *ddof (delta degrees of freedom)* parametresiyle programcıdan
istemektedir. ddof değeri *n eksi kaça bölüneceğini* belirtir. Örneğin ddof=0 ise n'e bölme ddof=1 ise (n - 1)'e bölme
uygulanır.

Aşağıdaki örnekte NumPy kullanılarak bir standart sapma hesaplayan fonksiyon yazılmıştır.

.. code-block:: python

    import numpy as np


    def sd(a, ddof=0):
        return np.sqrt(np.sum((a - np.mean(a)) ** 2) / (len(a) - ddof))


    a = [1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8]
    result = sd(a)
    print(result)           # 2.7688746209726918

Python Standart Kütüphanesinde statistics modülü içerisinde standart sapma hesabı yapan stdev ve pstdev fonksiyonları
bulunmaktadır. stdev fonksiyonu (n - 1)'e bölme yaparken pstdev (buradaki 'p' harfi *population* sözcüğünden
gelmektedir) fonksiyonu n'e bölme yapmaktadır.

.. code-block:: python

    import statistics


    a = [1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8]


    std = statistics.stdev(a)
    print(std)                          # 2.891995221924885

    std = statistics.pstdev(a)
    print(std)                          # 2.7688746209726918

NumPy kütüphanesinde std isimli fonksiyon eksensel standart sapma hesaplayabilmektedir. Fonksiyonun ddof parametresi
default durumda 0'dır. Yani default durumda fonksiyon n'e bölme yapmaktadır.

.. code-block:: python

    import numpy as np


    a = np.array([1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8])
    result = np.std(a)
    print(result)                       # 2.7688746209726918

Pandas kütüphanesinde de Series ve DataFrame sınıflarının std isimli metotları eksensel standart sapma hesabı
yapabilmektedir. Ancak bu metotlarda ddof parametresi default 1 durumundadır. Yani bu metotlar default durumda (n - 1)'e
bölme yapmaktadır.

.. code-block:: python

    import pandas as pd


    s = pd.Series([1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8])
    result = s.std()
    print(result)                       # 2.891995221924885

    s = pd.Series([1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8])
    result = s.std(ddof=0)
    print(result)                       # 2.7688746209726918

Varyans
-------

Standart sapmanın karesine *varyans (variance)* denilmektedir. Varyans işlemi Python standart kütüphanesindeki
statistics modülünde bulunan variance ve pvariance fonksiyonlarıyla yapılmaktadır. NumPy kütüphanesinde varyans işlemi
var fonksiyonuyla ya da ndarray sınıfının var metoduyla, Pandas kütüphanesinin Series ve DataFrame sınıflarındaki var
metoduyla yapılmaktadır. Yine NumPy'ın variance fonksiyonundaki ddof parametresinin default değeri 0, Pandas'ın variance
fonksiyonundaki ddof parametresinin default değeri 1'dir.

Peki neden standart sapma varken ayrıca onun karesi için varyans terimi uydurulmuştur? İşte istatistikte pek çok durumda
aslında doğrudan ortalamadan farkların karesel ortalamaları (yani standart sapmanın karesi) kullanılmaktadır. Bu nedenle
bu hesaba ayrı bir isim verilerek anlatımlar kolaylaştırılmak istenmiştir. Aşağıda varyans işleminin nasıl yapıldığına
yönelik bir örnek verilmiştir.

.. code-block:: python

    import statistics
    import numpy as np
    import pandas as pd


    data = [1, 4, 6, 8, 4, 2, 1, 8, 9, 3, 6, 8]


    result = statistics.pvariance(data)
    print(result)               # 7.666666666666667

    result = np.var(data)
    print(result)               # 7.666666666666667

    s = pd.Series(data)
    result = s.var(ddof=0)
    print(result)               # 7.666666666666667

Varyans hesaplamanın alternatif bir yolu daha vardır. Varyans değerlerin karelerinin ortalamasının değerlerin
ortalamasının karesinden çıkartılmasıyla da hesaplanabilmektedir:

::

    varyans = değerlerin karelerinin ortalaması - değerlerin ortalamasının karesi

Varyansın bu formülü tek geçişle (single pass) varyans hesaplamakta çokça kullanılmaktadır. Klasik formülle varyans
hesaplamak için çift geçiş gerekmektedir. Ancak bu yöntemde bir noktaya da dikkat etmek gerekir. Değerlerin kareleri çok
büyümektedir. Bu durumda çok fazla büyük değerin bulunduğu veri kümelerinde karelerin toplamı kullanılan veri türünün
limitleri dışına çıkabilir ya da yuvarlama hatalarından kaynaklanan sorunlar ortaya çıkabilir.

Aşağıda tek geçiş ile bu biçimde varyans hesabına bir örnek verilmiştir.

.. code-block:: python

    total = 0
    total_square = 0
    count = 0


    for x in a:
        total += x
        total_square += x ** 2
        count += 1


    v = total_square / count - (total / count) ** 2
    print(v)

Olasılık Teorisine Giriş
========================

Rassal Deneyler ve Determinizm
------------------------------

Bir deney sonucunda oluşacak durum baştan tam olarak belirlenemiyorsa böyle deneylere *rassal deneyler (random
experiments)* denilmektedir. Örneğin bir paranın atılması deneyinde para *yazı* ya da *tura* gelebilir. O halde *paranın
atılması* rassal bir deneydir. Benzer biçimde bir zarın atılması, bir desteden bir kağıt çekilmesi birer rassal
deneydir. Bir deneyin sonucu önceden bilinebiliyorsa bu tür deneylere *deterministik deneyler* de denilmektedir. Bazı
bilimlerdeki süreçler deterministiktir. Ancak bazı bilimlerdeki süreçlerin sonucunda oluşacak durumlar önceden tam
olarak kestirilememektedir. Önceden sonucu tam olarak kestirilemeyen süreçlere *olasılıksal (probabilistic)* ya da
*stokastik (stochastic)* süreçler denilmektedir.

Deterministik süreçlerle olasılıksal süreçler aslında üzerinde çok düşünülmüş konulardandır. Kimilerine göre olasılıksal
süreç diye bir şey yoktur. Her şey deterministiktir. Bir sürecin olasılıksal olması sadece *bizim onun sonucunu
belirleyemememizden* kaynaklanmaktır. Örneğin paranın atılması sırasındaki tüm bilgilere sahip olsak artık bu deneyin
sonucu olasılıksal değil deterministik hale gelecektir. Tabii evrende kaotik süreçler söz konusudur. Yani bir olay başka
bir olayı etkilemekte ve küçük değişiklikler büyük sonuçlara yol açabilmektedir. Buna felsefede *kaos teorisi* halk
arasında da *kelebek etkisi* denilmektedir. Eğer evrende mutlak bir determinizm varsa evren reset konumuna alındığında
her şey yine bugüne aynı biçimde gelecektir.

Örnek Uzayı, Olay ve Kuvvet Kümesi
----------------------------------

Bir rassal deney sonucunda oluşabilecek tüm olası durumların kümesine *örnek uzayı (sample space)* denilmektedir.
Örneğin bir paranın atılması deneyinde örnek uzayı S = {Yazı, Tura} biçimindedir. Biz zarın atılması deneyindeki örnek
uzayı ise S = {1, 2, 3, 4, 5, 6} biçimindedir. İki zarın atılmasındaki örnek uzayı S = {(1, 1), (1, 2), (6, 5), (6, 6)}
biçimindedir.

Örnek uzayın her bir alt kümesine *olay (event)* denilmektedir. Örneğin bir zarın atılmasındaki bazı olaylar şunlar
olabilir:

::

    E1 = {1, 3}
    E2 = {3, 4, 5}
    E3 = {6}

Bir kümenin bütün alt kümelerine o kümenin *kuvvet kümesi (power set)* denilmektedir. Bir rassal deneydeki bütün olaylar
kuvvet kümesi içerisindeki olaylardır. (Bir kümenin toplam 2^n tane alt kümesi olduğunu anımsayınız.)

Örnek uzayın tek elemanlı olaylarına (yani alt kümelerine) *basit olay (simple events)* denilmektedir. Örneğin paranın
atılması deneyindeki basit olaylar {Yazı} ve {Tura} biçimindedir.

Olasılığın Göreli Sıklık Tanımı
-------------------------------

Olasılığın (probability) değişik tanımları yapılabilmektedir. Olasılığın en yaygın tanımlarından birisi *göreli sıklık
(relative frequency)* tanımıdır. Bu tanıma göre bir rassal deney çok sayıda yinelendikçe elde edilen olasılık değerleri
belli bir değere yakınsamaya başlar. Örneğin bir paranın 100 kere atılmasında 50 kere yazı 50 tura gelmeyebilir. Ancak
para sonsuz sayıda atılırsa (ya da çok fazla sayıda atılırsa) tura gelme sayısının paranın atılma sayısına oranı 0.5'e
yakınsayacaktır. Buna istatistikte *büyük sayılar yasası (law of large numbers)* da denilmektedir.

Aşağıdaki örnekte bir para değişik miktarlarda yazı tura biçiminde atılmıştır. Elde edilen oranlar gitgide 0.5'e
yakınsayacaktır. Programın çalıştırılmasıyla şu değerler elde edilmiştir:

.. code-block:: text

    head = 0.4, tail = 0.6
    head = 0.5, tail = 0.5
    head = 0.479, tail = 0.521
    head = 0.4977, tail = 0.5023
    head = 0.50005, tail = 0.49995
    head = 0.500075, tail = 0.499925
    head = 0.5002417, tail = 0.4997583
    head = 0.49997078, tail = 0.50002922

Bu değerleri üreten program aşağıdadır:

.. code-block:: python

    import random


    HEAD = 1


    def head_tail(n):
        head = tail = 0

        for _ in range(n):
            val = random.randint(0, 1)
            if val == HEAD:
                head += 1
            else:
                tail += 1
        return head / n, tail / n


    head, tail = head_tail(10)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(100)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(1000)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(10_000)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(100_000)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(1_000_000)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(10_000_000)
    print(f'head = {head}, tail = {tail}')

    head, tail = head_tail(100_000_000)
    print(f'head = {head}, tail = {tail}')

Kolmogorov Aksiyomları
----------------------

Olasılığın temel matematiksel teorisi Kolmogorov tarafından oluşturulmuştur. Kolmogorov üç aksiyom kabul edildiğinde
bütün olasılık kurallarının teorem-ispat biçiminde açıklanabileceğini göstermiştir. Kolmogorov'un üç aksiyomu şöyledir:

1) Örnek uzayının olasılığı 1'dir. Yani P(S) = 1'dir. Buradan olasılığın en yüksek değerinin 1 olacağını ve tüm örnek
   uzayının olma olasılığının 1 olduğunu anlamalıyız. Örneğin bir zarın atılmasındaki örnek uzayı {1, 2, 3, 4, 5, 6}
   biçimindedir. P({1, 2, 3, 4, 5, 6}) = 1'dir. Buradaki P({1, 2, 3, 4, 5, 6}) bir zarın 1 ya da 2 ya da 3 ya da 4 ya da
   5 ya da 6 gelme olasılığı anlamındadır.
2) Herhangi bir olayın olasılığı 0 ya da 0'dan büyüktür. Yani P(E) >= 0'dır. Burada olasılığın en düşük değerinin 0
   olduğu belirtilmektedir. O halde olasılık değeri 0 ile 1 arasındadır.
3) Bir kümenin olasılığı demek rassal deney sonucunda o kümenin herhangi elemanının oluşma olasılığı demektir. Örneğin
   zarın atılmasındaki P({3, 5}) olasılığı zarın üç ya da 5 gelme olasılığı anlamına gelir. İki küme ayrıksa (yani ortak
   elemanları yoksa) bu iki kümenin birleşimlerinin olasılığı bu iki kümenin olasılık toplamlarına eşittir. Yani E1 ve
   E2 iki olay olmak üzere eğer bu iki olay ayrıksa (yani E1 ⋂ E2 = ∅ ise) P{E1 ∪ E2} = P{E1} + P{E2}'dir.

Bu üç kural kabul edildiğinde kümeler teorisi, permütasyon, kombinasyon gibi işlemlerle tüm olasılık formülleri elde
edilebilmektedir.

Rassal Değişkenler
==================

Rassal Değişken Kavramı
-----------------------

Olasılıkta ve istatistikte en çok kullanılan temel kavramlardan biri *rassal değişken (random variable)* denilen
kavramdır. Her ne kadar *rassal değişken* teriminde bir *değişken* sözcüğü geçiyorsa da aslında rassal değişken bir
fonksiyon belirtmektedir. Rassal değişken bir rassal deney ile ilgilidir. Bir rassal değişken örnek uzayın her bir
elemanını (yani basit olayını) gerçek (reel) bir değere eşleyen bir fonksiyon belirtmektedir. Rassal değişkenler
genellikle *sözel biçimde* ifade edilirler. Ancak bir fonksiyon belirtirler. Rassal değişkenler matematiksel
gösterimlerde genellikle büyük harflerle belirtilmektedir. Örneğin:

Z rassal değişkeni *iki zar atıldığında zarların üzerindeki sayıların toplamını* belirtiyor olsun. Burada aslında Z bir
fonksiyondur. Örnek uzayın her bir elemanını bir değere eşlemektedir. Matematiksel gösterimle Z rassal değişkeni şöyle
belirtilebilir:

::

    Z: S -> R

Burada Z fonksiyonunun S örnek uzayından R'ye bir fonksiyon belirttiği anlaşılmalıdır. Burada Z fonksiyonu aşağıdaki
gibi eşleme yapmaktadır:

::

    (1, 1) -> 2
    (1, 2) -> 3
    (1, 3) -> 4
    ...
    (6, 5) -> 11
    (6, 6) -> 12

K rassal değişkeni *rastgele seçilen bir kişinin kilosunu belirtiyor* olsun. Bu durumda örnek uzayı aslında dünyadaki
tüm insanlardır. Burada K fonksiyonu da her insanı onun kilosuna eşleyen bir fonksiyondur.

C rassal değişkeni *rastgele seçilen bir rengin RGB değerlerinin ortalamasını* belirtiyor olsun. Bu durumda her rengin
bir RGB ortalaması vardır. Bu fonksiyon belli bir rengi alıp onun ortalamasını belirten bir sayıya eşlemektedir.

Rassal değişkenler kümeler üzerinde işlemler yapmak yerine gerçek sayılar üzerinde işlem yapmamızı sağlayan,
anlatımlarda ve gösterimlerde kolaylık sağlayan bir kavramdır.

Rassal Değişkenlerin Olasılıkları
---------------------------------

Her rassal değişkenin belli değerler almasının bir olasılığı vardır. Örneğin *iki zarın atılması deneyinde üste gelen
sayılar toplamına ilişkin* R rassal değişkenini düşünelim. P(R = 5) demek S örnek uzayındaki 5 değerini veren kümenin
olasılığı demektir. Yani P(R = 5) ile aslında P({(1, 4), (4, 1) (2, 3), (3, 2)}) aynı anlamdadır. Buradaki P({(1, 4),
(4, 1) (2, 3), (3, 2)}) olasılığın *bu değerlerden herhangi birinin oluşmasına ilişkin* olasılık olduğunu anımsayınız.
Bu olasılığın değeri 1/9'dur.

Bir rassal değişkenin olasılığı belirtilirken P harfi olasılığı anlatmaktadır. Ancak bu P harfinden sonra bazı kişiler
normal parantezleri bazı kişiler küme parantezlerini tercih ederler. Yani örneğin bazı kişiler P(R = 5) gibi bir
gösterimi tercih derken bazı kişiler P{R = 5} gösterimini tercih etmektedir. Küme parantezli gösterim aslında *R = 5
ifadesinin bir küme belirttiğini ve bu kümenin olasılığının hesaplanmak istediğini* belirtmesi açısından daha doğal gibi
gözükmektedir.

K rassal değişkeni rastgele seçilen bir insanın kilosunu belirtiyor olsun. Bu durumda K aslında tüm insanları tek tek
onların kilolarına eşleyen bir fonksiyondur. O halde P{K < 60} olasılığı aslında *rastgele seçilen bir kişinin kilosunun
60'tan küçük olma olasılığı* anlamına gelmektedir.

Kesikli ve Sürekli Rassal Değişkenler
-------------------------------------

Rassal değişkenler tıpkı matematiksel diğer fonksiyonlarda olduğu gibi *kesikli (discrete)* ya da *sürekli (continuous)*
olabilmektedir. Eğer bir rassal değişken (yani fonksiyon) teorik olarak belli bir aralıkta tüm gerçek sayı değerlerini
alabiliyorsa böyle rassal değişkenlere *sürekli (continuous)*, yalnızca belli gerçek sayı değerlerini alabiliyorsa böyle
rassal değişkenlere ise *kesikli (discrete)* rassal değişkenler denilmektedir. Örneğin *iki zarın atılmasında üste gelen
sayılar toplamını belirten Z rassal değişkeni* kesiklidir. Çünkü yalnızca belli değerleri alabilmektedir. Ancak
*rastgele seçilen bir kişinin kilosunu belirten* K rassal değişkeni süreklidir. Çünkü teorik olarak belli bir aralıkta
tüm gerçek değerleri alabilir. (Biz kişilerin kilolarını yuvarlayarak ifade etmekteyiz. Ancak aslında onların kiloları
belli aralıktaki tüm gerçek değerlerden biri olabilir.)

Sürekli rassal değişkenlerin noktasal olasılıkları 0'dır. Örneğin *rastgele seçilen kişinin kilosunu* belirten K rassal
değişkeni söz konusu olsun. P{K = 67} gibi bir olasılık aslında 0'dır. Çünkü gerçek sayı ekseninde sonsuz tane nokta
vardır. 67 yalnızca bu sonsuz noktadan bir tanesini belirtir. Sayı / sonsuz da 0'dır. Ancak sürekli rassal değişkenlerin
aralıksal olasılıkları 0 olmak zorunda değildir. Yani örneğin P{66 < K < 67} olasılığı 0 değildir. Burada {66 < K < 67}
kümesinin de elemanlarının sonsuz sayıda olduğuna dikkat ediniz. Artık bu hesap matematikte *limit, türev, integral*
konularıyla ilişkili hale gelmektedir. Sürekli rassal değişkenlerin aralıksal olasılıklarını belirtirken aralıklardaki
'=' sembolünün bir anlamının olmayacağına dikkat ediniz. Örneğin P{66 < K < 67} ile P{66 <= K <= 67} arasında aslında
bir fark yoktur. Bu konuda da kişiler farklı gösterimleri tercih edebilmektedir. Bazı kişiler bir tarafa '=' sembolünü
koyup diğer tarafa koymamaktadır. Örneğin P{66 <= K < 67} gibi. Ancak bu '=' sembollerinin sürekli rassal değişkenlerde
bir etkisi yoktur. (Sonsuz büyüklükte bir kümeye bir eleman daha eklesek bunun bir etkisi olabilir mi?)

Sürekli Rassal Değişkenler ve Olasılık Yoğunluk Fonksiyonu
----------------------------------------------------------

Yapay zeka ve makine öğrenmesinde sürekli rassal değişkenler daha fazla karşımıza çıkmaktadır. Bu nedenle biz sürekli
rassal değişkenler üzerinde biraz daha duracağız.

Sürekli bir rassal değişkenin aralıksal olasılıkları *integral* işlemi ile hesaplanmaktadır. Tabii integral işlemi için
bir fonksiyona gereksinim vardır. İşte sürekli rassal değişkenlerin aralıksal olasılıklarının hesaplanması için
kullanılan fonksiyonlara *olasılık yoğunluk fonksiyonları (probability density functions)* denilmektedir. Birisi bize
bir rassal değişkenin belli bir aralıktaki olasılığını soruyorsa o kişinin bize o rassal değişkene ilişkin *olasılık
yoğunluk fonksiyonunu* vermiş olması gerekir. Biz de örneğin P{x0 < X < x1} olasılığını x0'dan x1'e f(x)'in integrali
ile elde ederiz.

Bir fonksiyonun olasılık yoğunluk fonksiyonu olabilmesi için eksi sonsuzdan artı sonsuza integralinin (yani tüm eğri
altında kalan alanın) 1 olması gerekir. Bir rassal değişkenin olasılık yoğunluk fonksiyonuna *o rassal değişkenin
dağılımı* da denilmektedir.

Olasılık Yoğunluk Fonksiyonlarının Elde Edilmesi
------------------------------------------------

Peki mademki bizim bir rassal değişkenin aralıksal olasılığını elde etmek için bir olasılık yoğunluk fonksiyonuna
ihtiyacımız var o halde bu fonksiyonu nasıl elde edeceğiz? İşte pek çok rassal değişkenin olasılık yoğunluk
fonksiyonunun bazı kalıplara uyduğu görülmektedir. Örneğin doğadaki pek çok olgunun (boy gibi, kilo gibi, zeka gibi)
olasılık yoğunluk fonksiyonu *normal dağılım* denilen dağılıma uymaktadır. Normal dağılım eğrisine *Gauss eğrisi* ya da
*çan eğrisi* de denilmektedir. Olasılık yoğunluk fonksiyonları bazı parametrelere de sahip olabilmektedir. Örneğin Gauss
eğrisinin iki parametresi vardır: Orta noktasını belirten *ortalama* ve zayıflığını ve şişmanlığını belirten *standart
sapma*.

Bu durumda örneğin sürekli rassal değişkenlerle ilgili bir olasılık sorusu şöyle olabilir: *Kişilerin zeka puanları (IQ)
ortalaması 100 standart sapması 15 olan normal dağılımla temsil ediliyor olsun. Rastgele seçilen bir kişinin zeka
puanının 120 ile 130 arasında olma olasılığı nedir?* Burada bize rassal değişkenin olasılık yoğunluk fonksiyonu
parametreleriyle verilmiştir. Bizim de bu olasılığı hesaplamak için tek yapacağımız şey Gauss fonksiyonunun 120'den
130'a fonksiyonun integralini hesaplamaktır.

Peki rassal değişkenimiz başkaları tarafından belirlenen herhangi bir kalıba uymuyorsa ne yapabiliriz? Bir rassal
değişkenin olasılık yoğunluk fonksiyonunun çıkarılması biraz zahmetli bir işlemdir. Ancak kümülatif olasılıklar
yardımıyla olasılık yoğunluk fonksiyonları tatmin edici bir biçimde elde edilebilmektedir. Tabii yukarıda da
belirttiğimiz gibi aslında pek çok olay zaten tespit edilmiş çeşitli kalıplara uymaktadır.

Sürekli Olasılık Dağılımları
============================

Normal Dağılım (Gauss Dağılımı)
-------------------------------

Doğada en fazla karşılaşılan sürekli dağılım *normal dağılım (normal distribution)* denilen dağılımdır. Bu dağılımın
olasılık yoğunluk fonksiyonu çan eğrisine benzemektedir. Yukarıda da belirttiğimiz gibi normal dağılımın iki parametresi
vardır: *Ortalama* ve *standart sapma*. Ortalama çan eğrisinin orta noktasını belirler. Standart sapma ise eğrinin zayıf
ya da şişman olması üzerinde etkili olur. Çan eğrisine teknik olarak *Gauss eğrisi*, Gauss eğrisine ilişkin olasılık
yoğunluk fonksiyonuna da *Gauss fonksiyonu* denilmektedir.

Gauss fonksiyonu simetrik bir fonksiyondur. Bu fonksiyon ortalama etrafında büyük bir alan kaplar, iki uca gidildikçe
hızlı bir düşüş yaşanır. Ancak eğri hiçbir zaman X ekseni ile kesişmemektedir. Yani eğri iki taraftan y değeri olarak
sıfıra oldukça yaklaşır, ancak sıfır olmaz.

Gauss fonksiyonu bir olasılık yoğunluk fonksiyonu belirttiğine göre fonksiyonun toplam eğri altında kalan alanı 1'dir.
Fonksiyon simetrik olduğuna göre ortalamanın iki yanındaki eğri altında kalan alan 0.5'tir.

Yukarıda da belirttiğimiz gibi değişik ortalama ve standart sapmaya ilişkin sonsuz sayıda Gauss eğrisi çizilebilir.
Ortalaması 0, standart sapması 1 olan normal dağılıma *standart normal dağılım*, standart normal dağılımdaki X
değerlerine de *Z değerleri* denilmektedir.

Aşağıdaki örnekte Gauss eğrisi çizdirilmiştir.

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt


    def gauss(x, mu=0, std=1):
        return 1 / (std * np.sqrt(2 * np.pi)) * np.e ** (-0.5 * ((x - mu) / std) ** 2)


    x = np.linspace(-5, 5, 1000)
    y = gauss(x)

    plt.title('Gauss Function')
    plt.plot(x, y)
    plt.show()

Yukarıdaki çizimde eksenleri kartezyen koordinat sistemindeki gibi de gösterebiliriz.

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt


    def gauss(x, mu=0, std=1):
        return 1 / (std * np.sqrt(2 * np.pi)) * np.e ** (-0.5 * ((x - mu) / std) ** 2)


    def draw_gauss(mu=0, std=1):
        x = np.linspace(-5 * std + mu, 5 * std + mu, 1000)
        y = gauss(x, mu, std)

        mu_y = gauss(mu, mu, std)

        plt.figure(figsize=(10, 4))
        plt.title('Gauss Function', pad=10, fontweight='bold')
        axis = plt.gca()

        axis.set_ylim([-mu_y * 1.1, mu_y * 1.1])
        axis.set_xlim([-5 * std + mu, 5 * std + mu])
        axis.set_xticks(np.arange(-4 * std + mu, 5 * std + mu, std))
        # axis.set_yticks(np.round(np.arange(-mu_y, mu_y, mu_y / 10), 2))
        axis.spines['left'].set_position('center')
        axis.spines['top'].set_color(None)
        axis.spines['bottom'].set_position('center')
        axis.spines['right'].set_color(None)
        axis.plot(x, y)
        plt.show()


    draw_gauss(100, 15)

Normal dağılımda eğri altında kalan toplam alanın 1 olduğunu belirtmiştik. Bu dağılımda toplaşmanın ortalama civarında
olduğu eğrinin şeklinden anlaşılmaktadır. Gerçekten de normal dağılımda ortalamadan bir standart sapma soldan ve sağdan
kaplanan alan yani P{mu - std < X < mu + std} olasılığı 0.6827, ortalamadan iki standart sapma soldan ve sağdan kaplanan
alan yani P{mu - std * 2 < X < mu + std * 2} olasılığı 0.9545, ortalamadan üç standart sapma soldan ve sağdan kaplanan
alan yani P{mu - std * 3 < X < mu + std * 3} olasılığı ise 0.9956 biçimindedir.

Matplotlib'te bir eğrinin altındaki alanı boyamak için fill_between isimli fonksiyon kullanılmaktadır. Bu fonksiyon axis
sınıfının bir metodu olarak da bulundurulmuştur. Aşağıdaki örnekte eğrinin altındaki belli bir alan fill_between metodu
ile boyanmıştır.

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt


    def gauss(x, mu=0, std=1):
        return 1 / (std * np.sqrt(2 * np.pi)) * np.e ** (-0.5 * ((x - mu) / std) ** 2)


    def fill_gauss(mu=0, std=1, fstart=0, fstop=0):
        x = np.linspace(-5 * std + mu, 5 * std + mu, 1000)
        y = gauss(x, mu, std)

        mu_y = gauss(mu, mu, std)

        plt.figure(figsize=(10, 4))
        plt.title('Gauss Function', pad=10, fontweight='bold')
        axis = plt.gca()

        axis.set_ylim([-mu_y * 1.1, mu_y * 1.1])
        axis.set_xlim([-5 * std + mu, 5 * std + mu])
        axis.set_xticks(np.arange(-4 * std + mu, 5 * std + mu, std))
        # axis.set_yticks(np.round(np.arange(-mu_y, mu_y, mu_y / 10), 2))
        axis.spines['left'].set_position('center')
        axis.spines['top'].set_color(None)
        axis.spines['bottom'].set_position('center')
        axis.spines['right'].set_color(None)
        axis.plot(x, y)

        x = np.linspace(fstart, fstop, 1000)
        y = gauss(x, mu, std)
        axis.fill_between(x, y)
        plt.show()


    fill_gauss(100, 15, 85, 115)

Yukarıda da belirttiğimiz gibi *kümülatif dağılım fonksiyonu (cumulative distribution function)* belli bir değere kadar
tüm birikimli olasılığı veren fonksiyondur. Genellikle F harfi ile gösterilmektedir. Örneğin F(x0) aslında P{X < x0}
anlamına gelmektedir. Normal dağılımda F(x0) değeri aslında X değerinin x0 olduğu noktanın solundaki tüm eğri altında
kalan alanı belirtmektedir. (Başka bir deyişle sürekli dağılımlarda F(x0) değeri *-sonsuzdan x0'a kadar olasılık
yoğunluk fonksiyonunun integraline eşittir*.)

Yukarıda da belirttiğimiz gibi normal dağılım istatistikte çok önemli bir sürekli dağılımdır. Normal dağılımın önemi
*merkezi limit teoremi (central limit theorem)* ile daha iyi anlaşılabilir. Çıkarımsal istatistiğin dayandığı temel
merkezi limit teoremi olduğu için normal dağılım da çok önemli olmaktadır. Merkezi limit teoremini izleyen paragraflarda
ele alacağız.

Bizim de Python programcısı olarak normal dağılım üzerinde aşağıdaki dört işlemi yapabiliyor olmamız gerekir:

1) Belli bir x değeri için eksi sonsuzdan o x değerine kadar eğri altında kalan alanı bulmak. Yukarıda da belirttiğimiz
   gibi aslında bu alanı veren fonksiyona istatistikte *kümülatif dağılım fonksiyonu (cumulative distribution function)*
   denmektedir. O halde aslında P{x0 < X < x1} olasılığı da F(x1) - F(x0) ile aynıdır.
2) Yukarıdaki işlemin tersi olan işlem. Yani bize kümülatif dağılım fonksiyonundan elde edilen değer verilmiş olabilir.
   Bizden buna ilişkin x değeri istenebilir.
3) Belli bir x değeri için Gauss fonksiyon değerinin elde edilmesi. (Yani belli bir x değeri için olasılık yoğunluk
   fonksiyonunun değerinin elde edilmesi.)
4) Normal dağılıma uygun rastgele sayıların üretilmesi. Aslında bunun için 0 ile 1 arasında rastgele sayı üretilip onu
   2'inci maddede belirtilen işleme sokarsak normal dağılmış rastgele sayı elde edebiliriz.

Normal dağılımla ilgili işlemleri yapabilmek için Python standart kütüphanesinde statistics modülü içerisinde NormalDist
isimli bir sınıf bulundurulmuştur. Programcı bu sınıf türünden bir nesne yaratır. İşlemlerini bu sınıfın metotlarıyla
yapar. NormalDist nesnesi yaratılırken ortalama ve standart sapma değerleri girilir. (Bu değerler girilmezse ortalama
için 0, standart sapma için 1 default değerleri kullanılmaktadır.) Örneğin:

.. code-block:: python

    import statistics

    nd = statistics.NormalDist(100, 15)

NormalDist sınıfının cdf (cumulative distribution function) isimli metodu verilen x değeri için eğrinin solunda kalan
toplam alanı yani kümülatif olasılığı bize vermektedir. Örneğin standart normal dağılımda x = 0'ın solundaki alan
0.5'tir.

.. code-block:: python

    import statistics


    nd = statistics.NormalDist()

    result = nd.cdf(0)
    print(result)           # 0.5

Örneğin biz ortalaması 100, standart sapması 15 olan bir normal dağılımda P{130 < X < 140} olasılığını aşağıdaki gibi
elde edebiliriz:

.. code-block:: python

    nd = statistics.NormalDist(100, 15)
    result = nd.cdf(140) - nd.cdf(130)

Şöyle bir soru sorulduğunu düşünelim: *İnsanların zekaları ortalaması 100, standart sapması 15 olan normal dağılıma
uyuyor olsun. Bu durumda zeka puanı 140'ın yukarısında olanların toplumdaki yüzdesi nedir?* Bu soruda istenen şey
aslında normal dağılımdaki P{X > 140} olasılığıdır. Yani x ekseninde belli bir noktanın sağındaki alan sorulmaktadır. Bu
alanı veren doğrudan bir fonksiyon olmadığı için bu işlem 1 - F(140) biçiminde ele alınarak sonuç elde edilebilir:

.. code-block:: python

    nd = statistics.NormalDist(100, 15)
    result = 1 - nd.cdf(140)
    print(result)                   # 0.003830380567589775

.. code-block:: python

    import statistics


    nd = statistics.NormalDist(100, 15)

    result = nd.cdf(140) - nd.cdf(130)
    print(result)

Yukarıda da belirttiğimiz gibi bir normal dağılımda iki x arasındaki alanı yani P{x1 < X <= x2} olasılığını biz cdf
fonksiyonuyla F(x2) - F(x1) işlemi ile elde edebiliriz. Örneğin ortalaması 100 standart sapması 15 olan normal dağılımda
120 ile 130 arasındaki olasılık aşağıdaki gibi hesaplanıp grafiği çizdirilebilir.

.. code-block:: python

    import statistics
    import numpy as np


    nd = statistics.NormalDist(100, 15)

    result = nd.cdf(130) - nd.cdf(120)
    print(result)


    import matplotlib.pyplot as plt


    plt.title('P{120 < x <= 130} Olasılığı ', pad=20, fontsize=14, fontweight='bold')
    x = np.linspace(40, 160, 1000)
    y = [nd.pdf(val) for val in x]

    axis = plt.gca()
    axis.set_ylim(-0.030, 0.030)
    axis.spines['left'].set_position('center')
    axis.spines['bottom'].set_position('center')
    axis.spines['top'].set_color(None)
    axis.spines['right'].set_color(None)

    axis.set_xticks(range(40, 170, 10))

    plt.plot(x, y)

    x = np.linspace(120, 130, 100)
    y = [nd.pdf(val) for val in x]

    axis.fill_between(x, y)
    plt.text(120, -0.01, f'P{{120 < x <= 130}} = {result:.3f}', color='blue', fontsize=14)

    plt.show()

Eskiden bilgisayarların bu kadar yoğun kullanılmadığı zamanlarda standart normal dağılım için *Z Tabloları*
düzenlenmekteydi. Bu tablolar belli bir Z değeri için (standart normal dağılımdaki X değerlerine Z değeri dendiğini
anımsayınız) kümülatif dağılım fonksiyonun değerini vermektedir. Örnek bir Z tablosu aşağıdakine benzemektedir:

::

            0.00    0.01    0.02    0.03    0.04    0.05    0.06    0.07    0.08    0.09
    0.0     0.5000  0.5040  0.5080  0.5120  0.5160  0.5199  0.5239  0.5279  0.5319  0.5359
    0.1     0.5398  0.5438  0.5478  0.5517  0.5557  0.5596  0.5636  0.5675  0.5714  0.5753
    0.2     0.5793  0.5832  0.5871  0.5910  0.5948  0.5987  0.6026  0.6064  0.6103  0.6141
    0.3     0.6179  0.6217  0.6255  0.6293  0.6331  0.6368  0.6406  0.6443  0.6480  0.6517
    0.4     0.6554  0.6591  0.6628  0.6664  0.6700  0.6736  0.6772  0.6808  0.6844  0.6879
    0.5     0.6915  0.6950  0.6985  0.7019  0.7054  0.7088  0.7123  0.7157  0.7190  0.7224
    0.6     0.7257  0.7291  0.7324  0.7357  0.7389  0.7422  0.7454  0.7486  0.7517  0.7549
    0.7     0.7580  0.7611  0.7642  0.7673  0.7704  0.7734  0.7764  0.7794  0.7823  0.7852
    0.8     0.7881  0.7910  0.7939  0.7967  0.7995  0.8023  0.8051  0.8078  0.8106  0.8133
    0.9     0.8159  0.8186  0.8212  0.8238  0.8264  0.8289  0.8315  0.8340  0.8365  0.8389
    1.0     0.8413  0.8438  0.8461  0.8485  0.8508  0.8531  0.8554  0.8577  0.8599  0.8621
    1.1     0.8643  0.8665  0.8686  0.8708  0.8729  0.8749  0.8770  0.8790  0.8810  0.8830
    1.2     0.8849  0.8869  0.8888  0.8907  0.8925  0.8944  0.8962  0.8980  0.8997  0.9015
    ......................................................................................

Bu tabloda ilgili hücredeki değer o Z değerinin kümülatif olasılığını vermektedir. Tabii artık bir bilgisayar
programcısının böyle bir tablo kullanmasına gerek yoktur. Yukarıdaki gibi tablolar yalnızca belli kesikli değerleri
yuvarlayarak vermektedir.

Peki bu Z tabloları standart normal dağılıma göre hazırlandığına göre biz belli bir ortalama ve standart sapmaya ilişkin
kümülatif olasılığı bu tablo yoluyla nasıl elde edebilmekteyiz? İşte aslında herhangi bir normal dağılım standart normal
dağılıma dönüştürülebilmektedir. Ortalaması mu standart sapması std olan normal dağılımdaki x değerinin standart normal
dağılımdaki Z değeri şöyle hesaplanmaktadır:

::

    Z = (x - mu) / std

Örneğin ortalaması 100, standart sapması 15 olan normal dağılımdaki x = 136 değerinin standart normal dağılımdaki Z
değeri 2.40'tır.

Belli bir kümülatif olasılık değeri için x değerinin bulunması işlemi de NormalDist sınıfının inv_cdf metoduyla
yapılmaktadır. Örneğin standart normal dağılımda 0.99 olan kümülatif olasılığın Z değeri aşağıdaki gibi bulunabilir:

.. code-block:: python

    nd = statistics.NormalDist()
    result = nd.inv_cdf(0.99)

.. code-block:: python

    import statistics


    nd = statistics.NormalDist()

    result = nd.inv_cdf(0.99)
    print(result)       # 2.32

Belli bir x değeri için Gauss fonksiyonunda ona karşı gelen y değeri sınıfın pdf metoduyla elde edilmektedir. Örneğin x
= 0 için standart normal dağılımda Gauss fonksiyonunun değerini aşağıdaki gibi elde edebiliriz:

.. code-block:: python

    nd = statistics.NormalDist()
    result = nd.pdf(0)
    print(result)

.. code-block:: python

    import statistics


    nd = statistics.NormalDist()

    result = nd.pdf(0)
    print(result)   # 0.3989422804014327

Normal dağılmış rastgele sayı üretmek için NormalDist sınıfının samples isimli metodu kullanılmaktadır. Bu metot kaç
rassal sayının üretileceğini parametre olarak alıp üretilen rassal sayıları float elemanlardan oluşan bir liste
biçiminde vermektedir. Örneğin:

.. code-block:: python

    nd = statistics.NormalDist()
    result = nd.samples(10)

Bu işlemden biz normal dağılmış 10 tane rastgele değerden oluşan bir liste elde ederiz.

.. code-block:: python

    import statistics


    nd = statistics.NormalDist()

    result = nd.samples(10)
    print(result)

Biz normal dağılmış rastgele sayılardan histogram çizersek histogramımızın Gauss eğrisine benzemesi gerekir.

.. code-block:: python

    import statistics


    nd = statistics.NormalDist()
    result = nd.samples(10000)


    import matplotlib.pyplot as plt


    plt.hist(result, bins=20)
    plt.show()

Peki normal dağılmış rastgele sayı üretme işlemini samples metodu nasıl yapmaktadır? Aslında klasik yöntem önce [0, 1]
aralığında rastgele sayı üretmek, bunu kümülatif dağılım olarak kabul etmek ve bu kümülatif dağılımın x değerini
hesaplamaktır.

.. code-block:: python

    import random
    import statistics


    nd = statistics.NormalDist(100, 15)

    result = [nd.inv_cdf(random.random()) for _ in range(10000)]


    import matplotlib.pyplot as plt


    plt.hist(result, bins=20)
    plt.show()

Aslında normal dağılmış rastgele sayı üretmek için standart kütüphanede random modülü içerisinde gauss isimli bir
fonksiyon da bulundurulmuştur. gauss fonksiyonunun parametrik yapısı şöyledir:

.. code-block:: python

    gauss(mu=0.0, sigma=1.0)

Python 3.11'den önce bu parametreler default değer almıyordu. Fonksiyonu kullanırken bu durumu dikkate alınız. Aşağıda
gauss fonksiyonu kullanılarak üretilen normal dağılmış rassal sayıların histogramı çizilmiştir.

.. code-block:: python

    import random


    result = [random.gauss(0, 1) for _ in range(10000)]


    import matplotlib.pyplot as plt


    plt.hist(result, bins=20)
    plt.show()

Python'un statistics modülündeki NormalDist sınıfı vektörel işlemler yapamamaktadır. Maalesef NumPy ve Pandas
kütüphanelerinde normal dağılım üzerinde vektörel işlem yapan öğeler yoktur. Ancak SciPy kütüphanesi içerisinde pek çok
dağılım üzerinde vektörel işlemler yapan sınıflar bulunmaktadır. Bu nedenle pratikte Python kütüphanesi yerine bu tür
işlemler için SciPy kütüphanesi tercih edilmektedir.

scipy.stats modülü içerisindeki *norm* isimli singleton nesne normal dağılım üzerinde vektörel işlem yapan metotlara
sahiptir. norm bir sınıf nesnesidir ve zaten yaratılmış bir biçimde bulunmaktadır. Dolayısıyla programcı doğrudan bu
nesne ile ilgili sınıfın metotlarını çağırabilir. Genellikle programcılar bu tür nesneleri kullanmak için *"from
import"* deyimini tercih ederler:

.. code-block:: python

    from scipy.stats import norm

norm nesnesine ilişkin sınıfın cdf isimli metodu üç parametre almaktadır:

.. code-block:: python

    cdf(x, loc=0, scale=1)

Buradaki x bir NumPy dizisi ya da Python dolaşılabilir nesnesi olabilir. Bu durumda tüm x değerlerinin kümülatif
olasılıkları hesaplanıp bir NumPy dizisi olarak verilmektedir. Burada loc ortalamayı, scale ise standart sapmayı
belirtmektedir. Örneğin:

.. code-block:: python

    result = norm.cdf([100, 130, 140], 100, 15)
    print(result)

.. code-block:: python

    from scipy.stats import norm


    result = norm.cdf([100, 130, 140], 100, 15)
    print(result)

norm nesnesinin ilişkin olduğu sınıfın ppf (percentage point function) isimli metodu cdf işleminin tersini yapmaktadır.
Yani kümülatif olasılığı bilindiği durumda bize bu kümülatif olasılığa karşı gelen x değerini verir. (Yani ppf
NormalDist sınıfındaki inv_cdf metoduna karşılık gelmektedir.):

.. code-block:: python

    ppf(q, loc=0, scale=1)

ppf (percentage point function) ismi size biraz tuhaf gelebilir. Bu isim birikimli dağılım fonksiyonunun tersini
belirtmek için kullanılmaktadır. ppf aslında *medyan (median)* kavramının genel biçimidir. Anımsanacağı gibi medyan
ortadan ikiye bölen noktayı belirtiyordu. Örneğin standart normal dağılımda medyan 0'dır. Yani ortalamaya eşittir.
İstatistikte tam ortadan bölen değil de diğer noktalardan bölen değerler için *percentage point* de denilmektedir.
Örneğin normal dağılımda 1/4 noktasından bölen değer aslında birikimli dağılım fonksiyonunun 0.25 için değeridir.

.. code-block:: python

    from scipy.stats import norm


    result = norm.ppf([0.50, 0.68, 0.95], 100, 15)
    print(result)

norm nesnesinin ilişkin olduğu sınıfın pdf (probability density function) isimli metodu yine x değerlerinin Gauss
eğrisindeki y değerlerini vermektedir. Metodun parametrik yapısı şöyledir:

::

    pdf(x, loc=0, scale=1)

Burada yine x hesaplanacak değeri, loc ortalamayı ve scale de standart sapmayı belirtmektedir.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm
    import matplotlib.pyplot as plt


    x = np.linspace(40, 160, 1000)
    y = norm.pdf(x, 100, 15)

    plt.plot(x, y)

    x = np.full(200, 100)       # 200 tane 100'lerden oluşan dizi
    yend = norm.pdf(100, 100, 15)
    y = np.linspace(0, yend, 200)
    plt.plot(x, y, linestyle='--')

    plt.show()

norm nesnesinin ilişkin olduğu sınıfın rvs metodu ise normal dağılıma ilişkin rassal sayı üretmek için kullanılmaktadır.
Metodun parametrik yapısı şöyledir:

.. code-block:: python

    rvs(loc=0, scale=1, size=1)

.. code-block:: python

    from scipy.stats import norm
    import matplotlib.pyplot as plt


    x = norm.rvs(100, 15, 10000)

    plt.hist(x, bins=20)
    plt.show()

Normal dağılımda ortalamadan birer standart sapma arasındaki bölgenin olasılığı, yani P{mu - sigma < X < mu + sigma}
olasılığı 0.68 civarındadır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm
    import matplotlib.pyplot as plt


    result = norm.cdf(1) - norm.cdf(-1)
    print(result)

    x = np.linspace(-5, 5, 1000)
    y = norm.pdf(x)

    plt.title('Ortalamadan 1 Standart Sapma Arası Bölge', fontweight='bold')
    axis = plt.gca()
    axis.set_ylim(-0.5, 0.5)
    axis.spines['left'].set_position('center')
    axis.spines['bottom'].set_position('center')
    axis.spines['top'].set_color(None)
    axis.spines['right'].set_color(None)

    axis.set_xticks(range(-4, 5))
    axis.text(2, 0.3, f'{result:.3f}', fontsize=14, fontweight='bold')

    plt.plot(x, y)

    x = np.linspace(-1, 1, 1000)
    y = norm.pdf(x)
    plt.fill_between(x, y)
    axis.arrow(2.5, 0.25, -2, -0.1, width=0.0255)

    plt.show()

Normal dağılımda ortalamadan iki standart sapma arasındaki bölgenin olasılığı, yani P{mu - 2 * sigma < X < mu + 2 *
sigma} olasılığı 0.95 civarındadır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm
    import matplotlib.pyplot as plt


    result = norm.cdf(2) - norm.cdf(-2)
    print(result)

    x = np.linspace(-5, 5, 1000)
    y = norm.pdf(x)

    plt.title('Ortalamadan 2 Standart Sapma Arası Bölge', fontweight='bold')
    axis = plt.gca()
    axis.set_ylim(-0.5, 0.5)
    axis.spines['left'].set_position('center')
    axis.spines['bottom'].set_position('center')
    axis.spines['top'].set_color(None)
    axis.spines['right'].set_color(None)

    axis.set_xticks(range(-4, 5))
    axis.text(2, 0.3, f'{result:.3f}', fontsize=14, fontweight='bold')

    plt.plot(x, y)

    x = np.linspace(-2, 2, 1000)
    y = norm.pdf(x)
    plt.fill_between(x, y)
    axis.arrow(2.5, 0.25, -2, -0.1, width=0.0255)

    plt.show()

Normal dağılımda ortalamadan üç standart sapma arasındaki bölgenin olasılığı, yani P{mu - 3 * sigma < X < mu + 3 *
sigma} olasılığı 0.997 civarındadır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm
    import matplotlib.pyplot as plt


    result = norm.cdf(3) - norm.cdf(-3)
    print(result)

    x = np.linspace(-5, 5, 1000)
    y = norm.pdf(x)

    axis = plt.gca()
    axis.set_ylim(-0.5, 0.5)
    axis.spines['left'].set_position('center')
    axis.spines['bottom'].set_position('center')
    axis.spines['top'].set_color(None)
    axis.spines['right'].set_color(None)

    axis.set_xticks(range(-4, 5))
    axis.text(2, 0.3, f'{result:.3f}', fontsize=14, fontweight='bold')

    plt.plot(x, y)

    x = np.linspace(-3, 3, 1000)
    y = norm.pdf(x)
    plt.fill_between(x, y)
    axis.arrow(2.5, 0.25, -2, -0.1, width=0.0255)

    plt.show()

Sürekli Düzgün Dağılım
----------------------

Diğer çok karşılaşılan sürekli dağılım *sürekli düzgün dağılım (continuous uniform distribution)* denilen dağılımdır.
Burada dağılımın a ve b biçiminde isimlendirebileceğimiz iki parametresi vardır. Sürekli düzgün dağılımın olasılık
yoğunluk fonksiyonu dikdörtgensel bir alandır. Dolayısıyla kümülatif dağılım fonksiyonu b - a değeriyle orantılı bir
değer vermektedir. Sürekli düzgün dağılımın olasılık yoğunluk fonksiyonu şöyle ifade edilebilir:

::

    f(x) = {
                1 / (b - a)     a < x < b
                0               diğer durumlarda
           }

Sürekli düzgün dağılım için Python'un standart kütüphanesinde bir sınıf bulunmamaktadır. NumPy'da da böyle bir sınıf
yoktur. Ancak SciPy içerisinde stats modülünde uniform isimli bir singleton nesne bulunmaktadır. Bu nesneye ilişkin
sınıfın yine cdf, ppf, pdf ve rvs metotları vardır. Bu metotlar sırasıyla a değerini ve a'dan uzunluğu parametre olarak
almaktadır. Örneğin:

.. code-block:: python

    result = uniform.pdf(15, 10, 10)

Burada aslında a = 10, b = 20 olan bir sürekli düzgün dağılımdaki olasılık yoğunluk fonksiyon değeri elde edilmektedir.
Tabii aslında 10 ile 20 arasındaki tüm olasılık yoğunluk fonksiyon değerleri 1 / 10 olacaktır. Örneğin:

.. code-block:: python

    result = uniform.cdf(15, 10, 10)

Burada a = 10, b = 20 olan bir sürekli düzgün dağılımda 15'in solundaki alan elde edilecektir. 15 burada orta nokta
olduğuna göre elde edilecek bu değer 0.5'tir. uniform nesnesinin metotlarındaki ikinci parametrenin (loc) a değeri
olduğuna ancak üçüncü parametrenin a'dan uzaklık belirttiğine (scale) dikkat ediniz. Bu dağılımın parametrik bilgileri a
ve b olsa da SciPy stats modülünde tüm dağılımlar için ortak bir parametrik yapı tercih edildiğinden dolayı böyle bir
tasarım kullanılmıştır.

.. code-block:: python

    import numpy as np
    from scipy.stats import uniform
    import matplotlib.pyplot as plt

    A = 10
    B = 20

    x = np.linspace(A - 5, B + 5, 1000)
    y = uniform.pdf(x, A, B - A)

    plt.title('Continuous Uniform Distribution', fontweight='bold')
    plt.plot(x, y)

    x = np.linspace(10, 12.5, 1000)
    y = uniform.pdf(x, A, B - A)
    plt.fill_between(x, y)
    plt.show()

    result = uniform.cdf(12.5, A, B - A)
    print(result)                               # 0.25

    result = uniform.ppf(0.5, A, B - A)
    print(result)                               # 15

Düzgün dağılmış rastgele sayı üretimi aslında bizim aşina olduğumuz klasik rastgele sayı üretimidir. Örneğin Python
standart kütüphanesindeki random modülünde bulunan random fonksiyonu 0 ile 1 arasında rastgele bir sayı veriyordu.
Aslında bu fonksiyon a = 0, b = 1 olan düzgün dağılımda rastgele sayı veren fonksiyonla tamamen aynıdır. Benzer biçimde
NumPy'daki random modülündeki random fonksiyonu 0 ile 1 arasında düzgün dağılmış rastgele sayı üretmektedir. Örneğin:

.. code-block:: python

    result = uniform.rvs(10, 10, 10)

Burada a = 10, b = 20 olan sürekli düzgün dağılımda 10 tane rastgele noktalı sayı elde edilecektir.

Örneğin 100 ile 200 arasında rastgele 10 tane gerçek sayı üretmek istesek bu işlemi şöyle yapmalıyız:

.. code-block:: python

    uniform.rvs(100, 100, 10)

.. code-block:: python

    from scipy.stats import uniform
    import numpy as np


    x = np.random.random(10)
    print(x)

    x = uniform.rvs(0, 1, 10)       # yukarıdakiyle tamamen aynı biçimde rassal sayı üretir
    print(x)

t Dağılımı (Student's t-Distribution)
-------------------------------------

Özellikle güven aralıklarında (confidence intervals) ve hipotez testlerinde (hypothesis testing) kullanılan diğer önemli
bir sürekli dağılım da *t dağılımı (t-distribution)* denilen dağılımdır. t dağılımını bulan kişi (William Sealy Gosset)
makalesini *Student* takma adıyla yayınladığından dolayı bu dağılıma İngilizce *Student's t-distribution* da
denilmektedir.

t dağılımı standart normal dağılıma oldukça benzemektedir. Bu dağılımın ortalaması 0'dır. Ancak standart sapması
*serbestlik derecesi (degrees of freedom)* denilen bir değere göre değişir. t dağılımının standart sapması sigma =
karekök(df / (df - 2)) biçimindedir. t dağılımının olasılık yoğunluk fonksiyonu biraz karmaşık bir görünümdedir. Ancak
fonksiyon standart normal dağılıma göre *daha az yüksek ve biraz daha şişman* gibi gözükmektedir. t dağılımının
serbestlik derecesi artırıldığında dağılım standart normal dağılıma çok benzer hale gelir. Serbestlik derecesi >= 30
durumunda standart normal dağılımla oldukça örtüşmektedir. Yani serbestlik derecesi >= 30 durumunda artık t dağılımı
kullanmakla standart normal dağılım kullanmak arasında önemli bir farklılık kalmamaktadır.

t dağılımı denildiğinde her zaman ortalaması 0 olan standart sapması karekök(df / (df - 2)) olan dağılım
anlaşılmaktadır. Tabii t dağılımı da eksende kaydırılabilir yani ortalaması değiştirilebilir. t dağılımı standart normal
dağılım için üretilmiştir. Dolayısıyla eğer söz konusu dağılım standart normal dağılım değilse t dağılımını kullanmak
için önce söz konusu normal dağılımı standart normal dağılıma dönüştürmek gerekir.

t dağılımı teorik bir dağılımdır. Yukarıda da belirttiğimiz gibi özellikle *güven aralıklarının oluşturulması* ve
*hipotez testlerinde* kullanım alanı bulmaktadır. Bu tür durumlarda anakütle standart sapması bilinmediği zaman örnek
standart sapması anakütle standart sapması olarak kullanılmakta ve t dağılımından faydalanılmaktadır. Eskiden t dağılımı
özellikle *anakütle standart sapmasının bilinmediği ve örneklem büyüklüğünün 30'dan küçük olduğu durumlarda*
kullanılıyordu. (Çünkü örneklem büyüklüğü >= 30 olduğu durumda zaten t dağılımı standart normal dağılıma çok
yaklaşmaktadır.) Ancak artık bilgisayarların yoğun kullanıldığı bu zamanlarda örnek büyüklüğü >= 30 olsa bile t
dağılımını kullanmak toplamda çok küçük bir farklılık oluştursa da tercih edilebilmektedir.

t dağılımının *serbestlik derecesi (degrees of freedom)* denilen bir parametresi vardır. Serbestlik derecesi *örneklem
büyüklüğünden bir eksik olan* değerdir. Örneğin örneklem büyüklüğü 10 ise serbestlik derecesi 9'dur. Serbestlik derecesi
(dolayısıyla örneklem büyüklüğü) artırıldıkça t dağılımı standart normal dağılıma benzer. Yukarıda da belirttiğimiz gibi
n >= 30 durumunda artık yavaş yavaş t dağılımının standart normal dağılımdan önemli bir farkı kalmamaktadır.

t dağılımına ilişkin Python standart kütüphanesinde bir sınıf yoktur. NumPy kütüphanesinde de t dağılımına ilişkin bir
öğe bulunmamaktadır. Ancak SciPy kütüphanesindeki stats modülünde t isimli singleton nesne t dağılımı ile işlem yapmak
için kullanılmaktadır. t isimli singleton nesnenin metotları norm nesnesinin metotlarıyla aynıdır. Bu fonksiyonlar genel
olarak önce x değerini sonra serbestlik derecesini, sonra da ortalama değeri ve standart sapma değerlerini parametre
olarak almaktadır. Ortalama ve standart sapma değerleri kullanılarak dağılım önce standart normal dağılıma
dönüştürülmekte ondan sonra t dağılımı ile işlemler yapılmaktadır.

Aşağıdaki programda standart normal dağılım ile 5 serbestlik derecesi ve 30 serbestlik derecesine ilişkin t
dağılımlarının olasılık yoğunluk fonksiyonları çizdirilmiştir. Burada özellikle 30 serbestlik derecesine ilişkin t
dağılımının grafiğinin standart normal dağılım grafiği ile örtüşmeye başladığına dikkat ediniz.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm, t
    import matplotlib.pyplot as plt

    plt.figure(figsize=(15, 10))
    x = np.linspace(-5, 5, 1000)
    y = norm.pdf(x)

    axis = plt.gca()
    axis.set_ylim(-0.5, 0.5)
    axis.spines['left'].set_position('center')
    axis.spines['bottom'].set_position('center')
    axis.spines['top'].set_color(None)
    axis.spines['right'].set_color(None)
    axis.set_xticks(range(-4, 5))
    plt.plot(x, y)

    y = t.pdf(x, 5)
    plt.plot(x, y)

    y = t.pdf(x, 30)
    plt.plot(x, y, color='red')

    plt.legend(['Standart Normal Dağılım', 't Dağılımı (Serbestlik Derecesi = 5)',
                't dağılımı (Serbestlik Derecesi = 30)'])

    plt.show()

Tabii standart normal dağılımla t dağılımının olasılık yoğunluk fonksiyonları farklı olduğuna göre aynı değerlere
ilişkin kümülatif olasılık değerleri de farklı olacaktır.

.. code-block:: python

    from scipy.stats import norm, t

    x = [-0.5, 0, 1, 1.25]
    result = norm.cdf(x)
    print(result)               # [0.30853754 0.5        0.84134475 0.89435023]

    x = [-0.5, 0, 1, 1.25]
    result = t.cdf(x, 5)
    print(result)               # [0.31914944 0.5        0.81839127 0.86669189]

Biz bu konuda sürekli dağılım olarak yalnızca *normal dağılımı*, *sürekli düzgün dağılımı* ve *t dağılımını* inceledik.
Aslında değişik olayları modellemek için başka dağılımlar da kullanılmaktadır. Bunlardan bazılarını ileride başka
konular içerisinde ele alacağız.

Kesikli Olasılık Dağılımları
============================

Olasılık Kütle Fonksiyonu
-------------------------

Biz yukarıda bazı sürekli dağılımları inceledik. Kursumuzda genellikle sürekli dağılımları kullanacağız. Ancak bu
noktada kesikli (discrete) dağılımlar üzerinde de bazı bilgiler vermek istiyoruz.

Kesikli dağılımlarda X değerleri her gerçek değeri almamaktadır. Dolayısıyla bunların fonksiyonları çizildiğinde sürekli
fonksiyonlar elde edilemeyecek kesikli noktalar elde edilecektir. Kesikli dağılımlarda X değerlerini onların
olasılıklarına eşleyen fonksiyonlara *olasılık kütle fonksiyonu (probability mass function)* denilmektedir. Sürekli
rassal değişkenlerin olasılık yoğunluk fonksiyonları integral hesap için kullanılırken kesikli rassal değişkenler için
olasılık kütle fonksiyonları doğrudan rassal değişkenin ilgili noktadaki olasılığını elde etmek için kullanılmaktadır.
Olasılık kütle fonksiyonu genellikle büyük P ya da küçük p harfi ile gösterilmektedir:

::

    px(x) = P{X = x}

Bu ifade X'in x değerine eşit olma olasılığını belirtmektedir. Buradaki X rassal değişkeni her gerçek değeri alamaz
yalnızca bazı değerleri alabilir. Tabii olasılık kütle fonksiyonu px(x) olmak üzere X'in her x değeri için px(x)
değerlerinin toplamının yine 1 olması gerekmektedir.

Poisson Dağılımı
----------------

Tıpkı sürekli rassal değişkenlerde olduğu gibi kesikli rassal değişkenlerde de çok sık karşılaşılan bazı olasılık
dağılımları vardır. En çok karşılaşılan kesikli dağılımlardan biri *poisson (genellikle puason biçiminde okunuyor)*
dağılımıdır. Bu kesikli dağılım adeta normal dağılımın kesikli biçimi gibidir. Poisson dağılımının olasılık kütle
fonksiyonu şöyledir:

::

    P(X = x) = (e^-lamda * lamda^x) / x!

Dağılımın olasılık kütle fonksiyonu size biraz karışık gelebilir. Buradaki x olasılığını hesaplamak istediğimiz kesikli
değeri belirtmektedir. Lamda ise ortalama olay sayısını belirtmektedir. Lamda değeri ortalama belirttiği için gerçek bir
değer olabilir. Ancak x değerleri 0, 1, 2, ... n biçiminde 0 ve pozitif tamsayılardan oluşmaktadır.

Yukarıda da belirttiğimiz gibi poisson dağılımı adeta normal dağılımın kesikli hali gibidir. Dolayısıyla doğada da çok
karşılaşılan kesikli dağılımlardandır. Buradaki lamda değeri *ortalama olay sayısını* belirtmektedir. Örneğin lamda
değeri *bir futbol maçındaki ortalama gol sayısını* ya da *İstanbul'da bir günde meydana gelen ortalama trafik kazası
sayısını* belirtiyor olabilir. Bir olgunun poisson dağılımı ile temsil edilmesi aslında *ortalama civarında yüksek
olasılıkların bulunduğu, ortalamadan iki yandan uzaklaştıkça olasılıkların çan eğrisi gibi düştüğü* bir olasılık kütle
fonksiyonunu belirtmektedir.

Poisson dağılımı için de Python standart kütüphanesinde ya da NumPy ve Pandas kütüphanelerinde özel fonksiyonlar ve
sınıflar bulunmamaktadır. Ancak SciPy kütüphanesinin stats modülü içerisinde poisson isimli bir singleton nesne ile bu
dağılımla ilgili işlemler kolaylıkla yapılabilmektedir.

SciPy'da kesikli dağılımlar üzerinde işlemler yapan singleton nesneler sürekli dağılımlarla işlemler yapan singleton
nesnelere kullanım bakımından oldukça benzemektedir. Ancak kesikli dağılımlar için fonksiyonun ismi *pdf* değil *pmf*
biçimindedir. Buradaki *pmf* ismi *probability mass function* sözcüklerinden kısaltılmıştır.

SciPy'daki poisson nesnesinin fonksiyonları genel olarak bizden x değerini ve lambda değerini parametre olarak
istemektedir. Örneğin futbol maçlarındaki gol sayısının poisson dağılımına uyduğunu varsayalım. Maçlardaki ortalama gol
sayısının 2 olduğunu kabul edelim. Bu durumda bir maçta 5 gol olma olasılığı aşağıdaki gibi elde edilebilir:

.. code-block:: python

    from scipy.stats import poisson

    result = poisson.pmf(5, 2)
    print(result)           # 0.03608940886309672

Yukarıdaki gibi poisson dağılımı sorularında genellikle soruyu soran kişi belli bir olayın ortalama gerçekleşme sayısını
verir. Sonra kişiden bazı değerleri bulmasını ister. Peki soruda *bir maçta ikiden fazla gol olma olasılığı* sorulmuş
olsaydı biz soruyu nasıl çözerdik? poisson nesnesi ile cdf fonksiyonunu çağırdığımızda bu cdf fonksiyonu bize x değerine
kadarki (x değeri de dahil olmak üzere) kümülatif olasılığı verecektir. Bu değeri de 1'den çıkartırsak istenen olasılığı
elde edebiliriz:

.. code-block:: python

    result = 1 - poisson.cdf(2, 2)
    print(result)   # 0.3233235838169366

Aşağıda lamda değeri (ortalaması) 10 olan poisson dağılımı için saçılma grafiği çizdirilmiştir. Bu grafiğin normal
dağılım grafiğini andırmakla birlikte sağdan çarpık olduğuna dikkat ediniz.

.. code-block:: python

    from scipy.stats import poisson
    import matplotlib.pyplot as plt

    plt.title('Lamda = 10 İçin Poisson Dağılımı', fontweight='bold', pad=10)
    x = range(0, 40)
    y = poisson.pmf(x, 10)

    plt.scatter(x, y)
    plt.show()

Poisson dağılımında lamda değeri yüksek tutulduğunda saçılma grafiğinin Gauss eğrisine benzediğine dikkat ediniz.

.. code-block:: python

    from scipy.stats import poisson
    import matplotlib.pyplot as plt

    plt.title('Lamda = 100 İçin Poisson Dağılımı', fontweight='bold', pad=10)
    x = range(0, 200)
    y = poisson.pmf(x, 100)

    plt.scatter(x, y)
    plt.show()

    result = poisson.pmf(3, 4)
    print(result)

Bernoulli Dağılımı
------------------

Bernoulli dağılımında X değeri 0 ya da 1 olabilir. X = 0 durumu bir olayın olumsuz olma ya da gerçekleşmeme olasılığını,
X = 1 durumu ise bir olayın olumlu olma ya da gerçekleşme olasılığını belirtmektedir. Bu rassal değişkenin yalnızca iki
değer aldığına dikkat ediniz. Sonucu iki değerden biri olan rassal deneylere *Bernoulli deneyleri* de denilmektedir.
Örneğin bir paranın atılması durumunda yazı ya da tura gelmesi iki durumlu bir deneydir. Dolayısıyla bir Bernoulli
deneyidir. Bernoulli deneylerinde genellikle X = 1 durumundaki olasılık verilir. Biz de bu olasılığı 1'den çıkartarak X
= 0 durumundaki olasılığı elde ederiz. Bernoulli dağılımının olasılık kütle fonksiyonu şöyle ifade edilebilir:

::

    P{X = x} =  {
                    p           X = 1 ise
                    1 - p       X = 0 ise
                }

Ya da bu olasılık kütle fonksiyonunu aşağıdaki gibi de ifade edebiliriz:

::

    P{X = x} = p^x * (1 - p)^(1 - x)

Burada X = 0 için 1 - p değerinin, X = 1 için p değerinin elde edildiğine dikkat ediniz.

Bernoulli dağılımı için de SciPy kütüphanesinde stats modülü içerisinde bernoulli isimli bir singleton nesne
bulundurulmuştur. Tabii bu dağılım çok basit olduğu için bu nesnenin kullanılması da genellikle gereksiz olmaktadır.
bernoulli nesnesinin ilişkin olduğu sınıfın metotları bizden X değerini (0 ya da 1 olabilir) ve X = 1 için p değerini
almaktadır. Örneğin:

.. code-block:: python

    bernoulli.pmf(0, 0.7)

buradan 0.3 değeri elde edilecektir.

Binom Dağılımı
--------------

Diğer çok karşılaşılan bir kesikli dağılım da *binom dağılımı* denilen dağılımdır. Binom dağılımında bir Bernoulli
deneyi (yani iki sonucu olan bir deney) toplam n defa yinelenmektedir. Bu n defa yinelenmede olayın tam olarak kaç defa
olumlu sonuçlanacağının olasılığı hesaplanmak istenmektedir. Dolayısıyla binom dağılımının olasılık kütle fonksiyonunda
X değerleri 0, 1, 2, ... gibi tamsayı değerler alır. Örneğin bir para 5 kez atılıyor olsun. Biz de bu 5 kez para
atımında tam olarak 3 kez Tura gelme olasılığını hesaplamak isteyelim. Burada paranın atılması bir Bernoulli deneyidir.
Bu deney 5 kez yinelenmiş olumlu kabul ettiğimiz Tura gelme durumunun toplamda 3 kez olmasının olasılığı elde edilmek
istenmiştir.

Binom dağılımının olasılık kütle fonksiyonu kombinasyon hesabıyla basit bir biçimde oluşturulabilir. Yukarıda
bahsettiğimiz paranın 5 kez atılması durumunda 3 Tura gelmesi aşağıdakiler gibi olabilir:

::

    T Y T Y T
    T T T Y Y
    Y T T Y T
    ...

Burada toplamda 3 kez Tura gelme durumu aslında C(5, 3) kadardır. Bu olaylar bir arada gerçekleşeceğine göre bu değerle
p^3 değerini çarpmamız gerekir. Öte yandan Tura gelmeyen olasılıkların toplamı de 5 - 3 = 2 kadardır. O halde bunun da
(1 - p)^2 ile çarpılması gerekir. Binom dağılımının olasılık kütle fonksiyonu şöyledir:

::

    P{X = x} = C(n, x)p^x * (1 - p)^(n - x)

Binom dağılımı için SciPy kütüphanesindeki stats modülünde bulunan binom isimli singleton nesne kullanılabilir. Nesnenin
kullanılması diğer singleton nesnelere benzemektedir. Örneğin ilgili sınıfın pmf fonksiyonu olasılık kütle fonksiyonunu
belirtmektedir. Bu fonksiyonlarda birinci parametre *olumlu gerçekleşme sayısını*, ikinci parametre *toplam deney
sayısını* ve üçüncü parametre de *olumlu gerçekleşme olasılığını* belirtmektedir. Örneğin yukarıda belirttiğimiz paranın
5 kez atılmasında tam olarak 3 kez tura gelme olasılığı şöyle elde edilebilir:

.. code-block:: python

    binom.pmf(3, 5, 0.5)

Merkezi Limit Teoremi
=====================

Şüphesiz *sonuç çıkartıcı istatistiğin (inferential statistics)* en önemli teoremi *merkezi limit teoremi (central limit
theorem)* denilen teoremdir. Bu teorem George Pólya tarafından 1920 yılında ilk kez resmi bir biçimde ifade edilmiştir.
Merkezi limit teoreminin biçimsel ifadesi biraz karmaşık bir görünümdedir. Biz burada teoremi basit biçimde
açıklayacağız. Bu teoreme göre bir anakütleden elde edilen örnek ortalamaları normal dağılma eğilimindedir. Eğer
anakütle normal dağılmışsa küçük örneklerin ortalamaları da normal dağılır. Ancak anakütle normal dağılmamışsa örnek
ortalamalarının normal dağılması için örneklerin belli bir büyüklükte (tipik olarak >= 30) olması gerekmektedir. Aksi
takdirde örneklem dağılımı soldan ya da sağdan çarpık olabilmektedir. Örneğin elimizde 1,000,000 elemanlı bir anakütle
olsun. Bu anakütleden 50'lik tüm alt kümeleri yani örnekleri elde edip bunların ortalamalarını hesaplarsak bu
ortalamaların normal dağıldığı görülecektir. Bir anakütleden alınan alt kümelere *örnek (sample)* bu işleme de genel
olarak *örnekleme (sampling)* denilmektedir.

Aşağıdaki örnekte 0 ile 1,000,000 arasındaki sayılardan oluşan 1,000,000 elemanlık düzgün dağılmış anakütle içerisinden
100,000 tane 50'lik rastgele örnekler elde edilmiştir. Sonra da elde edilen bu örneklerin ortalamaları hesaplanmış ve bu
ortalamaların histogramı çizdirilmiştir. Örnek ortalamalarının dağılımına ilişkin histogramın normal dağılıma
benzediğine dikkat ediniz.

.. code-block:: python

    import numpy as np

    POPULATION_RANGE = 1_000_000
    NSAMPLES = 100_000
    SAMPLE_SIZE = 50

    samples = np.random.randint(0, POPULATION_RANGE + 1, (NSAMPLES, SAMPLE_SIZE))
    samples_means = np.mean(samples, axis=1)

    import matplotlib.pyplot as plt

    plt.figure(figsize=(12, 8))
    plt.title('Merkezi Limit Teoremi', fontweight='bold', pad=10)
    plt.hist(samples_means, bins=50)

    plt.show()

Tabii yukarıdaki örneği hiç NumPy kullanmadan tamamen Python standart kütüphanesi ile de yapabilirdik.

.. code-block:: python

    import random
    import statistics

    POPULATION_RANGE = 1_000_000
    NSAMPLES = 100_000
    SAMPLE_SIZE = 50

    samples_means = [statistics.mean(random.sample(range(POPULATION_RANGE + 1), SAMPLE_SIZE))
                     for _ in range(NSAMPLES)]

    import matplotlib.pyplot as plt

    plt.figure(figsize=(12, 8))
    plt.title('Merkezi Limit Teoremi', fontweight='bold', pad=10)
    plt.hist(samples_means, bins=50)

    plt.show()

Merkezi limit teoremine göre örnek ortalamalarına ilişkin normal dağılımın ortalaması anakütle ortalamasına eşittir.
(Yani bir anakütleden çekilen örnek ortalamalarının ortalaması anakütle ortalaması ile aynıdır.) İstatistiksel
sembollerle bu durum aşağıdaki gibi ifade edilmektedir:

::

    μₓ̄ = μ

Aşağıdaki programda bu durum gösterilmiştir. Ancak aşağıdaki örnekte anakütle ortalaması ile örnek ortalamalarının
ortalaması arasında nispeten küçük bir fark oluşabilecektir. Bunun nedeni bizim tüm örnekleri değil yalnızca 10,000
örneği almamızdan kaynaklanmaktadır. 1,000,000 tane elemanın 50'li altküme sayıları Python'da math.comb fonksiyonu ile
elde edilebilir. Bu aşağıdaki gibi bir değerdir:

::

    328392407820232468120659145980537063071733850478231049855714233423603813357488386226050559849769116542462344220085901
    45569291064005813572729171162888456999821437660641232861427083961136203001102459836375149013720622748800690778924980000

.. code-block:: python

    import numpy as np

    POPULATION_RANGE = 1_000_000
    NSAMPLES = 100_000
    SAMPLE_SIZE = 50

    population_mean = np.mean(range(POPULATION_RANGE + 1))
    samples = np.random.randint(1, POPULATION_RANGE + 1, (NSAMPLES, SAMPLE_SIZE))
    samples_means = np.mean(samples, axis=1)
    samples_means_mean = np.mean(samples_means)

    print(f'Anakütle ortalaması: {population_mean}')
    print(f'Örnek ortalamalarının Ortalaması: {samples_means_mean}')

Yukarıda bir anakütleden alınan örnek ortalamalarının normal dağıldığını ve bu normal dağılımın ortalamasının da
anakütle ortalamasına eşit olduğunu söyledik. Peki örnek ortalamalarına ilişkin normal dağılımın standart sapması
nasıldır? İşte merkezi limit teoremine göre örnek ortalamalarının standart sapması *anakütle standart sapması /
karekök(n)* biçimindedir. Örnek ortalamalarının standart sapması sembolik biçimde şöyle ifade edilebilir:

::

    σₓ̄ = σ / √n

Örnek ortalamalarının standart sapması anakütle sapmasından oldukça küçüktür ve örnek büyüklüğüne bağlıdır. Örnek
ortalamalarının standart sapmasına *standart hata (standard error)* da denilmektedir. Görüldüğü gibi eğer örnek
ortalamalarına ilişkin normal dağılımın standart sapması düşürülmek isteniyorsa (başka bir deyişle standart hata
azaltılmak isteniyorsa) örnek büyüklüğü artırılmalıdır.

Aşağıdaki örnekte örnek ortalamalarına ilişkin dağılımın standart sapmasının merkezi limit teoreminde belirtilen durum
ile uygunluğu gösterilmektedir. Bu örnekte de aslında biz anakütle içerisinden az sayıda örnek aldığımız için olması
gereken değerlerden bir sapma söz konusu olacaktır.

.. code-block:: python

    import numpy as np

    POPULATION_RANGE = 1_000_000
    NSAMPLES = 100_000
    SAMPLE_SIZE = 50

    population_mean = np.mean(range(POPULATION_RANGE + 1))
    population_std = np.std(range(POPULATION_RANGE + 1))

    samples = np.random.randint(1, POPULATION_RANGE + 1, (NSAMPLES, SAMPLE_SIZE))
    samples_means = np.mean(samples, axis=1)
    samples_means_mean = np.mean(samples_means)
    sample_means_std = np.std(samples_means)

    print(f'Anakütle ortalaması: {population_mean}')
    print(f'Örnek ortalamalarının Ortalaması: {samples_means_mean}')
    print(f'Fark: {np.abs(population_mean - samples_means_mean)}')

    print(
        f'Merkezi limit teoreminden elde edilen örnek ortalamalarının standart sapması: '
        f'{population_std / np.sqrt(50)}'
    )
    print(f'Örnek ortalamalarının standart sapması: {sample_means_std}')

Merkezi limit teoremine göre eğer anakütleden çekilen örnekler büyükse yani tipik olarak n örnek büyüklüğü, N anakütle
büyüklüğü olmak üzere n / N >= 0.05 ise bu durumda örneklem dağılımın standart sapması için *anakütle standart sapması /
kök(n)* değeri *düzeltme faktörü (correction factor)* denilen bir çarpanla çarpılmalıdır. Düzeltme faktörü karekök((N -
n)/(N - 1)) biçimindedir. Bu konunun ayrıntıları için başka kaynaklara başvurabilirsiniz. Örneğin anakütle 100 elemandan
oluşuyor olsun. Biz 30 elemanlı örnekler çekersek bu düzeltme faktörünü kullanmalıyız. Tabii pratikte genellikle n / N
değeri 0.05'ten oldukça küçük olma eğilimindedir.

Yukarıdaki örneklerde anakütlenin normal dağılmadığına düzgün (uniform) dağıldığına dikkat ediniz. Çünkü biz anakütleyi
0'dan 1,000,000'a kadar sayılardan anakütleyi oluşturduk. Yukarıdaki örneklerde oluşturduğumuz anakütlenin histogramı
aşağıda çizdirilmiştir.

.. code-block:: python

    import matplotlib.pyplot as plt

    POPULATION_RANGE = 1_000_000

    population = range(0, POPULATION_RANGE + 1)

    plt.figure(figsize=(12, 8))
    plt.title('Merkezi Limit Teoremi', fontweight='bold', pad=10)
    plt.hist(population, bins=50)

Merkezi limit teoreminde anakütlenin normal dağılmış olması gerekmez. Nitekim yukarıdaki örneklerimizde bir anakütleyi
*düzgün dağılıma (uniform distribution)* ilişkin olacak biçimde oluşturduk. Ancak eğer anakütle normal dağılmamışsa
örneklem ortalamalarının dağılımının normal olması için örneklerin belli bir değerden büyük olması gerekmektedir. Bu
değer tipik olarak >= 30 biçimindedir. Tabii örnek büyüklüğü 30'dan küçükse de dağılım yine normal dağılıma
benzemektedir. Ancak anakütlenin normal dağılmadığı durumda örnek ortalamalarının normal dağılması için örnek büyüklüğü
>= 30 biçiminde alınmalıdır. Bu nedenle eğer anakütle *normal dağılmamışsa ve örnek büyüklüğü < 30* ise parametre
tahmininde merkezi limit teoreminden faydalanılması tatminkar sonuç elde edilmesini engelleyebilmektedir. Bu durumda
*parametrik olmayan (non-parametric) yöntemler* denilen yöntemler tercih edilmelidir.

Buradan çıkan sonuçlar özetle şöyledir:

- Eğer anakütle normal dağılmışsa örnek büyüklüğü ne olursa olsun örneklem ortalamalarının dağılımı normaldir.
- Eğer anakütle normal dağılmamışsa örnek ortalamalarının dağılımının normal olması için örnek büyüklüğünün >= 30 olması
  gerekir. Tabii n < 30 durumunda yine örneklem dağılımı normale benzemektedir ancak kusurlar oluşmaktadır.

Özetle anakütle normal dağılmamışsa örnek büyüklüklerinin artırılması gerekmektedir.

Normallik Testleri
==================

Parametrik istatistiksel yöntemler genel olarak anakütle ve/veya örneklem dağılımının normal olduğu varsayımı ile
yürütülmektedir. Bu nedenle bazen anakütlenin normal dağılıp dağılmadığının örneğe dayalı olarak test edilmesi
gerekebilmektedir. Bunun için anakütleden bir örnek alınır. Sonra bu örneğe bakılarak anakütlenin normal dağılıp
dağılmadığı belli bir *güven düzeyinde (confidence level)* belirlenir. Buna *normallik testleri* denilmektedir. Aslında
normallik testi gözle de üstünkörü yapılabilmektedir. Anakütle içerisinden bir örnek çekip onun histogramını çizersek
eğer bu histogram Gauss eğrisine benziyorsa biz anakütlenin de normal dağılmış olduğunu varsayabiliriz. Ancak
anakütlenin normal dağılıp dağılmadığının tespit edilmesi için bazı *hipotez testlerinden (hypothesis testing)*
faydalanılmaktadır. Normal dağılıma ilişkin iki önemli hipotez testi vardır: *Kolmogorov-Smirnov* testi ve
*Shapiro-Wilk* testi. Bu testlerin istatistiksel açıklaması biraz karmaşıktır ve ayrıntılar içermektedir. Biz bu bölümde
bu konuda ayrıntılı açıklamalarda bulunmayacağız. Hipotez testleri kursumuzun sonraki bölümleri içerisinde ayrı bir
başlık halinde ele alınmaktadır.

Hipotez testlerinde bir hipotez öne sürülür ve bu hipotezin belirli güven düzeyi içerisinde doğrulanıp doğrulanmadığına
bakılır. Genel olarak bizim doğrulanmasını istediğimiz hipoteze H0 hipotezi (buna *null hipotez* de denilmektedir),
bunun tersini belirten, yani arzu edilmeyen durumu belirten hipoteze de H1 hipotezi denilmektedir. Örneğin normallik
testindeki H0 ve H1 hipotezleri şöyle oluşturulabilir:

::

    H0: Seçilen örnek normal bir anakütleden gelmektedir.
    H1: Seçilen örnek normal dağılmış bir anakütleden gelmemektedir.

Normallik testlerinden birisi Kolmogorov-Smirnov testidir (test ünlü Sovyet matematikçisi ve istatistikçisi Andrey
Kolmogorov ve Nikolai Smirnov tarafından geliştirildiği için bu isimle anılmaktadır). Bu test SciPy kütüphanesindeki
stats modülü içerisinde bulunan kstest fonksiyonuyla uygulanabilmektedir. Fonksiyonun parametrik yapısı şöyledir:

.. code-block:: python

    kstest(rvs, cdf, args=(), N=20, alternative='two-sided', method='auto', *, axis=0,
           nan_policy='propagate', keepdims=False)

Fonksiyonun ilk iki parametresi zorunlu parametrelerdir. Birinci parametre anakütleden rastgele seçilen örneği, ikinci
parametre testi yapılacak dağılımın kümülatif dağılım fonksiyonunu almaktadır. Ancak bu parametre kolaylık olsun diye
yazısal biçimde de girilebilmektedir. (Kolmogorov-Smirnov testi aslında başka dağılımları test etmek amacıyla da
kullanılabilmektedir.) Normallik testi için bu parametre 'norm' ya da norm.cdf biçiminde girilebilir. Fonksiyonun diğer
parametrelerini SciPy dokümanlarından inceleyebilirsiniz. Biz burada bu fonksiyonu hedefe yönelik bir biçimde
kullanacağız.

kstest fonksiyonu çağrıldıktan sonra bize KstestResult türünden *isimli bir demet (named tuple)* verir. Demetin
statistic isimli ilk elemanı test istatistiğini, pvalue isimli ikinci elemanı p değerini belirtir. Bizim burada yapmamız
gereken bu p değerinin kendi seçtiğimiz belli bir kritik değerden büyük olup olmadığına bakmaktır. Bu kritik değer tipik
olarak 0.05 olarak alınmaktadır. Ancak testi daha katı yapacaksanız bu değeri 0.01 gibi daha küçük tutabilirsiniz.
Yukarıda da belirttiğimiz gibi bu testte iki hipotez vardır:

::

    H0: Seçilen örnek normal dağılmış bir anakütleden gelmektedir.
    H1: Seçilen örnek normal dağılmış bir anakütleden gelmemektedir.

Eğer test sonucunda elde ettiğimiz p değeri belirlediğimiz kritik değerden (0.05) büyükse H0 hipotezi kabul edilir, H1
hipotezi reddedilir. Eğer bu p değeri bu kritik değerden küçükse H0 hipotezi reddedilip, H1 hipotezi kabul edilmektedir.
Yani özetle bu p değeri 0.05 gibi bir kritik değerden büyükse örnek normal dağılmış bir anakütleden gelmektedir, 0.05
gibi bir kritik değerden küçükse örnek normal dağılmamış bir anakütleden gelmektedir.

Aşağıdaki örnekte normal dağılmış bir anakütleden ve düzgün dağılmış bir anakütleden rastgele örnekler çekilip kstest
fonksiyonuna sokulmuştur. Burada birinci örnek için p değeri 1'e yakın, ikinci örnek için p değeri 0'a çok yakın
çıkmıştır. Böylece birinci örneğin alındığı anakütlenin normal dağılmış olduğu, ikinci örneğin alındığı anakütlenin ise
normal dağılmamış olduğu söylenebilir.

.. code-block:: python

    from scipy.stats import norm, uniform, kstest


    sample_norm = norm.rvs(size=1000)

    result = kstest(sample_norm, 'norm')
    print(result.pvalue)        # 1'e yakın bir değer


    sample_uniform = uniform.rvs(size=1000)

    result = kstest(sample_uniform, norm.cdf)
    print(result.pvalue)        # 0'a çok yakın bir değer

kstest fonksiyonunda ikinci parametreye 'norm' girildiğinde birinci parametredeki değerler ortalaması 0, standart
sapması 1 olan standart normal dağılıma uygun değerler olmalıdır. Eğer ortalama ve standart sapması farklı bir normal
dağılım için test yapılacaksa dağılımın parametreleri de ayrıca args parametresiyle verilmelidir. Örneğin biz ortalaması
100 standart sapması 15 olan bir dağılıma ilişkin test yapmak isteyelim. Bu durumda test aşağıdaki gibi yapılmalıdır.

.. code-block:: python

    from scipy.stats import norm, uniform, kstest

    sample_norm = norm.rvs(100, 15, size=1000)
    result_norm = kstest(sample_norm, 'norm', args=(100, 15))

    sample_uniform = uniform.rvs(100, 100, size=1000)
    result_uniform = kstest(sample_uniform, 'norm', args=(100, 15))


    import matplotlib.pyplot as plt

    plt.figure(figsize=(20, 8))
    ax1 = plt.subplot(1, 2, 1)
    ax1.set_title(f'p değeri: {result_norm.pvalue}', pad=15, fontweight='bold')

    ax2 = plt.subplot(1, 2, 2)
    ax2.set_title(f'p değeri: {result_uniform.pvalue}', pad=15, fontweight='bold')
    ax1.hist(sample_norm, bins=20)

    ax2.hist(sample_uniform, bins=20)
    plt.show()

Shapiro-Wilk testi scipy.stats modülündeki shapiro fonksiyonuyla yapılmaktadır. Fonksiyonun parametrik yapısı şöyledir:

.. code-block:: python

    shapiro(x, *, axis=None, nan_policy='propagate', keepdims=False)

Bu fonksiyonun kullanılması daha kolaydır. Bu fonksiyonun tek bir zorunlu parametresi vardır. Bu parametre anakütleden
çekilen örneği belirtir. Buradaki normal dağılım herhangi bir ortalama ve standart sapmaya ilişkin olabilir. Yani bizim
dağılım değerlerini ortalaması 0, standart sapması 1 olacak biçimde ölçeklendirmemiz gerekmemektedir.

Aşağıdaki örnekte ortalaması 100, standart sapması 15 olan normal dağılmış ve düzgün dağılmış bir anakütleden 1000'lik
bir örnek seçilip Shapiro-Wilk testine sokulmuştur. Buradan elde edilen pvalue değerlerine dikkat ediniz.

.. code-block:: python

    from scipy.stats import norm, uniform, shapiro

    sample_norm = norm.rvs(100, 15, size=1000)

    result_norm = shapiro(sample_norm)
    sample_uniform = uniform.rvs(100, 100, size=1000)
    result_uniform = shapiro(sample_uniform)


    import matplotlib.pyplot as plt

    plt.figure(figsize=(20, 8))
    ax1 = plt.subplot(1, 2, 1)
    ax1.set_title(f'p değeri: {result_norm.pvalue}', pad=15, fontweight='bold')

    ax2 = plt.subplot(1, 2, 2)
    ax2.set_title(f'p değeri: {result_uniform.pvalue}', pad=15, fontweight='bold')
    ax1.hist(sample_norm, bins=20)

    ax2.hist(sample_uniform, bins=20)
    plt.show()

Peki Kolmogorov-Smirnov testi ile Shapiro-Wilk testi arasında ne farklılık vardır? Aslında bu iki test arasında bazı
spesifik farklılıklar bulunmaktadır. Ancak bunların her ikisi de normalliğin test edilmesi için kullanılabilmektedir.
Shapiro-Wilk testinin kullanımı daha kolaydır. Ayrıca anakütleden çekilen örnekler küçükse (tipik olarak <= 50)
Shapiro-Wilk testi Kolmogorov-Smirnov testine göre daha iyi bir sonucun elde edilmesine yol açmaktadır. Yani örneğiniz
küçükse Shapiro-Wilk testini tercih edebilirsiniz.

Güven Aralıkları
================

Parametre Tahmini ve Güven Aralığı Kavramı
------------------------------------------

İstatistikte örneğe dayalı olarak anakütlenin ortalamasını (ve/veya standart sapmasını) tahmin etme sürecine *parametre
tahmini (parameter estimation)* denilmektedir. Parametre tahmini *noktasal olarak (point estimate)* ya da *aralıksal
olarak (interval estimate)* yapılabilmektedir. Örnekten hareketle anakütle ortalamasının belli bir aralıkta ve belli bir
güven düzeyinde tahmin edilmesi önemli bir konudur. Böylece biz anakütlenin tamamını gözden geçirmeden, oradan aldığımız
bir örneğe bakarak anakütle ortalamasını belli bir güven düzeyinde (confidence level) aralıksal olarak tahmin
edebiliriz. Anakütle parametrelerinin aralıksal tahminine *güven aralıkları (confidence interval)* da denilmektedir.
Güven aralıkları tamamen merkezi limit teoremi kullanılarak oluşturulmaktadır. Yani güven aralıkları merkezi limit
teoreminin en açık uygulamalarından biridir.

Güven aralıkları bir anakütleden çekilen örneğe bağlı olarak anakütle parametrelerinin belli bir güven düzeyi
(confidence level) içerisinde aralıksal olarak belirlenmesini hedeflemektedir. Merkezi limit teoremine göre bir
anakütleden çekilen örneklemlerin ortalamalarının normal dağıldığını görmüştük. O halde biz bir anakütleden rastgele bir
örnek seçip onun ortalamasına bakarak anakütle ortalamasını belli bir güven düzeyinde tahmin edebiliriz.

Anakütle Standart Sapması Bilindiğinde Güven Aralığı Hesabı
-----------------------------------------------------------

Bizim anakütle ortalamasını bilmediğimizi ancak anakütle standart sapmasını bildiğimizi varsayalım. (Genellikle aslında
anakütle standart sapmasını da bilmeyiz. Ancak burada bildiğimizi varsayıyoruz.) Bu anakütleden rastgele bir örnek
seçtiğimizde o örneğin ortalamasına bakarak anakütle ortalamasını belli bir aralıkta belli bir güven düzeyinde tahmin
edebiliriz. Şöyle ki: Örneğin seçtiğimiz güven düzeyi %95 olsun. Bu durumda bizim örneğimiz örnek ortalamalarının
dağılımında en kötü olasılıkla soldan 0.025 ve sağdan 0.975 kümülatif olasılığa karşı gelen x değerlerinden biri
olabilir. O halde yapacağımız şey örnek ortalamasının örneklem dağılımına göre seçtiğimiz örneğin ortalamasının %47.5
soluna ve %47.5 sağına ilişkin değerlerin elde edilmesidir. Bu durumda anakütle ortalaması %95 güven düzeyi içerisinde
bu aralıkta olacaktır. Tabii aslında bu işlemi daha basit olarak *rastgele elde ettiğimiz örneğin ortalamasını normal
dağılımın merkezine alarak soldan 0.025 ve sağdan 0.975 kümülatif olasılık değerlerine karşı gelen noktaları elde ederek
de* yapabiliriz.

Örneğin standart sapması 15 olan bir anakütleden rastgele 60 elemanlık bir örnek elde etmiş olalım. Bu örneğin
ortalamasının 109 olduğunu varsayalım. Bu durumda %95 güven düzeyi içerisinde anakütle ortalamasına ilişkin güven
aralıkları aşağıdaki gibi elde edilebilir:

.. code-block:: python

    import numpy as np
    from scipy.stats import norm

    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)

    lower_bound = norm.ppf(0.025, sample_mean, sampling_mean_std)
    upper_bound = norm.ppf(0.975,  sample_mean, sampling_mean_std)

    print(f'[{lower_bound}, {upper_bound}]')              # [105.20454606435501, 112.79545393564499]

Burada biz anakütlenin standart sapmasını bildiğimiz için örnek ortalamalarına ilişkin normal dağılımın standart
sapmasını hesaplayabildik. Buradan elde ettiğimiz güven aralığı şöyle olmaktadır:

::

    [105.20454606435501, 112.79545393564499]

Güven düzeyini yükseltirsek güven aralığının genişleyeceği açıktır. Örneğin bu problem için güven düzeyini %99 olarak
belirlemiş olalım:

.. code-block:: python

    import numpy as np
    from scipy.stats import norm

    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)

    lower_bound = norm.ppf(0.005, sample_mean, sampling_mean_std)
    upper_bound = norm.ppf(0.995,  sample_mean, sampling_mean_std)

    print(f'[{lower_bound}, {upper_bound}]')              # [104.01192800234102, 113.98807199765896]

Burada güven aralığının aşağıdaki gibi olduğunu göreceksiniz:

::

    [104.01192800234102, 113.98807199765896]

Gördüğünüz gibi aralık büyümüştür.

Aşağıdaki programda %95 güven düzeyi için güven aralığı hesaplanmıştır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm


    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)


    lower_bound = norm.ppf(0.025, sample_mean, sampling_mean_std)
    upper_bound = norm.ppf(0.975,  sample_mean, sampling_mean_std)

    print(f'[{lower_bound}, {upper_bound}]')      # [105.20454606435501, 112.79545393564499]

Aşağıdaki programda ise %99 güven düzeyi için güven aralığı elde edilmiştir.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm


    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)


    lower_bound = norm.ppf(0.005, sample_mean, sampling_mean_std)
    upper_bound = norm.ppf(0.995,  sample_mean, sampling_mean_std)

    print(f'{lower_bound}, {upper_bound}')      # 104.01192800234102, 113.98807199765896

Örnek Büyüklüğünün Güven Aralığına Etkisi
-----------------------------------------

Anımsanacağı gibi örnek ortalamalarına ilişkin dağılımın standart sapmasına *standart hata (standard error)*
deniliyordu. Örnek ortalamalarına ilişkin dağılımın standart sapması azaltılırsa (yani standart hata düşürülürse)
değerler ortalamaya yaklaşacağına göre güven aralıkları da daralacaktır. O halde anakütle ortalamasını tahmin ederken
büyük örnek seçmemiz güven aralıklarını daraltacaktır. Aşağıdaki örnekte yukarıdaki problemin 30'dan 100'e kadar beşer
artırımla örnek büyüklükleri için %99 güven düzeyinde güven aralıkları elde edilmiştir. Elde edilen aralıklar şöyledir:

::

    sample size: 30: [103.63241756884852, 114.36758243115148]
    sample size: 35: [104.03058429805395, 113.96941570194605]
    sample size: 40: [104.35153725771579, 113.64846274228421]
    sample size: 45: [104.61738729711709, 113.38261270288291]
    sample size: 50: [104.84228852695097, 113.15771147304903]
    sample size: 55: [105.03577765357056, 112.96422234642944]
    sample size: 60: [105.20454606435501, 112.79545393564499]
    sample size: 65: [105.3534458105975, 112.6465541894025]
    sample size: 70: [105.48609245861904, 112.51390754138096]
    sample size: 75: [105.60524279777148, 112.39475720222852]
    sample size: 80: [105.71304047283782, 112.28695952716218]
    sample size: 85: [105.81118086644236, 112.18881913355763]
    sample size: 90: [105.9010248384772, 112.0989751615228]
    sample size: 95: [105.98367907149301, 112.01632092850699]
    sample size: 100: [106.06005402318992, 111.93994597681008]

Buradan da gördüğünüz gibi örneği büyüttüğümüzde güven aralıkları daralmakta ve anakütle ortalaması daha iyi tahmin
edilmektedir. Örnek büyüklüğünün artırılması belli bir noktaya kadar aralığı iyi bir biçimde daraltıyorsa da belli bir
noktadan sonra bu daralma azalmaya başlamaktadır. Örneklerin elde edilmesinin belli bir çaba gerektirdiği durumda örnek
büyüklüğünün makul seçilmesi önemli olmaktadır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm


    population_std = 15
    sample_mean = 109


    for sample_size in range(30, 105, 5):
        sampling_mean_std = population_std / np.sqrt(sample_size)

        lower_bound = norm.ppf(0.025, sample_mean, sampling_mean_std)
        upper_bound = norm.ppf(0.975,  sample_mean, sampling_mean_std)

        print(f'sample size: {sample_size}: [{lower_bound}, {upper_bound}]')

Anımsanacağı gibi anakütle normal dağılmamışsa merkezi limit teoreminin yeterli bir biçimde uygulanabilmesi için
örneklerin büyük olması (tipik olarak >= 30) gerekiyordu. O halde güven aralıklarını oluştururken eğer anakütle normal
dağılmamışsa bizim örnekleri >= 30 olacak biçimde seçmemiz uygun olur.

Z Tablosu Yöntemiyle Güven Aralığı Hesabı
-----------------------------------------

Daha önceden de belirttiğimiz gibi eskiden bilgisayarların yoğun olarak kullanılmadığı zamanlarda hesaplamaları pratik
hale getirmek için ortalaması 0, standart sapması 1 olan *standart normal dağılım* tabloları kullanılıyordu. Bunlara Z
tablosu dendiğini, bu Z tablolarında belli bir Z değeri için (standart normal dağılımdaki X değerlerine de Z değerleri
dendiğini anımsayınız) kümülatif olasılıklar bulundurulmaktaydı. Tabii artık bilgisayarların bu kadar yoğun kullanıldığı
günümüzde okul sınavları dışında Z tablolarının kullanımı ortadan kalkmıştır. İşte bu eski devirlerde güven aralıkları
da bu Z tablolarına bakılarak oluşturuluyordu. Herhangi bir standart sapma ve ortalamaya ilişkin x değerinin Z değerine
aşağıdaki gibi dönüştürüldüğünü anımsayınız:

::

    Z = (x - μ) / σ

O halde buradaki X örneğin ortalaması, sigma ise örnek ortalamalarına ilişkin örneklem dağılımının standart sapması
olmak üzere Z tablosuna dayalı olarak güven aralıkları aşağıdaki gibi oluşturulabilir:

::

    x̄ ± Z · σₓ̄

Aşağıda bu yöntemle Z değerleri kullanılarak güven aralığının oluşturulmasına bir örnek verilmiştir.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm

    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)

    upper_bound = sample_mean + norm.ppf(0.975) * sampling_mean_std
    lower_bound = sample_mean - norm.ppf(0.975) * sampling_mean_std

    print(f'[{lower_bound}, {upper_bound}]')      # [105.20454606435501, 112.79545393564499]

interval Metoduyla Güven Aralığı Hesabı
---------------------------------------

Örnekten hareketle anakütle ortalamaları aslında tek hamlede norm nesnesinin ilişkin olduğu sınıfın interval metoduyla
da elde edilebilmektedir. interval metodunun parametrik yapısı şöyledir:

.. code-block:: python

    interval(confidence, loc=0, scale=1)

Metodun birinci parametresi olan confidence güven düzeyini belirtmektedir. Örneğin %95 güven düzeyi için bu parametre
0.95 girilmelidir. Metodun ikinci ve üçüncü parametreleri (loc ve scale parametreleri) örneğin ortalamasını ve örneklem
dağılımının standart sapmasını belirtir. Yani biz ikinci parametreye örnek ortalamasını, üçüncü parametreye de anakütle
standart sapmasından hareketle elde ettiğimiz örneklem standart sapmasını (sigma / kök(n)) girmeliyiz. Metot güven
aralığını belirten bir demetle geri döner. Demetin ilk elemanı alt sınır, ikinci elemanı üst sınır değerlerini
vermektedir.

Bu durumda yukarıdaki problemi interval metoduyla aşağıdaki gibi de çözebiliriz:

.. code-block:: python

    import numpy as np
    from scipy.stats import norm

    sample_size = 60
    population_std = 15
    sample_mean = 109
    sampling_mean_std = population_std / np.sqrt(sample_size)

    lower_bound, upper_bound = norm.interval(0.95, sample_mean, sampling_mean_std)
    print(f'{lower_bound}, {upper_bound}')

.. code-block:: python

    import numpy as np
    from scipy.stats import norm

    sample_size = 60
    population_std = 15
    sample_mean = 109

    sampling_mean_std = population_std / np.sqrt(sample_size)

    lower_bound = norm.ppf(0.025, sample_mean, sampling_mean_std)
    upper_bound = norm.ppf(0.975,  sample_mean, sampling_mean_std)

    print(f'{lower_bound}, {upper_bound}')

    lower_bound, upper_bound = norm.interval(0.95, sample_mean, sampling_mean_std)

    print(f'{lower_bound}, {upper_bound}')

Aşağıdaki örnekte ortalaması 100, standart sapması 15 olan normal dağılıma uygun rastgele 1,000,000 değer üretilmiştir.
Bu değerlerin anakütleyi oluşturduğu varsayılmıştır. Sonra bu anakütle içerisinden rastgele 60 elemanlık bir örnek elde
edilmiştir. Bu örneğe dayanılarak anakütle ortalaması norm nesnesinin interval metoduyla 0.95 güven düzeyiyle elde
edilip ekrana yazdırılmıştır.

.. code-block:: python

    import numpy as np
    from scipy.stats import norm


    POPULATION_SIZE = 1_000_000
    SAMPLE_SIZE = 60


    population = norm.rvs(100, 15, POPULATION_SIZE)


    population_mean = np.mean(population)
    population_std = np.std(population)


    print(f'population mean: {population_mean}')
    print(f'population std: {population_std}')


    sample = np.random.choice(population, SAMPLE_SIZE)
    sample_mean = np.mean(sample)
    sampling_mean_std = population_std / np.sqrt(SAMPLE_SIZE)


    print(f'sample mean: {sample_mean}')


    lower_bound, upper_bound = norm.interval(0.95, sample_mean, sampling_mean_std)
    print(f'[{lower_bound}, {upper_bound}]')

Anakütle Standart Sapması Bilinmediğinde Güven Aralığı (t Dağılımı)
-------------------------------------------------------------------

Biz yukarıdaki örneklerde güven aralıklarını oluştururken anakütle standart sapmasının bilindiğini varsaydık. Halbuki
genellikle anakütle ortalamasının bilinmediği durumda anakütle standart sapması da bilinmemektedir. Peki bu durumda
örnekten hareketle anakütle ortalamasının aralık tahmini nasıl yapılacaktır? İşte bu durumda çektiğimiz örneğin standart
sapması sanki anakütlenin standart sapmasıymış gibi işleme sokulmaktadır. Ancak dağılım olarak normal dağılım değil t
dağılımı kullanılmaktadır. Zaten William Gosset t dağılımını tamamen böyle bir problem üzerinde çalışırken
geliştirmiştir. Yani t dağılımı zaten *anakütle standart sapmasının bilinmediği durumda örneğin standart sapmasının
anakütle standart sapması olarak alınmasıyla* elde edilen bir dağılımdır.

t dağılımının serbestlik derecesi denilen bir değere sahip olduğunu anımsayınız. Serbestlik derecesi örnek büyüklüğünün
bir eksik değeridir. Ayrıca 30 serbestlik derecesinden sonra zaten t dağılımının normal dağılıma çok benzediğini de
belirtmiştik. Çektiğimiz örneğin standart sapmasını anakütle standart sapması olarak kullanırken örneğin standart
sapması N'e değil (N - 1)'e bölünerek hesaplanmalıdır. Burada bölmenin neden (N - 1)'e yapıldığının açıklaması biraz
karmaşıktır. Biz kursumuzda bu konu üzerinde durmayacağız. Ancak Internet'te bu konuyu açıklayan pek çok kaynak
bulunmaktadır. İstatistikte çekilen örneklerin standart sapmaları genellikle sigma sembolü ile değil s harfiyle
belirtilmektedir.

Anımsanacağı gibi pek çok kütüphanede standart sapma ya da varyans hesaplanırken kaça bölme yapılacağına *ddof (delta
degrees of freedom)* deniyordu. Standart sapma ya da varyans hesabı yapan fonksiyonların ddof parametreleri vardı.
(NumPy'da bu ddof parametreleri default 0 iken Pandas'da 1'dir.) Yani bu ddof parametresi (N - değer)'deki değeri
belirtmektedir. Örneğin ddof = 0 ise bölme N'e ddof = 1 ise bölme (N - 1)'e yapılmaktadır.

Örneğin anakütleden aşağıdaki gibi 35'lik bir örnek çekmiş olalım:

.. code-block:: python

    sample = np.array([101.93386212, 106.66664836, 127.72179427,  67.18904948, 87.1273706,
                        76.37932669,  87.99167058,  95.16206704, 101.78211828,  80.71674993,
                        126.3793041, 105.07860807, 98.4475209, 124.47749601,  82.79645255,
                        82.65166373, 92.17531189, 117.31491413, 105.75232982,  94.46720598,
                        100.3795159,  94.34234528,  86.78805744,  97.79039692, 81.77519378,
                        117.61282039, 109.08162784, 119.30896688, 98.3008706,  96.21075454,
                        100.52072909, 127.48794967, 100.96706301, 104.24326515, 101.49111644])

Anakütlenin standart sapmasının da bilinmediğini varsayalım. Bu değerlerden hareketle %95 güven düzeyinde güven
aralığını şöyle oluşturabiliriz:

.. code-block:: python

    import numpy as np
    from scipy.stats import t


    sample = np.array([101.93386212, 106.66664836, 127.72179427,  67.18904948, 87.1273706,
                    87.99167058,  95.16206704, 101.78211828,  80.71674993, 126.3793041, 105.07860807,
                    98.4475209, 124.47749601,  82.79645255,  82.65166373, 92.17531189, 117.31491413,
                    105.75232982,  94.46720598, 100.3795159,  94.34234528,  86.78805744, 97.79039692,
                    81.77519378, 117.61282039, 109.08162784, 119.30896688, 98.3008706,  96.21075454,
                    100.52072909, 127.48794967, 100.96706301, 104.24326515, 101.49111644])


    sample_mean = np.mean(sample)
    sample_std = np.std(sample, ddof=1)
    sampling_mean_std = sample_std / np.sqrt(len(sample))


    lower_bound = t.ppf(0.025, len(sample) - 1, sample_mean, sampling_mean_std)
    upper_bound = t.ppf(0.975, len(sample) - 1, sample_mean, sampling_mean_std)


    print(f'[{lower_bound}, {upper_bound}]')    # [94.81902512213665, 105.0959541612919]

Burada örneğin standart sapmasını hesaplarken ddof=1 kullandığımıza dikkat ediniz. Güven aralıkları normal dağılım
kullanılarak değil t dağılımı kullanılarak elde edilmiştir. t dağılımındaki serbestlik derecesinin (ppf fonksiyonunun
ikinci parametresi) örnek büyüklüğünün bir eksik değeri olarak alındığına dikkat ediniz.

Örneklem dağılımının standart sapmasına standart hata denildiğini anımsayınız. Aslında scipy.stats modülünde bu değeri
hesaplayan sem isimli bir fonksiyon da bulunmaktadır. Yukarıdaki örneğimizde bu standart hata değerini iki satırda
bulmuştuk:

.. code-block:: python

    sample_std = np.std(sample, ddof=1)
    sampling_mean_std = sample_std / np.sqrt(len(sample))

Bu işlem tek hamlede sem fonksiyonuyla da yapılabilmektedir:

.. code-block:: python

    sampling_mean_std = sem(sample)

30 serbestlik derecesinden sonra artık t dağılımının normal dağılımla örtüşmeye başladığını anımsayınız. Buradaki
örneğimizde örnek büyüklüğü 35'tir. Örnek büyüklüğü >= 30 durumunda t dağılımı ile normal dağılım birbirine çok
benzediği için aslında bu örnekte t dağılımı yerine normal dağılım kullanılsaydı da önemli bir fark oluşmayacaktı.
Eskiden bilgisayarların yoğun kullanılmadığı zamanlarda t dağılımı için de *t tabloları* kullanılıyordu. t tablolarında
her bir serbestlik derecesi için ayrı girişler bulunduruluyordu. Genellikle t tabloları çok büyük olmasın diye 30'a
kadar serbestlik derecesini içeriyordu. Dolayısıyla eskiden N >= 30 durumunda t tablosu yerine Z tablolarının
kullanılması çok yaygındı. Ancak günümüzde bu tür işlemleri bilgisayarlarla yaptığımız için N >= 30 durumunda da t
dağılımını kullanmak daha uygun olmaktadır.

.. code-block:: python

    import numpy as np
    from scipy.stats import t


    sample = np.array([101.93386212, 106.66664836, 127.72179427,  67.18904948, 87.1273706,
                   87.99167058,  95.16206704, 101.78211828,  80.71674993, 126.3793041, 105.07860807,
                   98.4475209, 124.47749601,  82.79645255,  82.65166373, 92.17531189, 117.31491413,
                   105.75232982,  94.46720598, 100.3795159,  94.34234528,  86.78805744, 97.79039692,
                   81.77519378, 117.61282039, 109.08162784, 119.30896688, 98.3008706,  96.21075454,
                   100.52072909, 127.48794967, 100.96706301, 104.24326515, 101.49111644])


    sample_mean = np.mean(sample)
    sample_std = np.std(sample, ddof=1)
    sampling_mean_std = sample_std / np.sqrt(len(sample))


    lower_bound = t.ppf(0.025, len(sample) - 1, sample_mean, sampling_mean_std)
    upper_bound = t.ppf(0.975, len(sample) - 1, sample_mean, sampling_mean_std)

    print(f'[{lower_bound}, {upper_bound}]')

Dosya Sistemi: Katı Bağlar ve Sembolik Bağlar
=============================================

Katı Bağ (Hard Link) Kavramı
----------------------------

Farklı dizin girişlerinin aynı inode numarasına sahip olması durumuna UNIX/Linux sistemlerinde *katı bağ (hard link)*
denilmektedir. Örneğin farklı dizinlerde (aynı dizinde de olabilir) aşağıdaki gibi iki giriş olsun:

.. list-table::
   :header-rows: 1
   :widths: 20 20

   * - İsim
     - Inode No
   * - ...
     - ...
   * - ``x.txt``
     - 34718
   * - ...
     - ...

İkinci dizindeki giriş ise şöyledir:

.. list-table::
   :header-rows: 1
   :widths: 20 20

   * - İsim
     - Inode No
   * - ...
     - ...
   * - ``y.txt``
     - 34718
   * - ...
     - ...

Burada her iki dizin girişinin de aynı inode elemanına sahip olduğuna dikkat ediniz. Dosyaya erişmek için gereken tüm
metadata bilgileri inode elemanının içerisinde olduğuna göre bu dosyaya ``x.txt`` yol ifadesiyle erişmekle ``y.txt`` yol
ifadesiyle erişmek arasında hiçbir farklılık yoktur. İşte ``x.txt`` ve ``y.txt`` dizin girişleri *katı bağ (hard link)*
oluşturmuştur. Tabii katı bağa sahip dizin girişleri ikiden fazla da olabilir.

link Fonksiyonu
---------------

Katı bağ oluşturmak için link isimli POSIX fonksiyonu kullanılmaktadır. Linux sistemlerinde bu POSIX fonksiyonu sys_link
isimli sistem fonksiyonunu çağırmaktadır. link fonksiyonunun prototipi şöyledir:

.. code-block:: c

    #include <unistd.h>

    int link(const char *oldpath, const char *newpath);

Fonksiyonun birinci parametresi katı bağı oluşturulacak dosyanın yol ifadesini, ikinci parametresi oluşturulacak olan
yeni katı bağın yol ifadesini belirtmektedir. Fonksiyon başarı durumunda 0 değerine, başarısızlık durumunda -1 değerine
geri dönmektedir. Örneğin:

.. code-block:: c

    if (link("x.txt", "y.txt") == -1)
        exit_sys("link");

link fonksiyonunun linkat isimli at'li bir versiyonu da vardır:

.. code-block:: c

    #include <unistd.h>

    int linkat(int olddirfd, const char *oldpath, int newdirfd, const char *newpath, int flags);

POSIX dosya fonksiyonlarının at'li versiyonlarının nasıl çalıştığı ileride ele alınmaktadır.

Kaynak dosya yoksa ya da hedef dosya varsa fonksiyon başarısız olmaktadır. Yukarıdaki işlemin başarılı olduğunu
varsayalım. Bu iki dosyanın *"ls -l"* ile bilgilerine baktığımızda aynı şeyleri görürüz:

.. code-block:: console

    $ ls -li x.txt y.txt
    6076082 -rw-r--r-- 2 kaan study 41 Haz 23 13:43 x.txt
    6076082 -rw-r--r-- 2 kaan study 41 Haz 23 13:43 y.txt

Burada dosyanın katı bağ sayacının (3'üncü sütun) 2 haline geldiğine dikkat ediniz. Buradaki 2 değeri aynı fiziksel
dosyayı gösteren iki farklı dizin girişinin bulunduğunu belirtmektedir.

Katı bağ oluşturma dosya sisteminin disk tarafındaki tasarımına da bağlıdır. Her dosya sistemi katı bağ oluşturulmasını
desteklemek zorunda değildir. Bu durumda link fonksiyonu başarısızlıkla geri dönecektir. Örneğin Microsoft'un FAT dosya
sistemleri katı bağları desteklememektedir.

Disk bölümleri arasında da katı bağ oluşturulamamaktadır. Çünkü her disk bölümünün (dosya sisteminin) inode tablosu
farklıdır. Farklı disk bölümlerinde aynı inode numaraları bulunabilmektedir. Yani inode numaraları sistem genelinde
değil disk bölümü (dosya sistemi) genelinde tektir. Farklı bir disk bölümündeki dosyanın farklı bir disk bölümüne katı
bağı oluşturulmak istendiğinde link fonksiyonu başarısız olur ve errno değeri EXDEV (*Invalid cross-device link*) olarak
set edilmektedir.

Kabuk üzerinde katı bağlar *ln* isimli kabuk komutuyla oluşturulmaktadır. Bu kabuk komutu *cp* gibi kullanılmaktadır.
Örneğin:

.. code-block:: console

    $ ln x.txt y.txt

Burada ``x.txt`` dosyasına ilişkin inode elemanıyla aynı inode elemanına referans eden yeni bir ``y.txt`` dosyası
oluşturulmaktadır.

Aşağıdaki program *"ln"* komutunun benzer işlevini yerine getirmektedir. Programı şöyle kullanabilirsiniz:

.. code-block:: console

    $ ./makelink x.txt y.txt

.. code-block:: c

    /* makelink.c */

    #include <stdio.h>
    #include <stdlib.h>
    #include <unistd.h>


    void exit_sys(const char *msg);


    int main(int argc, char *argv[])
    {
        if (argc != 3) {
            fprintf(stderr, "wrong number of arguments!");
            exit(EXIT_FAILURE);
        }

        if (link(argv[1], argv[2]) == -1)
            exit_sys("link");

        return 0;
    }


    void exit_sys(const char *msg)
    {
        perror(msg);
        exit(EXIT_FAILURE);
    }

Dizinlerin Katı Bağları
-----------------------

Dizinlerin katı bağlarının oluşturulması bazı sorunlara yol açabilmektedir. Yukarıda da belirttiğimiz gibi bu tür
durumlarda dizin ağacını dolaşan programlar sonsuz döngüye girebilmektedir. Bu nedenle bazı UNIX/Linux sistemlerinde
dizinlerin katı bağlarının oluşturulması engellenmiştir. Bazı sistemlerde ise dizinlerin katı bağları ancak *root*
kullanıcısı tarafından (yani *sudo* ile) oluşturulabilmektedir. Linux dizinler üzerinde katı bağ oluşturulmasına izin
vermemektedir. Linux'ta dizinler üzerinde katı bağ oluşturulmak istendiğinde link fonksiyonu başarısız olur ve errno
değeri EPERM (*Permission denied*) ile set edilir. POSIX standardı bu konuda özetle şunu belirtmektedir: verilen yol bir
dizini gösteriyorsa, sürecin gerekli ayrıcalıklara sahip olmadığı ya da ilgili sistemin dizinler üzerinde link()
kullanımını desteklemediği durumlarda link() çağrısı başarısız olur.

Bir dizin yaratıldığında içerisinde ``.`` ve ``..`` isimli iki dizin girişi de yaratılmaktadır. ``.`` girişi bulunulan
dizini, ``..`` dizini ise üst dizini belirtmektedir. UNIX/Linux sistemlerinde başı ``.`` ile başlayan dosyalar *"ls"*
komutunda default durumda görüntülenmemektedir. Bu girişleri görebilmek için *"ls"* komutunda *-a* seçeneğinin
kullanılması gerekir. Örneğin:

.. code-block:: console

    $ mkdir xxx
    $ ls xxx
    $ ls -a xxx
    .  ..

İşte yeni bir dizin yaratıldığında oluşturulan ``.`` girişi aslında içinde bulunulan dizine bir katı bağ girişidir. Bu
nedenle bir dizin yaratıldığında üst dizinin katı bağ sayacı 1 artırılmaktadır. Şimdi ``xxx`` dizinini sıfırdan yeniden
yaratıp *"ls -l"* ile durumuna bakalım:

.. code-block:: console

    $ mkdir xxx
    $ ls -ld xxx
    drwxr-xr-x 2 kaan study 4096 Tem  9 13:41 xxx

Görüldüğü gibi ``xxx`` dizini yaratıldığında katı bağ sayacı 2 durumundadır. Çünkü onun içerisindeki ``.`` dizini üst
dizine katı bağ oluşturmaktadır. Bunu şöyle ispatlayabiliriz:

.. code-block:: console

    $ mkdir xxx
    $ ls -ldai xxx xxx/.
    6335620 drwxr-xr-x 2 kaan study 4096 Tem  9 13:41 xxx
    6335620 drwxr-xr-x 2 kaan study 4096 Tem  9 13:41 xxx/.

Tabii siz şimdi *hani Linux'ta dizinlere katı bağ oluşturulamıyordu* diye sorabilirsiniz. İşte işletim sistemi bu ``.``
ve ``..`` dizinleri için istisnai olarak katı bağ oluşturmaktadır.

Bir dizinin içerisinde başka bir dizin yarattığımızda yarattığımız dizindeki ``..`` girişi üst dizine katı bağ
belirttiği için üst dizinin katı bağ sayacı da artırılmaktadır. O halde dizin içerisinde yaratılan her dizin üst dizinin
katı bağ sayacını da 1 artırmaktadır. ``xxx`` dizinini silerek yeniden şu denemeyi yapalım:

.. code-block:: console

    $ mkdir xxx
    $ ls -ld xxx
    drwxr-xr-x 2 kaan study 4096 Tem  9 13:53 xxx
    $ mkdir xxx/yyy
    $ ls -ld xxx
    drwxr-xr-x 3 kaan study 4096 Tem  9 13:53 xxx
    $ mkdir xxx/zzz
    $ ls -ld xxx
    drwxr-xr-x 4 kaan study 4096 Tem  9 13:54 xxx
    $ ls -ldai xxx xxx/yyy/.. xxx/zzz/..
    6335620 drwxr-xr-x 4 kaan study 4096 Tem  9 13:54 xxx
    6335620 drwxr-xr-x 4 kaan study 4096 Tem  9 13:54 xxx/yyy/..
    6335620 drwxr-xr-x 4 kaan study 4096 Tem  9 13:54 xxx/zzz/..

Buradaki deneyden çıkan sonuçlara dikkat ediniz:

- Dizin ilk yaratıldığında dizinin kendisine ilişkin katı bağ sayacı ``.`` girişinden dolayı 2 olmaktadır.
- Dizin içerisinde her yeni dizin yaratıldığında o dizindeki ``..`` girişinden dolayı üst dizinin katı bağ sayacı 1
  artırılmaktadır.

Linux sistemleri ``.`` ve ``..`` dizinleri için istisna olarak katı bağ oluşturmaktadır ancak kullanıcılara dizinlere
katı bağ oluşturma olanağını vermemektedir.

Katı Bağın Silinmesi
--------------------

Aynı dosyaya referans eden ``x.txt`` ve ``y.txt`` biçiminde iki katı bağ girişi olsun. Biz bunlardan birini silersek ne
olur? Bu durumda eğer dosyanın kendisi silinirse diğer dizin girişi geçersiz duruma gelir. İşte işletim sistemi inode
elemanının içerisinde (stat yapısının st_nlink elemanı) ilgili dosyaya referans eden kaç katı bağın bulunduğu bilgisini
tutmaktadır. Bir dosyanın katı bağı silinmek istendiğinde işletim sistemi dizin girişini siler, dosyanın inode
elemanındaki katı bağ sayacını 1 eksiltir. Katı bağ sayacı 0'a düştüğünde diskten dosyayı gerçekten siler. Örneğin:

.. code-block:: console

    $ ls -li x.txt y.txt
    6076082 -rw-r--r-- 2 kaan study 41 Haz 23 13:43 x.txt
    6076082 -rw-r--r-- 2 kaan study 41 Haz 23 13:43 y.txt

Burada ``x.txt`` ve ``y.txt`` aynı dosyaya referans eden katı bağlardır. Bunlardan birini silelim:

.. code-block:: console

    $ rm x.txt

Artık ``x.txt`` girişi yok edilmiştir. Ancak ``y.txt`` girişi durmaktadır:

.. code-block:: console

    $ ls -li y.txt
    6076082 -rw-r--r-- 1 kaan study 41 Haz 23 13:43 y.txt

Dosyanın katı bağ sayacının 1'e düştüğüne dikkat ediniz. Artık biz bu ``y.txt`` dosyasını da sildiğimizde katı bağ
sayacı 0'a düştüğü için dosya da gerçekten silinecektir.

Sembolik Bağ (Symbolic Link) Kavramı
------------------------------------

UNIX/Linux sistemlerinde *sembolik bağ (symbolic link)* ya da *gevşek bağ (soft link)* denilen bir bağ türü de vardır.
Sembolik bağlar Windows sistemlerindeki *kısa yol dosyalarına* benzemektedir. UNIX/Linux sistemlerinde sembolik bağlar
katı bağlardan daha yaygın kullanılmaktadır. Sembolik bağ *başka bir dosyaya referans eden dosya* anlamına gelmektedir.
Sembolik bağın hangi dosyaya referans ettiği sembolik bağ dosyasının diskteki inode elemanında tutulmaktadır.
Anımsayacağınız gibi stat fonksiyonlarıyla dosya bilgileri elde edildiğinde dosyanın sembolik bağ dosyası olup olmadığı
bilgisi stat yapısının st_mode elemanında kodlanmış olarak bulunuyordu. Biz de dosyanın sembolik bağ dosyası olup
olmadığını S_IFLNK makrosuyla anlayabiliyorduk. Örneğin ``y.txt`` dosyası ``x.txt`` dosyasına sembolik bağ yapılmış
olsun. Biz bu durumu şöyle temsil edebiliriz:

::

    y.txt -> x.txt

Bazı POSIX fonksiyonları sembolik bağ dosyasına ilişkin bir yol ifadesi ile karşılaştığında sembolik bağı izleyerek
sembolik bağın hedefine ilişkin dosyayı tespit edip onun üzerinde işlem yapmaktadır. Yukarıdaki örneğimizde biz
``y.txt`` dosyasını open fonksiyonuyla açmış olalım:

.. code-block:: c

    fd = open("y.txt", O_RDONLY);

Burada işletim sistemi ``y.txt`` dosyasının bir sembolik bağ dosyası olduğunu anlar ve onun referans ettiği dosyayı
tespit eder ve gerçekte o dosyayı açmaya çalışır. Buna sembolik bağın izlenmesi de denilmektedir. Yukarıdaki open
işleminde aslında open fonksiyonu ``y.txt`` sembolik bağ dosyasını değil ``x.txt`` dosyasını açmaya çalışacaktır.
Sembolik bağların kullanım amacı olarak katı bağlara oldukça benzediğine dikkat ediniz. Yukarıdaki örneğimizde biz
``y.txt`` dosyası üzerinde işlem yapmak istediğimizde sistem aslında onun referans ettiği ``x.txt`` dosyası üzerinde
işlem yapmaktadır.

Her POSIX fonksiyonu sembolik bağları izlememektedir. Örneğin biz bir sembolik bağ dosyasını unlink fonksiyonuyla ya da
komut satırında *rm* komutuyla silmek istediğimizde onun referans ettiği dosya değil sembolik bağ dosyasının kendisi
silinmektedir. (Eğer dosya silmekte kullanılan unlink fonksiyonu sembolik bağı izleseydi yukarıdaki örneğimizde biz
``y.txt`` dosyasını silmeye çalıştığımızda ``x.txt`` dosyası silinirdi.) Örneğin stat fonksiyonu sembolik bağı izlediği
halde lstat fonksiyonu sembolik bağı izlememektedir. Yani biz stat fonksiyonuna bir sembolik bağ dosyası verdiğimizde
stat fonksiyonu sembolik bağı izleyerek bize onun referans ettiği dosyanın bilgilerini vermektedir. Ancak lstat
fonksiyonu sembolik bağı izlememekte, sembolik bağ dosyasının kendisine ilişkin dosya bilgilerini vermektedir.

symlink Fonksiyonu
------------------

Sembolik bağ dosyaları symlink isimli POSIX fonksiyonuyla yaratılmaktadır. Linux sistemlerinde bu fonksiyon sys_symlink
isimli sistem fonksiyonunu çağırmaktadır. symlink fonksiyonunun prototipi şöyledir:

.. code-block:: c

    #include <unistd.h>

    int symlink(const char *target, const char *linkpath);

Fonksiyonun birinci parametresi gerçek dosyanın yol ifadesini, ikinci parametresi ise oluşturulacak sembolik bağlantı
dosyasının yol ifadesini belirtmektedir. Fonksiyon başarı durumunda 0 değerine başarısızlık durumunda -1 değerine geri
dönmektedir. symlink fonksiyonunun symlinkat isimli at'li bir biçimi de vardır:

.. code-block:: c

    #include <unistd.h>

    int symlinkat(const char *target, int newdirfd, const char *linkpath);

Biz POSIX fonksiyonlarının at'li biçimleri hakkında izleyen bölümlerde bilgiler vereceğiz.

Örneğin:

.. code-block:: c

    if (symlink("x.txt", "y.txt") == -1)
        exit_sys("symlink");

Burada ``y.txt`` -> ``x.txt`` durumu oluşturulmaktadır. Bu işlemden sonra her iki dosyayı da *"ls -li"* komutuyla
görüntülediğimizde aşağıdakine benzer bir çıktı elde ederiz:

.. code-block:: console

    $ ls -li x.txt y.txt
    6076082 -rw-r--r-- 1 kaan study 38 Tem  9 11:39 x.txt
    6076114 lrwxrwxrwx 1 kaan study  5 Tem  9 11:39 y.txt -> x.txt

Burada dosyaların inode numaralarının farklı olduğuna dikkat ediniz. Çünkü sembolik bağ dosyaları ayrı bir dosya
gibidir. Onun ayrı bir inode elemanı vardır. Ancak inode elemanında o sembolik bağ dosyasının gerçekte hangi dosyaya
referans ettiği bilgisi de tutulmaktadır. *"ls -l"* komutunda sembolik bağlar ok işaretiyle gösterilmektedir. Sembolik
bağ dosyalarının tür belirten karakterinin 'l' olduğuna da dikkat ediniz. Sembolik bağlantı dosyalarının kendi erişim
hakları her zaman ``rwxrwxrwx`` biçiminde oluşturulmaktadır. Linux'ta sembolik bağlantı dosyasının kendisine ilişkin
erişim hakları herhangi bir biçimde değiştirilememektedir. Ancak örneğin BSD sistemleri buna izin vermektedir; POSIX
standartları ise bu konuda açık bir belirlemede bulunmamıştır (unspecified).

symlink fonksiyonunda kaynak dosyanın var olması gerekmez. Bu durumu izleyen paragraflarda açıklayacağız.

Aşağıda bir dosyanın sembolik bağlantısını oluşturan bir program örneği verilmiştir. Programı şöyle deneyebilirsiniz:

.. code-block:: console

    ./makesymlink x.txt y.txt

.. code-block:: c

    /* makesymlink.c */

    #include <stdio.h>
    #include <stdlib.h>
    #include <unistd.h>


    void exit_sys(const char *msg);


    int main(int argc, char *argv[])
    {
        if (argc != 3) {
            fprintf(stderr, "wrong number of arguments!");
            exit(EXIT_FAILURE);
        }

        if (symlink(argv[1], argv[2]) == -1)
            exit_sys("symlink");

        printf("Ok\n");

        return 0;
    }


    void exit_sys(const char *msg)
    {
        perror(msg);
        exit(EXIT_FAILURE);
    }

Sembolik Bağların Komut Satırından Oluşturulması ve Dangling Link
-----------------------------------------------------------------

Sembolik bağ dosyası komut satırından yine *ln* komutuyla oluşturulmaktadır. Ancak *ln* komutuna *-s* seçeneği de
girilmelidir. Örneğin:

.. code-block:: console

    $ ln -s x.txt y.txt

    $ ls -li x.txt y.txt
    6076082 -rw-r--r-- 1 kaan study 38 Tem  9 11:39 x.txt
    6076114 lrwxrwxrwx 1 kaan study  5 Tem  9 11:48 y.txt -> x.txt

Sembolik bağ oluştururken kaynak dosyanın var olması gerekmemektedir.

Peki bir sembolik bağ dosyasının referans ettiği dosya silinirse ne olur? Yukarıdaki örneğimizde ``x.txt`` dosyasını
silelim:

.. code-block:: console

    $ rm x.txt

.. code-block:: console

    $ ls -li y.txt
    6076114 lrwxrwxrwx 1 kaan study 5 Tem  9 11:48 y.txt -> x.txt

Görüldüğü gibi sembolik bağ yine var olmaya devam etmektedir. *"ls -l"* komutunda bu tuhaf durum *siyah üstüne kırmızı*
renk ile temsil edilmektedir. (Yani komutun çıktısındaki y.txt -> x.txt kısmı siyah üzerine kırmızı renkle
gösterilmektedir.)

Peki biz bu durumda ``y.txt`` dosyasını open fonksiyonuyla açmak istediğimizde (ya da örneğin *cat* komutuyla onun içini
görmek istediğimizde) ne olacaktır? İşte open fonksiyonu sembolik bağ dosyasının referans ettiği dosyanın olmadığını
anlamakta ve sanki olmayan bir dosya açılmak istenmiş gibi davranmaktadır. Yani bu durumda open fonksiyonu başarısız
olup -1 değerine geri döner ve errno değişkeni ENOENT (*No such file or directory*) değeriyle set edilir.

Sembolik bağ dosyasının referans ettiği dosyanın silinmiş olma durumuna İngilizce *dangling link* denilmektedir.
Dangling duruma gelmiş bir sembolik bağ dosyasının referans ettiği dosya yeniden yaratılırsa artık dangling durumu
ortadan kaldırılmış olur.

Bir sembolik bağ dosyasına da sembolik bağ oluşturulabilmektedir. Örneğin aşağıdaki gibi bir durum söz konusu olabilir:

::

    z.txt -> y.txt -> x.txt

Elimizde yalnızca ``x.txt`` dosyası olsun. Biz yukarıdaki durumu şöyle oluşturabiliriz:

.. code-block:: console

    $ ln -s x.txt y.txt
    $ ln -s y.txt z.txt
    $ ls -li x.txt y.txt z.txt
    6076082 -rw-r--r-- 1 kaan study 17 Tem  9 11:58 x.txt
    6076114 lrwxrwxrwx 1 kaan study  5 Tem  9 12:23 y.txt -> x.txt
    6076115 lrwxrwxrwx 1 kaan study  5 Tem  9 12:23 z.txt -> y.txt

Peki biz böylesi bir durumda ``z.txt`` dosyasını open fonksiyonuyla açmak istersek ne olur? İşte open fonksiyonu
sembolik bağları izler ve bunun nihai hedefindeki dosyayı tespit eder ve onu açmaya çalışır. Örneğimizde ``x.txt``
dosyası açılacaktır.

Sembolik bağ dosyaları döngüsel hale de gelebilir. Örneğin ``y.txt`` sembolik bağ dosyası ``z.txt`` sembolik bağ
dosyasını, ``z.txt`` sembolik bağ dosyası ise yeniden ``y.txt`` sembolik bağ dosyasını gösterir duruma getirilebilir. Bu
durumu yapay bir biçimde oluşturalım:

.. code-block:: console

    $ ln -s y.txt z.txt
    $ ln -s z.txt y.txt

Burada önce x.txt -> y.txt durumu sonra da y.txt -> z.txt durumu oluşturulmuştur. Sembolik bağ oluşturmak için kaynak
dosyanın var olmasının gerekmediğini anımsayınız. Durum şöyledir:

.. code-block:: console

    $ ls -li y.txt z.txt
    6076114 lrwxrwxrwx 1 kaan study 5 Tem  9 12:33 y.txt -> z.txt
    6076082 lrwxrwxrwx 1 kaan study 5 Tem  9 12:33 z.txt -> y.txt

Peki bu durumda open fonksiyonuyla ``y.txt`` ya da ``z.txt`` dosyasını açmak istersek ya da örneğin *cat* ile bu
dosyaları görüntülemek istersek ne olur? İşte open fonksiyonu belli bir kademe sembolik bağları izlemekte, eğer hedef
dosya hala bulunamadıysa errno değişkenini ELOOP (*Too many levels of symbolic links*) değeri ile set edip işlemi
başarısızlıkla sonlandırmaktadır.

readlink Fonksiyonu
-------------------

Biz lstat fonksiyonuyla bir dosyanın bilgilerini elde ettiğimizde o dosyanın bir sembolik bağ dosyası olup olmadığını
anlayabiliyorduk. Ancak o sembolik bağ dosyasının hangi dosyaya referans ettiğini lstat fonksiyonu bize vermemektedir.
İşte readlink isimli POSIX fonksiyonu bu işi yapmaktadır. Fonksiyonun prototipi şöyledir:

.. code-block:: c

    #include <unistd.h>

    ssize_t readlink(const char *path, char *buf, size_t bufsize);

Fonksiyonun birinci parametresi sembolik bağ dosyasının yol ifadesini, ikinci ve üçüncü parametreleri de sırasıyla
sembolik bağ dosyasının referans ettiği dosyanın yol ifadesinin yerleştirileceği yerin adresini ve uzunluğu almaktadır.
Bu alan küçük ise fonksiyon başarısız olmaz ancak yol ifadesinin son kısmı budanır. Fonksiyon verdiğimiz adrese
yerleştirdiği karakter sayısına geri dönmektedir. Fonksiyon (diğer fonksiyonların aksine) null karakteri dizinin sonuna
yerleştirmez. Bu durumda programcı referans edilen yol ifadesine erişirken dikkat etmelidir.

Fonksiyon başarı durumunda yerleştirilen karakter sayısına, başarısızlık durumunda -1 değerine geri dönmektedir.

readlink fonksiyonu sembolik bağ dosyasının içerisindeki hedefi verir. Yani fonksiyonun amacı sembolik bağı izlemek
değildir. Dolayısıyla readlink *kopuk (dangling)* sembolik bağlarda başarısız olmaz.

readlink fonksiyonunun readlinkat isminde at'li bir biçimi de vardır:

.. code-block:: c

    #include <unistd.h>

    int readlinkat(int dirfd, const char *pathname, char *buf, size_t bufsiz);

Biz POSIX dosya fonksiyonlarının at'li biçimlerini ileride ele alacağız.

readlink fonksiyonu kullanılarak yazılmış olan readlink isimli bir kabuk komutu da bulunmaktadır. Örneğin:

.. code-block:: console

    $ readlink x.txt
    test.txt

Aşağıda readlink fonksiyonunun kullanımına bir örnek verilmiştir. readlink fonksiyonunun null karakteri diziye
yerleştirmediğine dikkat ediniz. Sonunda null karakter olmayan result uzunlukta bir yazının printf ile bastırılması
şöyle yapılabilir:

.. code-block:: c

    printf("%.*s\n", result, buf);

printf *"%.10s"* gibi bir format karakterlerinde yazıyı null karakter görene kadar değil n karakter yazdırmaktadır.
(Örneğimizde 10). Tabii biz burada istersek null karakteri dizinin sonuna yerleştirip onu %s ile de yazdırabiliriz.
Ancak bu durumda da dizi uzunluğunun yeterli olduğuna dikkat etmemiz gerekir. Örneğin:

.. code-block:: c

    char buf[4096];
    /* ... */

    if ((result = readlink(argv[1], buf, 4096)) == -1)
        exit_sys("readlink");

    if (result < 4096) {         /* alternatifi -> printf("%.*s\n", (int)result, buf); */
        buf[result] = '\0';
        puts(buf);
    }
    else
        fprintf(stderr, "path truncated!...\n");

Bu örnekte biz yol ifadesinin yerleştirileceği diziyi 4096 eleman uzunluğunda açtık. Linux sistemlerinde x86 ve x64
mimarilerinde (genel olarak sayfa uzunluğunun 4K olduğu mimarilerde) yol ifadeleri en fazla null karakter dahil 4096
karakter olabilmektedir. Ancak diğer mimarilerde ve POSIX genelinde böyle bir zorunluluk yoktur. Bu tür durumlarda
tavsiye edilen yöntem diziyi büyütüp fonksiyonu başarılı olana kadar tekrar tekrar çağırmaktır. Ancak bir yol ifadesinin
4096 karakterden büyük olması zaten çok çok uç bir noktadır. (O sistemdeki maksimum yol ifadesi uzunluğu <limits.h>
dosyası içerisindeki PATH_MAX sembolik sabitiyle belirtilmektedir. Ancak maalesef bu sembolik sabitin define edilmiş
olması da zorunlu değildir.) Yol ifadelerinin null karakter dahil olmak üzere uzunluğu sistemin izin verdiği uzunluktan
daha büyük olursa (Linux'ta tipik olarak 4096) yol ifadesi alan fonksiyonlar başarısız olmakta ve errno değişkeni
ENAMETOOLONG değeri ile set edilmektedir. Bu konunun biraz ayrıntıları olduğu için konu bir başlık altında ileride ele
alınacaktır.

.. code-block:: c

    #include <stdio.h>
    #include <stdlib.h>
    #include <stdint.h>
    #include <unistd.h>


    void exit_sys(const char *msg);


    int main(int argc, char *argv[])
    {
        char buf[4096];
        ssize_t result;

        if (argc != 2) {
            fprintf(stderr, "wrong number of arguments!...\n");
            exit(EXIT_FAILURE);
        }

        if ((result = readlink(argv[1], buf, 4096)) == -1)
            exit_sys("readlink");

        printf("result = %jd\n", (intmax_t)result);

        if (result < 4096) {
            buf[result] = '\0';        /* alternatifi -> printf("%.*s\n", (int)result, buf); */
            puts(buf);
        }
        else
            fprintf(stderr, "path maybe truncated!...\n");

        return 0;
    }


    void exit_sys(const char *msg)
    {
        perror(msg);
        exit(EXIT_FAILURE);
    }

Eksik Veriler (Missing Data)
============================

Eksik Verilerin Tespiti ve Raporlanması
---------------------------------------

*Melbourne Housing Snapshot (MHS)* veri kümesinin eksik veri bakımından incelenmesi ve eksik verilerin rapor edilmesi
aşağıdaki gibi yapılabilir. Veri kümesini aşağıdaki sayfadan indirebilirsiniz:

https://www.kaggle.com/datasets/dansbecker/melbourne-housing-snapshot?resource=download

.. code-block:: python

    import pandas as pd

    df = pd.read_csv('melb_data.csv')

    missing_columns = [colname for colname in df.columns if df[colname].isna().any()]
    print(f'Eksik verilen bulunduğu sütunlar: {missing_columns}', end='\n\n')

    missing_column_dist = df.isna().sum()
    print('Eksik verilerin sütunlara göre dağılımı:')
    print(missing_column_dist, end='\n\n')

    missing_total = df.isna().sum().sum()
    print(f'Eksik verilen toplam sayısı: {missing_total}')

    missing_ratio = missing_total / df.size
    print(f'Eksik verilen oranı: {missing_ratio}')

    missing_rows = df.isna().any(axis=1).sum()
    print(f'Eksik veri bulunan satırların sayısı: {missing_rows}')

    missing_rows_ratio = missing_rows / len(df)
    print(f'Eksik veri bulunan satırların oranı: {missing_rows_ratio}')

Bu program çalıştırıldığında aşağıdaki gibi bir çıktı elde edilecektir:

.. code-block:: text

    Eksik verilen bulunduğu sütunlar: ['Car', 'BuildingArea', 'YearBuilt', 'CouncilArea']

    Eksik verilerin sütunlara göre dağılımı:
    Suburb              0
    Address             0
    Rooms               0
    Type                0
    Price               0
    Method              0
    SellerG             0
    Date                0
    Distance            0
    Postcode            0
    Bedroom2            0
    Bathroom            0
    Car                62
    Landsize            0
    BuildingArea     6450
    YearBuilt        5375
    CouncilArea      1369
    Lattitude           0
    Longtitude          0
    Regionname          0
    Propertycount       0
    dtype: int64

    Eksik verilen toplam sayısı: 13256
    Eksik verilen oranı: 0.04648292306613367
    Eksik veri bulunan satırların sayısı: 7384
    Eksik veri bulunan satırların oranı: 0.543740795287187

Eksik Verilerin Atılması (dropna)
---------------------------------

Eksik verileri DataFrame nesnesinden silmek için DataFrame sınıfının dropna metodu kullanılabilir. Bu metotta axis
parametresinin default değeri 0'dır. Yani default durumda satırlar atılmaktadır. Ancak axis=1 argümanıyla sütunların da
atılmasını sağlayabiliriz. Metot bize eksik verilerin atıldığı yeni bir DataFrame nesnesi vermektedir. Ancak metodun
inplace parametresi True yapılırsa nesne üzerinde atım yapılmaktadır.

Veri kümesinde çok fazla eksik veri içeren satır bulunuyorsa eksik verilerin bulunduğu satırların atılması önemli bir
veri kaybına yol açabilmektedir. Eksik verilerin bulunduğu satırların atılması bazen veri kümesini yanlı hale de
getirebilir. (Örneğin veri kümesi anket yöntemiyle elde ediliyor olsun. Kadınların yaşlarını söylememesi Türk kültüründe
yaygın bir davranıştır. Böyle bir veri kümesinde eksik verilerin bulunduğu satırlar atılırsa geri kalan satırların çoğu
erkeklere ilişkin olabilir.) İşte bu tür durumlarda eksik verilerin bulunduğu satırları atmak yerine eksik değerleri
başka değerlerle doldurmaya çalışmak (imputation) daha uygun olabilmektedir.

Aşağıda *Melbourne Housing Snapshot (MHS)* veri kümesinde eksik verilerin bulunduğu satır ve sütunların atılmasına bir
örnek verilmiştir.

.. code-block:: python

    import pandas as pd

    df = pd.read_csv('melb_data.csv')
    print(f'Veri kümesinin boyutu: {df.shape}')

    df_deleted_rows = df.dropna(axis=0)
    print(f'Satır atma sonucundaki yeni boyut: {df_deleted_rows.shape}')

    df_deleted_cols = df.dropna(axis=1)
    print(f'Sütun atma sonucundaki yeni boyut: {df_deleted_cols.shape}')

İmputation (Doldurma) Stratejileri
----------------------------------

Eksik verilerin yerine başka değerlerin yerleştirilmesi işlemine İngilizce *imputation* denildiğini söylemiştik. Biz
İngilizce *imputation* sözcüğü için Türkçe *doldurma* sözcüğünü de kullanacağız. Kullanılan tipik imputation
stratejileri şunlardır:

- Sütun sayısal ise eksik verilerin sütun ortalaması ile doldurulması
- Sütun kategorik ya da sırasal ise eksik verilerin mod değeri ile doldurulması
- Sütunlarda uç değerler varsa eksik değerlerin medyan değeri ile doldurulması
- Eksik verilerin yerine belli aralıkta ya da dağılımda rastgele değer yerleştirme yöntemi
- Eksik verilerin zaman serileri biçimindeki veri kümelerinde önceki ya da sonraki sütun değerleriyle doldurulması
- Eksik değerlerin regresyonla tahmin edilerek doldurulması
- Eksik değerlerin k-NN (K-Nearest Neighbours) yöntemi ile doldurulması

En çok uygulanan yöntem basitliği nedeniyle sütun ortalaması, sütun modu ya da sütun medyanı ile doldurma yöntemidir.

MHS Veri Kümesinde İmputation Uygulaması
----------------------------------------

Şimdi imputation işlemine MHS veri kümesi üzerinde örnek verelim. Bu veri kümesinde eksik veriler şu sütunlarda
bulunmaktaydı: Car, BuildingArea, YearBuilt, CouncilArea. Imputation işlemi için bu sütunların incelenmesi gerekir. Car
sütunu ev için ayrılan otopark alanının kaç arabayı içerdiğini belirtmektedir. Bu sütunda ayrık küçük tamsayı değerler
vardır. Burada imputation için sütun ortalaması kullanılabilir. Ancak bunların yuvarlanması daha uygun olabilir. Bu
işlem şöyle yapılabilir:

.. code-block:: python

    impute_val = df['Car'].mean().round()
    df['Car'] = df['Car'].fillna(impute_val)    # eşdeğeri df['Car'].fillna(impute_val, inplace=True)

DataFrame ve Series sınıflarının fillna metotları eksik verileri belli bir değerle doldurmak için kullanılmaktadır. Bu
metotta inplace parametresi True yapılırsa zaten doldurma doğrudan DataFrame ya da Series nesnesi güncellenecek biçimde
yapılmaktadır.

Eksik veri içeren diğer bir sütun da BuildingArea sütunudur. Bu sütun evin metrekare cinsinden büyüklüğünü
belirtmektedir. Eksik değerleri ortalamanın yuvarlanmış haliyle doldurabiliriz:

.. code-block:: python

    impute_val = df['BuildingArea'].mean().round()
    df['BuildingArea'] = df['BuildingArea'].fillna(impute_val)
    # eşdeğeri df['BuildingArea'].fillna(impute_val, inplace=True)

Veri kümesinin YearBuilt sütunu binanın yapım yılını belirtmektedir. Bu tür tarih bilgileri ya da yıl bilgileri hangi
ölçeğe sahiptir? Aslında bu tür bilgilerin ölçeklerini belirleme amaca da bağlıdır. Yıl bilgisi *kategorik*, *sıralı* ya
da aralıklı ölçek olarak değerlendirilebilir. Ancak genellikle bu tür yıl bilgilerinin *sıralı (ordinal)*
değerlendirilmesi daha uygun olabilmektedir. O halde biz bu sütunun ortalama değeri olarak medyan işlemi
uygulayabiliriz:

.. code-block:: python

    impute_val = df['YearBuilt'].median()
    df['YearBuilt'] = df['YearBuilt'].fillna(impute_val)
    # eşdeğeri df['YearBuilt'].fillna(impute_val, inplace=True)

Eksik veri içeren CouncilArea binanın içinde bulunduğu bölgeyi belirtmektedir. Dolayısıyla kategorik bir sütundur. O
halde mod işlemi ile *imputation* uygulayabiliriz:

.. code-block:: python

    impute_val = df['CouncilArea'].mode()
    df['CouncilArea'] = df['CouncilArea'].fillna(impute_val[0])
    # eşdeğeri df['CouncilArea'].fillna(impute_val, inplace=True)

Pandas'taki DataFrame ve Series sınıflarının mode metotları sonucu Series nesnesi biçiminde vermektedir. (Aynı miktarda
yinelenen birden fazla değer olabileceği için bu değerlerin hepsinin verilmesi tercih edilmiştir.) Dolayısıyla biz bu
Series nesnesinin ilk elemanını alarak mod değeri elde ettik.

Aşağıda MHS veri kümesinde uygulanan imputation işlemini bir bütün olarak veriyoruz.

.. code-block:: python

    import pandas as pd

    df = pd.read_csv('melb_data.csv')

    impute_val = df['Car'].mean().round()
    df['Car'] = df['Car'].fillna(impute_val)    # eşdeğeri df['Car'].fillna(impute_val, inplace=True)

    impute_val = df['BuildingArea'].mean().round()
    df['BuildingArea'] = df['BuildingArea'].fillna(impute_val)
    # eşdeğeri df['BuildingArea'].fillna(impute_val, inplace=True)

    impute_val = df['YearBuilt'].median()
    df['YearBuilt'] = df['YearBuilt'].fillna(impute_val)
    # eşdeğeri df['YearBuilt'].fillna(impute_val, inplace=True)

    impute_val = df['CouncilArea'].mode()
    df['CouncilArea'] = df['CouncilArea'].fillna(impute_val[0])
    # eşdeğeri df['CouncilArea'].fillna(impute_val, inplace=True)

İmputation Yöntemlerinin Sınırlılıkları
---------------------------------------

Biz yukarıda ortalama, medyan ve mod değerleriyle imputation uyguladık. Gerçekten de en çok uygulanan imputation
yöntemleri bunlardır. Ancak bu yöntemler bazen yetersiz kalabilmektedir. Bu durumda daha karmaşık yöntemlerin
uygulanması gerebilmektedir. Örneğin MHS veri kümesinde eksik veri olan evin metrekaresini ortalama yoluyla doldurmak
uygun olmayabilir. Çünkü bazı bölgeler pahalı olduğu için oradaki evler büyük ya da küçük olabilmektedir. Bazı
bölgelerin imar mevzuatları farklı olabilmektedir. Yani evin metrekaresi başka özelliklere göre (sütun bilgilerine göre)
değişebilmektedir. Peki bu tür durumlarda ne yapmak gerekir? İşte sütun değerleri satırdaki diğer değerlerden hareketle
regresyon modelleriyle tahmin edilebilir. Ancak uygulamada genellikle bu tür durumlar göz ardı edilip temel imputation
yöntemleri uygulanmaktadır.

scikit-learn Kütüphanesine Giriş
================================

Kütüphane Hakkında Genel Bilgiler
---------------------------------

Makine öğrenmesi uygulamalarında en çok kullanılan kütüphanelerden biri *scikit-learn* isimli kütüphanedir. NumPy ve
Pandas sayısal işlemler için kullanılan genel amaçlı ve temel kütüphanelerdir. SciPy ise matematik ve lineer cebir
konularına odaklanmış bir sayısal analiz kütüphanesidir. Oysa scikit-learn makine öğrenmesi uygulamaları için
tasarlanmıştır.

scikit-learn kütüphanesinin temelleri 2007 yılında atıldı. Önceleri SciPy kütüphanesine bir eklenti oluşturma amacıyla
geliştirilmeye başlandı. İlk sürümü 2010 yılında yayınlandı (0.1 sürümü). 2012'den sonra hızla yaygınlaştı. 2015 ve
sonrasında pek çok özelliği bünyesine katarak ve sürekli geliştirilerek bugünkü durumuna geldi. Kütüphanenin yüklenmesi
şöyle yapılabilir:

.. code-block:: python

    pip install scikit-learn

Ancak scikit-learn kütüphanesi yapay sinir ağları ve derin öğrenme ağlarına yönelik tasarlanmamıştır. scikit-learn
içerisindeki fonksiyonlar ve sınıflar matematiksel ve istatistiksel ağırlıklı öğrenme yöntemlerine ilişkindir.
scikit-learn kütüphanesinin import ismi sklearn biçimindedir. Örneğin:

.. code-block:: python

    import sklearn

Ancak genellikle uygulamacılar kütüphaneyi bir bütün olarak import etmek yerine kullanacakları öğeleri from import
deyimi ile import etmeyi tercih ederler. Örneğin:

.. code-block:: python

    from sklearn.impute import SimpleImputer

scikit-learn'ün Nesne Yönelimli Kullanım Biçimi
-----------------------------------------------

scikit-learn genel olarak *nesne yönelimli* biçimde oluşturulmuştur. Yani kütüphane daha çok fonksiyonlar yoluyla değil
sınıflar yoluyla kullanılmaktadır. Kütüphanenin belli bir kullanım biçimi vardır. Öğrenme kolay olsun diye ve bazı nesne
yönelimli tasarım kalıpları uygulansın diye bu biçim değişik sınıflarda uygulanmıştır. Kütüphanenin tipik kullanım
biçimi şöyledir:

1) Önce ilgili sınıf türünden nesne yaratılır. Örneğin sınıf SimpleImputer isimli sınıf olsun:

.. code-block:: python

    from sklearn.impute import SimpleImputer

    si = SimpleImputer(...)

2) Nesne yaratıldıktan sonra onun bir veri kümesi ile eğitilmesi gerekir. (Burada *eğitme* demekle denetimli bir
   öğrenmeyi kastetmiyoruz. Bunu genel bir terim olarak kullanıyoruz.) Bu işlem sınıfların fit metotlarıyla
   yapılmaktadır. fit işlemi sonrasında metot birtakım değerler elde edip onu nesnenin özniteliklerinde saklar. Yani fit
   metotları söz konusu veri kümesini ele alarak oradan faydalı birtakım bilgileri elde etmektedir. Örneğin:

.. code-block:: python

    si.fit(dataset)

fit işlemi genel olarak transform için kullanılacak bilgilerin elde edilmesi işlemini yapmaktadır. Dolayısıyla fit
işleminden sonra artık nesnenin özniteliklerini kullanabiliriz.

3) fit işleminden sonra fit işlemiyle elde edilen bilgilerin bir veri kümesine uygulanması gerekir. Bu işlem de
   sınıfların transform metotlarıyla yapılmaktadır. Bir veri kümesi üzerinde fit işlemi uyguladıktan sonra burada oluşan
   bilgilerle birden fazla veri kümesini transform edebiliriz. Örneğin:

.. code-block:: python

    si.fit(dataset)
    result1 = si.transform(dataset_foo)
    result2 = si.transform(dataset_bar)
    # ...

fit ve transform metotları bizden bilgiyi NumPy dizisi olarak, Pandas'ın Series ya da DataFrame nesnesi olarak ya da
Python listesi olarak alabilmektedir. fit metotları nesnenin kendisine, transform metotları da transform edilmiş NumPy
dizilerine geri dönmektedir.

4) Eğer fit edilecek veri kümesi ile transform edilecek veri kümesi aynı ise bu durumda önce fit sonra transform
   işlemini ayrı ayrı yapmak yerine bu iki işlem sınıfların fit_transform metotlarıyla tek hamlede de yapılabilir.
   Örneğin:

.. code-block:: python

    result = si.fit_transform(dataset)

5) Ayrıca sınıfların fit işlemi sonucunda oluşan bilgileri dışarıya vermek için kullanılan birtakım örnek öznitelikleri
   ve metotları da olabilmektedir.
6) Bazı sınıfların inverse_transform metotları da bulunmaktadır. inverse_transform metotları transform işleminin tersini
   yapmaktadır. Yani transform edilmiş bilgileri alıp onları transform edilmemiş hale getirmektedir.

fit, transform ve fit_transform metotları iki boyutlu veri kümelerini kabul etmektedir. Bu nedenle örneğin biz bu
metotlara Pandas'ın DataFrame nesnelerini verebiliriz fakat Series nesnelerini veremeyiz.

SimpleImputer Sınıfı ile Eksik Veri Doldurma
============================================

SimpleImputer Sınıfının Parametreleri
-------------------------------------

scikit-learn sınıflarının genel kullanımını açıkladıktan sonra şimdi eksik verilerin doldurulması işleminde kolaylık
sağlayan scikit-learn SimpleImputer sınıfını görebiliriz. SimpleImputer sınıfının kullanılması yukarıda açıkladığımız
genel kalıba uygundur. Önce nesne yaratılır, sonra fit ve transform işlemleri yapılır. Sınıfın __init__ metodunun
parametrik yapısı şöyledir:

.. code-block:: python

    class sklearn.impute.SimpleImputer(*, missing_values=nan, strategy='mean', fill_value=None,
            copy=True, add_indicator=False, keep_empty_features=False)

Görüldüğü gibi metodun bütün parametreleri default değer almış durumdadır. strategy parametresi doldurmanın nasıl
yapılacağını belirtmektedir. Bu parametrenin default değerinin *mean* biçiminde olduğunu görüyorsunuz. Yani default
durumda eksik veriler sütun ortalamaları ile doldurulmaktadır. *mean* dışındaki stratejiler şunlardır:

- *median*
- *most_frequent*
- *constant*

*constant* stratejisi doldurmanın belli bir değerle yapılacağı anlamına gelmektedir. Eğer bu strateji seçilirse
doldurulacak değerin fill_value parametresiyle belirtilmesi gerekir. Diğer parametreler için sınıfın dokümantasyonuna
başvurabilirsiniz.

SimpleImputer sınıfının fit, transform ve fit_transform metotları iki boyutlu bir dizi almaktadır. Yani bu metotlara bir
NumPy dizisi geçirecekseniz onun iki boyutlu olması gerekir. Pandas'ın Series nesnelerinin tek boyutlu bir dizi
belirttiğini anımsayınız. Bu durumda biz bu metotlara Series nesnesi geçemeyiz. Ancak DataFrame nesneleri iki boyutlu
dizi belirttiği için DataFrame nesnelerini geçebiliriz. Eğer elimizde tek boyutlu bir dizi varsa onu bir sütundan n
satırdan oluşan iki boyutlu bir diziye dönüştürmeliyiz. Bunun için NumPy ndarray sınıfının reshape metodunu
kullanabilirsiniz.

SimpleImputer nesnesi yaratılırken doldurma stratejisi nesnenin yaratımı sırasında verilmektedir. Yani nesne başta
belirtilen stratejiyi uygulamaktadır. Ancak veri kümelerinin değişik sütunları değişik stratejilerle doldurulmak
istenebilir. Bunun için birden fazla SimpleImputer nesnesi yaratılabilir. Örneğin:

::

    si1 = SimpleImputer(strategy='mean')
    si2 = SimpleImputer(strategy='median')
    ...

Ancak bunun yerine SimpleImputer sınıfının set_params metodu da kullanılabilir. Bu metot önceden belirlenmiş
parametreleri değiştirmekte kullanılmaktadır. Örneğin:

::

    si = SimpleImputer(strategy='mean')
    ...
    si.set_params(strategy='median')
    ...

SimpleImputer sınıfının __init__ metodunun missing_values parametresi eksik değerlerin özel değerler olarak
değerlendirilmesini sağlamak için kullanılabilmektedir. Yani örneğin eksik değerler NaN değerleri olmayabilir, 0
değerleri olabilir. Bu durumda bizim bunu bu parametreyle belirtmemiz gerekir. Örneğin:

::

    si = SimpleImputer(strategy='mean')

fit / transform / fit_transform Kullanımı
-----------------------------------------

SimpleImputer sınıfında yukarıda belirttiğimiz gibi doldurma işlemini fit metodu yapmaz, fit metodu doldurma işlemi için
gereken bilgileri elde eder. Yani örneğin:

::

    a = np.array([1, 1, None, 4, None]).reshape(-1, 1)

    si = SimpleImputer(strategy='mean')
    si.fit(a)

Burada fit metodu aslında yalnızca a dizisindeki sütunların ortalamalarını elde etmektedir. (Örneğimizde tek bir sütun
var). Biz fit yaptığımız bilgiyi transform etmek zorunda değiliz. Örneğin:

::

    b = np.array([1, 1, None, 4, None]).reshape(-1, 1)
    result = si.transform(b)

Biz şimdi burada a'dan elde ettiğimiz ortalama 3 değeri ile bu b dizisini doldurmuş oluruz. Tabii genellikle bu tür
durumlarda fit yapılan dizi ile transform yapılan dizi aynı dizi olur. Örneğin:

::

    a = np.array([1, 1, None, 4, None]).reshape(-1, 1)

    si = SimpleImputer(strategy='mean')
    si.fit(a)
    result = si.transform(a)

İşte bu tür durumlarda fit ve transform işlemleri bir arada fit_transform metoduyla yapılabilmektedir. Örneğin:

::

    a = np.array([1, 1, None, 4, None]).reshape(-1, 1)

    si = SimpleImputer(strategy='mean')
    result = si.fit_transform(a)

scikit-learn kütüphanesindeki pek çok sınıf aynı anda birden fazla sütun üzerinde işlem yapabilmektedir. Bu nedenle bu
sınıfların fit ve transform metotları bizden iki boyutlu dizi istemektedir. transform metotları da bize iki boyutlu dizi
geri döndürmektedir. Örneğin SimpleImputer sınıfına biz fit işleminde iki boyutlu bir dizi veririz. Bu durumda fit
metodu her sütunu diğerinden ayrı bir biçimde ele alır ve o sütunlara ilişkin bilgileri oluşturur. Örneğin biz fit
metoduna aşağıdaki gibi iki boyutlu bir dizi vermiş olalım:

::

    1       4
    None    7
    5       None
    3       8
    9       2

Stratejinin *mean* olduğunu varsayalım. Bu durumda fit metodu her iki sütunun da ortalamasını alıp nesnenin içerisinde
saklayacaktır. Biz artık transform metoduna iki boyutlu iki sütundan oluşan bir dizi verebiliriz. Bu transform metodu
bizim verdiğimiz dizinin ilk sütununu fit ettiğimiz dizinin ilk sütunundan elde ettiği bilgiyle, ikinci sütununu da fit
ettiğimiz dizinin ikinci sütunundan elde ettiği bilgiyle dolduracaktır. İşte scikit-learn sınıflarının fit ve transform
metotlarına biz iki boyutlu diziler veririz. O da bize iki boyutlu diziler geri döndürür. Eğer elimizde tek boyutlu bir
dizi varsa biz onu reshape metoduyla iki boyutlu hale getirerek fit ve transform metotlarına vermeliyiz. Örneğin:

.. code-block:: pycon

    >>> a = np.array([1, 2, 3, None, 5])
    >>> si.fit_transform(a.reshape(-1, 1))
    array([[1.  ],
        [2.  ],
        [3.  ],
        [2.75],
        [5.  ]])

MHS Veri Kümesinde SimpleImputer Uygulaması
-------------------------------------------

Aşağıda MHS veri kümesi üzerinde eksik verilerin bulunduğu sütunlar scikit-learn SimpleImputer sınıfı kullanılarak
doldurulmuştur.

.. code-block:: python

    import pandas as pd
    import numpy as np

    df = pd.read_csv('melb_data.csv')

    from sklearn.impute import SimpleImputer

    si = SimpleImputer(strategy='mean')
    df[['Car', 'BuildingArea']] = np.round(si.fit_transform(df[['Car', 'BuildingArea']]))

    si.set_params(strategy='median')
    df[['YearBuilt']] = np.round(si.fit_transform(df[['YearBuilt']]))

    si.set_params(strategy='most_frequent')
    df[['CouncilArea']] = si.fit_transform(df[['CouncilArea']])

Diğer Imputer Sınıfları
-----------------------

scikit-learn kütüphanesindeki sklearn.impute modülünde aşağıdaki imputer sınıfları bulunmaktadır:

- SimpleImputer
- IterativeImputer
- MissingIndicator
- KNNImputer

Buradaki KNNImputer sınıfı *en yakın komşuluk* yöntemini kullanmaktadır. Bu konu ileride ele alınacaktır.
IterativeImputer sınıfı ise regresyon yaparak doldurulacak değerleri oluşturmaktadır. Örneğin biz bu sınıfın fit
metoduna 5 sütunlu bir dizi vermiş olalım. Bu sınıf bu sütunların birini çıktı olarak, dördünü girdi olarak ele alıp
girdilerden çıktıyı tahmin edecek doğrusal bir model oluşturmaktadır. Yani bu sınıfta doldurulacak değerler yalnızca
doldurmanın yapılacağı sütunlar dikkate alınarak değil diğer sütunlar da dikkate alınarak belirlenmektedir. Örneğin MHS
veri kümesinde evin metrekaresi bilinmediğinde bu eksik veriyi ortalama metrekareyle doldurmak yerine *bölgeyi* ve
*binanın yaşını* da dikkate alarak doldurmak isteyebiliriz. Ancak yukarıda da belirttiğimiz gibi genellikle bu tür
karmaşık imputation işlemleri seyrek kullanılmaktadır.

Aşağıda MHS veri kümesi için üç sütuna dayalı olarak tahminleme yöntemiyle doldurmaya örnek verilmiştir.

.. code-block:: python

    import pandas as pd

    df = pd.read_csv('melb_data.csv')

    from sklearn.experimental import enable_iterative_imputer
    from sklearn.impute import IterativeImputer

    si = IterativeImputer()
    df[['Car', 'BuildingArea', 'YearBuilt']] = si.fit_transform(df[['Car', 'BuildingArea', 'YearBuilt']])

Kategorik Verilerin Sayısallaştırılması
=======================================

Etiket Kodlaması (Label Encoding) Kavramı
-----------------------------------------

Verilerin kullanıma hazır hale getirilmesi sürecinin en önemli işlemlerinden biri de *kategorik (nominal)* sütunların
sayısal biçime dönüştürülmesidir. Çünkü makine öğrenmesi algoritmaları veriler üzerinde *toplama*, *çarpma* gibi
işlemler yaparlar. Dolayısıyla kategorik veriler böylesi işlemlere sokulamazlar. Bunun için önce onların sayısal biçime
dönüştürülmeleri gerekir. Genellikle bu dönüştürme *eksik verilerin ele alınması* işleminden sonra yapılmaktadır. Ancak
bazen kategorik verilerin dönüştürülmesi işlemi eksik verilerin ele alınması işleminden önce de yapılabilmektedir.

Kategorik verilerin sayısal biçime dönüştürülmesi için kullanılan en temel yöntemlerden biri *etiket kodlaması (label
encoding)* denilen yöntemdir. Bu yöntemde kodlama her kategori (sınıf) için 0'dan itibaren artan bir tamsayı karşılık
düşürülerek yapılmaktadır. Örneğin bir veri kümesinde kişilerin renk tercihlerine ilişkin *Kırmızı*, *Yeşil* ve *Mavi*
seçeneklerinden oluşan aşağıdaki gibi bir sütun bulunuyor olsun:

::

    Kırmızı
    Mavi
    Kırmızı
    Yeşil
    Mavi
    Yeşil
    ...

Biz şimdi burada bu kategorik sütunu Kırmızı = 0, Mavi = 1, Yeşil = 2 biçiminde sayısallaştırabiliriz. Bu durumda bu
sütun şu hale gelecektir:

::

    0
    1
    0
    2
    1
    2
    ...

Kendi Etiket Kodlama Fonksiyonumuzu Yazmak
------------------------------------------

Biz yukarıdaki işlemi yapan bir fonksiyon da yazabiliriz. Fonksiyonun birinci parametresi bir DataFrame nesnesini,
ikinci parametresi ise hangi sütunun sayısallaştırılacağını belirten sütun isimlerinden oluşan bir nesneyi alabilir.

.. code-block:: python

    def category_encoder(df, colnames):
        for colname in colnames:
            labels = df[colname].unique()
            for index, label in enumerate(labels):
                df.loc[df[colname] == label, colname] = index

Burada biz önce sütun isimlerini tek tek elde etmek için dış bir döngü kullandık. Sonra ilgili sütundaki *tek olan
(unique)* etiketleri (labels) elde ettik. Sonra bu etiketleri iç bir döngüde dolaşarak sütunda ilgili etiketin bulunduğu
satırlara onları belirten sayıları yerleştirdik. Test işlemi için aşağıdaki gibi ``test.csv`` isimli bir CSV dosyasını
kullanabiliriz:

::

    AdıSoyadı,Kilo,Boy,Yaş,Cinsiyet,RenkTercihi
    Sacit Bulut,78,172,34,Erkek,Kırmızı
    Ayşe Er,67,168,45,Kadın,Yeşil
    Ahmet San,85,182,32,Erkek,Kırmızı
    Macit Şen,98,192,65,Erkek,Mavi
    Talat Demir,85,181,49,Erkek,Yeşil
    Sibel Ünlü,72,172,34,Kadın,Mavi
    Ali Serçe,75,165,21,Erkek,Yeşil

Test kodu da şöyle olabilir:

.. code-block:: python

    import pandas as pd

    def label_encode(df, colnames):
        for colname in colnames:
            labels = df[colname].unique()
            for index, label in enumerate(labels):
                df.loc[df[colname] == label, colname] = index

    label_encode(df, ['RenkTercihi', 'Cinsiyet'])
    print(df)

Şöyle bir çıktı elde edilmiştir:

.. code-block:: text

            AdıSoyadı  Kilo  Boy  Yaş Cinsiyet RenkTercihi
    0  Sacit Bulut    78  172   34        0            0
    1      Ayşe Er    67  168   45        1            1
    2    Ahmet San    85  182   32        0            0
    3    Macit Şen    98  192   65        0            2
    4  Talat Demir    85  181   49        0            1
    5   Sibel Ünlü    72  172   34        1            2
    6    Ali Serçe    75  165   21        0            1

Aşağıda da MHS veri kümesi üzerinde aynı işlem yapılmıştır.

.. code-block:: python

    import pandas as pd
    import numpy as np

    df = pd.read_csv('melb_data.csv')

    from sklearn.impute import SimpleImputer

    si = SimpleImputer(strategy='mean')
    df[['Car', 'BuildingArea']] = np.round(si.fit_transform(df[['Car', 'BuildingArea']]))

    si.set_params(strategy='median')
    df[['YearBuilt']] = np.round(si.fit_transform(df[['YearBuilt']]))

    si.set_params(strategy='most_frequent')
    df[['CouncilArea']] = si.fit_transform(df[['CouncilArea']])

    def category_encoder(df, colnames):
        for colname in colnames:
            labels = df[colname].unique()
            for index, label in enumerate(labels):
                df.loc[df[colname] == label, colname] = index

    category_encoder(df, ['Suburb', 'SellerG', 'Method', 'CouncilArea', 'Regionname'])
    print(df)

scikit-learn LabelEncoder Sınıfı
--------------------------------

Aslında yukarıdaki işlem scikit-learn kütüphanesindeki preprocessing modülünde bulunan LabelEncoder sınıfıyla
yapılabilmektedir. LabelEncoder sınıfının genel çalışma biçimi scikit-learn kütüphanesinin diğer sınıflarındaki gibidir.
Ancak bu sınıfın fit ve transform metotları tek boyutlu bir NumPy dizisini ya da Series nesnesini parametre olarak
almaktadır. (Halbuki yukarıda da belirttiğimiz gibi genel olarak fit ve transform metotlarının çoğu iki boyutlu dizileri
ya da DataFrame nesnelerini parametre olarak almaktadır.) fit metodu yukarıda bizim yaptığımız gibi *tek olan (unique)*
elemanları tespit edip bunu nesne içerisinde saklamaktadır. Asıl dönüştürme işlemi transform metoduyla yapılmaktadır.
Tabii eğer fit ve transform metotlarında aynı veriler kullanılacaksa bu işlemler tek hamlede fit_transform metoduyla da
yapılabilir. LabelEncoder sınıfı yukarıda bizim yaptığımızdan farklı olarak teke düşürdüğü etiketleri aynı zamanda
*yazısal biçimde (lexicographic)* de sıralamaktadır. Bu nedenle LabelEncoder ile sayısallaştırma sözlükteki sıraya göre
yapılmaktadır.

Örneğin yukarıdaki ``test.csv`` veri kümesindeki *Cinsiyet* ve *RenkTercihi* sütunlarını kategorik olmaktan çıkartıp
sayısal biçime şöyle dönüştürebiliriz:

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import LabelEncoder

    df = pd.read_csv('test.csv')

    le = LabelEncoder()

    transformed_data = le.fit_transform(df['RenkTercihi'])
    df['RenkTercihi'] = transformed_data

    transformed_data = le.fit_transform(df['Cinsiyet'])
    df['Cinsiyet'] = transformed_data
    print(df)

LabelEncoder sınıfının classes_ isimli örnek özniteliği fit metodu tarafından oluşturulmaktadır. Bu öznitelik *tek olan
(unique)* etiketleri bize NumPy dizisi olarak vermektedir.

Aşağıda MHS veri kümesindeki gerekli sütunlar LabelEncoder sınıfı ile sayısal biçime dönüştürülmüştür.

.. code-block:: python

    import pandas as pd
    import numpy as np

    df = pd.read_csv('melb_data.csv')
    print(df, end='\n\n')

    from sklearn.impute import SimpleImputer

    si = SimpleImputer(strategy='mean')
    df[['Car', 'BuildingArea']] = np.round(si.fit_transform(df[['Car', 'BuildingArea']]))

    si.set_params(strategy='median')
    df[['YearBuilt']] = np.round(si.fit_transform(df[['YearBuilt']]))

    si.set_params(strategy='most_frequent')
    df[['CouncilArea']] = si.fit_transform(df[['CouncilArea']])

    from sklearn.preprocessing import LabelEncoder

    le = LabelEncoder()
    for colname in ['Suburb', 'SellerG', 'Method', 'CouncilArea', 'Regionname']:
        df[colname] = le.fit_transform(df[colname])

    print(df)

inverse_transform ile Ters Dönüşüm
----------------------------------

LabelEncoder sınıfının inverse_transform metodu ters işlemi yapmaktadır. Yani bir kez fit işlemi yapıldıktan sonra nesne
zaten hangi etiketlerin hangi sayısal değerlere karşı geldiğini kendi içerisinde tutmaktadır. Böylece biz sayısal değer
verdiğimizde onun yazısal karşılığını inverse_transform ile elde edebiliriz. Örneğin:

.. code-block:: python

    some_label_numbers = [0, 1, 1, 2, 2, 1]
    label_names = le.inverse_transform(some_label_numbers)

Aşağıda ``test.csv`` dosyasının *RenkTercihi* ve *Cinsiyet* sütunları üzerinde önce transform sonra inverse_transform
işlemi örneği verilmiştir.

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import LabelEncoder

    df = pd.read_csv('test.csv')
    print(df, end='\n\n')

    le = LabelEncoder()

    transformed_data = le.fit_transform(df['RenkTercihi'])
    df['RenkTercihi'] = transformed_data

    some_label_numbers = [0, 1, 1, 2, 2, 1]
    label_names = le.inverse_transform(some_label_numbers)
    print(label_names, end='\n\n')

    transformed_data = le.fit_transform(df['Cinsiyet'])
    df['Cinsiyet'] = transformed_data
    print(df)

    some_label_numbers = [0, 1, 1, 1, 0, 1]
    label_names = le.inverse_transform(some_label_numbers)
    print(label_names)

Aslında kategorik verilerin 0'dan itibaren birer tamsayı ile numaralandırılması çoğu kez iyi bir teknik değildir.
Kategorik verilerin sayısallaştırılması için *one-hot-encoding* denilen yöntem tercih edilmektedir. Biz
*one-hot-encoding* dönüştürmesini izleyen paragraflarda ele alacağız.

Sıralı (Ordinal) Verilerin Kodlanması
-------------------------------------

Sıralı (ordinal) verilerin sayısal biçime dönüştürülmesi tipik olarak 0'dan başlanarak düşük sıranın düşük numarayla
ifade edilmesi biçiminde olabilir. Örneğin *EğitimDurumu*, *ilkokul*, *ortaokul*, *lise*, *üniversite* biçiminde dört
kategoride sıralı bir bilgi olabilir. Biz de bu bilgilere sırasıyla birer numara vermek isteyebiliriz. Örneğin:

::

    İlkokul     --> 0
    Ortaokul    --> 1
    Lise        --> 2
    Üniversite  --> 3

scikit-learn içerisindeki LabelEncoder sınıfı bu amaçla kullanılamamaktadır. Çünkü LabelEncoder etiketlere bizim
istediğimiz gibi numara vermemektedir. scikit-learn içerisinde bu işlemi pratik bir biçimde yapan hazır bir sınıf
bulunmamaktadır. Gerçi scikit-learn içerisinde OrdinalEncoder isimli bir sınıf vardır ama o sınıf bu tür amaçları
gerçekleştirmek için tasarlanmamıştır. scikit-learn içerisindeki OrdinalEncoder sınıfı LabelEncoder sınıfının yaptığına
benzer bir işlem yapmaktadır.

OrdinalEncoder Sınıfı ile Çok Sütunlu Kodlama
---------------------------------------------

OrdinalEncoder sınıfında da önce fit sonra transform işlemi yapılır. Eğer fit ve transform metodunda aynı veri kümesi
kullanılacaksa fit_transform metodu ile bu iki işlem bir arada da yapılabilir. OrdinalEncoder sınıfının categories_
örnek özniteliği oluşturulan kategorileri NumPy dizisi olarak vermektedir. fit işlemine sokulan sütunların sayısı ise
sınıfın n_features_in_ elemanından elde edilmektedir.

OrdinalEncoder sınıfı kodlanacak sütunları eğer onlar yazısal biçimdeyse tıpkı LabelEncoder sınıfı gibi önce onları
*lexicographic* olarak sıralayıp numaralandırmaktadır. (Yani sözlükte ilk gördüğü kategoriye düşük numara vermektedir.
Tabii bu işlem UNICODE tabloya göre yapılmaktadır.) Bu sınıf kategorilere bizim istediğimiz numaraları vermemektedir.
Ayrıca bu sınıfın fit ve transform metotları iki boyutlu nesneleri kabul etmektedir. Bu bağlamda OrdinalEncoder
sınıfının LabelEncoder sınıfından farkı OrdinalEncoder sınıfının birden fazla sütunu (özelliği) kabul etmesidir. Halbuki
LabelEncoder sınıfı tek bir sütunu (özelliği) sayısallaştırmaktadır. Örneğin ``test.csv`` veri kümemiz şöyle olsun:

::

    AdıSoyadı,Kilo,Boy,Yaş,Cinsiyet,RenkTercihi,EğitimDurumu
    Sacit Bulut,78,172,34,Erkek,Kırmızı,İlkokul
    Ayşe Er,67,168,45,Kadın,Yeşil,Ortaokul
    Ahmet San,85,182,32,Erkek,Kırmızı,İlkokul
    Macit Şen,98,192,65,Erkek,Mavi,Lise
    Talat Demir,85,181,49,Erkek,Yeşil,Üniversite
    Sibel Ünlü,72,172,34,Kadın,Mavi,Ortaokul
    Ali Serçe,75,165,21,Erkek,Yeşil,İlkokul

Burada *Cinsiyet* ve *RenkTercihi* kategorik (nominal) ölçekte sütunlardır. *EğitimDurumu* sütunu kategorik ya da sıralı
olarak ele alınabilir. Eğer biz İlkokul = 0, Ortaokul = 1, Lise = 2, Üniversite = 3 biçiminde sıralı ölçeğe ilişkin bir
kodlama yapmak istersek bunu LabelEncoder ya da OrdinalEncoder ile sağlayamayız. Örneğin:

.. code-block:: python

    df = pd.read_csv('test.csv')
    print(df, end='\n\n')

    oe = OrdinalEncoder()
    transformed_data = oe.fit_transform(df[['Cinsiyet', 'RenkTercihi', 'EğitimDurumu']])
    df[['Cinsiyet', 'RenkTercihi', 'EğitimDurumu']] = transformed_data

Buradan şöyle bir DataFrame elde edilecektir:

.. code-block:: text

            AdıSoyadı  Kilo  Boy  Yaş  Cinsiyet  RenkTercihi  EğitimDurumu
    0  Sacit Bulut    78  172   34       0.0           0.0            3.0
    1      Ayşe Er    67  168   45       1.0           2.0            1.0
    2    Ahmet San    85  182   32       0.0           0.0            3.0
    3    Macit Şen    98  192   65       0.0           1.0            0.0
    4  Talat Demir    85  181   49       0.0           2.0            2.0
    5   Sibel Ünlü    72  172   34       1.0           1.0            1.0
    6    Ali Serçe    75  165   21       0.0           2.0            3.0

Bunu OrdinalEncoder sınıfı ile kodlamaya çalışırsak muhtemelen tam istediğimiz gibi bir kodlama yapamayız.

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import OrdinalEncoder

    df = pd.read_csv('test.csv')
    print(df, end='\n\n')

    oe = OrdinalEncoder()
    transformed_data = oe.fit_transform(df[['Cinsiyet', 'RenkTercihi', 'EğitimDurumu']])

    df[['Cinsiyet', 'RenkTercihi', 'EğitimDurumu']] = transformed_data

    print(df)

converters Parametresiyle Manuel Kodlama
----------------------------------------

Eğer kategorilere istediğiniz gibi değer vermek istiyorsanız bunu manuel bir biçimde yapabilirsiniz. Örneğin veri kümesi
read_csv fonksiyonuyla okunurken converters parametresi yoluyla hemen dönüştürme yapılabilir. read_csv ve loadtxt
fonksiyonlarında converters parametresi bir sözlük nesnesi almaktadır. Bu sözlük nesnesi hangi sütun değerleri okunurken
hangi dönüştürmenin yapılacağını belirtmektedir. Buradaki sözlüğün her elemanının anahtarı bir sütun isminden ya da
sütun indeksinden, değeri ise o sütunun dönüştürülmesinde kullanılacak fonksiyondan oluşmaktadır. Tabii bu fonksiyon
lambda ifadesi olarak da girilebilir. Örneğin:

.. code-block:: python

    edu_map = {'İlkokul': 0, 'Ortaokul': 1, 'Lise': 2, 'Üniversite': 3}
    df = pd.read_csv('test.csv', converters={'EğitimDurumu': lambda s: edu_map[s]})

Elde edilecek DataFrame nesnesi şöyle olacaktır:

.. code-block:: text

            AdıSoyadı  Kilo  Boy  Yaş Cinsiyet RenkTercihi  EğitimDurumu
    0  Sacit Bulut    78  172   34    Erkek      Kırmızı              0
    1      Ayşe Er    67  168   45    Kadın        Yeşil              1
    2    Ahmet San    85  182   32    Erkek      Kırmızı              0
    3    Macit Şen    98  192   65    Erkek         Mavi              2
    4  Talat Demir    85  181   49    Erkek        Yeşil              3
    5   Sibel Ünlü    72  172   34    Kadın         Mavi              1
    6    Ali Serçe    75  165   21    Erkek        Yeşil              0

.. code-block:: python

    import pandas as pd

    edu_map = {'İlkokul': 0, 'Ortaokul': 1, 'Lise': 2, 'Üniversite': 3}
    df = pd.read_csv('test.csv', converters={'EğitimDurumu': lambda s: edu_map[s]})
    print(df, end='\n\n')

One-Hot-Encoding Kavramı
------------------------

Aslında makine öğrenmesi algoritmalarının bazılarında kategorik verilerin 0'dan itibaren LabelEncoder ya da
OrdinalEncoder sınıfı ile sayısallaştırılması olumsuz etkilere yol açabilmektedir. Çünkü bu durumda bazı algoritmalar bu
kategorik verileri sanki *sıralı (ordinal)* bir veriymiş gibi ele almaktadır. Örneğin veri kümesinin bir sütununda
*RenkTercihi* olsun. Bu *RenkTercihi* de *Kırmızı*, *Mavi* ve *Yeşil* renklerinden oluşuyor olsun. Biz bu sütunu
LabelEncoder ile sayısal hale getirdiğimizde örneğin Kırmızı = 0, Mavi = 1, Yeşil = 2 biçiminde renklere numara
verilecektir. İşte burada makine öğrenmesi algoritmaları sanki *Mavi* > *Kırmızı*, *Yeşil* > *Mavi* biçiminde bir ilişki
varmış gibi sonuçlara yol açabilecektir. Hatta örneğin bu kodlamadan *Kırmızı* + *Mavi* = *Mavi* gibi, gerçekte var
olmayan özellikler de ortaya çıkabilecektir. İşte bu nedenle kategorik verilerin tek bir sütunla değil birden fazla
sütunla ifade edilmesi yoluna gidilmektedir. Kategorik verilerin birden fazla sütunla ifade edilmesinde en yaygın
kullanılan yöntem *one-hot-encoding* denilen yöntemdir.

One-hot-encoding yönteminde önce veri kümesine sütundaki kategorilerin sayısı kadar sütun eklenir. (*One-hot* terimi
*bir grup bitten hepsinin sıfır yalnızca bir tanesinin 1 olma durumunu* anlatmaktadır.) Sonra her kategori yalnızca tek
bir sütunda 1 diğer sütunlarda 0 olacak biçimde kodlanır. Örneğin:

::

    RenkTercihi
    -----------
    Kırmızı
    Kırmızı
    Mavi
    Kırmızı
    Yeşil
    Mavi
    Yeşil
    ...

Burada 3 renk olduğunu düşünelim. Bunun *one-hot-encoding* dönüştürmesi şöyle olacaktır:

::

    Kırmızı     Mavi        Yeşil
    1           0           0
    1           0           0
    0           1           0
    1           0           0
    0           0           1
    0           1           0
    0           0           1
    ...

Eğer sütundaki kategori sayısı 2 tane ise böyle sütunlar üzerinde *one-hot-encoding* uygulamanın bir faydası yoktur. Bu
tür ikili sütunlar 0 ve 1 biçiminde kodlanabilir. (Yani bu işlem LabelEncoder sınıfıyla yapılabilir). Biz de kursumuzda
yalnızca iki kategori içeren sütunları *one-hot-encoding* ile kodlamayacağız.

OneHotEncoder Sınıfı
--------------------

Programlama yoluyla *one-hot-encoding* uygulamak için birkaç yöntem kullanılabilmektedir. Örneğin scikit-learn
içerisindeki preprocessing modülünde bulunan OneHotEncoder sınıfı bu işlem için kullanılabilir. Sınıfın genel kullanımı
diğer scikit-learn sınıflarında olduğu gibidir. Yani önce fit işlemi sonra transform işlemi yapılır. fit işleminden
sonra sütunlardaki *tek olan (unique)* elemanlar sınıfın categories_ örnek özniteliğinde NumPy dizilerinden oluşan bir
liste biçiminde saklanmaktadır. Örneğimizde kullanacağımız ``test.csv`` dosyası şöyle olsun:

::

    AdıSoyadı,Kilo,Boy,Yaş,RenkTercihi
    Sacit Bulut,78,172,34,Kırmızı
    Ayşe Er,67,168,45,Yeşil
    Ahmet San,85,182,32,Kırmızı
    Macit Şen,98,192,65,Mavi
    Talat Demir,85,181,49,Yeşil
    Sibel Ünlü,72,172,34,Mavi
    Ali Serçe,75,165,21,Yeşil

Pandas'ın DataFrame nesnesi üzerinde *one-hot-encoding* yapılırken DataFrame içerisindeki eski sütun silinmeli onun
yerine elde edilen yeni sütunlar eklenmelidir. DataFrame sütununa bir isim vererek atama yapılırsa o sütun zaten
DataFrame nesnesine otomatik eklenmektedir. *One-hot-encoding* ile oluşturulan sütunların isimleri önemli değildir.
Ancak OneHotEncoder sınıfı önce sütunu np.unique fonksiyonuna sokmakta ondan sonra encoding işlemini yapmaktadır.
NumPy'ın unique fonksiyonunun aynı zamanda sıraya dizme işlemini de zaten yaptığını anımsayınız. Dolayısıyla
OneHotEncoder aslında kategorik değerleri alfabetik sıraya göre sütunsal olarak dönüştürmektedir. Yukarıda da
belirttiğimiz gibi OneHotEncoder nesnesi fit işlemi yapıldığında zaten kategorileri categories_ isimli örnek özniteliği
yoluyla bir NumPy dizi listesi olarak bize vermektedir. Biz DataFrame eklemesi yaparken doğrudan bu isimleri
kullanabiliriz. categories_ örnek özniteliğinin bir liste olduğuna dikkat ediniz. Çünkü birden fazla sütun tek hamlede
*one-hot-encoding* yapılabilmektedir. Dolayısıyla programcı bu listenin ilgili elemanından kategorileri elde etmelidir.

Yukarıda da belirttiğimiz gibi OneHotEncoder sınıfının fit ve transform metotları çok boyutlu dizileri kabul etmektedir.
Bu durumda biz bu metotlara Pandas'ın Series nesnesini değil DataFrame nesnesini vermeliyiz.

OneHotEncoder nesnesini yaratırken *sparse_output* parametresini False biçimde geçmeyi unutmayınız. (Bu parametrenin
eski ismi *sparse* biçimindeydi). Çünkü bu sınıf default olarak transform edilmiş nesneyi *seyrek matris (sparse
matrix)* olarak vermektedir. Elemanlarının büyük çoğunluğu 0 olan matrislere *seyrek matris (sparse matrix)*
denilmektedir. Bu tür matrisler *fazla yer kaplamasın diye* sıkıştırılmış bir biçimde ifade edilebilmektedir. Seyrek
matrisler üzerinde işlemler kursumuzun sonraki bölümlerinde ele alınacaktır.

Yine OneHotEncoder nesnesi yaratılırken parametre olarak dtype türünü belirtebiliriz. Default dtype türü np.float64
alınmaktadır. Matris seyrek formda elde edilmeyecekse bu dtype türünü *uint8* gibi en küçük türde tutabilirsiniz.
max_categories parametresi kategori sayısını belli bir değerde tutmak için kullanılmaktadır. Bu durumda diğer tüm
kategoriler başka tek bir kategori oluşturmaktadır.

OneHotEncoder sınıfı ile one-hot-encoding uygulamaya yönelik şöyle bir örnek verebiliriz:

.. code-block:: python

    df = pd.read_csv('test.csv')
    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')
    transformed_data = ohe.fit_transform(df[['RenkTercihi']])
    df.drop(['RenkTercihi'], axis=1, inplace=True)
    df[ohe.categories_[0]] = transformed_data

Burada önce veri kümesi okunmuş sonra OneHotEncoder sınıfıyla fit_transform işlemi yapılmıştır. Daha sonra ise DataFrame
içerisindeki *RenkTercihi* sütunu silinip onun yerine categories_ örnek özniteliğindeki kategori isimleri nesneye
eklenmiştir.

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import OneHotEncoder

    df = pd.read_csv('test.csv')

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')
    transformed_data = ohe.fit_transform(df[['RenkTercihi']])
    df.drop(['RenkTercihi'], axis=1, inplace=True)
    df[ohe.categories_[0]] = transformed_data

    print(df)

Sütun İsim Çakışmalarını Önlemek: Önek Kullanımı
------------------------------------------------

DataFrame nesnesine yukarıdaki gibi birden fazla sütun eklerken dikkat etmek gerekir. Çünkü tesadüfen bu kategori
isimlerine ilişkin sütunlardan biri zaten varsa o sütun yok edilip yerine bu kategori sütunu gelecektir. Bunu engellemek
için oluşturacağınız kategori sütunlarını önekler vererek isimlendirebilirsiniz. Önek verirken orijinal sütun ismini
kullanırsanız bu durumda çakışma olasılığını neredeyse ortadan kaldırabilirsiniz. Yani örneğin *RenkTercihi* sütunu için
*Kırmızı*, *Mavi*, *Yeşil* isimleri yerine *RenkTercihi_Kırmızı*, *RenkTercihi_Mavi* ve *RenkTercihi_Yeşil* isimlerini
kullanabilirsiniz. Bir liste içlemiyle bu biçimdeki isimleri kolayca elde edebilirsiniz. Örneğin:

.. code-block:: python

    category_names = ['RenkTercihi_' + category for category in ohe.categories_[0]]

Aşağıda buna örnek verilmiştir.

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import OneHotEncoder

    df = pd.read_csv('test.csv')

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')

    transformed_data = ohe.fit_transform(df[['RenkTercihi']])

    df.drop(['RenkTercihi'], axis=1, inplace=True)

    category_names = ['RenkTercihi_' + category for category in ohe.categories_[0]]
    df[category_names] = transformed_data

    print(df)

Birden Fazla Sütunun Tek Seferde Kodlanması
-------------------------------------------

Veri kümesinin birden fazla sütununda kategorik bilgiler olabilir. Bunlar OneHotEncoder sınıfıyla tek tek
kodlanabilirler. Ancak aslında yukarıda da belirttiğimiz gibi OneHotEncoder sınıfı bir grup sütunu tek hamlede de
kodlayabilmektedir. Örneğin ``test.csv`` veri kümemiz şöyle olsun:

::

    AdıSoyadı,Kilo,Boy,Yaş,RenkTercihi,Meslek
    Sacit Bulut,78,172,34,Kırmızı,Mühendis
    Ayşe Er,67,168,45,Yeşil,Mühendis
    Ahmet San,85,182,32,Kırmızı,Avukat
    Macit Şen,98,192,65,Mavi,Doktor
    Talat Demir,85,181,49,Yeşil,Avukat
    Sibel Ünlü,72,172,34,Mavi,Doktor
    Ali Serçe,75,165,21,Yeşil,Mühendis

Burada *RenkTercihi*'nin yanı sıra *Meslek* de kategorik bir sütundur. Bunun her ikisini birden tek hamlede
*one-hot-encoding* işlemine sokabiliriz:

.. code-block:: python

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')
    transformed_data = ohe.fit_transform(df[['RenkTercihi', 'Meslek']])
    df.drop(['RenkTercihi', 'Meslek'], axis=1, inplace=True)
    categories1 = ['RenkTercihi_' + category for category in ohe.categories_[0]]
    categories2 = ['Meslek_' + category for category in ohe.categories_[1]]
    df[categories1 + categories2] = transformed_data

.. code-block:: python

    import pandas as pd
    from sklearn.preprocessing import OneHotEncoder

    df = pd.read_csv('test.csv')

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')

    transformed_data = ohe.fit_transform(df[['RenkTercihi', 'Meslek']])

    df.drop(['RenkTercihi', 'Meslek'], axis=1, inplace=True)

    categories1 = ['RenkTercihi_' + category for category in ohe.categories_[0]]
    categories2 = ['Meslek_' + category for category in ohe.categories_[1]]

    df[categories1 + categories2] = transformed_data

    print(df)

NumPy Dizisine Dönüştürerek One-Hot-Encoding
--------------------------------------------

Aslında makine öğrenmesi uygulamalarında veri kümesinin sütun isimlerinin hiçbir önemi yoktur. Dolayısıyla biz
*one-hot-encoding* işleminden önce NumPy dizisine geçip hiç sütun isimlerini oluşturmadan geri kalan kısmı NumPy
üzerinde de yapabiliriz. Örneğin:

.. code-block:: python

    df = pd.read_csv('test.csv')

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')
    transformed_data = ohe.fit_transform(df[['RenkTercihi', 'Meslek']])

    df.drop(['AdıSoyadı', 'RenkTercihi', 'Meslek'], axis=1, inplace=True)
    dataset = df.to_numpy()
    dataset = np.concatenate((dataset, transformed_data), axis=1)

Aşağıda buna bir örnek verilmektedir.

.. code-block:: python

    import numpy as np
    import pandas as pd
    from sklearn.preprocessing import OneHotEncoder

    df = pd.read_csv('test.csv')

    ohe = OneHotEncoder(sparse_output=False, dtype='uint8')
    transformed_data = ohe.fit_transform(df[['RenkTercihi', 'Meslek']])

    df.drop(['AdıSoyadı', 'RenkTercihi', 'Meslek'], axis=1, inplace=True)
    dataset = df.to_numpy()
    dataset = np.concatenate((dataset, transformed_data), axis=1)

    print(dataset)

get_dummies Fonksiyonu ile One-Hot-Encoding
-------------------------------------------

One-hot-encoding uygulamanın diğer bir yolu Pandas kütüphanesindeki get_dummies fonksiyonunu kullanmaktır. get_dummies
fonksiyonu bizden bir DataFrame, Series ya da dolaşılabilir herhangi bir nesneyi alır. Eğer biz get_dummies fonksiyonuna
bütün bir DataFrame geçirirsek fonksiyon oldukça akıllı davranmaktadır. Bu durumda fonksiyon DataFrame nesnesi
içerisindeki yazısal sütunları tespit eder. Yalnızca yazısal sütunları *one-hot-encoding* işlemine sokar ve bize yazısal
sütunları dönüştürülmüş yeni bir DataFrame nesnesi verir. Pandas ile çalışırken bu fonksiyon çok kolaylık sağlamaktadır.
``test.csv`` veri kümemiz şöyle olsun:

::

    AdıSoyadı,Kilo,Boy,Yaş,RenkTercihi,Meslek
    Sacit Bulut,78,172,34,Kırmızı,Mühendis
    Ayşe Er,67,168,45,Yeşil,Mühendis
    Ahmet San,85,182,32,Kırmızı,Avukat
    Macit Şen,98,192,65,Mavi,Doktor
    Talat Demir,85,181,49,Yeşil,Avukat
    Sibel Ünlü,72,172,34,Mavi,Doktor
    Ali Serçe,75,165,21,Yeşil,Mühendis

Biz get_dummies fonksiyonuyla daha önce yapmış olduğumuz işlemleri aşağıdaki gibi tek hamlede yapabiliriz:

.. code-block:: python

    df = pd.read_csv('test.csv')
    transformed_df = pd.get_dummies(df, dtype='uint8')

Burada biz tek hamlede istediğimiz dönüştürmeyi yapabildik. Bu dönüştürmede yine sütun isimleri orijinal sütun isimleri
ve kategori isimleriyle öneklendirilmiştir. Yukarıdaki koddan şöyle bir çıktı elde edilecektir:

.. code-block:: text

       Kilo  Boy  Yaş  ...  Meslek_Avukat  Meslek_Doktor  Meslek_Mühendis
    0    78  172   34  ...              0              0                1
    1    67  168   45  ...              0              0                1
    2    85  182   32  ...              1              0                0
    3    98  192   65  ...              0              1                0
    4    85  181   49  ...              1              0                0
    5    72  172   34  ...              0              1                0
    6    75  165   21  ...              0              0                1

Eğer isterse programcı *prefix* parametresi ile bu öneki değiştirebilir, *prefix_sep* parametresiyle de '_' karakteri
yerine başka birleştirme karakterlerini kullanabilir. get_dummies fonksiyonu default durumda sparse olmayan bool türden
bir DataFrame nesnesi vermektedir. Ancak get_dummies fonksiyonunda dtype parametresi belirtilerek uint8 gibi bir türden
çıktı oluşturulması sağlanabilmektedir.

Biz bir DataFrame nesnesinin tüm yazısal sütunlarını değil bazı yazısal sütunlarını da one-hot-encoding işlemine sokmak
isteyebiliriz. Bu durumda fonksiyon DataFrame nesnesinin diğer sütunlarına hiç dokunmamaktadır. Örneğin:

.. code-block:: python

    transformed_df = pd.get_dummies(df, columns=['Meslek'], dtype='uint8')

Biz burada yalnızca DataFrame nesnesinin *Meslek* sütununu *one-hot-encoding* yapmış olduk. get_dummies fonksiyonunun
zaten *one-hot-encoding* yapılan sütunu sildiğine dikkat ediniz. Bu bizim genellikle istediğimiz bir şeydir. Yukarıdaki
örnekte ``test.csv`` dosyasında *AdıSoyadı* sütunu yazısal bir sütundur. Dolayısıyla default durumda bu sütun da
one-hot-encoding işlemine sokulacaktır. Bunu engellemek için *columns* parametresinden faydalanabiliriz ya da baştan o
sütunu atabiliriz. Örneğin:

.. code-block:: python

    transformed_df = pd.get_dummies(df.iloc[:, 1:], dtype='uint8')
