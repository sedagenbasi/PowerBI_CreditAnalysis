# PowerBI_CreditAnalysis
Bu proje, bir finans kurumunun kredi analizini ve performans değerlendirmesini görselleştirmek için geliştirilmiştir. Kullanılan araçlar ve oluşturulan raporlar, iş süreçlerini optimize etmek ve performans ölçümlerini daha anlaşılır hale getirmek amacıyla hazırlanmıştır.
## Proje Özellikleri
- Veri temizleme adımları
- Kredi risk faktörlerinin analizi
- Etkileşimli grafikler ve görselleştirmeler
## Kullanılan Araçlar ve Teknolojiler
- **Power BI**: Dashboard oluşturma ve veri görselleştirme
- **Excel**: Veri hazırlama ve temizleme
## Proje Özeti
- **Kredi Türleri:** Tüketici, otomobil, konut kredileri.
- **Kapsam:** 7 bölge, 81 şehir.
- **Zaman Aralığı:** 2020-2022 yılları arasındaki veriler.
- **Amaç:** Verileri temizleyerek ve görselleştirerek, kredi performansını analiz etmek ve iş kararlarını desteklemek.
## Proje Detayları
- Tüm veriler incelendikten sonra veri temizleme ve düzenleme gerçekleştirilmiştir. 3 sayfalık bir iş analizi hazırlanmıştır. 

### Sayfa 1- Genel bakış
- Bu sayfada grafikleri kredi türlerine göre görüntüleyebilmek için dilimleyici eklenmiştir.
- Kartlar yardımıyla toplam satış ve hedef değerleri ve hedef gerçekleşme oranı eklenmiştir.
- Grafiklerde toplam satış ve toplam hedef değerleri karşılaştırmaları hedeflenmiştir.
- Bölge ve şehir(şube kodu) bazında grafikler eklenerek genel bir bakış kazanılmaya çalışılmıştır.
 ![Genel Bakış Sayfası](https://github.com/sedagenbasi/PowerBI_CreditAnalysis/blob/main/genel%20bak%C4%B1%C5%9F-t%C3%BCm%C3%BC.png)

### Sayfa 2- Bölge Detayları
- Bu sayfada bölgesel satışlar ve diğer performans metrikleri görselleştirildi.
- Ege Bölgesi özelinde detaylı analizler gerçekleştirildi.
- Ay bazında performans metrikleri dinamik olarak tooltiplerle analiz edildi.
- Yıllara göre satış trendleri grafiğinde yılın çeyreklerine göre toplam satış, toplam hedefin altında ise sarı renk, üstünde ise kırmızı renk ile dinamik bir tooltip oluşturulmuştur.
- Aylara göre toplam satış ve satış hedefi analizi grafiğinde satış hedefi 1.10 sabit değer belirlenmiştir.
   ![Bölge Detayları Sayfası]()
### Sayfa 3- Performnas Analizi
- Bu sayfada şehirler bazında en yüksek ve en düşük performanslı konum ve bölgeleri daha net şekilde göstermek hedeflenmiştir.
- Sayfanın sağ üst köşesindeki sayfa gezginlerine (ctrl+ yardımıyla) tıklandığında en düşük ve en yüksek performans değerleri üstteki iki grafikte gösterilmiştir.
- Üstteki 2 grafikte ayrıca filtreleme yapılarak en yüksek ve en düşük 5 şehrin değerleri karşılaştırılmıştır.
- Sayfanın üstünde bulunan 'En yüksek performanslı bölge','En yüksek performanslı konum' ve 'en düşük performanslı konum' kartları dax ile oluşturulmuştur. DAX içerikleri aşağıda paylaşılmıştır.
### DAX Formülleri

```DAX
En Yüksek Performanslı Bölge = 
CALCULATE(
    FIRSTNONBLANK('Şubeler'[Bölge], 1),
    TOPN(1, SUMMARIZE('Şubeler', 'Şubeler'[Bölge], "ToplamSatış", SUM(Krediler[Satış])), [ToplamSatış], DESC)
)

En Yüksek Performanslı Konum = 
CALCULATE(
    FIRSTNONBLANK('Şubeler'[Konum], 1),
    TOPN(1, SUMMARIZE('Şubeler', 'Şubeler'[Konum], "ToplamSatış", SUM(Krediler[Satış])), [ToplamSatış], DESC)
)
```
## Proje Sonucu
- Verilerin görselleştirilmesi ve analiz edilmesi sonucunda, kredi türleri, bölgesel ve şehir bazlı performanslar net bir şekilde ortaya konulmuştur.
- Dinamik tooltipler ve etkileşimli raporlarla, kullanıcıların iş kararlarını destekleyecek içgörüler sağlanmıştır.
- DAX ile hesaplanan metrikler, performans analizlerini kolaylaştırmıştır.








