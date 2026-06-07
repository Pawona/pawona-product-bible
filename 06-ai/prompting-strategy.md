# Prompting Strategy

**Document:** Prompting Strategy
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi prompting yang digunakan oleh seluruh sistem AI Pawona.

Prompting bukan sumber utama kecerdasan Pawona.

Kecerdasan utama berasal dari:

* Knowledge Layer
* Retrieval Layer
* Memory Layer
* Recipe Intelligence Engine

Prompting berfungsi sebagai mekanisme yang menghubungkan sistem tersebut dengan Large Language Model (LLM).

---

# 2. Prompting Philosophy

Pawona menggunakan pendekatan:

> Context First, Prompt Second.

---

AI tidak diminta berpikir dari nol.

AI diberikan:

* fakta
* konteks
* preferensi
* kandidat solusi

sebelum diminta menghasilkan jawaban.

---

Flow:

```text
Knowledge
↓
Retrieval
↓
Memory
↓
Context Assembly
↓
Prompt
↓
Model
↓
Response
```

---

# 3. Prompting Goals

Prompt harus membantu model:

---

## Generate Consistent Outputs

---

## Reduce Hallucinations

---

## Follow Product Principles

---

## Respect User Context

---

## Produce Structured Responses

---

# 4. Prompting Architecture

Pawona menggunakan layered prompting architecture.

---

```text
System Prompt
↓
Task Prompt
↓
Retrieved Context
↓
User Context
↓
User Input
```

---

Setiap layer memiliki tanggung jawab berbeda.

---

# 5. System Prompt Layer

## Purpose

Menentukan identitas dasar AI.

---

System Prompt menjelaskan:

* siapa Pawona
* domain yang diperbolehkan
* prinsip AI
* gaya komunikasi

---

Example Responsibilities

* culinary assistant
* Indonesian cooking expert
* practical helper

---

System Prompt bersifat relatif stabil.

---

# 6. Task Prompt Layer

## Purpose

Menentukan pekerjaan yang harus dilakukan.

---

Contoh task:

### Recipe Recommendation

---

### Recipe Adaptation

---

### Cooking Assistance

---

### Ingredient Explanation

---

Setiap task memiliki template tersendiri.

---

# 7. Retrieved Context Layer

## Purpose

Memberikan fakta yang relevan.

---

Sources:

* recipes
* ingredients
* cooking methods
* culinary knowledge

---

Example

```json
{
  "candidate_recipes": [],
  "ingredient_context": {},
  "retrieved_knowledge": {}
}
```

---

Model tidak boleh mengabaikan context ini.

---

# 8. User Context Layer

## Purpose

Memberikan personalisasi.

---

Sources:

* preferences
* cooking history
* behavior signals

---

Example

```json
{
  "spicy_level": "high",
  "budget_type": "low",
  "favorite_region": "jawa"
}
```

---

# 9. User Input Layer

Input asli pengguna.

---

Examples

```text
Saya punya telur dan tempe.
```

---

```text
Menu murah untuk 4 orang.
```

---

Layer ini selalu berada paling bawah.

---

# 10. Context Assembly Strategy

Sebelum prompt dikirim ke model.

Sistem membangun Context Package.

---

Example:

```json
{
  "user_preferences": {},
  "candidate_recipes": [],
  "knowledge_context": {},
  "task": "recipe_recommendation"
}
```

---

Prompt menerima Context Package yang telah dipersiapkan.

---

# 11. Prompt Templates

Pawona menggunakan template-based prompting.

---

## Recipe Recommendation Template

Purpose:

Merekomendasikan menu.

---

Inputs:

* ingredients
* preferences
* candidate recipes

---

Output:

* ranked recommendations
* explanations

---

## Recipe Adaptation Template

Purpose:

Menyesuaikan resep.

---

Inputs:

* original recipe
* user constraints

---

Output:

* adapted recipe

---

## Cooking Assistant Template

Purpose:

Membantu saat memasak.

