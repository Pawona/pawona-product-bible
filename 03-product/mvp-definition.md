# MVP Definition

**Document:** MVP Definition
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Product Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan ruang lingkup Minimum Viable Product (MVP) Pawona.

Tujuan MVP bukan untuk membangun seluruh visi Pawona.

Tujuan MVP adalah memvalidasi Product Thesis:

> Pengguna akan menggunakan AI untuk membantu menentukan menu dari bahan yang tersedia dan menyelesaikan proses memasak dengan lebih mudah.

Seluruh keputusan scope harus mengutamakan kecepatan validasi dibanding kelengkapan fitur.

---

# 2. MVP Objective

Membuktikan bahwa pengguna memperoleh nilai nyata dari pengalaman:

```text
Ingredients
↓
Recipe
↓
Cook
↓
Save
```

dan bersedia kembali menggunakan Pawona untuk kebutuhan memasak berikutnya.

---

# 3. MVP Success Criteria

MVP dianggap berhasil apabila mampu mencapai indikator berikut dalam 3 bulan pertama setelah peluncuran beta:

### Product Metrics

* WAU Retention > 30%
* Cooking Completion Rate > 40%
* Recipe Save Rate > 20%
* 3+ Recipe Generations per User per Week

---

### Technical Metrics

* Crash Free Rate > 99%
* AI Success Rate > 95%
* Average AI Response Time < 5 Seconds

---

### User Validation Metrics

* Pengguna memahami value proposition dalam kurang dari 1 menit
* Pengguna dapat menemukan resep dalam kurang dari 30 detik
* Pengguna dapat memulai cooking mode tanpa bantuan eksternal

---

# 4. MVP Scope

MVP mencakup lima area utama.

---

## Authentication

Tujuan:

Mengidentifikasi pengguna dan menyimpan preferensi.

---

Features:

* Google Login
* Apple Login
* Guest Mode
* Basic Profile

---

Priority:

P0

---

## Recipe Discovery

Tujuan:

Membantu pengguna menemukan resep dari bahan yang tersedia.

---

Features:

* Text-Based Ingredient Input
* Natural Language Search
* Recipe Recommendation
* Recipe Result Screen

---

Priority:

P0

---

## Recipe Experience

Tujuan:

Memberikan informasi resep yang jelas dan mudah dipahami.

---

Features:

* Recipe Detail
* Ingredients List
* Recipe Metadata
* AI Cooking Tips

---

Priority:

P0

---

## Cooking Experience

Tujuan:

Membantu pengguna berhasil menyelesaikan proses memasak.

---

Features:

* Cooking Mode
* Step Navigation
* Progress Tracking
* Cooking Completion

---

Priority:

P0

---

## Personal Kitchen

Tujuan:

Menyimpan aktivitas yang bernilai bagi pengguna.

---

Features:

* Saved Recipes
* Cooking History
* User Preferences
* Shopping Lists

---

Priority:

P0

---

# 5. MVP User Flow

Core flow MVP:

```text
Open App
↓
Input Ingredients
↓
Recipe Recommendations
↓
Recipe Detail
↓
Cooking Mode
↓
Cooking Completed
↓
Save Recipe
```

Flow ini menjadi prioritas utama seluruh tim produk.

---

# 6. AI Scope

AI dalam MVP memiliki tiga tanggung jawab utama.

---

## AI Recipe Generator

Input:

* ingredients
* natural language request

Output:

* ranked recipe recommendations

---

## AI Recipe Search

Input:

* conversational search query

Output:

* relevant recipe results

---

## AI Personalization

Input:

* user behavior
* saved recipes
* preferences

Output:

* personalized recommendations

---

# 7. Vision AI Scope

Vision AI tidak termasuk dalam MVP Core.

Vision AI masuk dalam MVP+ atau Beta Release.

---

Features:

* Ingredient Detection
* Refrigerator Scan
* AI Recipe Generation from Image

---

Reason:

Value utama produk sudah dapat divalidasi tanpa Vision AI.

---

Priority:

P1

---

# 8. AI Cooking Assistant Scope

AI Cooking Assistant tidak termasuk MVP Core.

Masuk fase Beta.

---

Features:

* contextual cooking help
* conversational guidance
* cooking troubleshooting

---

Reason:

Meningkatkan experience tetapi tidak diperlukan untuk memvalidasi Product Thesis.

---

Priority:

P1

---

# 9. Out of Scope

Fitur berikut tidak termasuk MVP.

---

## Community

Priority:

P3

---

## Culinary Heritage Explorer

Priority:

P3

---

## Regional Food Map

Priority:

P3

---

## Nutrition Coach

Priority:

P3

---

## Commodity Pricing

Priority:

P3

---

## Pantry Inventory

Priority:

P2

---

## Meal Planner

Priority:

P2

---

## Family Account

Priority:

P2

---

## Grocery Marketplace

Priority:

P3

---

# 10. Feature Prioritization Matrix

| Feature              | Priority |
| -------------------- | -------- |
| Authentication       | P0       |
| Ingredient Input     | P0       |
| Recipe Generation    | P0       |
| Recipe Search        | P0       |
| Recipe Detail        | P0       |
| Cooking Mode         | P0       |
| Saved Recipes        | P0       |
| User Preferences     | P0       |
| Shopping List        | P0       |
| Analytics            | P0       |
| Ingredient Scan      | P1       |
| AI Cooking Assistant | P1       |
| Push Notification    | P1       |
| Meal Planner         | P2       |
| Pantry Management    | P2       |
| Nutrition Coach      | P3       |
| Community            | P3       |
| Heritage Explorer    | P3       |

---

# 11. MVP Release Strategy

## Alpha

Internal Testing

Target:

20 users

---

## Closed Beta

Early Adopters

Target:

50–100 users

---

## Public Beta

Open Testing

Target:

500–1000 users

---

## General Availability

Setelah Product-Market Fit Signal muncul.

---

# 12. What MVP Is Not

MVP bukan:

* aplikasi resep terbesar
* platform komunitas kuliner
* aplikasi nutrisi
* marketplace bahan makanan

MVP adalah alat untuk membuktikan bahwa AI dapat membantu pengguna menentukan menu dan memasak dengan lebih baik.

---

# 13. Product Thesis Validation

MVP dianggap berhasil apabila dapat menjawab pertanyaan berikut:

1. Apakah pengguna mau memasukkan bahan yang mereka miliki?
2. Apakah pengguna mempercayai rekomendasi AI?
3. Apakah pengguna menyelesaikan proses memasak?
4. Apakah pengguna kembali menggunakan Pawona?

Jika keempat pertanyaan tersebut terjawab positif, maka Product Thesis tervalidasi.

---

# 14. Summary

Pawona MVP berfokus pada satu pengalaman inti:

Mengubah bahan yang tersedia menjadi makanan yang berhasil dimasak.

Seluruh fitur MVP dirancang untuk memperkuat Core Product Loop:

Ingredients → Recipe → Cook → Save

dan memvalidasi bahwa AI dapat menjadi asisten dapur yang benar-benar berguna bagi pengguna Indonesia.
