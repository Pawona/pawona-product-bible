# Technical Architecture

**Document:** Technical Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur teknis tingkat tinggi untuk platform Pawona.

Technical Architecture menjadi referensi utama bagi seluruh keputusan engineering dan menjelaskan bagaimana komponen frontend, backend, AI, data, dan infrastructure bekerja bersama untuk mendukung Product Vision.

Dokumen ini tidak membahas detail implementasi masing-masing komponen secara mendalam. Detail tersebut dijelaskan pada dokumen engineering terkait.

---

# 2. Architecture Vision

Pawona dibangun sebagai:

> AI-Native Culinary Intelligence Platform untuk rumah tangga Indonesia.

Arsitektur dirancang untuk:

* mempercepat validasi Product-Market Fit
* menjaga kompleksitas tetap rendah
* memungkinkan iterasi produk yang cepat
* mendukung evolusi menuju platform kecerdasan kuliner jangka panjang

---

# 3. Engineering Principles

## Principle 1 — Product-Market Fit First

Optimalkan kecepatan belajar dibanding skalabilitas prematur.

---

## Principle 2 — Simplicity Over Complexity

Pilih solusi paling sederhana yang dapat memenuhi kebutuhan bisnis.

---

## Principle 3 — Modular by Design

Setiap domain dibangun secara modular agar dapat dipisahkan menjadi service terpisah di masa depan apabila diperlukan.

---

## Principle 4 — AI as a Platform Capability

AI bukan fitur.

AI adalah kapabilitas inti platform.

---

## Principle 5 — Cloud-Native

Seluruh sistem dirancang untuk berjalan di cloud sejak hari pertama.

---

## Principle 6 — Model Agnostic

Pawona tidak bergantung pada satu provider AI.

---

# 4. High-Level System Architecture

```text
┌────────────────────────────┐
│        Flutter App         │
└─────────────┬──────────────┘
              │
              ▼
┌────────────────────────────┐
│        API Gateway         │
│          NestJS            │
└─────────────┬──────────────┘
              │
 ┌────────────┼────────────┐
 ▼            ▼            ▼

User      Recipe      AI Gateway
Domain    Domain

              │
              ▼

     ┌─────────────────┐
     │ Supabase (PG)   │
     └─────────────────┘

              │
              ▼

     ┌─────────────────┐
     │ Knowledge Layer │
     └─────────────────┘

              │
              ▼

     ┌─────────────────┐
     │ AI Providers    │
     └─────────────────┘
```

---

# 5. Architecture Style

## MVP Architecture

Pawona menggunakan:

### Modular Monolith

---

Reason:

* tim kecil
* deployment sederhana
* biaya rendah
* pengembangan cepat

---

Bukan:

* microservices
* distributed architecture
* service mesh

---

# 6. Core Architecture Layers

Platform dibagi menjadi lima lapisan utama.

---

## Presentation Layer

Flutter Mobile Application.

---

Responsibilities:

* UI
* UX
* state management
* offline cache

---

## Application Layer

NestJS API.

---

Responsibilities:

* business logic
* orchestration
* validation

---

## Intelligence Layer

AI Platform.

---

Responsibilities:

* retrieval
* ranking
* reasoning
* personalization

---

## Data Layer

Database dan storage.

---

Responsibilities:

* persistence
* knowledge storage
* analytics

---

## Infrastructure Layer

Cloud services.

---

Responsibilities:

* deployment
* networking
* monitoring

---

# 7. Core Domains

Backend dibangun berdasarkan domain bisnis.

---

## User Domain

Examples:

* authentication
* profile
* preferences

---

## Recipe Domain

Examples:

* recipes
* ingredients
* recommendations

---

## Cooking Domain

Examples:

* cooking sessions
* progress tracking

---

## Kitchen Domain

Examples:

* shopping lists
* saved recipes

---

## AI Domain

Examples:

* recommendations
* retrieval
* personalization

---

## Analytics Domain

Examples:

* events
* metrics
* telemetry

---

# 8. Primary User Flow

Core Product Loop:

```text
User
↓
Ingredients
↓
Recipe Recommendation
↓
Recipe Detail
↓
Cooking Session
↓
Completion
↓
Memory Update
↓
Better Recommendations
```