---

Inputs:

* recipe
* cooking step
* user question

---

Output:

* contextual guidance

---

# 12. Structured Output Strategy

Sebisa mungkin model menghasilkan output terstruktur.

---

Example:

```json
{
  "recommended_recipes": [],
  "reasoning": [],
  "tips": []
}
```

---

Structured outputs:

* lebih mudah diuji
* lebih mudah divalidasi
* lebih mudah diproses aplikasi

---

# 13. Prompt Routing Strategy

Tidak semua request menggunakan prompt yang sama.

---

Routing Layer menentukan:

```text
Recipe Request
↓
Recipe Prompt
```

---

```text
Cooking Question
↓
Cooking Prompt
```

---

```text
Ingredient Question
↓
Ingredient Prompt
```

---

Setiap use case memiliki prompt yang berbeda.

---

# 14. Model Routing Strategy

Prompting Strategy bekerja bersama Model Routing.

---

Fast Models

Use Cases:

* classification
* extraction
* tagging

---

Smart Models

Use Cases:

* recommendation reasoning
* adaptation
* cooking assistance

---

Model dipilih berdasarkan kebutuhan tugas.

---

# 15. Prompt Versioning

Semua prompt harus memiliki versi.

---

Example:

```text
recipe_recommendation_v1

recipe_recommendation_v2

recipe_recommendation_v3
```

---

Tujuan:

* rollback
* experimentation
* evaluation

---

# 16. Prompt Experimentation

Perubahan prompt harus diuji.

---

Metrics:

* acceptance rate
* recommendation quality
* completion rate

---

Prompt tidak boleh diubah hanya berdasarkan opini.

---

# 17. Hallucination Prevention

Prompt harus:

---

Instruct Retrieval Usage

---

Prefer Retrieved Facts

---

Avoid Unsupported Claims

---

Reject Unknown Facts

---

Model harus lebih memilih:

"I don't know."

dibanding mengarang.

---

# 18. Personalization Injection

Personalisasi tidak ditulis ulang dalam prompt.

---

Personalisasi diberikan sebagai context.

---

Bad:

```text
User suka pedas.
User suka pedas.
User suka pedas.
```

---

Good:

```json
{
  "spicy_level": "high"
}
```

---

Prompt kemudian menggunakan informasi tersebut.

---

# 19. Cost Optimization Principles

Prompt harus:

* ringkas
* relevan
* terstruktur

---

Prompt tidak boleh:

* membawa seluruh histori
* membawa seluruh knowledge base
* membawa seluruh profil pengguna

---

Hanya konteks yang diperlukan.

---

# 20. Relationship with Other Systems

Prompting Strategy berada di atas:

* RAG Strategy
* Memory Strategy
* Recipe Intelligence Engine

---

Prompt bukan pengganti sistem tersebut.

Prompt adalah jembatan antara sistem dan model.

---

# 21. Future Evolution

Phase 1

Template Prompting

---

Phase 2

Dynamic Context Assembly

---

Phase 3

Tool-Aware Prompting

---

Phase 4

Agent-Oriented Orchestration

---

Phase 5

Multi-Agent Culinary Intelligence

---

# 22. Success Metrics

## Structured Output Success Rate

Target:

> 95%

---

## Hallucination Rate

Target:

< 5%

---

## Prompt Failure Rate

Target:

< 2%

---

## Recommendation Acceptance Rate

Target:

> 30%

---

# 23. Summary

Pawona menggunakan pendekatan Context First, Prompt Second.

Prompting bukan sumber kecerdasan utama.

Prompting adalah orchestration layer yang menghubungkan Knowledge Layer, Retrieval Layer, dan Memory Layer dengan model AI.

Dengan menggunakan layered prompting, structured outputs, prompt routing, dan context assembly, Pawona dapat menghasilkan respons yang lebih konsisten, lebih aman, lebih personal, dan lebih mudah dievaluasi dibanding pendekatan prompt-centric tradisional.
