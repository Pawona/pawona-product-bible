# Memory Strategy

**Document:** Memory Strategy
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi memori dan personalisasi yang digunakan oleh Pawona.

Tujuan utama Memory System adalah memungkinkan Pawona memahami preferensi, kebiasaan, dan konteks pengguna secara berkelanjutan sehingga kualitas rekomendasi meningkat seiring waktu.

Memory merupakan salah satu komponen terpenting dalam membangun pengalaman yang terasa personal.

---

# 2. Why Memory Exists

Tanpa memory.

Pawona memperlakukan semua pengguna secara identik.

---

Dengan memory.

Pawona dapat memahami:

* apa yang disukai pengguna
* apa yang dihindari pengguna
* bagaimana pola memasak pengguna
* bagaimana kondisi dapur pengguna

---

Tujuan akhirnya adalah:

Memberikan rekomendasi yang semakin relevan dari waktu ke waktu.

---

# 3. Memory Vision

Membangun Culinary Preference Memory yang memungkinkan Pawona memahami setiap dapur secara unik.

---

AI tidak hanya mengetahui:

> Apa yang bisa dimasak?

Tetapi juga:

> Apa yang paling mungkin dimasak oleh pengguna ini?

---

# 4. Memory Philosophy

Pawona tidak mengingat percakapan.

Pawona mengingat sinyal perilaku.

---

Bad Memory:

```text id="1k8q4w"
User berkata:
Saya suka makanan pedas.
```

---

Good Memory:

```text id="g7m2ry"
Preference:
Spicy Level = High
```

---

Behavioral Memory jauh lebih stabil dibanding conversation memory.

---

# 5. Memory Architecture

High-Level Architecture:

```text id="z71v6t"
User Actions
↓
Behavior Signals
↓
Preference Extraction
↓
Memory Store
↓
Personalization Layer
↓
Recommendations
```

---

# 6. Memory Categories

Pawona menggunakan empat kategori memory utama.

---

## Preference Memory

Preferensi eksplisit pengguna.

---

Examples:

* spicy level
* budget type
* diet type
* favorite cuisines

---

Source:

* onboarding
* profile settings

---

## Behavioral Memory

Preferensi yang dipelajari dari perilaku.

---

Examples:

* frequently saved recipes
* frequently cooked recipes
* preferred cooking duration

---

Source:

* user activity

---

## Contextual Memory

Konteks yang berubah seiring waktu.

---

Examples:

* recent cooking history
* recent ingredient usage
* seasonal trends

---

Source:

* recent events

---

## Household Memory

Future.

---

Examples:

* family preferences
* household patterns
* recurring meals

---

# 7. Memory Layers

## Layer 1 — Explicit Preferences

Data yang diberikan langsung oleh pengguna.

---

Examples:

```json id="xrrdjl"
{
  "spicy_level": "high",
  "budget_type": "economical"
}
```

---

Confidence:

Very High

---

## Layer 2 — Behavioral Signals

Data yang diobservasi sistem.

---

Examples:

```text id="65gqmx"
Saved Recipe
Completed Recipe
Search Query
```

---

Confidence:

Medium to High

---

## Layer 3 — Inferred Preferences

Data yang disimpulkan AI.

---

Examples:

```text id="zygu76"
Likely prefers Javanese cuisine
Likely avoids spicy dishes
```

---

Confidence:

Variable

---

# 8. Preference Model

Setiap pengguna memiliki Preference Profile.

---

Example:

```json id="2oced8"
{
  "spicy_level": "medium",
  "budget_type": "low",
  "diet_type": "normal",
  "favorite_regions": [
    "jawa"
  ],
  "skill_level": "beginner"
}
```

---

Profile ini menjadi input utama Recommendation Engine.

---

# 9. Behavioral Signal Framework

Semua aktivitas penting menghasilkan sinyal.

---

## High Value Signals

### Recipe Completed

Weight:

Very High

---

### Recipe Saved

