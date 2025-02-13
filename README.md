# Cash Ratio Optimization

## 📌 Overview
Kurangnya efisiensi dalam pengelolaan uang tunai di berbagai unit kerja, mesin CRM (Cash Recycle Machine), dan mesin ATM (Automated Teller Machine) dapat meningkatkan biaya operasional serta menghilangkan peluang bisnis bagi BRI. Proyek ini bertujuan untuk mengembangkan model Machine Learning yang dapat memprediksi dan mengoptimalkan pengelolaan kas untuk 31 hari ke depan.

## 🎯 Objective
Membangun model prediksi berbasis Machine Learning untuk:
- **kas_kantor** (cash in kantor)
- **kas_echannel** (cash in e-channel)

dengan periode prediksi dari **1 Oktober 2020 - 31 Oktober 2020**.

## 📂 Dataset
Dataset yang digunakan dalam kompetisi ini mencakup:
- **cash_in_kantor, cash_out_kantor** → menentukan kas_kantor
- **cash_in_echannel, cash_out_echannel** → menentukan kas_echannel

Dengan formula:
```math
kas_kantort = kas_kantort-1 + cash_in_kantort + cash_out_kantort
kas_echannelt = kas_echannelt-1 + cash_in_echannelt + cash_out_echannelt
```

## 📊 Evaluation Metric
Evaluasi model menggunakan **Root Mean Squared Logarithmic Error (RMSLE)** dengan rumus:
```math
RMSLE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (\log(p_i+1) - \log(a_i+1))^2}
```
Dimana:
- **n** : Jumlah observasi pada dataset
- **p_i** : Prediksi nilai ke-i
- **a_i** : Nilai aktual ke-i

## 📤 Submission Format
File submission harus berisi **62 baris** dengan 2 kolom: `id` dan `value`, yaitu:
- **31 baris pertama** → Prediksi `kas_kantor` untuk 1-31 Oktober 2020
- **31 baris berikutnya** → Prediksi `kas_echannel` untuk 1-31 Oktober 2020

Contoh format:
```csv
id,value
0,123456
1,234567
...
60,345678
61,456789
```

## 🚀 How to Run
1. Clone repository ini:
   ```bash
   git clone https://github.com/yourusername/cash-ratio-optimization.git
   cd cash-ratio-optimization
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Jalankan notebook untuk eksplorasi data & modeling:
   ```bash
   jupyter notebook
   ```
4. Generate submission file dengan script:
   ```bash
   python generate_submission.py
   ```

## 🔗 Reference
BRI Data Hackathon 2020 - Cash Ratio Optimization: [Kaggle Competition](https://kaggle.com/competitions/bri-data-hackathon-cr-optimization)


