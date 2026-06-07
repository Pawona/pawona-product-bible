# Data Architecture

**Document:** Data Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Data & Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur data Pawona.

Data Architecture menjelaskan:

* bagaimana data disimpan
* bagaimana data mengalir
* bagaimana data digunakan
* bagaimana data mendukung AI dan product intelligence

Data menjadi fondasi utama Culinary Intelligence Platform.

---

# 2. Data Vision

Pawona mengadopsi pendekatan:

> Knowledge-Driven & Behavior-Driven Intelligence.

Tujuan utama data bukan hanya menyimpan informasi.

Tujuan utama data adalah membantu sistem memahami:

* kuliner
* pengguna
* perilaku memasak

secara berkelanjutan.

---

# 3. Data Principles

## Principle 1 — Single Source of Truth

Setiap data memiliki satu sumber utama.

---

## Principle 2 — Structured First

Gunakan data terstruktur sebelum menggunakan data tidak terstruktur.

---

## Principle 3 — Product Learning Driven

Data harus membantu peningkatan produk.

---

## Principle 4 — Privacy First

Kumpulkan hanya data yang memberikan nilai.

---

## Principle 5 — AI Ready

Seluruh data model harus mendukung evolusi AI.

---

# 4. High-Level Data Architecture

```text
Users
 │
 ▼

Application Layer
 │
 ▼

Operational Database
 │
 ├───────────────┐
 ▼               ▼

Knowledge      Memory
Layer          Layer

 │               │
 └──────┬────────┘
        ▼

AI Layer

        ▼

Analytics Layer

        ▼

Product Intelligence
```

---

# 5. Data Domains

Data dibagi menjadi lima domain utama.

---

## User Data

---

## Knowledge Data

---

## Behavioral Data

---

## Memory Data

---

## Analytics Data

---

# 6. User Data Domain

Represents:

Identity and Preferences

---

Examples:

* user profile
* onboarding
* settings
* preferences

---

Tables:

```text
users
user_preferences
```

---

Source of Truth:

PostgreSQL

---

# 7. Knowledge Data Domain

Represents:

Culinary Knowledge

---

Examples:

* recipes
* ingredients
* cooking methods
* regional cuisine

---

Tables:

```text
recipes
ingredients
recipe_ingredients
```

---

Source of Truth:

Knowledge Layer

---

# 8. Behavioral Data Domain

Represents:

User Actions

---

Examples:

* searches
* recipe views
* saves
* cooking sessions

---

Tables:

```text
user_events
cooking_sessions
saved_recipes
```

---

Behavior drives personalization.

---

# 9. Memory Data Domain

Represents:

Learned Preferences

---

Examples:

* spicy preference
* cuisine preference
* cooking complexity preference

---

Tables:

```text
preference_profiles
behavior_signals
```

---

Generated from behavior.

---

# 10. Analytics Data Domain

Represents:

Business Intelligence

---

Examples:

* funnels
* retention
* engagement

---

Stored in:

PostHog

---

Not primary transactional storage.

---

# 11. Data Classification

Category 1

Operational Data

---

Category 2

Knowledge Data

---

Category 3

Behavioral Data

---

Category 4

Analytical Data

---

Category 5

AI Data

---

# 12. Source of Truth Strategy

User Data:

PostgreSQL

---

Recipe Data:

PostgreSQL

---

Knowledge Data:

PostgreSQL

---

Memory Data:

PostgreSQL

---

Analytics Data:

PostHog

---

Every domain has one owner.

---

# 13. Data Lifecycle

Standard Lifecycle:

```text
Create
↓
Use
↓
Analyze
↓
Improve
↓
Archive
```

---

Data should not live forever.

---

# 14. Data Flow — Recipe Recommendation

```text
User Request
↓
User Preferences
↓
Knowledge Retrieval
↓
Memory Retrieval
↓
AI Recommendation
↓
User Interaction
↓
Behavior Signals
↓
Memory Update
```

---

Most important data flow.

---

# 15. Data Flow — Cooking Session

```text
Cooking Start
↓
Step Tracking
↓
Completion
↓
Behavior Capture
↓
Analytics
↓
Memory Update
```

