## Analisis Perbandingan Varian Naive Bayes untuk Deteksi Berita Hoaks Berbahasa Indonesia
Repositori ini berisi source code dan dokumentasi lengkap mengenai sistem deteksi berita bohong (hoaks) menggunakan algoritma Naive Bayes Classifier. Penelitian ini mengeksplorasi efektivitas tiga varian algoritma—Multinomial, Bernoulli, dan Gaussian—serta membandingkan kinerjanya pada kondisi dataset yang seimbang (balanced) dan tidak seimbang (unbalanced).
### 📌 Deskripsi Proyek
Meningkatnya penyebaran misinformasi di Indonesia mendorong perlunya solusi otomatis berbasis Natural Language Processing (NLP). Proyek ini mengembangkan model klasifikasi teks untuk membedakan antara berita valid dan hoaks dengan fokus pada pencapaian nilai Recall tertinggi untuk meminimalisir berita hoaks yang lolos dari deteksi.
### 🛠️ Metodologi
Alur kerja sistem mengikuti standar pemrosesan data teks ilmiah:
1. **Preprocessing:**
   - Case Folding (Penyeragaman huruf kecil).
   - Tokenizing (Pemecahan kalimat menjadi kata).
   - Stopword Removal (Penghapusan kata umum tak bermakna menggunakan library Sastrawi).
   - Stemming (Pengubahan kata ke bentuk dasar menggunakan library Sastrawi).
2. **Ekstraksi Fitur:** Menggunakan TF-IDF (Term Frequency-Inverse Document Frequency) dengan batasan 5.000 fitur.
3. **Klasifikasi:** Implementasi Teorema Bayes dalam tiga varian:
### 📊 Dataset
- **Sumber:** Kaggle Dataset.
- **Volume:** 27.433 artikel berita berbahasa Indonesia.
- **Skenario:**
  - Unbalanced (Proporsi asli 2:1).
  - Balanced (Proporsi seimbang 1:1).
- **Unduh:** [Dataset](https://drive.google.com/file/d/1I_X1VKekoi-K8GuuIbBViu1jUipxJeJP/view?usp=sharing)
### 📈 Hasil Eksperimen
Berdasarkan pengujian, diperoleh hasil performa metrik sebagai berikut:

**Temuan Kunci:**

| Model | Accuracy | Precision | Recall | F1-Score
| -------- | -------- | -------- | -------- | -------- |
| Multinomial (Balanced) | 0.942 | **0.959** | 0.924 | **0.941** |
| Bernoulli (Balanced) | 0.897 | 0.853 | **0.960**| 0.903 |
| Gaussian (Balanced) | 0.905 | 0.926 | 0.879 | 0.902 |

- Multinomial NB unggul dalam akurasi umum dan deteksi berita valid.
- Bernoulli NB merupakan model terbaik untuk deteksi preventif karena memiliki nilai Recall tertinggi (96,06%), artinya sangat efektif menangkap berita hoaks agar tidak lolos dari sistem.
- Analisis Word Cloud menunjukkan berita hoaks sering menggunakan kata-kata subjektif dan sensasional, sementara berita valid didominasi istilah institusional.
### 🚀 Cara Menjalankan
1. Clone repositori ini.
2. Buka file .ipynb di Google Colab.
3. Pastikan dataset telah diunggah ke Google Drive Anda pada path yang sesuai.
4. Jalankan sel secara berurutan mulai dari instalasi library hingga pengujian manual.
