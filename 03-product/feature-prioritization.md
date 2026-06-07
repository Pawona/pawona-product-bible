# Feature Prioritization Framework

**Document:** Feature Prioritization
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Product Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan kerangka kerja resmi untuk mengevaluasi, memprioritaskan, dan menjadwalkan fitur baru di Pawona.

Tujuan utama dokumen ini adalah menjaga fokus produk agar tetap selaras dengan Product Vision, Product Pillars, dan Core Product Loop.

Tanpa framework prioritas yang jelas, produk berisiko berkembang menjadi kumpulan fitur yang tidak terhubung dan sulit mencapai Product-Market Fit.

---

# 2. Product Prioritization Philosophy

Pawona tidak memprioritaskan fitur berdasarkan:

* tren teknologi terbaru
* permintaan individu yang paling vokal
* kompleksitas teknis
* daya tarik demo

Sebaliknya, fitur diprioritaskan berdasarkan kontribusinya terhadap nilai pengguna dan tujuan bisnis.

---

# 3. Prioritization Principles

Semua fitur harus dievaluasi menggunakan prinsip berikut.

---

## Principle 1 — Core Loop First

Fitur yang memperkuat Core Product Loop selalu memiliki prioritas lebih tinggi.

Core Loop:

```text
Ingredients
↓
Recipe
↓
Cook
↓
Save
↓
Learn
↓
Repeat
```

---

Contoh:

Cooking Mode lebih penting daripada Community karena secara langsung meningkatkan keberhasilan memasak.

---

## Principle 2 — User Value Over Novelty

Fitur yang menyelesaikan masalah nyata lebih penting daripada fitur yang terlihat inovatif.

---

Contoh:

Shopping List lebih penting daripada AI Chef Avatar.

---

## Principle 3 — MVP Before Ecosystem

Validasi Product Thesis harus dilakukan sebelum membangun ekosistem yang lebih luas.

---

Contoh:

Recipe Generation lebih penting daripada Grocery Marketplace.

---

## Principle 4 — Retention Over Acquisition

Fitur yang meningkatkan kemungkinan pengguna kembali memiliki prioritas lebih tinggi dibanding fitur yang hanya meningkatkan daya tarik awal.

---

Contoh:

Saved Recipes lebih penting daripada fitur berbagi ke media sosial.

---

## Principle 5 — Simplicity Wins

Jika dua solusi menghasilkan nilai yang sama, pilih solusi yang lebih sederhana untuk dibangun dan dipelihara.

---

# 4. Evaluation Framework

Setiap fitur dinilai berdasarkan lima dimensi.

---

## Dimension 1 — User Impact

Seberapa besar masalah pengguna yang diselesaikan?

Score:

1–5

---

## Dimension 2 — Core Loop Contribution

Seberapa besar fitur memperkuat Core Product Loop?

Score:

1–5

---

## Dimension 3 — Persona Coverage

Berapa banyak persona utama yang terbantu?

Score:

1–5

---

## Dimension 4 — Strategic Alignment

Seberapa kuat hubungan fitur dengan Product Vision dan Product Pillars?

Score:

1–5

---

## Dimension 5 — Development Effort

Seberapa sulit fitur dibangun?

Score:

1–5

Catatan:

Semakin tinggi skor, semakin besar effort.

---

# 5. Priority Formula

Priority Score:

```text
(User Impact
+
Core Loop Contribution
+
Persona Coverage
+
Strategic Alignment)
-
Development Effort
```

Semakin tinggi skor, semakin tinggi prioritas.

---

# 6. Priority Levels

## P0 — Core MVP

Fitur yang wajib ada agar Product Thesis dapat divalidasi.

Tanpa fitur ini, MVP tidak dapat diluncurkan.

---

## P1 — Enhancement

Meningkatkan pengalaman pengguna secara signifikan tetapi tidak wajib untuk validasi awal.

---

## P2 — Growth

Fitur yang membantu retensi, engagement, dan diferensiasi setelah MVP tervalidasi.

---

## P3 — Ecosystem

