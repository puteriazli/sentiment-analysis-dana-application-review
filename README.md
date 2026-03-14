# 🧠 Sentiment Intelligence System (3-Class)
### Transformer-Based Review Analytics for Business Monitoring

---

## 📌 Executive Overview

Sistem ini membangun model analisis sentimen berbasis XLM-RoBERTa untuk mengklasifikasikan ulasan aplikasi menjadi:

- 🔴 Negatif
- 🟡 Netral
- 🟢 Positif

Tujuan utama bukan hanya klasifikasi, tetapi menghasilkan sinyal terstruktur untuk mendukung pengambilan keputusan berbasis data.

---

## 📊 Model Performance

Hasil evaluasi pada test set:
pictures/matrix evaluation.png
| Metric | Score |
|--------|--------|
| Accuracy | 0.693 |
| Macro F1 | 0.690 |
| Cohen’s Kappa | 0.539 |

### Classification Report
pictures/classification report.png
| Class | Precision | Recall | F1 |
|--------|-----------|--------|--------|
| Negatif | 0.786 | 0.636 | 0.703 |
| Netral | 0.571 | 0.570 | 0.571 |
| Positif | 0.730 | 0.871 | 0.795 |

### Confusion Matrix
pictures/confusion matrix.png

---

## 🔎 Performance Interpretation

### 🔴 Negatif
- Precision tinggi (0.786) → prediksi negatif cukup akurat
- Recall moderat (0.636) → masih ada keluhan yang tidak terdeteksi

### 🟡 Netral
- F1 paling rendah (0.571)
- Kelas paling sulit dipelajari karena:
  - Jumlah data lebih sedikit
  - Batasan antara netral dan positif sering ambigu
  - Banyak data noisy

### 🟢 Positif
- Recall tinggi (0.871)
- Model cenderung lebih mudah mengenali ulasan positif

---

## 📈 Apa Artinya untuk Bisnis?

Model ini:

✔ Cukup baik dalam mengidentifikasi sentimen umum  
✔ Stabil untuk monitoring tren  
✔ Dapat digunakan sebagai sistem filtering awal  

Namun:

⚠ Belum optimal untuk sistem keputusan kritikal tanpa lapisan tambahan  
⚠ Netral masih ambigu  
⚠ Label rating mengandung noise (rating ≠ isi teks)

---

## 🧠 Mengapa Accuracy Tidak Tinggi?

Beberapa faktor:

1. Label berdasarkan rating (proxy label)
2. Terdapat konflik rating vs isi review
3. Bahasa informal dan slang
4. Kelas netral relatif kecil

Macro F1 ≈ 0.69 masih wajar untuk dataset noisy skala besar.

---

## 💼 Business Integration Strategy

Alih-alih hanya menggunakan label final, sistem dapat diperkuat dengan:

### Impact Scoring
Impact Score = P(Negatif) × log(1 + dukungan_ulasan)


Dengan pendekatan ini:

- Review negatif dengan banyak dukungan akan diprioritaskan
- Review ambigu tidak langsung mempengaruhi keputusan

---

## 🚀 Recommended Usage

Model ini cocok untuk:

- Monitoring sentimen agregat
- Deteksi lonjakan sentimen negatif
- Filtering awal sebelum analisis manual
- Sistem prioritas berbasis probabilitas

---

## 🔮 Next Optimization Opportunities

- Confidence-based label cleaning
- Binary refinement (Negatif vs Non-Negatif)
- Hard example mining
- Semi-supervised relabeling
- Aspect-based sentiment extraction

---

## 🏁 Conclusion

Model menunjukkan performa moderat dan stabil pada dataset besar dengan label noisy.

Belum sempurna, tetapi cukup kuat sebagai fondasi sistem monitoring dan dapat ditingkatkan menuju decision-grade intelligence system.
