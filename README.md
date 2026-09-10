**Nama:** Dania Hafiza
**NIM:** 25/559418/PA/23530

## 1. Metodologi
4 citra uji dipilih untuk meninjau karakteristik visual yang berbeda:
| Image | Type | Characteristic |
|---|---|---|
| Astronaut | Color, 512×512 | Mixed content — smooth regions (sky, suit) plus fine detail (visor, patches) |
| Checkerboard | Grayscale, 200×200 | Pure high-frequency, sharp repeating edges — a stress test for aliasing |
| Cameraman | Grayscale, 512×512 | Natural photo with fine texture (grass, buildings) and smooth sky |
| Coins | Grayscale, 303×384 | Distinct round objects on a textured background |

**Down Sampling** (factor = 4) diimplementasikan manual dengan block-based pooling: citra di-split menjadi 4x4 blok yang tidak overlap, dan tiap blok direduksi menjadi 1 pixel menggunakan nilai maksimum, mean, atau median dari blok.
**Up Sampling** (factor = 4) menggunakan tiga kernel standard interpolation, yaitu Nearest Neighbor, Bilinear, dan Bicubic. Masing-masing fiterapkan untuk merekonstruksi citra beresolusi rendah (average-pooled) menjadi original size.

Kualitas rekonstruksi diukur terhadap citra awal menggunakan **PSNR** (peak Signal-to-Noise Ratio, dB) dan **SSIM** (Structural Similarity Index, 0-1). Nilai yang lebih tinggi mengindikasikan kecocokan dengan citra awal.

## 2. Hasil Down Sampling
Di antara empat citra, tiga metode pooling terlihat menghasilkan hasil yang berbeda. Pada citra checkerboard, terjadi bias, yaitu citra yang tereduksi didominasi oleh kotak hitam dan putih yang melebur menjadi sepotong garis tipis diagonal
- **Max pooling**
- **Average pooling**
- **Median pooling**
## 3. Hasil Up Sampling
- **Nearest Neighbor**
- **Bilinear**
- **Bicubic**
## 4. Interaksi antara Down Sampling dan Up Sampling
## 5. Kesimpulan
