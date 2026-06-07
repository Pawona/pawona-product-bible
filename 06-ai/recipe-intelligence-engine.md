# Recipe Intelligence Engine

**Document:** Recipe Intelligence Engine
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Recipe Intelligence Engine merupakan sistem inti yang bertanggung jawab menghasilkan rekomendasi resep di Pawona.

Engine ini menghubungkan:

* bahan yang tersedia
* preferensi pengguna
* pengetahuan kuliner
* kemampuan AI

untuk menghasilkan rekomendasi yang relevan dan dapat dieksekusi.

Recipe Intelligence Engine adalah fondasi utama pengalaman pengguna Pawona dan merupakan salah satu aset strategis terpenting dalam sistem AI.

---

# 2. Purpose

Tujuan utama Recipe Intelligence Engine adalah:

Membantu pengguna menentukan menu terbaik yang dapat dimasak berdasarkan kondisi dapur mereka saat ini.

Engine tidak bertujuan menghasilkan resep paling kreatif.

Engine bertujuan menghasilkan keputusan memasak terbaik.

---

# 3. Design Philosophy

Recipe Intelligence Engine mengikuti prinsip:

> Recommend Before Generate.

Sistem harus mengutamakan pencarian dan adaptasi pengetahuan yang sudah tersedia sebelum menghasilkan konten baru.

---

# 4. Why Not Pure LLM

Pendekatan sederhana:

```text
Ingredients
↓
LLM
↓
Recipe
```

tidak digunakan sebagai arsitektur utama.

---

## Problems

### Inconsistent

Resep yang dihasilkan dapat berbeda untuk input yang sama.

---

### Expensive

Seluruh reasoning dilakukan oleh model.

---

### Difficult to Evaluate

Kualitas sulit diukur secara objektif.

---

### Hallucination Risk

Model dapat menciptakan kombinasi yang tidak realistis.

---

# 5. Intelligence Architecture

Recipe Intelligence Engine menggunakan pendekatan:

```text
User Input
↓
Ingredient Understanding
↓
Recipe Retrieval
↓
Recipe Ranking
↓
Recipe Adaptation
↓
Response Generation
```

---

# 6. Stage 1 — Ingredient Understanding

## Objective

Memahami kondisi awal pengguna.

---

## Input Types

### Text

Contoh:

```text
telur
tempe
cabai
```

---

### Natural Language

Contoh:

```text
menu murah untuk 4 orang
```

---

### Voice

Future.

---

### Image

Future.

---

## Output

Structured Context

```json
{
  "ingredients": [
    "telur",
    "tempe",
    "cabai"
  ],
  "budget": "low",
  "servings": 4
}
```

---

# 7. Stage 2 — Recipe Retrieval

## Objective

Menemukan kandidat resep yang relevan.

---

## Retrieval Sources

### Recipe Database

Resep terstruktur.

---

### Culinary Knowledge Base

Pengetahuan kuliner tambahan.

---

### Regional Food Data

Informasi daerah dan budaya.

---

## Retrieval Criteria

* ingredient overlap
* cuisine relevance
* cooking complexity
* estimated cost

---

## Output

Candidate Recipes

Biasanya:

```text
Top 20–50 recipes
```

---

# 8. Stage 3 — Recipe Ranking

## Objective

Menentukan urutan rekomendasi terbaik.

---

## Ranking Factors

### Ingredient Match

Bobot tertinggi.

---

### User Preferences

* pedas
* diet
* budget

---

### Cooking History

* pernah dimasak
* belum pernah dimasak

---

### Popularity Signals

Future.

---

### Completion Signals

Resep yang sering berhasil diselesaikan.

---

## Ranking Formula

Konsep:

```text
Recipe Score
=
Ingredient Match
+
Preference Match
+
Behavior Match
+
Completion Score
```

---

# 9. Stage 4 — Recipe Adaptation

## Objective

Menyesuaikan resep dengan konteks pengguna.

---

## Adaptation Examples

### Budget Adaptation

Premium → Hemat

---

### Spice Adaptation

Pedas → Sedang

---

### Ingredient Substitution

Tidak ada bawang merah.

↓

Alternatif yang tersedia.

---

## Why Adaptation Matters

Pengguna tidak membutuhkan resep sempurna.

Pengguna membutuhkan resep yang dapat dibuat sekarang.

---

# 10. Stage 5 — Response Generation

## Objective

Mengubah hasil sistem menjadi pengalaman yang mudah dipahami.

---

## Generated Components

### Recipe Recommendation

### Cooking Tips

### Alternative Suggestions

### Personalization Explanation

---

## Example

"Resep ini direkomendasikan karena Anda memiliki seluruh bahan utamanya dan sebelumnya menyukai menu berbasis tempe."

---

# 11. Personalization Layer

Personalisasi bekerja di seluruh tahapan engine.

---

## Preference Signals

* spicy level
* budget type
* diet type

---

## Behavioral Signals

* saved recipes
* completed recipes
* searches

---

## Context Signals

* time of day
* seasonality
* special events

Future.

---

# 12. Knowledge Layer

Engine bergantung pada Knowledge Layer.

---

Knowledge Sources:

### Recipes

### Ingredients

### Cooking Methods

### Regional Cuisine

### Ingredient Relationships

### Culinary Taxonomy

---

Knowledge Layer akan dijelaskan lebih detail pada dokumen RAG Strategy.

---

# 13. Decision Quality Framework

Engine harus mengoptimalkan:

---

## Relevance

Apakah resep sesuai kondisi pengguna?

---

## Feasibility

Apakah resep dapat dimasak sekarang?

---

## Confidence

Seberapa yakin sistem terhadap rekomendasi?

---

## Personalization

Apakah rekomendasi terasa personal?

---

# 14. Future Intelligence Capabilities

Setelah MVP.

---

## Meal Planning Engine

---

## Pantry Intelligence

---

## Budget Optimization

---

## Nutrition Optimization

---

## Family Preference Engine

---

Semua sistem tersebut akan dibangun di atas Recipe Intelligence Engine.

---

# 15. Intelligence Flywheel

```text
More Cooking Sessions
↓
More Behavioral Signals
↓
Better Personalization
↓
Better Recommendations
↓
Higher User Satisfaction
↓
More Cooking Sessions
```

---

Semakin banyak pengguna memasak, semakin baik kualitas sistem.

---

# 16. Success Metrics

Engine dievaluasi menggunakan:

---

## Recommendation Acceptance Rate

Target:

> 30%

---

## Cooking Completion Rate

Target:

> 40%

---

## Recipe Save Rate

Target:

> 20%

---

## Personalization Engagement

Target:

Meningkat secara konsisten.

---

# 17. Relationship with Other AI Systems

Recipe Intelligence Engine adalah pusat seluruh sistem AI.

---

Terhubung dengan:

### RAG Strategy

Knowledge Source

---

### Memory Strategy

Personalization Source

---

### Prompting Strategy

Response Layer

---

### Vision AI

Input Layer

---

# 18. Summary

Recipe Intelligence Engine merupakan sistem inti yang mengubah bahan yang tersedia menjadi rekomendasi memasak yang relevan.

Engine dibangun menggunakan pendekatan:

```text
Ingredient Understanding
↓
Retrieval
↓
Ranking
↓
Adaptation
↓
Response
```

Pendekatan ini memungkinkan Pawona menghasilkan rekomendasi yang lebih akurat, lebih konsisten, lebih personal, dan lebih hemat biaya dibandingkan pendekatan berbasis LLM murni.

Recipe Intelligence Engine menjadi fondasi utama Culinary Intelligence Platform yang sedang dibangun Pawona.
