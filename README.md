# American-Sign-Language-Recognition-CNN
Projenin amacı: Projem evrişimsel sinir ağları(CNN) kullanarak Amerikan işaret dili (ASL) alfabesindeki el işaretlerini tanımayı amaçlayan bir makine öğrenmesi uygulamasıdır.

Kaggle veri seti: https://www.kaggle.com/datasets/datamunge/sign-language-mnist
Kaggle notebook: https://www.kaggle.com/code/selendilsaydam/american-sign-language-recognition-cnn

Veri seti: Kaggle'da kullandığım veri seti 'sign-language-mnist' dir. J ve Z harfleri hariç 24 işaret sınıfı içermektedir. İçinde bulunan görüntüler 28x28 piksel boyutunda olmaktadırlar.

Kullanılan teknolojiler: Programlama için makine öğrenmesinde en yaygın kullanılan dil olan Python'u kullandım. CNN mimarisi için TensorFlow ve Keras kütüphanelerini kullandım. Veri yönetimi için NumPy ve Pandas'ı; görselleştirme için de Matplotlib'i kullandım.

Model mimarisi ve eğitimi: Model tipi olarak CNN yani evrişimsel sinir ağını kullandım. Görüntü verilerindeki el şekillerini yüksek doğrulukta öğrenmekte diğer bilinen ağlardan daha başarı olduğu için CNN'i tercih ettim.

Optimizasyon: Modeli ilk çalıştırdığımda grafikleri inceledim ve overfitting sorunu olduğunu fark ettim. Bunu düzetlmek için ne yapacağımı okulda aldığım ac475 yapay zeka dersinde öğrenmiştim. Görseller tek şekilde olduğu için model öğrenmiyor sadece olan verilerin cevaplarını veriyordu. Ben de learning rate'ini 0.001 den 0.0005 e çektim, görüntüleri rastgele 15 dereceye kadar döndürdüm rotation_range=15, yatay ve dikey kaydırmalar uyguladım width_shift_range=0.15, yakınlaştırma yaptım zoom_range=0.10 ve eğme/bükme shear_range=0.10 uyguladım. Buna benzer çözümlerle bu sorunu en aza indirgemeye çalıştım. Genel olarak veri büyütme, dropout katmanları ve callback ayarlarıyla overfitting sorununu çözmüş oldum.

Proje başarısı: Model test doğruluğu olarak %99.97 gibi bir performans göstermiştir. Bu yüksek doğruluk seviyesinde de sadece 0.0117 gibi bir sayıyla son derece düşük bir test kaybı değeri elde etmiştir.
<img width="822" height="336" alt="image" src="https://github.com/user-attachments/assets/d4c92ae6-6127-42dc-9879-8bd84c2d7406" />
