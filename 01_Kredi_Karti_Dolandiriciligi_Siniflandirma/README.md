# Kredi Kartı Dolandırıcılığı Tespiti (Fraud Detection)

## Proje Hakkında
Bu proje, makine öğrenmesi algoritmaları kullanılarak kredi kartı işlemlerinin normal mi yoksa dolandırıcılık (fraud) işlemi mi olduğunu tespit etmeyi amaçlamaktadır. Ciddi bir sınıf dengesizliğine (class imbalance) sahip olan finansal veri seti üzerinde çeşitli veri ön işleme teknikleri uygulanmış ve üç farklı modelin sınıflandırma performansları karşılaştırmalı olarak analiz edilmiştir.

## Kullanılan Veri Seti
Projede kullanılan veri seti Kaggle üzerinden sağlanmıştır. Toplam 284.807 işlemden oluşan veri setinde, dolandırıcılık vakaları tüm işlemlerin yalnızca %0.17'sini oluşturmaktadır. 
Veri setini projenin bulunduğu dizine otomatik olarak indirmek için `kaggle_data_puli.py` betiğini kullanabilirsiniz.

## Veri Ön İşleme ve Metodoloji
Veri setindeki dengesizlikleri ve ölçek farklarını gidermek amacıyla aşağıdaki adımlar uygulanmıştır:
* **Normalizasyon:** `Amount` ve `Time` değişkenleri, değer aralıklarının model performansını olumsuz etkilememesi için `StandardScaler` kullanılarak normalize edilmiştir.
* **Eksik Veri Kontrolü:** Veri setindeki sonsuz (inf) değerler NaN formatına çevrilmiş ve boş değerler sıfır ile doldurulmuştur.
* **Dengesizliğin Giderilmesi (SMOTE):** Sınıf dengesizliğini aşmak ve modelin azınlık sınıfını (dolandırıcılık) daha iyi öğrenmesini sağlamak için Sentetik Azınlık Aşırı Örnekleme Tekniği (SMOTE) uygulanmıştır.

## Kullanılan Modeller
Çalışma kapsamında aşağıdaki makine öğrenmesi ve derin öğrenme tabanlı modeller eğitilmiş ve test edilmiştir:
1. Random Forest Classifier
2. XGBoost Classifier
3. Multi-Layer Perceptron (MLP) Neural Network

## Sonuçlar ve Değerlendirme
Test setindeki gerçek dolandırıcılık vakaları üzerinden yapılan değerlendirmeler sonucunda en başarılı ve dengeli model **XGBoost** olmuştur.

* **XGBoost:** Dolandırıcılığı yakalama (Recall: 0.85) ve doğru alarm verme (Precision: 0.83) metriklerinde en yüksek F1-Score (0.84) değerine ulaşmıştır.
* **Random Forest:** XGBoost'a yakın bir performans sergilemiş ancak yanlış işaretleme oranları bir miktar daha yüksek çıkmıştır.
* **MLP:** Sadece 11 dolandırıcılığı kaçırarak en yüksek yakalama oranına (Recall) sahip olsa da, 598 adet normal işlemi yanlışlıkla dolandırıcılık olarak işaretleyerek çok yüksek bir yanlış alarm (False Positive) oranı vermiştir.

## Klasör İçeriği
* `Data_Mine.ipynb`: Veri ön işleme, model eğitimi ve karmaşıklık matrisi (confusion matrix) görselleştirmelerini içeren ana Jupyter Notebook dosyası.
* `kaggle_data_puli.py`: Kaggle API üzerinden veri setini indiren Python betiği.
* `data_mine_cassification_rapor.pdf`: Projenin detaylı analizini, metodolojisini ve sonuç grafiklerini içeren proje raporu.
* `Data_Mine_ipynb.pdf`: Kod adımlarının ve çıktıların PDF formatındaki derlemesi.

## Nasıl Çalıştırılır?
1. Kodların çalışması için `pandas`, `xgboost`, `scikit-learn`, `imblearn`, `matplotlib` ve `seaborn` kütüphanelerinin yüklü olduğundan emin olun.
2. Terminal üzerinden `python kaggle_data_puli.py` komutunu çalıştırarak veri setini indirin.
3. `Data_Mine.ipynb` dosyasını Jupyter ortamında açarak hücreleri sırasıyla çalıştırın.