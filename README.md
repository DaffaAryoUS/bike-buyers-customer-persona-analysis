# Bike Buyers Customer Persona Analysis 🚲🎯

## 📌 Project Overview
Proyek ini bertujuan untuk menentukan **customer persona** pembeli sepeda melalui analisis mendalam terhadap informasi pribadi responden. Dengan memahami karakteristik unik dari konsumen yang memiliki tingkat konversi tinggi, perusahaan dapat menyusun strategi komunikasi pemasaran yang lebih personal, efektif, dan tepat sasaran demi mendorong pertumbuhan bisnis.

---

## ⚠️ Problem Statement
Berdasarkan riset dari *McKinsey & Company (2021)*, personalisasi merupakan pendorong utama pertumbuhan bisnis di mana perusahaan yang unggul dalam segmentasi mampu mencapai pendapatan **40% lebih tinggi**. Sebanyak 71% konsumen mengharapkan perusahaan memberikan interaksi yang terpersonalisasi, dan 76% merasa frustrasi jika pendekatan pemasaran terlalu umum (*generic*). Oleh karena itu, identifikasi persona pembeli menjadi sangat krusial agar pendekatan pemasaran tidak lagi bersifat generalisasi melainkan berbasis data preferensi yang kuat.

---

## 📂 About Data
* **Data File:** Bike Buyers
* **Format File:** Comma-Separated Values (CSV)
* **Baris:** 1,000
* **Kolom:** 13
* **Tahun Publikasi (Last Update):** 2020
* **Sumber:** [Kaggle]([https://www.kaggle.com/](https://www.kaggle.com/datasets/heeraldedhia/bike-buyers/data?select=bike_buyers.csv))

---

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Libraries:** Pandas (Data Preprocessing & Cleaning), NumPy, Shapiro & Spearman (Statistical Hypothesis Testing)
* **Environment:** Jupyter Notebook
* **Typography & Reporting:** Times New Roman Style Report (2026)

---

## 💡 Key Insights & Data Issues

### 1. Data Issues & Handling (Pembersihan Data)
* **Missing Values:** Ditemukan nilai kosong sebesar 5.3% yang tersebar di beberapa kolom, seperti `Cars` (0.9%), `Children` (0.8%), `Age` (0.8%), dan `Income` (0.6%). Kolom numerik diimputasi menggunakan nilai *Median* agar lebih tahan terhadap pencilan (*outlier*).
* **Kasus Khusus Gender & Marital Status:** `Gender` yang kosong diisi dengan kategori baru *"Unknown"* untuk menghindari bias data. Sementara `Marital_Status` yang kosong diimputasi secara logis (*Imputation Method*): jika status `Home_Owner == 'Yes'`, maka diisi *"Married"* (berdasarkan tren basis data sebesar 64%).
* **Ketidaksesuaian Tipe Data:** Mengubah tipe data kolom `Children`, `Cars`, dan `Age` dari *float* menjadi *integer* setelah proses pembersihan selesai agar selaras dengan karakteristik data bilangan bulat.

### 2. Eksplorasi & Distribusi Data (Red Flags)
* **Uji Normalitas (Shapiro Test):** Hasil uji statistik Shapiro menunjukkan bahwa seluruh kolom numerik memiliki *P-Value < 0.05*, yang berarti **seluruh distribusi data numerik tidak normal** (cenderung *right-skewed* pada kolom `Income`, `Age`, dan `Cars`).
* **Analisis Korelasi Kuat:** Berdasarkan *Spearman Correlation*, hubungan terkuat ditemukan pada kolom `Age` & `Children` (0.53) serta `Cars` & `Income` (0.43). Semakin tinggi pendapatan seseorang, terdapat kecenderungan linier jumlah kepemilikan mobil yang semakin banyak.

### 3. Paradoks Kepemilikan Mobil vs Pembelian Sepeda
* Berdasarkan total populasi, hanya **48.1% (481 responden)** yang membeli sepeda.
* Dari 481 orang pembeli tersebut, terdapat korelasi negatif antara kepemilikan mobil dan konversi sepeda (-0.20). Responden yang **tidak memiliki mobil memiliki proporsi konversi tertinggi sebesar 61.76%** untuk membeli sepeda. 

### 4. Karakteristik Demografis & Geografis Pembeli
* **Jarak Tempuh (*Commute Distance*):** Mayoritas pembeli sepeda (41.6%) hanya melakukan perjalanan dekat sekitar **0 - 1 Miles**. Namun, peluang konversi tertinggi secara spesifik dipegang oleh kelompok jarak **2 - 5 Miles** dengan angka konversi 58.64%.
* **Edukasi & Status Pekerjaan:** Responden dengan latar belakang pendidikan *Bachelors Degree* menjadi mayoritas pembeli (35.1%) dengan tingkat konversi 55.23%. Di sisi lain, kategori pekerjaan *Professional* mendominasi pembelian sebesar 31.2%.
* **Faktor Geografis (Region):** Wilayah *North America* menyumbang kuantitas pembeli sepeda terbesar secara volume (45.7% dari total pembeli), namun wilayah *Pacific* memegang rekor tingkat konversi atau persentase pembelian tertinggi sebesar **58.85%**.

---

## 🚀 Actionable Recommendations

### 1. Definisi Persona Pembeli Sepeda (Ideal Customer Profile)
Targetkan kampanye pemasaran secara spesifik kepada profil pelanggan ideal berikut:
* **Gender:** Male / Female
* **Age Range:** 30 - 50 Tahun (*Middle-Aged*)
* **Occupation:** Professional
* **Commute Distance:** 0 - 5 Miles (*Urban/City Commuting*)
* **Income Range:** $50,000 - $170,000 (*Middle to Ultra High Income*)
* **Education:** Kuliah (*Enroll College / Bachelors / Graduate*)
* **Car Owner:** Tidak memiliki mobil (*No*)

### 2. Strategi Alokasi Target Pasar Berdasarkan Wilayah (Region)
* **Jangka Pendek (*Core Market - Pacific*):** Fokuskan kampanye pemasaran digital agresif di wilayah **Pacific** karena memiliki tingkat konversi alami yang sangat tinggi (58.85%) untuk memanen profit cepat.
* **Jangka Panjang (*Volume Market - North America*):** Lakukan edukasi pasar (*market education*) yang lebih intensif di **North America** untuk mendongkrak tingkat konversinya yang saat ini masih tertahan di 49.33%, mengingat wilayah ini memegang populasi terbesar (50.8%).

### 3. Restrukturisasi & Inovasi Produk
* **Peluncuran Urban & Folding Bike:** Mengingat persona pembeli mayoritas berkomuter di jarak pendek (0 - 5 Miles) dan bekerja sebagai profesional yang tidak memiliki mobil, luncurkan lini produk sepeda perkotaan (*urban bike*) atau sepeda lipat (*folding bike*) yang praktis untuk transportasi harian atau gaya hidup sehat.
* **Pricing Tiering:** Sesuaikan rentang harga produk dengan kategori pendapatan *Middle Income* agar tetap kompetitif namun menguntungkan bagi perusahaan.