---

Creates high-value signals.

---

# 16. Data Flow — Vision AI

Future.

---

```text
Image Upload
↓
Image Processing
↓
Ingredient Detection
↓
Structured Ingredients
↓
Recipe Pipeline
```

---

Images become structured data.

---

# 17. Knowledge Architecture

Knowledge stored as:

---

Structured Data

Primary.

---

Vector Data

Secondary.

---

Knowledge Graph

Future.

---

Structured data remains dominant.

---

# 18. Vector Data Architecture

Used For:

* semantic retrieval
* ingredient similarity
* recipe similarity

---

Storage:

pgvector

---

Source:

Knowledge Layer

---

# 19. Memory Data Architecture

Memory stores:

---

Explicit Preferences

---

Behavior Signals

---

Derived Preferences

---

No conversation memory.

---

Structured memory only.

---

# 20. Behavioral Signal Architecture

Examples:

```text
recipe_viewed

recipe_saved

cooking_started

cooking_completed
```

---

Signal importance hierarchy:

```text
Completed
↓
Saved
↓
Started
↓
Viewed
```

---

# 21. Event Architecture

Every important user action generates an event.

---

Example:

```json
{
  "event": "recipe_saved",
  "user_id": "...",
  "recipe_id": "...",
  "timestamp": "..."
}
```

---

Events support analytics and personalization.

---

# 22. Data Ownership

User Domain

Owns user data.

---

Recipe Domain

Owns recipe data.

---

AI Domain

Consumes data.

---

Analytics Domain

Measures outcomes.

---

Ownership must be clear.

---

# 23. Data Quality Principles

Required:

* consistency
* accuracy
* completeness
* traceability

---

Bad data creates bad AI outcomes.

---

# 24. Data Retention

Operational Data:

Long-term.

---

Behavioral Signals:

Configurable.

---

Analytics Events:

Retention policy applied.

---

Images:

Only retained when necessary.

---

# 25. Privacy Strategy

Collect only:

Data that improves user experience.

---

Avoid:

Unnecessary personal information.

---

Users retain control over preferences.

---

# 26. AI Data Architecture

AI consumes:

---

Knowledge Data

---

Memory Data

---

Behavior Data

---

AI does not own data.

AI consumes data.

---

# 27. Recommendation Intelligence Flywheel

```text
User Activity
↓
Behavior Signals
↓
Memory Updates
↓
Better Recommendations
↓
Higher Satisfaction
↓
More Activity
```

---

Core intelligence loop.

---

# 28. Data Access Architecture

```text
Flutter
↓
Backend
↓
Database
```

---

Clients never access database directly.

---

Backend controls all access.

---

# 29. Data Security Alignment

Data Architecture follows:

Security Architecture

---

Requirements:

* encryption
* access control
* auditability

---

Security applies across all domains.

---

# 30. Scalability Roadmap

Phase 1

Single PostgreSQL Database

---

Phase 2

Optimized Analytics

---

Phase 3

Dedicated Data Services

---

Phase 4

Knowledge Platform

---

No premature complexity.

---

# 31. Non-Goals

MVP does not include:

* data lake
* warehouse architecture
* streaming platforms
* Kafka
* Snowflake
* Hadoop

---

Complexity not justified.

---

# 32. Success Metrics

Data Architecture is successful when:

* AI quality improves
* personalization improves
* product decisions become data-driven
* data remains trustworthy
* operational complexity stays low

---

# 33. Relationship with Other Documents

Supports:

* ERD
* AI Architecture
* Backend Architecture
* Memory Strategy
* RAG Strategy
* Evaluation Framework

---

Acts as bridge between data storage and intelligence systems.

---

# 34. Summary

Pawona Data Architecture is built around five core domains:

User Data.
Knowledge Data.
Behavioral Data.
Memory Data.
Analytics Data.

The architecture enables a continuous intelligence flywheel where user activity generates signals, signals improve memory, memory improves recommendations, and recommendations improve user outcomes.

Core Principle:

Data is the foundation of Culinary Intelligence.
