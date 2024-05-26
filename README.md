# car-motobice

Tabii, adım adım detaylı olarak anlatayım:

1. **Kütüphanelerin Yüklenmesi**: Kodun başında, kullanılacak kütüphaneler yüklenir. `os` işletim sistemi ile ilgili işlemleri yapmak için, `numpy` sayısal işlemler için, `matplotlib.pyplot` grafik çizimleri için, `tensorflow.keras.preprocessing.image` görüntü işleme için ve `tensorflow.keras.models` ise model oluşturma için kullanılır.

2. **Veri Setinin Yüklenmesi ve Hazırlanması**: Veri setinin yer aldığı dizinler `train_dir` ve `test_dir` değişkenlerine atanır.

3. **Veri Artırma (Data Augmentation)**: Görüntü verisi artırılarak modelin daha genelleştirilebilir ve daha iyi performans gösterebilmesi sağlanır. Eğitim verisi için `ImageDataGenerator` oluşturulur ve bu verilere dönüşümler uygulanır. Bu dönüşümler, veri setindeki görüntülerin çeşitlendirilmesini sağlar.

4. **Veri Yükleyici Oluşturma**: `ImageDataGenerator` nesneleri kullanılarak eğitim ve test verisi için veri yükleyicileri (`train_generator` ve `test_generator`) oluşturulur. Bu yükleyiciler, belirtilen dizinlerdeki görüntüleri ve ilgili etiketleri yükler.

5. **Modelin Oluşturulması**: `Sequential` model oluşturulur. Bu, katmanları sırayla eklemek için kullanılır. Modelde evrişim katmanları (`Conv2D`), havuzlama katmanları (`MaxPooling2D`) ve tam bağlantı katmanları (`Dense`) bulunur.

6. **Modelin Derlenmesi**: `compile` yöntemiyle model derlenir. Bu adımda modelin optimize edici (optimizer), kayıp fonksiyonu (loss function) ve metrikleri belirlenir. Optimizer olarak "adam" seçilir, kayıp fonksiyonu olarak ikili çapraz entropi (binary_crossentropy) kullanılır ve metrik olarak doğruluk (accuracy) belirlenir.

7. **Modelin Eğitilmesi**: `fit` yöntemiyle model eğitilir. Eğitim verisi (`train_generator`) kullanılarak modelin belirtilen sayıda epoch (burada 20) boyunca eğitilmesi sağlanır.

8. **Sonuçların Değerlendirilmesi**: Eğitim sonucu elde edilen doğruluk ve kayıp değerleri (`accuracy` ve `loss`) her epoch sonunda kaydedilir. Bu değerler daha sonra grafiklerle görselleştirilir, böylece modelin eğitim süreci hakkında bilgi edinilebilir.

Bu şekilde, veri setinin yüklenmesinden başlayarak, bir evrişimli sinir ağı modelinin oluşturulması, eğitilmesi ve sonuçlarının değerlendirilmesi adımları gerçekleştirilir. Bu süreç, genellikle makine öğrenimi ve derin öğrenme projelerinde sıkça kullanılan bir yaklaşımdır.

POWERED BY CHATGPT 4.0
