# Fetüs Ultrason Görüntülerinde Kenar Tespiti Projesi

Bu proje, ultrason görüntülerinde fetüs konturlarının otomatik olarak tespit edilmesi için geliştirilmiş bir görüntü işleme uygulamasıdır. Canny kenar algılama algoritması ve çeşitli görüntü işleme teknikleri kullanılarak fetüs sınırlarının belirlenmesi amaçlanmaktadır.

## 🎯 Proje Amacı

Tıbbi görüntüleme alanında, ultrason görüntülerinden fetüsün konumunu ve sınırlarını tespit etmek önemli bir görevdir. Bu proje, aşağıdaki hedeflere ulaşmayı amaçlamaktadır:

- **Otomatik Kenar Tespiti**: Ultrason görüntülerinde fetüs konturlarının otomatik olarak belirlenmesi
- **Görüntü İyileştirme**: Gürültü azaltma ve kontrast iyileştirme ile daha net kenar tespiti
- **Hızlı Analiz**: Toplu görüntü işleme ile birden fazla ultrason görüntüsünün hızlı analizi
- **Görselleştirme**: Tespit edilen kenarların ve sonuçların görsel olarak sunulması

## 🔬 Kullanılan Yöntemler

### 1. Görüntü Ön İşleme
- **Gri Tonlamaya Dönüştürme**: RGB görüntülerin gri tonlamaya çevrilmesi
- **Gaussian Blur**: Gürültü azaltma ve yumuşatma işlemi
- **Histogram Eşitleme**: Kontrast iyileştirme

### 2. Kenar Algılama
- **Canny Edge Detection**: Optimal kenar tespiti için Canny algoritması
- **Threshold Ayarları**: Alt ve üst eşik değerlerinin optimize edilmesi
- **Morfolojik İşlemler**: Kenarların iyileştirilmesi ve gürültü temizleme

### 3. Post-Processing
- **Kontur Analizi**: Tespit edilen kenarların analizi
- **Filtreleme**: İstenmeyen küçük kenarların temizlenmesi
- **Overlay Görselleştirme**: Orijinal görüntü üzerine tespit edilen kenarların çizilmesi

## 📁 Proje Yapısı

```
edge-detection-project/
├── data/
│   ├── test_images/      # Ultrason test görüntüleri (10 adet)
│   │   ├── 1.png
│   │   ├── 2.png
│   │   └── ...
│   └── test_labels/      # Manuel olarak işaretlenmiş etiket görüntüleri
│       ├── 1.png
│       ├── 2.png
│       └── ...
├── results/              # İşlenmiş çıktı görselleri
│   ├── canny_result.png  # Canny algoritması sonucu
│   └── kenar1.png        # İkili (binary) kenar görüntüsü
├── notebooks/
│   └── KenarDeseniKodla2.ipynb  # Ana analiz notebook'u
├── .gitignore
└── README.md
```

## 🚀 Kurulum ve Kullanım

### Gereksinimler

Python 3.7 veya üzeri sürüm gereklidir. Gerekli kütüphaneleri yüklemek için:

```bash
pip install numpy opencv-python matplotlib jupyter scikit-image
```

### Kullanım

1. **Repository'yi klonlayın:**
```bash
git clone https://github.com/kullanici-adin/edge-detection-project.git
cd edge-detection-project
```

2. **Jupyter Notebook'u başlatın:**
```bash
jupyter notebook notebooks/KenarDeseniKodla2.ipynb
```

3. **Notebook'u çalıştırın:**
   - Hücreleri sırayla çalıştırarak görüntü işleme adımlarını gözlemleyin
   - Parametreleri (threshold değerleri, blur miktarı vb.) ihtiyacınıza göre ayarlayın
   - Sonuçları `results/` klasöründe inceleyin

## 📊 Örnek Sonuçlar

Proje, ultrason görüntülerinde başarılı bir şekilde fetüs kenarlarını tespit edebilmektedir:

- **Giriş**: Orijinal ultrason görüntüsü
- **İşleme**: Canny kenar algılama ve morfolojik işlemler
- **Çıkış**: Tespit edilmiş kenar haritası ve overlay görüntüsü

## 🔧 Parametre Ayarları

Notebook içerisinde ayarlanabilir parametreler:

- **Canny Threshold Değerleri**: Alt ve üst eşik değerleri (örn: 50, 150)
- **Gaussian Blur Kernel**: Bulanıklık miktarı (örn: 5x5)
- **Morfolojik İşlem Boyutu**: Kernel boyutu (örn: 3x3, 5x5)

## 📈 Gelecek Geliştirmeler

- [ ] Derin öğrenme modeli entegrasyonu (U-Net, Mask R-CNN)
- [ ] Otomatik threshold optimizasyonu
- [ ] 3D ultrason görüntü desteği
- [ ] Gerçek zamanlı video işleme
- [ ] Fetüs ölçüm özellikleri (baş çevresi, femur uzunluğu vb.)

## 📝 Veri Seti Hakkında

- **Test Görüntüleri**: 10 adet ultrason görüntüsü
- **Etiketler**: Manuel olarak işaretlenmiş referans kenar görüntüleri
- **Format**: PNG (24-bit RGB veya 8-bit grayscale)
- **Çözünürlük**: Değişken (ultrason cihazına bağlı)

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Lütfen pull request göndermeden önce:

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/YeniOzellik`)
3. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/YeniOzellik`)
5. Pull Request oluşturun

## 📄 Lisans

Bu proje eğitim ve araştırma amaçlı geliştirilmiştir.

## 👤 İletişim

Sorularınız veya önerileriniz için issue açabilirsiniz.

---

**Not**: Bu proje tıbbi teşhis amaçlı kullanılmamalıdır. Sadece eğitim ve araştırma amaçlıdır.
