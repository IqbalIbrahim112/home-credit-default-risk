# 🏦 Home Credit Default Risk: Advanced Credit Scoring Analytics
> **Predicting Creditworthiness to Enhance Financial Inclusion and Risk Management**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Random Forest](https://img.shields.io/badge/Model-Random%20Forest-green?style=for-the-badge)
![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-blue?style=for-the-badge&logo=kaggle)

## 📌 Executive Summary
Proyek ini berfokus pada pengembangan model *machine learning* untuk memprediksi risiko gagal bayar (*default*) pada pemohon pinjaman di **Home Credit**. Tantangan utama dalam industri kredit adalah memastikan nasabah yang mampu membayar tidak ditolak, sementara risiko dari nasabah yang berpotensi gagal bayar dapat dimitigasi.

Melalui pendekatan berbasis data, proyek ini mengolah ribuan baris data aplikasi untuk menghasilkan skor kredit yang objektif, transparan, dan dapat dipertanggungjawabkan.

---

## 🛠️ Machine Learning Pipeline
Alur kerja pengembangan model mencakup tahapan *end-to-end* sebagai berikut:

1.  **Exploratory Data Analysis (EDA):** Identifikasi pola perilaku nasabah, distribusi target, dan analisis korelasi fitur.
2.  **Data Preprocessing:**
    * Handling missing values & outliers.
    * Feature Engineering (pembuatan rasio keuangan seperti `CREDIT_TERM` & `ANNUITY_INCOME_PERCENT`).
    * Categorical Encoding & Feature Scaling.
3.  **Modeling & Optimization:** Eksperimen menggunakan *Baseline Model* (Logistic Regression) hingga *Ensemble Method* (Random Forest).
4.  **Evaluation:** Menggunakan metrik **ROC-AUC** untuk mengukur kemampuan model dalam membedakan kelas nasabah.

---

## 📊 Model Performance & Comparison
Model dievaluasi secara ketat untuk memastikan stabilitas prediksi.

| Model Algorithm | Training ROC-AUC | Validation/Test ROC-AUC | Status |
| :--- | :---: | :---: | :---: |
| **Logistic Regression** | 0.614 | 0.601 | Stable (Baseline) |
| **Random Forest Classifier** | **1.000** | **0.709** | **Best Performer** |

> *Note: Model Random Forest menunjukkan performa yang sangat kuat dalam menangkap pola kompleks pada data training, dengan skor validasi yang kompetitif di angka 0.709.*

---

## 🔑 Key Features Importance
Berdasarkan analisis model, berikut adalah 5 fitur teratas yang paling krusial dalam menentukan kelayakan kredit nasabah:

1.  **EXT_SOURCE (2 & 3):** Skor normalisasi dari sumber data eksternal (indikator terkuat).
2.  **DAYS_BIRTH:** Usia nasabah (nasabah lebih muda cenderung memiliki risiko lebih tinggi).
3.  **DAYS_EMPLOYED:** Durasi masa kerja yang menunjukkan stabilitas finansial.
4.  **CREDIT_TERM:** Rasio antara jumlah pinjaman dengan durasi pembayaran.
5.  **ANNUITY_INCOME_PERCENT:** Beban cicilan dibandingkan dengan total pendapatan nasabah.

---

## 💡 Business Insights & Recommendations
Berdasarkan hasil pemodelan, strategi bisnis yang direkomendasikan adalah:

* **Segmentasi Usia:** Melakukan validasi tambahan atau persyaratan jaminan yang lebih ketat bagi segmen nasabah muda karena probabilitas gagal bayar yang lebih tinggi secara statistik.
* **Threshold Debt-to-Income:** Menetapkan batas maksimal rasio pinjaman terhadap pendapatan untuk mencegah *over-leveraging* pada nasabah.
* **Optimasi Data Eksternal:** Meningkatkan integrasi dengan penyedia data pihak ketiga (External Sources) karena terbukti memiliki korelasi tertinggi terhadap akurasi prediksi.

---

## 📂 Repository Structure
```bash
.
├── home-credit-analysis.ipynb   # Main Jupyter Notebook
├── README.md                    # Project Documentation
└── [data]                       # Dataset source (link provided)
