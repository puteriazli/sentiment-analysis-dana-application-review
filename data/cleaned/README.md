# 📊 Dataset: Ulasan Aplikasi DANA

Dataset ini berisi kumpulan ulasan pengguna aplikasi DANA yang telah dibersihkan dan siap digunakan untuk analisis sentimen, eksplorasi perilaku pengguna, serta pengambilan keputusan berbasis data. Data diambil dengan rentang waktu 12/31/2023 - 1/22/2026.

🔗 Dataset dapat diakses di:  
https://www.kaggle.com/datasets/puteriameliaazli/review-aplikasi-dana

---

## 🎯 Tujuan Dataset

Dataset ini dirancang untuk mendukung:

- Analisis sentimen pengguna
- Monitoring reputasi aplikasi
- Identifikasi pola keluhan
- Evaluasi dampak pembaruan aplikasi
- Pengembangan sistem decision intelligence

Dataset sudah melalui proses pembersihan dasar dan siap digunakan tanpa preprocessing berat.

---

## 📦 Struktur Dataset

Total data: ±740.000 ulasan

| Kolom | Tipe Data | Deskripsi |
|--------|------------|------------|
| id_ulasan | object | ID unik ulasan |
| user | object | Nama pengguna |
| ulasan | object | Teks review pengguna |
| rating | int64 | Rating skala 1–5 |
| dukungan_ulasan | int64 | Jumlah pengguna yang menilai review membantu |
| tanggal | datetime | Tanggal review |
| versi_aplikasi | category | Versi aplikasi saat review dibuat |

---

## 🏷 Distribusi Rating

Rating menggunakan skala 1 sampai 5:

- 1–2 → Keluhan / pengalaman buruk
- 3 → Netral / campuran
- 4–5 → Pengalaman positif

⚠ Catatan penting:
Rating bukan anotasi manual sentimen, melainkan representasi persepsi pengguna. Terdapat kemungkinan label noise (rating tidak selalu konsisten dengan isi teks).

---

## 🧹 Status Kebersihan Data

Dataset telah:

✔ Dibersihkan dari duplikasi  
✔ Diformat tipe datanya  
✔ Disesuaikan format tanggal  
✔ Siap digunakan untuk training model NLP  

Namun tetap disarankan melakukan:

- Validasi ulang label jika digunakan untuk supervised learning
- Filtering tambahan sesuai kebutuhan use case

---

## 📊 Potensi Analisis

Dataset ini mendukung berbagai analisis lanjutan:

### 1️⃣ Sentiment Analysis
- 3-class classification (Negatif, Netral, Positif)
- Binary classification (Negatif vs Non-negatif)

### 2️⃣ Impact Analysis
Menggunakan kolom `dukungan_ulasan` untuk mengukur relevansi sosial suatu review.

Contoh pendekatan:

Impact Score = Prob(Negatif) × log(1 + dukungan_ulasan)

### 3️⃣ Trend Monitoring
- Distribusi sentimen per periode waktu
- Perbandingan sentimen antar versi aplikasi
- Lonjakan keluhan pasca update

### 4️⃣ Topic & Issue Mining
- Clustering review negatif
- Identifikasi kata kunci dominan
- Deteksi isu sistemik (error, login, transaksi gagal, dll)

---

## ⚠ Limitations

- Label sentimen berbasis rating (proxy label)
- Tidak dilakukan anotasi manual
- Bahasa informal dan slang cukup dominan
- Tidak tersedia metadata demografis pengguna

---

## 💼 Business Relevance

Dataset ini sangat relevan untuk:

- Tim Product
- Customer Experience
- Risk Monitoring
- Business Intelligence
- Data Science & AI Development

Dapat digunakan sebagai fondasi untuk membangun:

- Sentiment monitoring dashboard
- Early warning system
- Decision support engine

---

## 🔮 Recommended Next Steps

Untuk penggunaan tingkat lanjut:

- Lakukan label noise detection
- Terapkan confidence filtering
- Bangun impact-based prioritization
- Integrasikan dengan dashboard real-time

---

## 🏁 Kesimpulan

Dataset Ulasan DANA menyediakan data skala besar yang siap digunakan untuk analisis sentimen dan pengembangan sistem intelligence berbasis ulasan pengguna.

Dengan pendekatan yang tepat, dataset ini dapat diubah dari sekadar kumpulan review menjadi sumber insight strategis untuk pengambilan keputusan bisnis.
