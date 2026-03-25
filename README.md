# Non-Linear Classification with PyTorch

Sismik aktivite verisi kullanarak ikili sınıflandırma (binary classification) problemi. Lineer ve non-lineer modelin performans farkı karşılaştırılmaktadır.

## Problem

Yeraltı dalga enerjisi (`underground_wave_energy`) ve titreşim ekseni değişimi (`vibration_axis_variation`) özelliklerine bakarak sismik olay tespit edilip edilmediğini tahmin etmek. (0: olay yok, 1: olay var)

## Veri Seti

- 400 örnek, 2 özellik, 1 hedef sütun
- Dengeli sınıf dağılımı: 200 pozitif, 200 negatif
- %80 eğitim / %20 test olarak bölündü

## Model Mimarisi

Giriş (2) → Linear → ReLU → Linear → ReLU → Linear → Çıkış (1)
(2→10)          (10→10)          (10→1)

Aktivasyon fonksiyonu olmadan (lineer model) veri düz çizgiyle ayrılamadığı için ~%50 doğrulukta kalır. **ReLU** eklenince model eğri karar sınırları öğrenerek **%100** doğruluğa ulaşır.

## Sonuçlar

| Model | Doğruluk |
|-------|----------|
| Lineer (aktivasyon yok) | ~%50 |
| Non-lineer (ReLU) | ~%100 |

## Kullanılan Teknolojiler

- Python
- PyTorch
- Scikit-learn
- Matplotlib / Seaborn / NumPy

## Çalıştırma

```bash
pip install torch pandas scikit-learn matplotlib seaborn numpy
jupyter notebook pytorch_nonlinear.ipynb
