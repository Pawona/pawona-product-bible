# Backend Architecture

**Document:** Backend Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur backend Pawona.

Backend bertanggung jawab sebagai orchestration layer yang menghubungkan aplikasi mobile, database, knowledge systems, AI systems, dan analytics platform.

Backend tidak hanya berfungsi sebagai CRUD API.

Backend merupakan pusat koordinasi seluruh Culinary Intelligence Platform.

---

# 2. Architecture Vision

Backend Pawona dibangun untuk:

* mendukung iterasi produk yang cepat
* menjaga kompleksitas tetap rendah
* mempermudah pengembangan oleh tim kecil
* memungkinkan ekspansi menuju AI Platform di masa depan

---

# 3. Architecture Style

## Selected Architecture

Modular Monolith

---

Framework:

NestJS

---

Database:

Supabase PostgreSQL

---

Reason:

* deployment sederhana
* biaya rendah
* mudah dipahami
* cocok untuk tim kecil
* mudah dipecah menjadi services jika diperlukan

---

# 4. High-Level Backend Architecture

```text
Flutter App
     │
     ▼
API Layer
     │
     ▼
Application Layer
     │
 ┌───┼───────────────┐
 ▼   ▼               ▼

Domain Modules   AI Layer
       │
       ▼
Data Layer
       │
       ▼
Supabase PostgreSQL
```

---

# 5. Backend Responsibilities

Backend bertanggung jawab untuk:

---

Authentication

---

Business Logic

---

Recipe Recommendation Orchestration

---

AI Orchestration

---

Knowledge Retrieval

---

User Memory Updates

---

Analytics Events

---

Third-Party Integrations

---

# 6. Module Architecture

Backend dibagi menjadi domain modules.

---

```text
src/

modules/
```

---

Setiap module memiliki:

```text
controllers
services
repositories
dto
entities
```

---

# 7. Core Modules

## Auth Module

Responsibilities:

* authentication
* session validation
* user onboarding

---

Integrates With:

Supabase Auth

---

# 8. User Module

Responsibilities:

* profiles
* preferences
* settings

---

Tables:

```text
users
user_preferences
```

---

# 9. Recipe Module

Responsibilities:

* recipes
* ingredients
* recipe metadata

---

Tables:

```text
recipes
recipe_ingredients
ingredients
```

---

# 10. Recommendation Module

Responsibilities:

* recommendation orchestration
* ranking
* adaptation

---

Inputs:

* ingredients
* preferences
* memory

---

Outputs:

* ranked recipes

---

Core Product Module.

---

# 11. Cooking Module

Responsibilities:

* cooking sessions
* cooking progress
* completion tracking

---

Tables:

```text
cooking_sessions
cooking_steps
```

---

# 12. Kitchen Module

Responsibilities:

* saved recipes
* shopping lists

---

Tables:

```text
saved_recipes
shopping_lists
shopping_list_items
```

---

# 13. AI Module

Responsibilities:

* model routing
* prompt orchestration
* response generation

---

Integrates With:

* OpenAI
* Anthropic
* Gemini

---

Detailed architecture dijelaskan pada AI Architecture.

---

# 14. Memory Module

Responsibilities:

* preference updates
* behavioral signals
* personalization data

---

Tables:

```text
user_behavior_signals
preference_profiles
```

---

# 15. Analytics Module

Responsibilities:

* event collection
* telemetry
* product metrics

---

Examples:

```text
recipe_generated
recipe_saved
cooking_started
cooking_completed
```

---

# 16. API Layer

Architecture:

REST API

---

Versioning:

```text
/api/v1
```

---

Future:

```text
/api/v2
```

---

GraphQL tidak digunakan.

---

Reason:

REST lebih sederhana untuk MVP.

---

# 17. Request Lifecycle

Standard Flow:

```text
Client Request
↓
Controller
↓
DTO Validation
↓
Service
↓
Repository
↓
Database
↓
Response
```

---

Business logic hanya boleh berada di Service Layer.

---

# 18. Validation Strategy

Validation menggunakan:

class-validator

class-transformer

---

Validation dilakukan sebelum business logic dieksekusi.

---

# 19. Repository Pattern

Database access tidak dilakukan langsung dari service.

---

Flow:

```text
Service
↓
Repository
↓
Database
```

---

Benefits:

* maintainability
* testability

---

# 20. AI Request Flow

Recommendation Request:

```text
Ingredients
↓
Recommendation Service
↓
Retrieval
↓
Memory
↓
AI Gateway
↓
Response
```

---

Backend menjadi orchestration layer.

---

# 21. Background Jobs

MVP menggunakan:

BullMQ

Redis

---

Use Cases:

* analytics processing
* embeddings generation
* notification delivery
* evaluation jobs

---

Tidak digunakan untuk seluruh request.

---

# 22. Caching Strategy

Level 1

Application Cache

---

Level 2

Recipe Cache

---

Level 3

Recommendation Cache

---

Redis digunakan sebagai cache utama.

---

# 23. Error Handling Strategy

Standard Response Format:

```json
{
  "success": false,
  "error": {
    "code": "RECIPE_NOT_FOUND",
    "message": "Recipe not found"
  }
}
```

---

Seluruh API harus konsisten.

---

# 24. Security Layer

Applied Globally:

---

Authentication Guards

---

Rate Limiting

---

Input Validation

---

Audit Logging

---

Detailed implementation dijelaskan pada Security Architecture.

---

# 25. Event Strategy

MVP menggunakan Domain Events sederhana.

---

Examples:

```text
RecipeGenerated
RecipeSaved
CookingCompleted
```

---

Implementation:

NestJS EventEmitter

---

Kafka tidak digunakan.

---

# 26. Database Access Strategy

Source of Truth:

Supabase PostgreSQL

---

ORM:

Prisma

---

Reason:

* developer experience
* type safety
* migrations
* maintainability

---

# 27. File Upload Flow

```text
Flutter
↓
Backend
↓
Supabase Storage
↓
URL
↓
Database
```

---

Backend tetap menjadi kontrol utama.

---

# 28. API Design Principles

Principle 1

Consistency

---

Principle 2

Predictability

---

Principle 3

Idempotency

---

Principle 4

Backward Compatibility

---

# 29. Scalability Strategy

Phase 1

Single Service

---

Phase 2

Dedicated AI Service

---

Phase 3

Dedicated Analytics Service

---

Hanya dilakukan ketika diperlukan.

---

# 30. Development Structure

Recommended Structure:

```text
src/

common/

config/

modules/

ai/

database/

queues/

integrations/

analytics/
```

---

Feature-first organization.

---

# 31. Non-Goals

Backend MVP tidak menggunakan:

* microservices
* GraphQL
* Kafka
* CQRS
* service mesh
* distributed transactions

---

Reason:

Tidak memberikan nilai signifikan pada tahap MVP.

---

# 32. Architecture Success Metrics

Backend dianggap berhasil apabila:

* deployment sederhana
* mudah dipahami engineer baru
* mampu mendukung iterasi produk cepat
* AI dapat diintegrasikan tanpa kompleksitas tinggi
* maintainable oleh tim kecil

---

# 33. Summary

Backend Pawona dibangun menggunakan NestJS Modular Monolith dengan pendekatan domain-driven modules.

Backend berfungsi sebagai Culinary Intelligence Orchestrator yang menghubungkan mobile application, knowledge systems, memory systems, dan AI systems.

Prinsip utama:

Simple Architecture.
Fast Iteration.
AI-Native Design.