Seluruh arsitektur harus mendukung flow ini.

---

# 9. AI Architecture Position

AI merupakan first-class architecture component.

---

AI tidak berada di sisi frontend.

AI tidak berada di dalam database.

AI berjalan sebagai domain khusus dalam backend.

---

Flow:

```text
Request
↓
AI Gateway
↓
Retrieval
↓
Memory
↓
Prompt Assembly
↓
Model Routing
↓
Response
```

---

# 10. Data Architecture

Data dibagi menjadi tiga kategori utama.

---

## Transactional Data

Examples:

* users
* preferences
* cooking sessions

---

## Knowledge Data

Examples:

* recipes
* ingredients
* culinary knowledge

---

## Behavioral Data

Examples:

* events
* interactions
* recommendations

---

# 11. Source of Truth Strategy

Single Source of Truth.

---

User Data:

PostgreSQL

---

Recipe Data:

PostgreSQL

---

Knowledge Data:

PostgreSQL + Vector Index

---

Behavior Data:

Analytics Platform

---

# 12. AI Provider Strategy

Pawona menggunakan provider abstraction layer.

---

Supported Providers:

* OpenAI
* Anthropic
* Gemini

Future:

* Open Source Models

---

Default Provider:

OpenAI

---

Benefits:

* vendor independence
* cost optimization
* model experimentation

---

# 13. Scalability Strategy

Scalability dilakukan secara bertahap.

---

Phase 1

Single Backend Service

---

Phase 2

Separate AI Services

---

Phase 3

Dedicated Intelligence Infrastructure

---

Phase 4

Distributed Services

Jika benar-benar diperlukan.

---

# 14. Security Philosophy

Security by Default.

---

Key Principles:

* least privilege
* secure secrets
* encrypted communication
* privacy first

---

Detailed architecture dijelaskan pada Security Architecture.

---

# 15. Reliability Philosophy

Platform harus:

* resilient
* observable
* recoverable

---

Failure pada AI provider tidak boleh menyebabkan aplikasi gagal total.

---

Fallback strategy wajib tersedia.

---

# 16. Observability Philosophy

Semua komponen harus dapat diukur.

---

Categories:

* application metrics
* AI metrics
* business metrics
* infrastructure metrics

---

"If it cannot be measured, it cannot be improved."

---

# 17. Deployment Strategy

Environment:

### Development

---

### Staging

---

### Production

---

CI/CD menjadi standar deployment.

---

Manual deployment hanya digunakan untuk emergency situations.

---

# 18. Technology Decisions

## Mobile

Flutter

---

## Backend

NestJS

---

## Database

Supabase PostgreSQL

---

## Authentication

Supabase Auth

---

## Storage

Supabase Storage

---

## AI Providers

OpenAI
Anthropic
Gemini

---

## Analytics

PostHog

---

## Monitoring

Sentry

---

## CDN

Cloudflare

---

# 19. Non-Goals

Arsitektur ini tidak dioptimalkan untuk:

* multi-region deployment
* multi-cloud strategy
* enterprise compliance
* millions of concurrent users

pada fase awal.

---

Prioritas utama adalah:

* speed
* simplicity
* maintainability

---

# 20. Future Evolution

Expected Evolution:

```text
MVP
↓
Product-Market Fit
↓
Growth
↓
AI Platform Expansion
↓
Household Intelligence Platform
```

Arsitektur harus mampu berkembang mengikuti tahapan tersebut tanpa memerlukan rewrite besar.

---

# 21. Architecture Success Metrics

Technical Architecture dianggap berhasil apabila:

* engineering velocity tinggi
* deployment sederhana
* biaya operasional terkendali
* AI dapat berkembang tanpa perubahan besar
* produk dapat mencapai Product-Market Fit dengan cepat

---

# 22. Summary

Pawona dibangun menggunakan pendekatan Modular Monolith berbasis NestJS, Flutter, dan Supabase dengan AI sebagai komponen inti platform.

Arsitektur dirancang untuk mendukung tujuan utama:

Membantu rumah tangga Indonesia mengambil keputusan memasak yang lebih cerdas melalui Culinary Intelligence Platform yang sederhana, scalable, dan berkelanjutan.

Prinsip utama:

Product-Market Fit First.
