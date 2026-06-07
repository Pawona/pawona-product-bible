# RAG Strategy

**Document:** Retrieval-Augmented Generation Strategy
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi Retrieval-Augmented Generation (RAG) yang digunakan oleh Pawona.

Tujuan utama RAG bukan untuk menambahkan AI ke dalam produk.

Tujuan utama RAG adalah memastikan bahwa sistem AI menggunakan pengetahuan yang akurat, relevan, dan dapat dikontrol ketika menghasilkan rekomendasi.

RAG menjadi fondasi utama bagi:

* Recipe Intelligence Engine
* Recipe Search
* Personalized Recommendations
* Future Culinary Intelligence Systems

---

# 2. Why RAG Exists

Model bahasa memiliki keterbatasan:

* pengetahuan tidak selalu lengkap
* tidak memahami konteks lokal secara mendalam
* berpotensi menghasilkan halusinasi
* sulit diperbarui secara real-time

---

Pawona tidak mengandalkan model sebagai sumber kebenaran.

Sebaliknya:

```text
Knowledge Base
↓
Retrieval
↓
Reasoning
↓
Response
```

---

# 3. RAG Vision

Membangun Culinary Knowledge Infrastructure yang menjadi sumber pengetahuan utama seluruh sistem AI Pawona.

AI harus mengambil pengetahuan dari sistem ini sebelum menghasilkan rekomendasi.

---

# 4. Knowledge Architecture

Pawona menggunakan pendekatan:

```text
Knowledge Layer
↓
Retrieval Layer
↓
Reasoning Layer
↓
Response Layer
```

---

## Knowledge Layer

Menyimpan fakta.

---

## Retrieval Layer

Mengambil fakta yang relevan.

---

## Reasoning Layer

Mengolah fakta.

---

## Response Layer

Menyampaikan hasil kepada pengguna.

---

# 5. Culinary Knowledge Domains

Knowledge Base dibagi menjadi beberapa domain utama.

---

## Recipes

Informasi resep terstruktur.

---

Attributes:

* title
* ingredients
* steps
* servings
* duration
* difficulty
* region
* estimated_cost

---

## Ingredients

Pengetahuan bahan makanan.

---

Attributes:

* name
* aliases
* category
* storage information
* substitutions

---

## Cooking Methods

Teknik memasak.

---

Examples:

* tumis
* rebus
* goreng
* bakar

---

## Regional Cuisine

Kuliner daerah.

---

Examples:

* Jawa
* Sunda
* Minang
* Bali
* Bugis

---

## Ingredient Relationships

Hubungan antar bahan.

---

Examples:

* substitutions
* complementary ingredients
* flavor pairings

---

## Culinary Knowledge

Pengetahuan umum kuliner.

---

Examples:

* sejarah makanan
* budaya makanan
* tradisi memasak

---

# 6. Culinary Knowledge Graph

Dalam jangka panjang, Pawona akan membangun Culinary Knowledge Graph.

---

Concept:

```text
Ingredient
│
├── belongs_to
│
▼
Category

Ingredient
│
├── used_in
│
▼
Recipe

Recipe
│
├── originated_from
│
▼
Region

Recipe
│
├── uses
│
▼
Cooking Method
```

---

Knowledge Graph memungkinkan reasoning yang lebih baik dibanding pencarian teks biasa.

---

# 7. Retrieval Philosophy

Pawona menggunakan:

> Retrieve the simplest way possible.

---

Tidak semua query memerlukan vector search.

---

# 8. Retrieval Types

## Type 1 — Structured Retrieval

Menggunakan PostgreSQL.

---

Examples:

```text
Recipes
where region = Jawa
and difficulty = Easy
```

---

Use Cases:

* filters
* categories
* metadata

---

## Type 2 — Semantic Retrieval

Menggunakan pgvector.

---

Examples:

```text
menu murah untuk anak kos
```

---

Use Cases:

* natural language search
* similarity search
* concept search

---

## Type 3 — Hybrid Retrieval

Menggabungkan metadata dan semantic search.

---

Examples:

