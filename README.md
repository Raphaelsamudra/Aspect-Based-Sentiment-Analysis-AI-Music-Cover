# 🎵 Aspect-Based Sentiment Analysis of AI Music Covers

Analisis sentimen berbasis aspek terhadap komentar YouTube pada konten AI Cover Musik menggunakan pendekatan Aspect-Based Sentiment Analysis (ABSA).

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk menganalisis sentimen komentar YouTube terkait AI Cover Musik berdasarkan beberapa aspek yang telah ditentukan.

Analisis dilakukan dengan menggabungkan:
- preprocessing teks
- identifikasi aspek
- klasifikasi sentimen
- Logistic Regression
- SMOTE
- evaluasi model
- visualisasi hasil

## 🎯 Aspek yang Dianalisis

1. 🎧 Aktivitas Pendengar
2. 🤖 Konten & Teknologi AI
3. 🎵 Kualitas Musik & Audio
4. 💬 Penilaian & Opini

## 📊 Dataset

Dataset penelitian berasal dari komentar YouTube yang berkaitan dengan konten AI Cover Musik.

Tahapan data meliputi:
- data awal
- preprocessing
- pelabelan aspek
- validasi manual
- data hasil koreksi
- pembagian dataset untuk pemodelan

## 🧠 Metode Analisis

Model klasifikasi yang digunakan adalah Logistic Regression.

Untuk menangani ketidakseimbangan kelas pada data pelatihan, digunakan metode SMOTE (Synthetic Minority Over-sampling Technique).

Model dibandingkan dalam dua kondisi:
- Logistic Regression tanpa SMOTE
- Logistic Regression dengan SMOTE

## 📈 Evaluasi

Evaluasi model dilakukan menggunakan:
- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score

Hasil evaluasi digunakan untuk membandingkan performa model sebelum dan sesudah penerapan SMOTE.

## 📁 Struktur Repository

```text
├── Code_ANALISIS_AI_COVER.ipynb
├── data/
└── results/
