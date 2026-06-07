# AI Architecture

**Document:** AI Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** AI Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur teknis AI yang digunakan oleh Pawona.

AI Architecture menerjemahkan seluruh strategi AI yang telah didefinisikan pada Chapter 06 menjadi sistem yang dapat diimplementasikan oleh engineering team.

Tujuan utama AI Architecture adalah membangun Culinary Intelligence Platform yang:

* scalable
* maintainable
* model agnostic
* cost efficient
* measurable

---

# 2. AI Architecture Vision

AI bukan fitur.

AI adalah platform capability.

---

Pawona membangun:

> Culinary Intelligence Platform

yang mampu:

* memahami bahan
* memahami pengguna
* memahami konteks
* menghasilkan keputusan memasak

secara konsisten.

---

# 3. AI System Principles

## Retrieval Before Generation

---

## Context Before Prompt

---

## Memory Before Personalization

---

## Safety Before Response

---

## Outcome Before Intelligence

---

Seluruh komponen AI harus mengikuti prinsip tersebut.

---

# 4. High-Level AI Architecture

```text
User Request
      │
      ▼

AI Gateway
      │

 ┌────┼──────────────┐
 ▼    ▼              ▼

Retrieval Memory Prompting

      │
      ▼

Context Assembly
      │
      ▼

Model Router
      │

 ┌────┼──────────────┐
 ▼    ▼              ▼

OpenAI Claude Gemini

      │
      ▼

Safety Layer
      │
      ▼

Response
```

---

# 5. AI Architecture Layers

AI dibagi menjadi enam layer utama.

---

## Layer 1 — Input Layer

Memahami input pengguna.

---

Sources:

* text
* voice (future)
* image (future)

---

## Layer 2 — Knowledge Layer

Menyediakan pengetahuan kuliner.

---

Sources:

* recipes
* ingredients
* culinary knowledge

---

## Layer 3 — Memory Layer

Menyediakan personalisasi.

---

Sources:

* preferences
* behavior
* cooking history

---

## Layer 4 — Reasoning Layer

Melakukan pengambilan keputusan.

---

Components:

* ranking
* adaptation
* recommendation

---

## Layer 5 — Safety Layer

Melakukan validasi.

---

## Layer 6 — Delivery Layer

Menghasilkan respons final.

---

# 6. AI Gateway

AI Gateway menjadi pintu masuk seluruh request AI.

---

Responsibilities:

* request routing
* model selection
* retry logic
* fallback logic
* logging

---

AI Gateway mengisolasi aplikasi dari provider AI.

---

# 7. AI Internal Structure

Recommended Structure:

```text
src/

ai/

gateway/

providers/

retrieval/

memory/

prompting/

evaluation/

safety/

vision/
```

---

Setiap domain memiliki tanggung jawab yang jelas.

---

# 8. Provider Layer

Provider Layer bertanggung jawab menghubungkan sistem dengan model eksternal.

---

Supported Providers:

### OpenAI

Default.

---

### Anthropic

Secondary.

---

### Gemini

Secondary.

---

Future:

### Open Source Models

Optional.

---

# 9. Model Agnostic Design

Business logic tidak boleh bergantung pada provider.

---

Bad:

```text
RecommendationService
↓
OpenAI SDK
```

---

Good:

```text
RecommendationService
↓
AI Gateway
↓
Provider
```

---

# 10. Retrieval Layer

Implements:

RAG Strategy

---

Responsibilities:

* retrieval
* semantic search
* hybrid search
* context building

---

Sources:

* PostgreSQL
* pgvector

---

# 11. Memory Layer

Implements:

Memory Strategy

---

Responsibilities:

* preference retrieval
* behavior aggregation
* personalization context

---

Inputs:

* user profile
* behavior signals

---

Outputs:

* preference context

---

# 12. Prompting Layer

Implements:

Prompting Strategy

---

Responsibilities:

* prompt assembly
* context injection
* prompt versioning

---

Inputs:

* task
* retrieval context
* memory context

---

Outputs:

* final prompt package

---

