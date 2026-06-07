# Vision AI Strategy

**Document:** Vision AI Strategy
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi Computer Vision dan Multimodal AI yang digunakan oleh Pawona.

Vision AI memungkinkan Pawona memahami kondisi dapur pengguna melalui gambar dan mengubah informasi visual menjadi konteks yang dapat digunakan oleh Recipe Intelligence Engine.

Vision AI bukan sistem yang berdiri sendiri.

Vision AI merupakan bagian dari Culinary Intelligence Platform yang bertugas mengurangi hambatan antara pengguna dan rekomendasi memasak.

---

# 2. Vision Statement

Memungkinkan pengguna berinteraksi dengan Pawona menggunakan dunia nyata, bukan hanya teks.

---

# 3. Why Vision AI Exists

Sebagian besar pengguna mengetahui apa yang mereka miliki.

Tetapi mereka tidak selalu ingin mengetikkan seluruh daftar bahan.

---

Contoh:

Pengguna membuka kulkas.

Melihat:

* telur
* cabai
* tomat
* tempe

Daripada mengetik semuanya.

Pengguna cukup memotret isi kulkas.

---

Vision AI mengubah:

```text
Photo
↓
Ingredient Understanding
↓
Recipe Recommendation
```

---

# 4. Vision AI Philosophy

Vision AI mengikuti prinsip:

> Detect for Decisions.

---

Tujuan utama bukan mendeteksi objek.

Tujuan utama adalah membantu pengambilan keputusan memasak.

---

Bad Outcome:

```text
95% detection accuracy
0 value generated
```

---

Good Outcome:

```text
85% detection accuracy
Recipe successfully recommended
```

---

# 5. Vision AI Scope

MVP+

---

Vision AI tidak termasuk MVP Core.

---

Reason:

Product Thesis dapat divalidasi tanpa Computer Vision.

---

Vision AI diperkenalkan setelah:

* Recipe Engine stabil
* Retrieval stabil
* Personalization stabil

---

# 6. Vision AI Capability Roadmap

## Phase 1 — Ingredient Detection

Objective:

Mendeteksi bahan makanan.

---

Examples:

* telur
* tomat
* cabai
* tempe

---

Output:

Structured Ingredients List

---

## Phase 2 — Refrigerator Understanding

Objective:

Memahami isi kulkas secara lebih lengkap.

---

Output:

Ingredient Inventory

---

## Phase 3 — Pantry Understanding

Objective:

Memahami kondisi dapur secara menyeluruh.

---

Output:

Kitchen Context

---

## Phase 4 — Cooking Scene Understanding

Objective:

Memahami proses memasak.

---

Examples:

* bahan sedang dipotong
* bahan terlalu matang
* tingkat kematangan

---

## Phase 5 — Visual Cooking Assistant

Objective:

Memberikan bantuan memasak berbasis kamera secara real-time.

---

# 7. Vision AI Architecture

High-Level Flow:

```text
Image
↓
Image Processing
↓
Ingredient Detection
↓
Confidence Scoring
↓
Ingredient Extraction
↓
Recipe Intelligence Engine
↓
Recommendations
```

---

Vision AI menghasilkan konteks.

Recipe Intelligence Engine menghasilkan keputusan.

---

# 8. Input Sources

## Camera Capture

Primary.

---

## Gallery Upload

Primary.

---

## Multi-Image Upload

Future.

---

## Video Stream

Future.

---

# 9. Ingredient Detection System

## Purpose

Mengidentifikasi bahan makanan dari gambar.

---

Examples:

* bawang merah
* bawang putih
* cabai
* telur
* tempe
* tahu
* tomat

---

Output:

```json
{
  "ingredients": [
    {
      "name": "telur",
      "confidence": 0.94
    }
  ]
}
```

---

# 10. Ingredient Normalization

Deteksi visual harus dikonversi ke format standar.

---

Example:

```text
Cabe Rawit
↓
cabai_rawit
```

---

Example:

```text
Cabe Merah
↓
cabai_merah
```

---

