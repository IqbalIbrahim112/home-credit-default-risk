# 🏦 Home Credit Default Risk: Predictive Credit Scoring Model
> **Empowering Financial Inclusion through Advanced Machine Learning Analytics**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-1572B6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

## 📌 Business Overview
Proyek ini bertujuan untuk mengatasi tantangan inklusi keuangan dengan membangun model prediksi risiko gagal bayar (*default*) bagi pemohon pinjaman. Menggunakan dataset dari Home Credit, analisis ini mengidentifikasi pola perilaku nasabah untuk membedakan antara nasabah yang mampu membayar tepat waktu (**TARGET 0**) dan nasabah yang memiliki kesulitan pembayaran (**TARGET 1**).

---

## 📊 Dataset Insights
Berdasarkan eksplorasi data terhadap **307.511 catatan aplikasi**:
* **Imbalance Ratio**: Terdapat ketidakseimbangan kelas yang signifikan, di mana hanya **8,07%** pemohon yang tergolong berisiko tinggi (gagal bayar).
* **Key Risk Drivers**: 
    * **External Sources**: Variabel `EXT_SOURCE_1`, `2`, dan `3` merupakan indikator terkuat dengan korelasi negatif yang tinggi terhadap risiko gagal bayar.
    * **Demografi & Stabilitas**: Nasabah berusia muda (`DAYS_BIRTH`) dan mereka yang sering mengganti telepon (`DAYS_LAST_PHONE_CHANGE`) cenderung memiliki profil risiko yang lebih tinggi secara statistik.

---

## 🛠️ Data Science Pipeline
Alur kerja pengembangan model dirancang untuk memastikan kualitas data dan performa model yang stabil:

1.  **Anomaly Handling**: Mengatasi nilai tidak wajar pada fitur `DAYS_EMPLOYED` (anomali 365.243 hari) dengan teknik *flagging* dan penggantian nilai.
2.  **Advanced Preprocessing**:
    * **Winsorization**: Penanganan *outliers* menggunakan batas IQR untuk menstabilkan distribusi fitur numerik.
    * **Strategic Imputation**: Pengisian *missing values* menggunakan strategi *mean imputation*.
    * **Encoding**: Transformasi variabel kategorikal melalui *Label Encoding* dan pemetaan biner.
3.  **Class Imbalance Strategy**: 
    * Implementasi **SMOTE** (*Synthetic Minority Over-sampling Technique*) untuk model Logistic Regression.
    * Optimasi parameter `scale_pos_weight` pada model XGBoost.

---

## 📈 Model Performance & Comparison
Evaluasi dilakukan menggunakan **Stratified K-Fold Cross Validation (5-Splits)** dengan metrik utama **AUC-ROC**:

| Model Algorithm | Mean Accuracy | Mean Log Loss | Mean AUC-ROC |
| :--- | :---: | :---: | :---: |
| **Logistic Regression (SMOTE)** | 0.6890 | 0.5924 | 0.7343 |
| **XGBoost Classifier** | **0.7419** | **0.5159** | **0.7366** |

> **Analisis**: Model **XGBoost** memberikan performa terbaik dengan tingkat akurasi yang lebih tinggi dan Log Loss yang lebih rendah dibandingkan model baseline.

---

## 💡 Key Business Recommendations
* **Prioritas Validasi Data**: Fokuskan verifikasi mendalam pada pemohon dengan skor *External Source* yang rendah, karena fitur ini memiliki daya prediksi terkuat.
* **Segmentasi Risiko**: Perketat syarat jaminan atau durasi tenor bagi segmen nasabah muda yang secara statistik menunjukkan probabilitas *default* lebih tinggi.
* **Efisiensi Operasional**: Model XGBoost dapat diintegrasikan sebagai sistem skor kredit otomatis untuk mempercepat proses persetujuan pinjaman tanpa meningkatkan paparan risiko.

---

## 📫 Contact
**Iqbal Tri Wicaksono**
* **GitHub**: [IqbalIbrahim112](https://github.com/IqbalIbrahim112)
* **Email**: iqbaltriwicaksono112@gmail.com

---
*Generated based on Home Credit Score Card Model Analysis.*
