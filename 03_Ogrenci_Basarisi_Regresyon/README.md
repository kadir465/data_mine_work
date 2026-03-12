# Ders Dışı Çalışma Süresinin Başarıya Etkisi: Regresyon Analizi

## Proje Hakkında
Bu çalışma, öğrencilerin ders dışı çalışma süreleri, sınıf düzeyleri ve dersi alma tekrar sayıları gibi çeşitli faktörlerin vize başarı puanı üzerindeki etkisini incelemeyi amaçlamaktadır. "Ayrık Matematik ve Mantık" dersini alan öğrenciler üzerinde yapılan bir anket çalışmasından elde edilen verilerle üç farklı regresyon modeli kullanılarak vize notu tahminlemesi yapılmıştır.

## Kullanılan Veri Seti
Projede kullanılan veri seti, öğrencilere uygulanan bir anket formu (`veri madenciliği - Form Yanıtları 1.csv`) aracılığıyla birincil kaynaklardan toplanmıştır. Veri temizleme adımlarından sonra analiz 24 gözlem üzerinden yürütülmüştür. 
Tahmin edilecek hedef değişken (Y) "Vize Başarı Puanı" iken, bağımsız değişkenler (X) arasında ders dışı çalışma saati, dersin AKTS'si, sınıf düzeyi ve dersi alma sayısı gibi metrikler yer almaktadır.

## Kullanılan Modeller
Çalışma kapsamında bağımsız değişkenlerin vize notuna katkısını değerlendirmek için aşağıdaki regresyon algoritmaları eğitilmiş ve karşılaştırılmıştır:
1. Çoklu Doğrusal Regresyon (Linear Regression)
2. ElasticNet Regresyonu
3. Rastgele Orman Regresyonu (Random Forest Regression)

## Sonuçlar ve Değerlendirme
Veri setinin son derece kısıtlı bir hacme (24 gözlem) sahip olması ve test setindeki muhtemel aykırı değerler sebebiyle, modellerin genel tahmin performansı düşük kalmış ve test verisi üzerindeki R-kare metrikleri negatif aralıkta hesaplanmıştır.
* Tüm zorluklara rağmen, hata payı metrikleri (MAE/MSE) değerlendirildiğinde diğerlerine kıyasla en iyi performansı **Linear Regression** (Çoklu Doğrusal Regresyon) modeli göstermiştir.
* Geliştirilen model üzerinden yapılan simülasyonlarda, ders dışı çalışma saati arttıkça vize puanında belirgin bir artış öngörülmüştür (Örneğin: Haftada 0.5 saat ekstra çalışma için tahmini not yaklaşık 42 iken, 2.0 saat çalışma için yaklaşık 83 olarak hesaplanmıştır).
* Bu çalışma, makine öğrenmesi modellerinin genellenebilir ve yüksek doğrulukta sonuçlar üretebilmesi için geniş çaplı veri setlerine duyulan ihtiyacı uygulamalı bir şekilde ortaya koymuştur.

## Klasör İçeriği
* `data.ipynb`: Veri ön işleme, veri görselleştirme, model kurulumu ve senaryo bazlı not tahminlerini içeren Jupyter Notebook dosyası.
* `veri madenciliği - Form Yanıtları 1.csv`: Analizde kullanılan ham anket verilerini barındıran veri seti.
* `veri_madeni_ödev_raporu.docx`: Projenin amacını, metodolojisini, analiz sürecini ve elde edilen bulguları kapsamlı bir şekilde inceleyen proje sonuç raporu.

## Nasıl Çalıştırılır?
1. Kodların çalışması için ortamınızda `pandas`, `numpy`, `scikit-learn`, `matplotlib` ve `seaborn` kütüphanelerinin yüklü olması gerekmektedir.
2. `data.ipynb` dosyasını Jupyter ortamında açın.
3. İlgili hücreleri sırasıyla çalıştırarak modellerin hata metriklerini ve farklı çalışma saatleri için oluşturulan tahmin tablolarını görüntüleyebilirsiniz.