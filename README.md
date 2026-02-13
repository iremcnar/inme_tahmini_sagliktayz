# 🏥 Sağlıkta Yapay Zeka: İnme (Stroke) Riski Tahmini

Bu proje, **Burdur Mehmet Akif Ersoy Üniversitesi** bünyesindeki **Sağlıkta Yapay Zeka** dersi uygulama çalışmaları kapsamında geliştirilmiştir. Projenin amacı, hastaların demografik bilgilerini ve sağlık geçmişlerini analiz ederek inme (stroke) geçirme riskini tahmin eden bir makine öğrenmesi modeli oluşturmaktır.

## 📌 Proje Özeti
İnme, dünya genelinde engellilik ve ölüm nedenleri arasında üst sıralarda yer almaktadır. Bu projede, risk faktörleri (yaş, hipertansiyon, kalp hastalığı, BMI vb.) kullanılarak bir hastanın inme geçirip geçirmeyeceği tahmin edilmektedir.

**Veri Seti:** [Healthcare Dataset: Stroke Data](https://www.kaggle.com/datasets/aouatifcherdid/healthcare-dataset-stroke-data)

## 🛠️ Kullanılan Teknolojiler
- **Python** (Veri Bilimi Ekosistemi)
- **Pandas & NumPy** (Veri manipülasyonu)
- **Matplotlib & Seaborn** (Veri görselleştirme ve EDA)
- **Scikit-Learn** (Makine öğrenmesi algoritmaları ve ön işleme)
- **Imbalanced-learn (SMOTE)** (Dengesiz veri yönetimi)

## 🚀 Proje Uygulama Adımları

### 1. Veri Hazırlığı ve Ön İşleme
- **Eksik Veri Yönetimi:** BMI (Vücut Kitle İndeksi) sütunundaki eksik değerler analiz edilerek uygun yöntemlerle (ortalama/medyan) doldurulmuştur.
- **Kategorik Veri Dönüştürme:** Cinsiyet, evlilik durumu, çalışma tipi ve ikamet türü gibi veriler `LabelEncoder` ve `OneHotEncoder` kullanılarak sayısal formata getirilmiştir.
- **Veri Ölçeklendirme:** Model performansını artırmak için sayısal veriler standardize edilmiştir.

### 2. Dengesiz Veri ile Mücadele (Oversampling)
Veri setinde inme geçiren hasta sayısı, geçirmeyenlere göre oldukça az olduğu için (imbalanced data), **SMOTE** yöntemi kullanılarak sentetik veri üretilmiş ve sınıflar dengelenmiştir.

### 3. Modelleme ve Tahmin
Projede sınıflandırma yaklaşımları kullanılmıştır:
- **Random Forest / Decision Tree:** Veri setindeki karmaşık ilişkileri yakalamak için ağaç tabanlı algoritmalar tercih edilmiştir.
- **Olasılıksal Tahmin:** `predict_proba` fonksiyonu ile hastaların sadece risk grubunda olup olmadıkları değil, yüzde kaç risk taşıdıkları da analiz edilmiştir.

### 4. Performans Değerlendirme
- **Confusion Matrix:** Modelin doğru ve yanlış tahminleri (True Positive, False Negative vb.) görselleştirilmiştir.
- **Metrikler:** Sadece başarı oranı (Accuracy) değil, sağlık projelerinde kritik olan **Recall** ve **F1-Score** değerleri üzerinden model optimize edilmiştir.

## 📊 Öne Çıkan Bulgular
- Yaş ve ortalama glikoz seviyesinin inme riski üzerindeki en belirleyici özellikler olduğu gözlemlenmiştir.
- Veri dengeleme (SMOTE) işlemi uygulanmadan önce modelin inme geçiren vakaları yakalamada zorlandığı, ancak işlem sonrası "Recall" değerlerinde ciddi bir artış yaşandığı saptanmıştır.

## 📂 Dosya Yapısı
- `inme_tahmini.ipynb`: Veri temizleme, görselleştirme, SMOTE uygulaması ve modelleme adımlarını içeren ana notebook.
- `healthcare-dataset-stroke-data.csv`: Projede kullanılan ham veri seti.
