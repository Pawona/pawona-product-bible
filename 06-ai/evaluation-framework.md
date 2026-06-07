# Evaluation Framework

**Document:** AI Evaluation Framework
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan framework evaluasi resmi untuk seluruh sistem AI Pawona.

Tujuan utama evaluasi bukan untuk mengukur kecanggihan model.

Tujuan utama evaluasi adalah memastikan bahwa sistem AI secara konsisten membantu pengguna mengambil keputusan memasak yang lebih baik.

Framework ini berlaku untuk:

* Recipe Intelligence Engine
* RAG System
* Memory System
* Prompting System
* Vision AI
* Future AI Agents

---

# 2. Evaluation Philosophy

Pawona mengadopsi prinsip:

> Evaluate User Outcomes, Not Model Outputs.

---

Output:

* jawaban AI
* hasil retrieval
* hasil ranking

---

Outcome:

* pengguna menemukan resep
* pengguna memilih rekomendasi
* pengguna memasak
* pengguna kembali menggunakan produk

---

Outcome selalu lebih penting daripada output.

---

# 3. Evaluation Hierarchy

Framework evaluasi Pawona memiliki lima lapisan.

---

```text
Business Outcomes
↑
Product Outcomes
↑
AI Outcomes
↑
System Quality
↑
Model Quality
```

---

Model hanyalah lapisan paling bawah.

---

# 4. Evaluation Categories

AI dievaluasi melalui:

---

## Product Evaluation

---

## Recommendation Evaluation

---

## Retrieval Evaluation

---

## Personalization Evaluation

---

## Safety Evaluation

---

## Vision Evaluation

---

## Operational Evaluation

---

# 5. Product Outcome Evaluation

Level evaluasi tertinggi.

---

## North Star Metric

AI-Assisted Meals Completed

---

Definition:

Jumlah sesi memasak yang berhasil diselesaikan menggunakan bantuan Pawona.

---

Target:

Growing Consistently

---

## Cooking Completion Rate

Target:

> 40%

---

## Repeat Cooking Rate

Target:

> 30%

---

## Recipe Save Rate

Target:

> 20%

---

Jika metrik ini tidak meningkat.

Maka peningkatan model dianggap tidak bernilai.

---

# 6. Recommendation Evaluation

Mengukur kualitas rekomendasi.

---

## Recommendation Acceptance Rate

Definition:

Persentase rekomendasi yang dipilih pengguna.

---

Target:

> 30%

---

## Top 3 Recommendation Accuracy

Definition:

Kemungkinan rekomendasi terbaik muncul dalam tiga posisi pertama.

---

Target:

> 80%

---

## Recipe Relevance Score

Human Evaluation.

---

Scale:

1–5

---

Target:

> 4.0

---

# 7. Retrieval Evaluation

Mengukur kualitas RAG.

---

## Retrieval Accuracy

Target:

> 90%

---

## Top 5 Retrieval Recall

Target:

> 85%

---

## Retrieval Latency

Target:

< 300 ms

---

## Knowledge Coverage

Definition:

Persentase query yang memiliki knowledge support.

---

Target:

Growing Consistently

---

# 8. Personalization Evaluation

Mengukur kualitas Memory System.

---

## Personalized CTR

Target:

Lebih tinggi dibanding baseline.

---

## Preference Prediction Accuracy

Future.

---

## Recommendation Lift

Definition:

Peningkatan performa rekomendasi personal dibanding non-personal.

---

Target:

Positive

---

## Repeat Usage Lift

Target:

Positive

---

# 9. Prompt Evaluation

Mengukur kualitas Prompting Layer.

---

## Structured Output Success Rate

Target:

> 95%

---

## Prompt Failure Rate

Target:

< 2%

---

## Template Compliance

Target:

> 98%

---

## Context Utilization Score

Target:

Growing Consistently

---

# 10. Vision AI Evaluation

Mengukur kualitas Computer Vision.

---

## Ingredient Detection Accuracy

Target:

> 85%

---

## Ingredient Recall

Target:

> 80%

---

## False Detection Rate

Target:

< 10%

---

## Scan-to-Recipe Conversion

Target:

> 50%

---

# 11. Safety Evaluation

Kategori yang wajib dilalui seluruh sistem.

---

## Hallucination Rate

Target:

< 5%

---

## Unsafe Recommendation Rate

Target:

≈ 0%

---

## Safety Compliance Rate

Target:

> 99%

---

## Prompt Injection Resistance

