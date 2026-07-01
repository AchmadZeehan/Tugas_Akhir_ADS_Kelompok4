# 🚆 Proyek Analisis Data Statistik – Kelompok 4

**Analisis Perbedaan Rata-Rata Harga Tiket Kereta Api Berdasarkan Kelas Layanan Ekonomi, Bisnis, dan Eksekutif**

---

## 📋 Identitas Proyek

| **Nama/NIM** | **Kelas** | **Dosen Pengampu** | **Semester** |
|--------------|-----------|-------------------|--------------|
| **Achmad Zeehan Wardana** (0102525001) | IF25A | **Tri Aji Nugroho, S.T., M.T.** | 2 / 2025–2026 |
| **Adnan** (0102525002) | | | |
| **Habibie Rahman Abdillah** (0102525006) | | | |
| **Miyv Faissal** (0102525008) | | | |

---

## 📌 Latar Belakang

Kereta api merupakan moda transportasi publik andalan di Indonesia, terutama di Pulau Jawa. PT KAI menyediakan tiga kelas layanan  Ekonomi, Bisnis, dan Eksekutif  dengan harga tiket dan fasilitas yang berbeda.  
Berdasarkan data 200 jadwal keberangkatan pada Juni 2026, terlihat kesenjangan harga yang mencolok:

- **Ekonomi** rata-rata Rp148.600  
- **Bisnis** rata-rata Rp220.958 (+48,69% dari Ekonomi)  
- **Eksekutif** rata-rata Rp386.713 (+75,02% dari Bisnis, atau +160% dari Ekonomi)

Penelitian ini bertujuan menguji secara statistik apakah perbedaan harga tersebut **signifikan** dan apakah pola yang sama juga terjadi pada ketersediaan kursi.

---

## 🎯 Rumusan Masalah & Hipotesis

**Rumusan Masalah:**
1. Apakah terdapat perbedaan rata-rata harga tiket yang signifikan antara kelas Ekonomi, Bisnis, dan Eksekutif?
2. Apakah rata-rata kursi tersedia berbeda secara signifikan antar kelas?

**Hipotesis (Harga Tiket):**
- **H₀** : μ_Ekonomi = μ_Bisnis = μ_Eksekutif  
- **H₁** : Minimal satu kelas memiliki rata-rata harga yang berbeda.

**Hipotesis (Kursi Tersedia):**
- **H₀** : Rata-rata kursi tersedia sama untuk semua kelas.  
- **H₁** : Rata-rata kursi tersedia berbeda antar kelas.

---

## 📊 Data

- **Sumber**: Dataset simulasi `dataset_tiket_kereta.readable.csv` (berdasarkan data jadwal KAI).
- **Observasi**: 200 baris (jadwal keberangkatan).
- **Variabel utama**:  
  - `Kelas` (Kategorikal: Ekonomi, Bisnis, Eksekutif) – **Variabel Independen**  
  - `Harga Tiket` (Numerik) – **Variabel Dependen 1**  
  - `Kursi Tersedia` (Numerik) – **Variabel Dependen 2**

Tidak terdapat *missing values* pada dataset.

---

## 🛠 Metode Statistik

| No | Metode | Referensi Bab | Tujuan |
|----|--------|---------------|--------|
| 1 | **Statistik Deskriptif** | Bab 2–3 | Menggambarkan data (mean, median, std, boxplot, bar chart) |
| 2 | **Uji ANOVA Satu Arah** | Bab 10 | Menguji perbedaan rata-rata antar tiga kelas (parametrik) |
| 3 | **Uji Kruskal-Wallis** | Bab 11 | Alternatif non-parametrik jika asumsi ANOVA tidak terpenuhi |

---

## 📈 Hasil Analisis

### A. Statistik Deskriptif

| Kelas | n | Rata-rata Harga | Median Harga | Std. Dev Harga | Rata-rata Kursi | Median Kursi |
|-------|---|----------------|--------------|----------------|-----------------|--------------|
| Ekonomi | 65 | Rp148.600 | Rp148.000 | Rp38.823 | 160,8 | 159,0 |
| Bisnis | 48 | Rp220.958 | Rp210.500 | Rp65.930 | 93,9 | 97,5 |
| Eksekutif | 87 | Rp386.713 | Rp409.000 | Rp109.681 | 66,3 | 67,0 |

### B. Uji ANOVA

| Variabel | F-Statistic | p-value | Kesimpulan (α=0.05) |
|----------|-------------|---------|----------------------|
| Harga Tiket | **166,5948** | **4,45×10⁻⁴³** | Tolak H₀ – Signifikan |
| Kursi Tersedia | **708,6998** | **1,04×10⁻⁹⁰** | Tolak H₀ – Signifikan |

### C. Uji Kruskal-Wallis (Penguat)

| Variabel | H-Statistic | p-value | Kesimpulan (α=0.05) |
|----------|-------------|---------|----------------------|
| Harga Tiket | **119,7365** | **9,99×10⁻²⁷** | Tolak H₀ – Signifikan |
| Kursi Tersedia | **163,1332** | **3,77×10⁻³⁶** | Tolak H₀ – Signifikan |

---

## ✅ Kesimpulan

1. **Harga tiket berbeda signifikan antar kelas** – Eksekutif 160% lebih mahal dari Ekonomi dan 75% lebih mahal dari Bisnis.  
2. **Kursi tersedia berbanding terbalik dengan harga** – Ekonomi memiliki kursi terbanyak (160,8) namun harga terendah, sedangkan Eksekutif kursi tersedikit (66,3) namun harga tertinggi.  
3. **Rekomendasi**:  
   - PT KAI perlu mengkomunikasikan justifikasi selisih harga secara transparan.  
   - Regulator perlu mengkaji disparitas harga agar aksesibilitas publik tetap terjaga.  
   - Penelitian lanjut dapat menambahkan variabel jarak, durasi, dan fasilitas onboard untuk model yang lebih prediktif.

---

## 🖥️ Cara Menjalankan Proyek

### 1. Jalankan Notebook (Google Colab / Local)
- Buka file `Proyek_ADS_KEL4 (2).ipynb` di Google Colab atau Jupyter.
- Jalankan semua cell secara berurutan.
- Upload file `dataset_tiket_kereta.readable.csv` saat diminta.

### 2. Lihat Website Interaktif
- Buka file `index.html` di browser.
- Atau akses via GitHub Pages: [https://username.github.io/repo-name/](https://username.github.io/repo-name/) (sesuaikan dengan link deployment Anda).

---

## 📁 Struktur File Repository
