# 🏦 Home Credit Default Risk: Predictive Credit Scoring Model
> **Optimizing Financial Inclusion through Advanced Machine Learning & Robust Credit Risk Analytics**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-1572B6?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

---

## 📌 Business Overview
Home Credit memiliki misi besar untuk memberikan akses finansial kepada masyarakat yang belum terjangkau perbankan (*unbanked population*). Namun, tantangan operasional utama adalah memitigasi risiko kredit macet (**default**) tanpa menghambat kecepatan proses persetujuan.

**Project Goal:**
Membangun sistem skor kredit otomatis berbasis **Machine Learning** yang mampu membedakan pemohon berkemampuan bayar (**TARGET 0**) dan pemohon berisiko tinggi (**TARGET 1**) secara akurat menggunakan metrik **AUC-ROC**.

---

## 📊 Dataset & Exploratory Data Analysis (EDA)
Analisis dilakukan pada dataset historis mencakup **307.511 aplikasi** dengan **122 fitur** kompleks.

### **Key Insights:**
* **Class Imbalance**: Terdapat ketidakseimbangan kelas yang signifikan di mana hanya **8,07%** nasabah yang tercatat gagal bayar. Hal ini memerlukan penanganan khusus melalui *sampling* atau pembobotan model.
* **Risk Indicators**: 
    * **External Sources**: `EXT_SOURCE_1, 2, 3` adalah prediktor terkuat. Semakin rendah skor ini, semakin tinggi peluang nasabah gagal bayar.
    * **Demografi**: Pemohon berusia muda (`DAYS_BIRTH`) dan mereka dengan masa kerja singkat (`DAYS_EMPLOYED`) secara statistik menunjukkan kecenderungan risiko yang lebih tinggi.
    * **Stabilitas**: Nasabah yang sering mengganti telepon genggam memiliki korelasi positif terhadap risiko kredit.

---

## 🛠️ Data Science Pipeline
Proses pengolahan data dirancang secara sistematis untuk memastikan integritas hasil:

1.  **Anomaly Detection**: Menangani nilai anomali **365.243 hari** pada fitur `DAYS_EMPLOYED` dengan melakukan konversi menjadi *null* dan pengisian nilai yang logis.
2.  **Robust Preprocessing**:
    * **Winsorization**: Menangani *outliers* pada **101 fitur** numerik menggunakan teknik batasan IQR.
    * **Strategic Imputation**: Mengisi *missing values* menggunakan nilai rata-rata (*Mean Imputation*) untuk menjaga distribusi data.
    * **Feature Encoding**: Implementasi *Label Encoding* dan *Binary Mapping* pada fitur kategorikal.
3.  **Handling Imbalance**: 
    * Penerapan **SMOTE** (*Synthetic Minority Over-sampling*) untuk model Logistic Regression.
    * Konfigurasi parameter `scale_pos_weight` pada model XGBoost untuk fokus pada kelas minoritas.

---

## 📈 Model Performance Benchmark
Evaluasi dilakukan menggunakan **Stratified K-Fold Cross Validation (5-Splits)**:

| Algorithm | Mean Accuracy | Mean Log Loss | Mean AUC-ROC |
| :--- | :---: | :---: | :---: |
| Logistic Regression (SMOTE) | 0.6890 | 0.5924 | 0.7343 |
| **XGBoost Classifier** | **0.7419** | **0.5159** | **0.7366** |

> **Highlight**: Model **XGBoost** terpilih sebagai model final karena memberikan kestabilan prediksi yang lebih tinggi (Low Log Loss) dan performa pemisahan kelas yang lebih baik (Higher AUC). Pada pengujian data tertentu, model mampu mencapai skor **AUC hingga 0.85**.

---

## 🧠 Feature Importance (XGBoost)
Model mengidentifikasi 5 faktor utama yang paling memengaruhi keputusan kredit:
1.  **EXT_SOURCE (1, 2, 3)**: Penilaian dari biro kredit/pihak ketiga.
2.  **Education Type**: Tingkat pendidikan nasabah.
3.  **Days Employed**: Total durasi bekerja (stabilitas finansial).
4.  **Days Birth**: Usia nasabah saat pengajuan.
5.  **AMT_ANNUITY**: Besaran cicilan yang harus dibayarkan.

---

## 💡 Key Business Recommendations
* 🚀 **Otomatisasi Underwriting**: Integrasikan model XGBoost ke dalam sistem *Decision Engine* untuk mempercepat proses persetujuan aplikasi tanpa intervensi manual yang berlebihan.
* 🔍 **Data Enrichment**: Memperkuat kerja sama dengan pihak ketiga untuk validasi `EXT_SOURCE` karena variabel ini adalah filter risiko paling krusial.
* 🛡️ **Segmented Policy**: Terapkan kebijakan pengetatan (seperti DP lebih tinggi atau tenor lebih singkat) bagi nasabah usia muda atau dengan masa kerja < 2 tahun.
* 🎁 **Incentive Program**: Berikan suku bunga kompetitif bagi nasabah dengan profil "Aman" (pendidikan tinggi/kepemilikan aset) guna ekspansi pasar yang sehat.

---

## 📫 Contact
**Iqbal Tri Wicaksono Ibrahim**
* **LinkedIn**: [Iqbal Tri Wicaksono](https://linkedin.com/in/iqbaltriwicaksono)
* **GitHub**: [IqbalIbrahim112](https://github.com/IqbalIbrahim112)
* **Email**: iqbaltriwicaksono112@gmail.com

---
*Generated as part of the Home Credit Scorecard Analysis Project | Rakamin Academy*