Target:

> 95%

---

Tidak ada release yang boleh lolos apabila safety memburuk.

---

# 12. Operational Evaluation

Mengukur performa sistem produksi.

---

## AI Response Time

Target:

< 5 detik

---

## API Success Rate

Target:

> 99%

---

## AI Availability

Target:

> 99.5%

---

## Cost Per Request

Target:

Menurun seiring optimasi.

---

# 13. Evaluation Datasets

Pawona harus memiliki dataset evaluasi internal.

---

## Recipe Dataset

Examples:

* ingredient matching
* recipe retrieval

---

## Search Dataset

Examples:

* natural language queries

---

## Personalization Dataset

Examples:

* preference prediction

---

## Vision Dataset

Examples:

* ingredient images

---

## Safety Dataset

Examples:

* unsafe prompts
* adversarial prompts

---

# 14. Golden Dataset Strategy

Pawona membangun Golden Dataset.

---

Definition:

Dataset yang digunakan untuk evaluasi lintas model dan lintas versi.

---

Benefits:

* consistency
* regression testing
* release comparison

---

Golden Dataset tidak boleh sering berubah.

---

# 15. Offline Evaluation

Dilakukan sebelum deployment.

---

Examples:

* retrieval tests
* ranking tests
* prompt tests
* vision tests

---

Goal:

Mengurangi risiko regresi.

---

# 16. Online Evaluation

Dilakukan setelah deployment.

---

Examples:

* A/B testing
* shadow testing
* canary releases

---

Goal:

Mengukur dampak nyata terhadap pengguna.

---

# 17. Release Gates

Setiap release AI harus melewati:

---

## Quality Gate

---

## Safety Gate

---

## Performance Gate

---

## Cost Gate

---

Jika salah satu gagal.

Release tidak boleh dipromosikan ke production.

---

# 18. A/B Testing Framework

Eksperimen dapat dilakukan pada:

---

## Ranking Models

---

## Prompt Versions

---

## Retrieval Strategies

---

## Personalization Logic

---

Winner ditentukan oleh Product Outcomes.

Bukan opini tim.

---

# 19. Model Evaluation

Model dievaluasi sebagai komponen.

Bukan tujuan akhir.

---

Metrics:

### Accuracy

---

### Latency

---

### Cost

---

### Reliability

---

Model terbaik adalah model yang memberikan outcome terbaik.

Bukan benchmark terbaik.

---

# 20. Evaluation Dashboard

Dashboard AI harus menampilkan:

---

## Product Metrics

* AI-Assisted Meals Completed
* Completion Rate
* Save Rate

---

## AI Metrics

* Recommendation Acceptance
* Retrieval Accuracy
* Personalization Lift

---

## Safety Metrics

* Hallucination Rate
* Unsafe Recommendation Rate

---

## Operations Metrics

* Latency
* Availability
* Cost

---

# 21. Evaluation Flywheel

```text
Better Evaluation
↓
Better Insights
↓
Better AI Decisions
↓
Better User Outcomes
↓
More Usage
↓
More Data
↓
Better Evaluation
```

---

Evaluasi menjadi mekanisme pembelajaran utama organisasi.

---

# 22. Success Definition

Framework dianggap berhasil apabila:

Tim dapat mengetahui dengan jelas apakah perubahan AI:

* meningkatkan kualitas rekomendasi
* meningkatkan pengalaman memasak
* meningkatkan retensi pengguna
* meningkatkan North Star Metric

---

Tanpa framework ini.

Keputusan AI hanya akan berdasarkan intuisi.

---

# 23. Relationship with Other Documents

Evaluation Framework berada di atas seluruh sistem AI.

---

Evaluates:

* AI Vision
* Recipe Intelligence Engine
* RAG Strategy
* Memory Strategy
* Prompting Strategy
* Vision AI
* AI Safety

---

Semua sistem harus dapat diukur menggunakan framework ini.

---

# 24. Summary

Pawona mengevaluasi AI berdasarkan dampaknya terhadap pengguna, bukan hanya kualitas model.

Framework evaluasi dibangun melalui lima lapisan:

Model Quality → System Quality → AI Outcomes → Product Outcomes → Business Outcomes

Keberhasilan akhir AI diukur menggunakan North Star Metric:

AI-Assisted Meals Completed

Karena tujuan utama Pawona bukan menghasilkan jawaban yang lebih baik.

Tujuan utama Pawona adalah membantu lebih banyak orang berhasil memasak.