Normalization penting untuk integrasi dengan Knowledge Layer.

---

# 11. Confidence Framework

Setiap hasil deteksi memiliki confidence score.

---

Example:

```json
{
  "ingredient": "tomat",
  "confidence": 0.91
}
```

---

Confidence digunakan untuk:

* ranking
* UI validation
* user confirmation

---

# 12. Human Verification Layer

Pawona tidak menganggap hasil Vision AI selalu benar.

---

Flow:

```text
Detected Ingredients
↓
User Confirmation
↓
Recipe Generation
```

---

Example:

"Saya menemukan:
✓ telur
✓ cabai
✓ tomat

Apakah sudah benar?"

---

# 13. Indonesian Ingredient Coverage

Vision AI harus dioptimalkan untuk bahan yang umum ditemukan di Indonesia.

---

Priority Categories:

### Protein

* ayam
* telur
* tempe
* tahu
* ikan

---

### Vegetables

* kangkung
* bayam
* sawi
* kol

---

### Spices

* cabai
* bawang
* jahe
* kunyit

---

### Pantry Items

* santan
* kecap
* saus

Future.

---

# 14. Multimodal Context Assembly

Vision AI tidak bekerja sendiri.

---

Image Output:

```json
{
  "ingredients": []
}
```

---

Digabung dengan:

```json
{
  "user_preferences": {},
  "memory_context": {}
}
```

---

Menjadi:

```json
{
  "kitchen_context": {}
}
```

---

Input untuk Recipe Intelligence Engine.

---

# 15. Vision + Memory Synergy

Vision mengetahui:

Apa yang ada di dapur.

---

Memory mengetahui:

Apa yang disukai pengguna.

---

Example:

Vision:

```text
Telur
Tempe
Cabai
```

---

Memory:

```text
Prefers spicy food
```

---

Output:

```text
Orek Tempe Pedas
```

---

# 16. Vision + RAG Synergy

Vision:

Ingredient Detection

---

RAG:

Knowledge Retrieval

---

Flow:

```text
Image
↓
Ingredient Extraction
↓
Knowledge Retrieval
↓
Recommendation
```

---

Vision tidak menghasilkan resep.

Vision menghasilkan konteks.

---

# 17. Future Advanced Capabilities

## Freshness Detection

Future.

---

Examples:

* sayur layu
* buah busuk

---

## Quantity Estimation

Future.

---

Examples:

* 3 telur
* 2 tomat

---

## Shelf-Life Prediction

Future.

---

Examples:

* segera digunakan
* masih aman

---

## Food Waste Prevention

Future.

---

Examples:

* bahan yang perlu diprioritaskan

---

# 18. Privacy Principles

Semua gambar diperlakukan sebagai data sensitif.

---

Principles:

* minimal retention
* secure storage
* explicit user consent

---

Images tidak digunakan di luar tujuan produk tanpa persetujuan pengguna.

---

# 19. Success Metrics

## Ingredient Detection Accuracy

Target:

> 85%

---

## Ingredient Confirmation Rate

Target:

> 80%

---

## Scan-to-Recipe Conversion

Target:

> 50%

---

## Vision-Assisted Cooking Sessions

Target:

Meningkat secara konsisten.

---

# 20. Relationship with Other AI Systems

Vision AI adalah Input Layer.

---

Terhubung dengan:

### Recipe Intelligence Engine

Decision Layer

---

### RAG Strategy

Knowledge Layer

---

### Memory Strategy

Personalization Layer

---

### Prompting Strategy

Response Layer

---

# 21. Summary

Vision AI memungkinkan Pawona memahami kondisi dapur pengguna melalui gambar.

Vision AI bukan generator resep.

Vision AI adalah friction removal layer yang mengubah dunia visual menjadi konteks yang dapat digunakan oleh Recipe Intelligence Engine.

Dengan menggabungkan Ingredient Detection, Memory, dan Knowledge Retrieval, Pawona dapat memberikan pengalaman memasak yang lebih cepat, lebih natural, dan lebih personal.
