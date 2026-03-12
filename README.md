# Veri Madenciliği ve Makine Öğrenmesi Projeleri

Bu depo, Veri Madenciliği (Data Mining) prensipleri ve Makine Öğrenmesi (Machine Learning) algoritmaları kullanılarak geliştirilmiş çeşitli veri bilimi projelerini içermektedir. Projeler; gözetimli öğrenme (sınıflandırma ve regresyon) ile gözetimsiz öğrenme (kümeleme) problemlerine analitik yaklaşımlar getirmeyi amaçlamaktadır.

## Proje Klasör Yapısı ve İçerikler

Depo içerisinde, her biri farklı bir veri madenciliği konseptine odaklanan üç ana proje bulunmaktadır:

### 1. Kredi Kartı Dolandırıcılığı Tespiti (Sınıflandırma)
* **Klasör:** `01_Kredi_Karti_Dolandiriciligi_Siniflandirma`
* **Konu:** Sınıf dengesizliği (class imbalance) içeren finansal veriler üzerinde dolandırıcılık tespiti.
* **Kullanılan Modeller:** Random Forest, XGBoost, Multi-Layer Perceptron (MLP).
* **Öne Çıkanlar:** Veri ön işleme, StandardScaler ile normalizasyon, SMOTE ile sentetik veri üretimi ve karmaşıklık matrisi analizi.

### 2. Göğüs Kanseri Veri Seti ile Kümeleme Analizi (Kümeleme)
* **Klasör:** `02_Gogus_Kanseri_Kumeleme`
* **Konu:** Etiketleri gizlenmiş tıbbi veriler üzerinden gözetimsiz öğrenme ile iyi huylu/kötü huylu tümör kümelerinin oluşturulması.
* **Kullanılan Modeller:** K-Means, DBSCAN.
* **Öne Çıkanlar:** Uzaklık tabanlı ve yoğunluk tabanlı algoritmaların karşılaştırılması, ARI ve NMI metrikleri ile model başarısının ölçülmesi.

### 3. Ders Dışı Çalışma Süresinin Başarıya Etkisi (Regresyon)
* **Klasör:** `03_Ogrenci_Basarisi_Regresyon`
* **Konu:** Birincil kaynaklardan anket yoluyla toplanan veriler üzerinden öğrencilerin çalışma saatlerine göre vize notlarının tahmin edilmesi.
* **Kullanılan Modeller:** Multiple Linear Regression, ElasticNet, Random Forest Regressor.
* **Öne Çıkanlar:** Küçük hacimli gerçek dünya verisiyle çalışma, hata metrikleri (MAE, MSE, R-kare) analizi ve senaryo bazlı not simülasyonları.

## Kullanılan Teknolojiler
Bu projelerin geliştirilmesinde aşağıdaki araçlar ve kütüphaneler kullanılmıştır:
* **Programlama Dili:** Python
* **Veri İşleme:** Pandas, NumPy
* **Makine Öğrenmesi:** Scikit-Learn, XGBoost, Imbalanced-Learn
* **Görselleştirme:** Matplotlib, Seaborn
* **Geliştirme Ortamı:** Jupyter Notebook

## Kurulum ve Çalıştırma

Projeleri kendi yerel ortamınızda çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

1. Depoyu bilgisayarınıza klonlayın:
   ```bash
   git clone <repo-url-adresi>

2. Gerekli kütüphaneleri yüklemek için proje ana dizininde aşağıdaki komutu çalıştırın: 
pip install -r requirements.txt