# Success Metrics

**Document:** Success Metrics
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Product Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan kerangka pengukuran keberhasilan produk Pawona.

Tujuan utama dokumen ini adalah memastikan seluruh tim menggunakan definisi keberhasilan yang sama ketika mengevaluasi produk, fitur, eksperimen, dan roadmap.

Keberhasilan Pawona tidak diukur berdasarkan jumlah fitur yang dibangun, tetapi berdasarkan nilai yang berhasil diberikan kepada pengguna.

---

# 2. Measurement Philosophy

Pawona mengadopsi prinsip:

> Measure Outcomes, Not Outputs.

Output:

* jumlah fitur
* jumlah release
* jumlah halaman

Outcome:

* pengguna berhasil memasak
* pengguna kembali menggunakan aplikasi
* pengguna mendapatkan nilai dari produk

Semua metrik dalam dokumen ini dirancang untuk mengukur outcome.

---

# 3. Product Success Definition

Pawona dianggap berhasil apabila:

Pengguna dapat menemukan resep yang relevan dari bahan yang tersedia dan berhasil menyelesaikan proses memasak dengan bantuan produk.

Karena itu, fokus utama pengukuran berada pada aktivitas memasak, bukan aktivitas browsing.

---

# 4. North Star Metric

## AI-Assisted Meals Completed

Definisi:

Jumlah sesi memasak yang berhasil diselesaikan menggunakan bantuan Pawona.

---

### Formula

```text
Cooking Sessions Completed
```

---

### Why This Metric

Metrik ini merepresentasikan:

* nilai yang diterima pengguna
* keberhasilan Core Product Loop
* kualitas rekomendasi
* kualitas pengalaman memasak

---

### What It Measures

* pengguna menemukan resep
* pengguna memulai memasak
* pengguna menyelesaikan memasak

---

### What It Does Not Measure

* sekadar membuka aplikasi
* melihat resep
* melakukan pencarian tanpa memasak

---

# 5. Product Metric Hierarchy

```text
North Star Metric
│
├── Acquisition Metrics
├── Activation Metrics
├── Engagement Metrics
├── Retention Metrics
└── Monetization Metrics
```

---

# 6. Acquisition Metrics

Mengukur kemampuan produk memperoleh pengguna baru.

---

## New Users

Jumlah pengguna baru.

---

## Signup Conversion Rate

Persentase pengunjung yang menjadi pengguna.

---

## Cost Per Acquisition (Future)

Biaya memperoleh pengguna baru.

---

## Organic Acquisition Rate

Persentase pengguna yang datang secara organik.

---

# 7. Activation Metrics

Mengukur seberapa cepat pengguna mendapatkan nilai pertama.

---

## Time to First Recipe

Definisi:

Waktu dari membuka aplikasi hingga melihat resep pertama.

---

Target:

< 30 detik

---

## First Recipe Generated Rate

Definisi:

Persentase pengguna yang berhasil menghasilkan resep pertama.

---

Target:

> 80%

---

## First Cooking Session Rate

Definisi:

Persentase pengguna yang memulai cooking mode.

---

Target:

> 50%

---

# 8. Core Loop Metrics

Setiap tahap Core Product Loop memiliki metrik utama.

---

## Ingredients

### Ingredient Submission Rate

Persentase pengguna yang memasukkan bahan.

---

## Recipe

### Recipe Generation Rate

Persentase permintaan yang menghasilkan rekomendasi.

---

Target:

> 95%

---

## Cook

### Cooking Session Start Rate

Persentase pengguna yang memulai memasak.

---

### Cooking Completion Rate

Persentase sesi memasak yang diselesaikan.

---

Target:

> 40%

---

## Save

### Recipe Save Rate

Persentase resep yang disimpan.

---

Target:

> 20%

---

## Learn

### Personalization Engagement Rate

Persentase interaksi dengan rekomendasi personal.

---

## Repeat

### Weekly Active Users

Jumlah pengguna aktif mingguan.

---

