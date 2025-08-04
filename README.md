# 🏠 Home Credit Default Risk — Credit Scoring Project

Proyek ini bertujuan membangun model prediksi risiko gagal bayar pada pinjaman individu menggunakan dataset **Home Credit Default Risk** dari Kaggle. Notebook ini memuat proses **EDA**, **data preprocessing**, **pemodelan**, dan **rekomendasi bisnis** untuk mendukung pengambilan keputusan kredit yang lebih cermat dan terukur.

---

## 📊 Dataset

- **Sumber:** [Home Credit Default Risk — Kaggle](https://www.kaggle.com/competitions/home-credit-default-risk)
- **File Utama:**
  - `application_train.csv` — Data latih dengan label TARGET.
  - `application_test.csv` — Data uji tanpa label.
- **Fokus Target:**
  - `TARGET = 0` → Nasabah membayar pinjaman dengan lancar.
  - `TARGET = 1` → Nasabah gagal bayar.

---

## ⚙️ Model

- **Model Akhir:** Random Forest Classifier  
  - ROC AUC (Train): **1.000**  
  - ROC AUC (Valid): **0.709**
- **Baseline:** Logistic Regression  
  - ROC AUC (Train): **0.614**  
  - ROC AUC (Test): **0.601**

---

## 🔑 Fitur Penting

Berikut 10 fitur teratas yang paling berkontribusi pada prediksi risiko:

1. `EXT_SOURCE_2`
2. `EXT_SOURCE_3`
3. `DAYS_ID_PUBLISH`
4. `DAYS_BIRTH`
5. `DAYS_REGISTRATION`
6. `CREDIT_TERM`
7. `ANNUITY_INCOME_PERCENT`
8. `CREDIT_INCOME_PERCENT`
9. `DAYS_EMPLOYED`
10. `DAYS_LAST_PHONE_CHANGE`

Fitur-fitur ini membantu perusahaan memfokuskan validasi dokumen, verifikasi data eksternal, dan penilaian kemampuan bayar calon peminjam.

---

## 📌 Insight Utama

- **Nasabah Muda Lebih Berisiko:**  
  Nasabah berusia muda cenderung memiliki peluang gagal bayar lebih tinggi dibanding nasabah usia matang.

- **Rasio Pinjaman-Pendapatan:**  
  Semakin besar proporsi pinjaman dibandingkan pendapatan, semakin tinggi risiko gagal bayar.

---

## ✅ Rekomendasi Bisnis

- Perketat persyaratan pinjaman untuk segmen nasabah berusia muda.
- Tetapkan rasio pinjaman terhadap pendapatan maksimum untuk menekan risiko gagal bayar.
- Fokus pada verifikasi data eksternal untuk memastikan validitas informasi kredit.

---

## 🙌 Penutup

Terima kasih telah membaca!  
Proyek ini diharapkan dapat membantu perusahaan mengambil keputusan kredit yang lebih tepat sasaran dan minim risiko.

---

## 📫 Kontak

- **GitHub:** [IqbalIbrahim112](https://github.com/IqbalIbrahim112)
- **Email:** *iqbaltriwicaksono112@gmail.com*
