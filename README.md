# 📊 Data Visualization & EDA: Bike Buyers Survey 

## 🎯 1. Problem Statement & Objective
Berdasarkan riset dari McKinsey & Company (2021), personalisasi merupakan pendorong utama pertumbuhan bisnis, di mana perusahaan yang unggul dalam segmentasi mampu mencapai pendapatan 40% lebih tinggi. 
- **Objective:** Analisis ini berfokus pada informasi pribadi responden untuk menentukan **Persona Pembeli Sepeda** agar strategi komunikasi pemasaran perusahaan dapat berjalan tepat sasaran (tidak bersifat *generic*).

---

## 🛠️ 2. Tech Stack & Dataset Overview
- **Tools & Language:** Python (Jupyter Notebook), Pandas, Matplotlib, Seaborn, Canva (for Reporting).
- **Dataset:** 1,000 baris dan 13 kolom format CSV bersumber dari Kaggle (Tahun Publikasi: 2020).

---

## 🔄 3. Data Analytics Workflow

### A. Data Preparation & Cleaning
1. **Column Renaming:** Menghapus spasi tersembunyi dan mengganti spasi antar kata dengan underscore `_` untuk menghindari *syntax error* di Python.
2. **Missing Value Handling (Total 5.3% data kosong):**
   - Kolom numerik (`Cars`, `Children`, `Age`, `Income`) diisi menggunakan nilai **Median** karena lebih tahan terhadap *outlier*.
   - Kolom `Gender` diisi dengan kategori baru **"Unknown"** untuk mencegah bias.
   - Kolom `Marital_Status` dan `Home_Owner` diisi menggunakan metode **Imputation** berbasis logika korelasi data yang memiliki probabilitas kebenaran tinggi (64% & 74%).
3. **Data Type Validity:** Mengubah tipe data kolom `Children`, `Cars`, dan `Age` dari `float64` menjadi `int64` setelah data terisi penuh.

### B. Feature Engineering
Membuat 4 kolom kategori baru untuk mempermudah segmentasi:
- `Income_Category` (Low, Middle, High, Ultra High)
- `Age_Group` (Young Adult, Middle Aged, Senior, Old)
- `Having_Children` (Yes/No) & `Car_Owner` (Yes/No)
- Melakukan **Label Encoding** untuk data biner/nominal tanpa tingkatan, dan **Ordinal Encoding** untuk data multiclass yang memiliki tingkatan (`Education` & `Commute_Distance`).

### C. Data Exploration & Hypothesis Testing
- **Distribution Test:** Menggunakan *Probability Mass Function (PDF)* dan **Shapiro Test**, ditemukan bahwa seluruh kolom numerik memiliki distribusi yang tidak normal ($P\text{-Value} < 0.05$).
- **Hypothesis Testing:** Menggunakan **Spearman Correlation** (Non-Parametrik):
  - Hubungan *Age vs Children* ($0.53$) & *Cars vs Income* ($0.43$) menunjukkan korelasi positif tingkat **Sedang**.
  - Hubungan status pembelian sepeda dengan jumlah mobil dan jarak tempuh menunjukkan tren **korelasi negatif**.

---

## 📈 4. Key Insights
1. **Car Owner:** Responden yang tidak memiliki mobil memiliki tingkat konversi pembelian sepeda yang lebih tinggi, mencapai **61.76%**.
2. **Commute Distance:** Kategori jarak tempuh **2 - 5 Miles** memiliki potensi konversi tertinggi untuk membeli sepeda (**58.64%**).
3. **Income:** Kategori pendapatan *Ultra High* dan *Middle* menunjukkan potensi konversi yang tinggi, mengindikasikan pembelian sepeda untuk kebutuhan *lifestyle* atau kesehatan.
4. **Education & Age:** Kelompok berpendidikan tinggi (Bachelors mencapai **55.23%**)[cite: 2] dan rentang usia *Middle-Aged* (31 - 50 tahun mencapai **54.05%**) menjadi kelompok mayoritas pembeli sepeda.

---

## 💡 5. Conclusion & Actionable Suggestions

### 🚴 Persona Pembeli Sepeda: "Practical Urban Commuter"
- **Karakteristik:** Berusia 30 - 50 tahun (*Middle-Aged*), bekerja sebagai *Professional*, menempuh pendidikan tinggi, berjarak tempuh 0 - 5 Miles, pendapatan kelas menengah ke atas, dan tidak memiliki mobil.

### 🚀 Rekomendasi Bisnis:
1. **Product Development:** Meluncurkan tipe sepeda perkotaan (*urban/folding bike*) yang cocok digunakan untuk komuter dalam kota.
2. **Marketing Campaign:** Menargetkan wilayah **Pacific** sebagai *Core Market* jangka pendek karena tingkat konversi tingginya (**58.85%**), serta melakukan edukasi pasar di **North America** untuk jangka panjang.
3. **Pricing Strategy:** Menghadirkan rentang harga ekonomis untuk kategori pendapatan *Middle* serta paket *bundling* aksesoris premium untuk kategori pendapatan *Ultra High*.

---
*Presentasi laporan visual lengkap untuk proyek ini dapat diakses melalui [Tautan Canva Portofolio Saya](https://bit.ly/BikeBuyersPersona).*