Weight:

High

---

### Shopping List Generated

Weight:

Medium

---

### Recipe Viewed

Weight:

Low

---

## Signal Hierarchy

```text id="kkj5ak"
Completed
↓
Saved
↓
Started
↓
Viewed
```

---

Perilaku lebih penting daripada klik.

---

# 10. Memory Extraction

Behavioral signals diubah menjadi preference signals.

---

Example:

```text id="n39egf"
10 resep pedas selesai dimasak
↓
Preference Update
↓
Spicy Affinity +20
```

---

Example:

```text id="jlwm9u"
8 resep Jawa disimpan
↓
Regional Preference
↓
Javanese Cuisine +15
```

---

# 11. Personalization Engine

Memory digunakan oleh:

---

Recipe Ranking

---

Recommendation Engine

---

Search Ranking

---

Future Meal Planning

---

Cooking Assistant

---

# 12. Memory Freshness

Tidak semua memory berlaku selamanya.

---

## Long-Term Memory

Examples:

* diet type
* spice preference

---

TTL:

Unlimited

---

## Medium-Term Memory

Examples:

* favorite cuisines

---

TTL:

Months

---

## Short-Term Memory

Examples:

* recently cooked recipes

---

TTL:

Days to weeks

---

# 13. Memory Storage Strategy

MVP menggunakan:

---

PostgreSQL

---

Tables:

```text id="lj6m3h"
user_preferences

user_behavior_signals

cooking_sessions

saved_recipes
```

---

No Vector Memory.

---

Reason:

Structured memory lebih mudah dikontrol dan dievaluasi.

---

# 14. Why Not Vector Memory

Untuk MVP.

Vector memory tidak memberikan nilai yang signifikan.

---

Structured Preferences:

* lebih murah
* lebih cepat
* lebih dapat dijelaskan

---

Sebagian besar kebutuhan personalisasi Pawona dapat diselesaikan menggunakan relational data.

---

# 15. Memory Privacy Principles

Pawona hanya menyimpan informasi yang relevan dengan pengalaman memasak.

---

Memory tidak digunakan untuk:

* profiling di luar domain kuliner
* iklan berbasis perilaku
* penggunaan lintas domain

---

Pengguna dapat:

* melihat preferensi
* memperbarui preferensi
* menghapus preferensi

---

# 16. Memory Flywheel

```text id="n0f2iz"
More Cooking Sessions
↓
More Behavioral Signals
↓
Better Preference Model
↓
Better Recommendations
↓
Higher Satisfaction
↓
More Cooking Sessions
```

---

Memory menjadi salah satu flywheel utama produk.

---

# 17. Relationship with RAG

RAG menjawab:

> Apa yang diketahui sistem tentang kuliner?

---

Memory menjawab:

> Apa yang diketahui sistem tentang pengguna?

---

Keduanya digunakan bersama oleh Recipe Intelligence Engine.

---

# 18. Future Evolution

Phase 1:

Preference Memory

---

Phase 2:

Behavioral Memory

---

Phase 3:

Household Memory

---

Phase 4:

Family Intelligence

---

Phase 5:

Household Food Intelligence

---

# 19. Success Metrics

## Recommendation Acceptance Rate

Target:

> 30%

---

## Repeat Cooking Rate

Target:

> 30%

---

## Personalized Recommendation CTR

Target:

Meningkat secara konsisten.

---

## Preference Prediction Accuracy

Future.

---

# 20. Summary

Memory System Pawona dibangun untuk memahami pengguna melalui preferensi dan perilaku memasak.

Pawona tidak berfokus pada conversation memory.

Pawona berfokus pada Culinary Preference Memory.

Dengan menggabungkan explicit preferences, behavioral signals, dan inferred preferences, Pawona mampu menghasilkan pengalaman yang semakin personal seiring waktu.

Memory menjadi fondasi utama personalisasi dan salah satu moat terpenting dalam jangka panjang.