# 13. Context Assembly Layer

Central orchestration layer.

---

Combines:

```text
Knowledge
+
Memory
+
Task Context
+
User Context
```

---

Output:

Context Package

---

Example:

```json
{
  "task": "recipe_recommendation",
  "recipes": [],
  "preferences": {},
  "ingredients": []
}
```

---

# 14. Model Routing Layer

Responsible for selecting the most appropriate model.

---

Routing Criteria:

* task complexity
* latency requirements
* cost
* provider availability

---

# 15. Routing Strategy

## Fast Models

Tasks:

* extraction
* classification

---

## Standard Models

Tasks:

* recommendation
* adaptation

---

## Premium Models

Tasks:

* advanced cooking assistant

Future.

---

# 16. Fallback Strategy

Provider failures should not break the system.

---

Flow:

```text
OpenAI
↓ fail
Anthropic
↓ fail
Gemini
```

---

Graceful degradation is required.

---

# 17. Recommendation Pipeline

Core Pipeline:

```text
Ingredients
↓
Retrieval
↓
Ranking
↓
Memory
↓
Prompt Assembly
↓
Model
↓
Safety
↓
Response
```

---

Most important pipeline in Pawona.

---

# 18. Vision Pipeline

Future.

---

Flow:

```text
Image
↓
Vision Model
↓
Ingredient Extraction
↓
Knowledge Retrieval
↓
Recommendation Pipeline
```

---

Vision becomes input.

Not decision layer.

---

# 19. Safety Pipeline

Every AI response passes through:

---

Safety Validation

---

Policy Validation

---

Confidence Validation

---

Only then:

Response Delivery

---

# 20. Evaluation Pipeline

Every AI interaction generates:

* telemetry
* metrics
* quality signals

---

Examples:

```text
recommendation_accepted
cooking_completed
prompt_failed
```

---

Used by Evaluation Framework.

---

# 21. Cost Optimization Architecture

Priority Order:

```text
Cache
↓
Retrieval
↓
Small Model
↓
Large Model
```

---

LLM should be the last expensive step.

---

# 22. Caching Strategy

## Recommendation Cache

---

## Retrieval Cache

---

## Prompt Cache

Future.

---

Goal:

Reduce cost and latency.

---

# 23. AI Queue Strategy

BullMQ + Redis

---

Use Cases:

* embeddings generation
* evaluation jobs
* knowledge ingestion

---

Not for real-time recommendations.

---

# 24. Knowledge Ingestion Pipeline

```text
Recipe Source
↓
Normalization
↓
Validation
↓
Embedding
↓
Knowledge Base
```

---

Allows continuous expansion of Culinary Knowledge.

---

# 25. Observability

AI-specific metrics:

---

Latency

---

Cost

---

Acceptance Rate

---

Completion Rate

---

Hallucination Rate

---

Every AI component must be observable.

---

# 26. Security

AI-specific protections:

---

Prompt Injection Protection

---

Rate Limiting

---

Provider Key Isolation

---

Audit Logging

---

Integrated with Security Architecture.

---

# 27. Scalability Roadmap

Phase 1

Embedded AI Module

---

Phase 2

Dedicated AI Service

---

Phase 3

Dedicated Intelligence Platform

---

Phase 4

Multi-Agent Architecture

Future.

---

# 28. Non-Goals

AI Architecture MVP does not include:

* autonomous agents
* long-running workflows
* multi-agent orchestration
* self-training systems

---

Focus remains on recommendation quality.

---

# 29. Architecture Success Metrics

AI Architecture is successful when:

* recommendations improve over time
* costs remain predictable
* provider changes are easy
* latency stays low
* personalization improves

---

# 30. Summary

Pawona AI Architecture is built around six core layers:

Input → Knowledge → Memory → Reasoning → Safety → Delivery

The architecture is model agnostic and designed around retrieval, personalization, and orchestration rather than dependence on a single AI provider.

AI is treated as a platform capability that powers the entire Culinary Intelligence Platform and serves as the foundation for future household food intelligence systems.
