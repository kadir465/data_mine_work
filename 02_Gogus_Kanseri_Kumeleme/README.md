# Göğüs Kanseri Veri Seti ile Kümeleme Analizi (Clustering)

## Proje Hakkında
Bu proje, gözetimsiz makine öğrenmesi (unsupervised learning) algoritmaları kullanılarak tümör verilerinin analiz edilmesini ve hastaların "İyi Huylu" (Benign) veya "Kötü Huylu" (Malignant) olarak kümelere ayrılmasını amaçlamaktadır. Algoritmalar eğitilirken veri setindeki gerçek etiketler (hedef değişkenler) modele verilmemiş, modelin verilerdeki örüntüleri kendi başına bulması sağlanmıştır.

## Kullanılan Veri Seti
Çalışmada UCI Machine Learning Repository üzerinden sağlanan "Breast Cancer Wisconsin (Diagnostic)" veri seti kullanılmıştır. Veri seti `ucimlrepo` kütüphanesi aracılığıyla doğrudan koda çekilmektedir.

## Veri Ön İşleme ve Metodoloji
Uzaklık tabanlı kümeleme algoritmalarının doğru çalışabilmesi için verilerdeki ölçek farklarının giderilmesi gerekmiştir. Bu amaçla tüm öznitelikler (features) `StandardScaler` kullanılarak standartlaştırılmıştır.

Çalışma kapsamında iki farklı kümeleme algoritması uygulanmıştır:
1. **K-Means Kümeleme:** Veriyi önceden belirlenen sayıda (k=2) kümeye ayırmak için kullanılmıştır.
2. **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):** Yoğunluk tabanlı bu algoritma ile verideki doğal kümeler aranmış ve aykırı değerler (gürültü) tespit edilerek analiz dışında bırakılmıştır.

## Değerlendirme Metrikleri ve Sonuçlar
Gözetimsiz modellerin başarısı, veri setinde önceden bilinen gerçek etiketler ile modelin oluşturduğu kümeler karşılaştırılarak ölçülmüştür. Değerlendirme için şu metrikler kullanılmıştır:
* **Adjusted Rand Score (ARI):** Kümeleme sonuçlarının gerçek etiketlerle olan benzerliğini rastlantısallığı düzelterek ölçer.
* **Normalized Mutual Information (NMI):** Kümeler ve gerçek sınıflar arasındaki karşılıklı bilgi miktarını ölçer.
* **Karmaşıklık Matrisi (Confusion Matrix):** K-Means ve DBSCAN algoritmalarının iyi huylu ve kötü huylu tümörleri hangi kümelere atadığını görselleştirmek için kullanılmıştır (Isı haritası formatında sunulmuştur).

## Klasör İçeriği
* `page1.ipynb`: Veri çekme, ön işleme, K-Means ve DBSCAN modellerinin uygulanması ile değerlendirme grafiklerini içeren Jupyter Notebook dosyası.

## Nasıl Çalıştırılır?
1. Kodların çalışması için `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` ve `ucimlrepo` kütüphanelerinin yüklü olduğundan emin olun.
2. `page1.ipynb` dosyasını Jupyter ortamında açın.
3. Hücreleri sırasıyla çalıştırarak analizleri ve ısı haritası (heatmap) görsellerini elde edebilirsiniz.