Fitur jangka panjang yang mendukung visi besar Pawona.

---

# 7. P0 Features

## Authentication

Reason:

Menyimpan identitas dan preferensi pengguna.

---

## Ingredient Input

Reason:

Pintu masuk Core Loop.

---

## Recipe Generation

Reason:

Value proposition utama.

---

## Recipe Search

Reason:

Discovery experience.

---

## Recipe Detail

Reason:

Informasi resep.

---

## Cooking Mode

Reason:

Meningkatkan keberhasilan memasak.

---

## Saved Recipes

Reason:

Meningkatkan retensi.

---

## User Preferences

Reason:

Fondasi personalisasi.

---

## Shopping List

Reason:

Mendukung pilar Save.

---

## Analytics

Reason:

Mengukur Product-Market Fit.

---

# 8. P1 Features

## Ingredient Scan

Reason:

Mempermudah input.

---

## Vision AI

Reason:

Meningkatkan convenience.

---

## AI Cooking Assistant

Reason:

Meningkatkan pengalaman memasak.

---

## Push Notifications

Reason:

Mendukung re-engagement.

---

# 9. P2 Features

## Meal Planner

Reason:

Meningkatkan penggunaan rutin.

---

## Pantry Management

Reason:

Mendukung household management.

---

## Family Profiles

Reason:

Meningkatkan personalisasi.

---

## Budget Planner

Reason:

Memperkuat pilar Save.

---

# 10. P3 Features

## Community

Reason:

Ekspansi sosial.

---

## Heritage Explorer

Reason:

Memperkuat pilar Preserve.

---

## Regional Food Map

Reason:

Eksplorasi budaya.

---

## Nutrition Coach

Reason:

Ekspansi health domain.

---

## Grocery Marketplace

Reason:

Commerce layer.

---

# 11. Prioritization Matrix

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
| Vision AI            | P1       |
| AI Cooking Assistant | P1       |
| Push Notification    | P1       |
| Meal Planner         | P2       |
| Pantry Management    | P2       |
| Family Profiles      | P2       |
| Budget Planner       | P2       |
| Community            | P3       |
| Heritage Explorer    | P3       |
| Regional Food Map    | P3       |
| Nutrition Coach      | P3       |
| Grocery Marketplace  | P3       |

---

# 12. Product Roadmap Mapping

## MVP Phase

Focus:

Discover + Cook + Save

---

Features:

Semua P0

---

## Growth Phase

Focus:

Retention + Personalization

---

Features:

P1 + sebagian P2

---

## Intelligence Phase

Focus:

Kitchen Optimization

---

Features:

Meal Planning

Budget Optimization

Pantry Management

---

## Ecosystem Phase

Focus:

Community + Heritage + Commerce

---

Features:

P3

---

# 13. Feature Acceptance Gate

Sebelum fitur masuk roadmap, tim harus menjawab:

1. Masalah pengguna apa yang diselesaikan?
2. Persona mana yang terbantu?
3. Pilar produk mana yang diperkuat?
4. Tahap Core Loop mana yang ditingkatkan?
5. Metrik apa yang diharapkan meningkat?
6. Mengapa fitur ini harus dibangun sekarang?

Jika salah satu pertanyaan tidak dapat dijawab dengan jelas, fitur tidak boleh diprioritaskan.

---

# 14. Anti-Patterns

Pawona tidak akan memprioritaskan fitur hanya karena:

* sedang tren
* kompetitor memilikinya
* terlihat menarik saat demo
* menggunakan teknologi AI terbaru

Semua fitur harus dapat menunjukkan hubungan yang jelas dengan Product Vision dan Core Product Loop.

---

# 15. Summary

Framework prioritas Pawona memastikan bahwa seluruh investasi produk berfokus pada satu tujuan utama:

Membantu pengguna mengubah bahan yang tersedia menjadi makanan yang berhasil dimasak.

Setiap fitur harus memperkuat Product Vision, Product Pillars, dan Core Product Loop sebelum dipertimbangkan untuk masuk ke roadmap pengembangan.