```text
masakan jawa murah untuk 4 orang
```

---

Flow:

```text
Metadata Filter
+
Vector Search
```

---

Ini menjadi strategi utama Pawona.

---

# 9. Retrieval Pipeline

Standard Pipeline:

```text
User Query
↓
Intent Understanding
↓
Retrieval Strategy Selection
↓
Knowledge Retrieval
↓
Ranking
↓
Reasoning
↓
Response
```

---

# 10. Embedding Strategy

Embedding digunakan untuk:

* recipes
* ingredients
* culinary descriptions

---

Embedding tidak digunakan untuk:

* user accounts
* analytics
* transactional data

---

# 11. Recipe Embeddings

Recipe embedding dibangun dari:

---

Recipe Title

---

Description

---

Ingredients

---

Cooking Method

---

Regional Metadata

---

Difficulty

---

Tujuan:

Meningkatkan kualitas semantic retrieval.

---

# 12. Ingredient Embeddings

Ingredient embeddings memungkinkan sistem memahami:

---

Synonyms

Examples:

* cabai
* cabe

---

Related Concepts

Examples:

* santan
* kelapa

---

Substitutions

Examples:

* bawang merah
* bawang bombay

---

# 13. Retrieval Ranking

Hasil retrieval tidak langsung diberikan ke pengguna.

Semua kandidat harus diranking.

---

Ranking Factors:

### Relevance

---

### Ingredient Match

---

### Personalization

---

### Budget Match

---

### Cooking Difficulty

---

### Completion Signals

Future.

---

# 14. Context Assembly

Setelah retrieval selesai.

Sistem membangun Context Package.

---

Example:

```json
{
  "user_preferences": {},
  "candidate_recipes": [],
  "ingredient_context": {},
  "regional_context": {}
}
```

---

Context Package menjadi input bagi AI Reasoning Layer.

---

# 15. RAG Cost Strategy

Pawona mengoptimalkan biaya sejak awal.

---

Hierarchy:

```text
Structured Query
↓
Hybrid Retrieval
↓
LLM Reasoning
```

---

LLM adalah resource paling mahal.

Karena itu digunakan terakhir.

---

# 16. Future Knowledge Expansion

Phase 1:

Recipe Knowledge

---

Phase 2:

Cooking Knowledge

---

Phase 3:

Pantry Knowledge

---

Phase 4:

Nutrition Knowledge

---

Phase 5:

Household Food Intelligence

---

Knowledge Layer akan berkembang tanpa perlu mengubah arsitektur inti.

---

# 17. Relationship with Memory

RAG menjawab:

> Apa yang diketahui sistem?

---

Memory menjawab:

> Apa yang diketahui sistem tentang pengguna?

---

Keduanya bekerja bersama.

---

# 18. Relationship with Recipe Intelligence Engine

Recipe Intelligence Engine adalah konsumen utama Knowledge Layer.

---

Flow:

```text
Knowledge Base
↓
Retrieval
↓
Recipe Intelligence Engine
↓
Recommendation
```

---

Tanpa RAG, Recipe Intelligence Engine kehilangan sumber pengetahuan utamanya.

---

# 19. Success Metrics

## Retrieval Accuracy

Target:

> 90%

---

## Top 5 Recipe Relevance

Target:

> 80%

---

## Query Success Rate

Target:

> 95%

---

## Retrieval Latency

Target:

< 300 ms

---

# 20. Summary

Pawona menggunakan pendekatan Knowledge-Driven AI yang mengutamakan retrieval sebelum generation.

Strategi RAG dibangun di atas tiga jenis retrieval:

1. Structured Retrieval
2. Semantic Retrieval
3. Hybrid Retrieval

Dengan memanfaatkan PostgreSQL, pgvector, metadata filtering, dan Culinary Knowledge Graph, Pawona membangun fondasi pengetahuan yang dapat berkembang menjadi sistem kecerdasan kuliner Indonesia dalam jangka panjang.

Knowledge menjadi sumber kebenaran utama.

AI menjadi lapisan reasoning dan personalisasi di atas pengetahuan tersebut.
