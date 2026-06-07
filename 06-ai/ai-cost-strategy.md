# AI Cost Strategy

**Document:** AI Cost Strategy
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi pengelolaan biaya AI untuk seluruh platform Pawona.

Tujuan utama strategi ini adalah memastikan bahwa sistem AI dapat berkembang secara berkelanjutan tanpa mengorbankan kualitas pengalaman pengguna maupun kesehatan bisnis.

AI Cost Strategy berlaku untuk:

* LLM Usage
* Vision AI
* Retrieval Systems
* Embedding Systems
* Future AI Agents

---

# 2. Cost Philosophy

Pawona mengadopsi prinsip:

> Intelligence First. Tokens Second.

Namun.

Pawona juga mengadopsi prinsip:

> Every Token Must Create User Value.

---

AI tidak boleh digunakan hanya karena tersedia.

AI hanya digunakan ketika benar-benar memberikan nilai bagi pengguna.

---

# 3. Strategic Goal

Membangun AI Platform yang:

* scalable
* sustainable
* cost-efficient

bahkan ketika jumlah pengguna meningkat secara signifikan.

---

# 4. Why AI Cost Matters

Consumer AI memiliki karakteristik unik.

---

Revenue per User:

Rendah

---

AI Cost per User:

Berpotensi tinggi

---

Tanpa strategi biaya yang jelas.

Pertumbuhan pengguna justru dapat menjadi risiko bisnis.

---

# 5. Cost Hierarchy

Semua request harus mengikuti hirarki biaya berikut.

---

```text
Cached Response
↓
Database Query
↓
Rule Engine
↓
Retrieval Layer
↓
Small Model
↓
Large Model
↓
Vision Model
```

---

Semakin ke atas.

Semakin murah.

---

Semakin ke bawah.

Semakin mahal.

---

# 6. Intelligence Hierarchy

Pawona menggunakan prinsip:

> Solve Without AI If Possible.

---

Examples:

### Shopping List

Database Logic

---

### Recipe Metadata

Database Query

---

### User Preferences

Memory Store

---

### Recommendation Ranking

Hybrid Logic

---

LLM hanya digunakan ketika reasoning diperlukan.

---

# 7. Cost-Aware Architecture

High-Level Flow:

```text
Request
↓
Can Cache Solve?
↓
Can Rules Solve?
↓
Can Retrieval Solve?
↓
Need AI?
↓
Model Routing
```

---

AI menjadi pilihan terakhir.

---

# 8. Model Routing Strategy

Tidak semua request menggunakan model yang sama.

---

## Tier 1

Fast / Cheap Models

Use Cases:

* classification
* extraction
* tagging

---

## Tier 2

Balanced Models

Use Cases:

* recommendation reasoning
* adaptation

---

## Tier 3

Premium Models

Use Cases:

* complex cooking assistance
* advanced personalization

---

Premium model harus digunakan secara selektif.

---

# 9. Retrieval Before Generation

Salah satu strategi penghematan biaya terbesar.

---

Flow:

```text
Knowledge
↓
Retrieval
↓
Reasoning
↓
Response
```

---

Bukan:

```text
Question
↓
LLM
↓
Everything
```

---

Expected Savings:

Significant

---

# 10. Structured Output Strategy

Output terstruktur mengurangi token.

---

Bad:

Paragraf panjang.

---

Good:

JSON terstruktur.

---

Benefits:

* cheaper
* predictable
* easier to cache

---

# 11. Context Optimization

Prompt tidak boleh membawa:

* seluruh profile pengguna
* seluruh history
* seluruh knowledge base

---

Only Relevant Context.

---

Benefits:

* lower latency
* lower cost
* better reliability

---

# 12. Memory Cost Strategy

Memory disimpan dalam:

---

PostgreSQL

---

Bukan:

Conversation Replay

---

Reason:

Structured memory lebih murah dibanding mengirim histori panjang ke model.

---