# 9. Retention Metrics

Retensi merupakan indikator paling penting setelah MVP diluncurkan.

---

## Day 1 Retention

Target:

> 40%

---

## Day 7 Retention

Target:

> 25%

---

## Day 30 Retention

Target:

> 15%

---

## Weekly Active Users

Target:

Bertumbuh secara konsisten.

---

## Repeat Cooking Rate

Definisi:

Persentase pengguna yang menyelesaikan lebih dari satu sesi memasak.

---

Target:

> 30%

---

# 10. AI Metrics

Sebagai AI-first product, Pawona membutuhkan metrik AI tersendiri.

---

## AI Recipe Success Rate

Definisi:

Persentase permintaan yang menghasilkan resep valid.

---

Target:

> 95%

---

## Recommendation Acceptance Rate

Definisi:

Persentase rekomendasi yang dipilih pengguna.

---

Target:

> 30%

---

## Personalization Effectiveness

Definisi:

Perbandingan performa rekomendasi personal dan non-personal.

---

## AI Fallback Rate

Definisi:

Persentase request yang gagal menghasilkan jawaban yang layak.

---

Target:

< 5%

---

# 11. Vision AI Metrics

Untuk fase Beta dan Growth.

---

## Ingredient Detection Accuracy

Target:

> 85%

---

## Ingredient Recognition Coverage

Jumlah bahan yang dapat dikenali sistem.

---

## Scan-to-Recipe Conversion

Definisi:

Persentase scan yang menghasilkan sesi memasak.

---

# 12. Engineering Metrics

Mengukur kualitas platform.

---

## Crash Free Rate

Target:

> 99%

---

## API Success Rate

Target:

> 99%

---

## Average API Response Time

Target:

< 500 ms

---

## AI Response Time

Target:

< 5 detik

---

## Uptime

Target:

> 99.5%

---

# 13. Business Metrics

Untuk fase setelah MVP.

---

## Monthly Active Users

---

## Paid Conversion Rate

---

## Average Revenue Per User

---

## Monthly Recurring Revenue

---

## Customer Acquisition Cost

---

## Lifetime Value

---

# 14. Product-Market Fit Indicators

Pawona dianggap menunjukkan sinyal Product-Market Fit apabila:

---

## Retention

Day 30 Retention > 15%

---

## Engagement

3+ Recipe Generations per User per Week

---

## Usage

2+ Cooking Sessions per User per Month

---

## Satisfaction

Recipe Save Rate > 20%

---

## Core Value

Cooking Completion Rate > 40%

---

# 15. Metrics Dashboard

Dashboard MVP harus menampilkan:

---

### North Star

AI-Assisted Meals Completed

---

### Product

* WAU
* Recipe Generated
* Cooking Sessions
* Saved Recipes

---

### AI

* AI Success Rate
* Recommendation Acceptance Rate

---

### Engineering

* Crash Free Rate
* API Success Rate
* AI Latency

---

# 16. Metrics Ownership

| Metric Category     | Owner       |
| ------------------- | ----------- |
| North Star          | Product     |
| Activation          | Product     |
| Engagement          | Product     |
| Retention           | Product     |
| AI Metrics          | AI Team     |
| Engineering Metrics | Engineering |
| Revenue Metrics     | Business    |

---

# 17. Anti-Metrics

Pawona tidak menggunakan metrik berikut sebagai indikator utama keberhasilan:

* Total Downloads
* Page Views
* Social Media Followers
* Total Registered Users

Metrik tersebut dapat dipantau tetapi tidak boleh menjadi dasar keputusan produk.

---

# 18. Summary

Keberhasilan Pawona diukur melalui satu tujuan utama:

Membantu pengguna mengubah bahan yang tersedia menjadi makanan yang berhasil dimasak.

North Star Metric:

AI-Assisted Meals Completed

Seluruh metrik produk, AI, engineering, dan bisnis harus berkontribusi terhadap peningkatan metrik tersebut dalam jangka panjang.
