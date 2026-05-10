# 🌸 Flower Classification with MobileNetV2

Bu proje, **Transfer Learning** (Transfer Öğrenme) tekniğini kullanarak farklı çiçek türlerini yüksek doğrulukla sınıflandırmayı amaçlayan bir Derin Öğrenme projesidir.

## 🚀 Proje Özeti
Modelin temelinde, ImageNet veri seti üzerinde önceden eğitilmiş **MobileNetV2** mimarisi yer almaktadır. Modelin "feature extraction" (özellik çıkarma) katmanları dondurulmuş, sonuna özel sınıflandırma katmanları eklenerek çiçekleri tanıyacak şekilde yeniden eğitilmiştir.

## 🛠️ Kullanılan Teknolojiler
* **Python 3.x**
* **TensorFlow / Keras** (Model mimarisi ve eğitim)
* **OpenCV** (Görüntü ön işleme)
* **NumPy** (Veri manipülasyonu)
* **Scikit-learn** (Veri setini bölme)
* **Matplotlib** (Görselleştirme)

## 📊 Model Mimarisi
Model şu aşamalardan oluşmaktadır:
1. **Input Layer:** 224x224x3 boyutunda girişler.
2. **Lambda Layer:** [0,1] arası değerleri [-1,1] arasına çeken normalizasyon.
3. **MobileNetV2 (Base):** Dondurulmuş (trainable=False) ana model.
4. **Global Average Pooling:** Özellikleri vektöre dönüştürme.
5. **Dense (256):** ReLU aktivasyonlu gizli katman.
6. **Dropout (0.4):** Aşırı öğrenmeyi (overfitting) engelleme.
7. **Dense (Output):** Softmax aktivasyonlu sınıflandırma katmanı.