# 13. Embedding Cost Strategy

Embedding dilakukan:

---

At Ingestion Time

---

Not Query Time

---

Flow:

```text
New Recipe
↓
Embedding Once
↓
Store Forever
```

---

Avoid:

```text
Every Query
↓
New Embedding
```

---

# 14. Caching Strategy

Caching adalah cost lever terbesar.

---

## Layer 1

API Cache

---

## Layer 2

Retrieval Cache

---

## Layer 3

Recommendation Cache

---

## Layer 4

Prompt Cache

Future.

---

Frequently repeated requests harus dilayani dari cache.

---

# 15. Vision AI Cost Strategy

Vision AI adalah fitur mahal.

---

Rules:

* image compression
* limited image count
* confidence thresholds

---

Vision hanya digunakan ketika pengguna memang mengirim gambar.

---

Tidak ada background image processing.

---

# 16. AI Budget Allocation

Perkiraan distribusi biaya AI.

---

Recipe Recommendation

40%

---

Personalization

15%

---

Retrieval

15%

---

Vision AI

20%

---

Evaluation

10%

---

Distribusi dapat berubah seiring pertumbuhan produk.

---

# 17. Cost Monitoring

Metrics:

---

## Cost Per Request

---

## Cost Per Active User

---

## Cost Per Meal Completed

---

## Vision Cost Per Scan

---

## Retrieval Cost Per Query

---

Seluruh metrik harus dipantau secara real-time.

---

# 18. Unit Economics Framework

North Star Cost Metric:

Cost Per Successful Meal

---

Formula:

```text
Total AI Cost
/
AI-Assisted Meals Completed
```

---

Ini lebih penting daripada cost per request.

---

# 19. Cost Guardrails

Target awal:

---

AI Cost per Active User

Harus tetap rendah dan dapat diprediksi.

---

AI Cost Growth

Tidak boleh tumbuh lebih cepat daripada engagement growth.

---

Premium Features

Harus memiliki batas penggunaan yang jelas.

---

# 20. Free vs Premium AI Strategy

## Free Users

* recipe generation
* recipe search
* limited personalization

---

## Premium Users

* advanced cooking assistant
* vision AI quota lebih tinggi
* advanced personalization
* future meal planning

---

Model yang lebih mahal dapat dialokasikan untuk pengguna premium.

---

# 21. Future Optimization Opportunities

Phase 2

Model Distillation

---

Phase 3

Fine-Tuned Models

---

Phase 4

Local Inference

Selective.

---

Phase 5

Hybrid Multi-Model Architecture

---

# 22. Relationship with Other Documents

AI Cost Strategy mendukung:

---

Recipe Intelligence Engine

---

RAG Strategy

---

Memory Strategy

---

Prompting Strategy

---

Evaluation Framework

---

Seluruh keputusan AI harus mempertimbangkan biaya sebagai faktor desain utama.

---

# 23. Success Metrics

## Cost Per Successful Meal

Target:

Menurun seiring waktu.

---

## AI Cost Per Active User

Target:

Stabil.

---

## Average AI Latency

Target:

< 5 detik.

---

## Cache Hit Rate

Target:

Meningkat secara konsisten.

---

## Retrieval-to-Generation Ratio

Target:

Semakin banyak nilai diperoleh dari retrieval dibanding generation.

---

# 24. Summary

Pawona mengadopsi pendekatan Cost-Aware AI Architecture yang mengutamakan retrieval, memory, caching, dan structured systems sebelum menggunakan model AI yang mahal.

Prinsip utama:

Cached Response → Database → Rules → Retrieval → Small Model → Large Model → Vision Model

Dengan strategi ini, Pawona dapat membangun Culinary Intelligence Platform yang tetap ekonomis dan berkelanjutan meskipun jumlah pengguna berkembang secara signifikan.

Keberhasilan biaya AI diukur menggunakan metrik utama:

Cost Per Successful Meal.
