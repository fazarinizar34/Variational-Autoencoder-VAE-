# Variational-Autoencoder-VAE-
# Variational Autoencoder (VAE) pada Dataset Fashion-MNIST

Repositori ini berisi implementasi **Variational Autoencoder (VAE)** menggunakan dataset **Fashion-MNIST**. Proyek ini bertujuan untuk memahami bagaimana VAE mempelajari representasi laten (latent space), membandingkannya dengan Autoencoder (AE) biasa, serta mengeksplorasi kemampuan latent space melalui interpolasi, visualisasi 2D, dan aritmetika vektor.

---

## Tujuan Proyek

1. Mengimplementasikan Variational Autoencoder (VAE) untuk data citra grayscale.
2. Membandingkan hasil rekonstruksi **VAE (bersifat halus/probabilistik)** dengan **Autoencoder (AE) deterministik**.
3. Menganalisis struktur latent space dalam 2 dimensi.
4. Melakukan eksplorasi latent space melalui:

   * Grid interpolasi
   * Visualisasi distribusi kelas
   * Latent space arithmetic

---

## Dataset

Dataset yang digunakan adalah **Fashion-MNIST**, terdiri dari 70.000 gambar grayscale berukuran 28x28 piksel yang terbagi ke dalam 10 kelas:

* T-shirt/top
* Trouser
* Pullover
* Dress
* Coat
* Sandal
* Shirt
* Sneaker
* Bag
* Ankle boot

Dataset ini dipilih karena kompleksitasnya lebih tinggi dibanding MNIST angka, sehingga cocok untuk mengevaluasi kemampuan model generatif.

---

## Arsitektur Model

### 1. Autoencoder (AE)

* Encoder memetakan citra input ke latent vector.
* Decoder merekonstruksi kembali citra dari latent vector.
* Bersifat deterministik.

### 2. Variational Autoencoder (VAE)

* Encoder menghasilkan **mean (μ)** dan **log-variance (log σ²)**.
* Sampling latent vector menggunakan **reparameterization trick**.
* Decoder menghasilkan rekonstruksi citra.
* Loss function terdiri dari:

  * Reconstruction Loss
  * KL Divergence

---

## Struktur File

```
├── 41236824_tugas_VAE.ipynb   # Notebook utama eksperimen VAE dan AE
├── GRID VA.png               # Visualisasi grid interpolasi latent space VAE
├── VAE VS SA.png             # Perbandingan citra asli, rekonstruksi VAE, dan AE
├── LSA.png                   # Latent Space Arithmetic (operasi vektor laten)
├── 2D.png                    # Distribusi latent space 2D dari VAE
└── README.md                 # Dokumentasi proyek
```

---

## Hasil dan Visualisasi

### 1. Grid Interpolasi Latent Space

Gambar `GRID VA.png` menampilkan interpolasi grid 2D pada latent space VAE. Setiap sumbu merepresentasikan satu dimensi laten. Perubahan visual yang halus menunjukkan bahwa VAE berhasil mempelajari latent space yang **kontinu dan terstruktur**.

**Insight:**

* Transisi antar bentuk objek terjadi secara gradual.
* Tidak terdapat perubahan ekstrem antar titik berdekatan.

---

### 2. Perbandingan Rekonstruksi (VAE vs AE)

Gambar `VAE VS SA.png` memperlihatkan:

* Baris 1: Gambar asli
* Baris 2: Rekonstruksi VAE (lebih halus/blurry)
* Baris 3: Rekonstruksi AE (lebih tajam)

**Insight:**

* AE menghasilkan rekonstruksi lebih tajam.
* VAE menghasilkan rekonstruksi lebih halus karena regularisasi distribusi laten.
* Trade-off antara kualitas visual dan kemampuan generatif.

---

### 3. Latent Space Arithmetic

Gambar `LSA.png` menunjukkan operasi:

```
(Mean Ankle boot − Mean Sandal) + Mean T-shirt/top
```

Hasilnya adalah citra baru yang mencerminkan transformasi fitur dari sepatu ke bentuk pakaian.

**Insight:**

* Latent space VAE bersifat semantik.
* Operasi vektor dapat merepresentasikan perubahan konsep visual.

---

### 4. Visualisasi Distribusi Latent Space 2D

Gambar `2D.png` menampilkan sebaran latent space 2D dengan pewarnaan berdasarkan kelas Fashion-MNIST.

**Insight:**

* Beberapa kelas membentuk klaster yang jelas (misalnya sepatu dan tas).
* Kelas pakaian memiliki overlap, menunjukkan kemiripan visual.
* Menunjukkan VAE mampu menangkap struktur global data.

---

## Kesimpulan

* Variational Autoencoder berhasil mempelajari representasi laten yang kontinu dan bermakna.
* Dibanding AE, VAE unggul dalam eksplorasi dan generasi data baru.
* Latent space arithmetic membuktikan adanya representasi semantik dalam ruang laten.
* Visualisasi 2D membantu memahami hubungan antar kelas.

---

## Teknologi yang Digunakan

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Google Colab

---

## Catatan

Notebook ini dirancang untuk keperluan **pembelajaran dan eksplorasi konsep deep generative model**, khususnya Variational Autoencoder.

Jika Anda tertarik mengembangkan lebih lanjut, eksperimen dapat diperluas ke:

* Latent dimension lebih tinggi
* Conditional VAE (CVAE)
* Dataset lain (misalnya CIFAR-10)

---

📌 *Silakan gunakan README ini sebagai dokumentasi utama saat mengunggah proyek ke GitHub.*
