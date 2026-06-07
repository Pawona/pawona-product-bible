# Observability

**Document:** Observability Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan strategi observability Pawona.

Observability memungkinkan tim memahami:

* kondisi sistem
* performa produk
* kualitas AI
* perilaku pengguna

secara real-time dan historis.

---

# 2. Observability Vision

Pawona mengadopsi pendekatan:

> Observe Everything That Matters.

Tujuan utama bukan mengumpulkan data sebanyak mungkin.

Tujuan utama adalah mengumpulkan data yang membantu pengambilan keputusan.

---

# 3. Observability Principles

## Principle 1 — Product First

Metrik produk lebih penting daripada metrik infrastruktur.

---

## Principle 2 — AI Is Observable

AI bukan black box.

---

## Principle 3 — Actionable Metrics

Setiap metrik harus memiliki kegunaan.

---

## Principle 4 — Minimal Operational Overhead

Gunakan managed tools bila memungkinkan.

---

## Principle 5 — Privacy Aware

Observability tidak boleh mengorbankan privasi pengguna.

---

# 4. Observability Architecture

```text
Flutter App
      │
      ▼

Telemetry Layer
      │

 ┌────┼──────────┐
 ▼    ▼          ▼

System AI Product

      │
      ▼

Observability Platform

      │

 ┌────┼─────────────┐
 ▼    ▼             ▼

Sentry PostHog Internal Dashboards
```

---

# 5. Observability Domains

Observability dibagi menjadi tiga domain utama.

---

## System Observability

---

## AI Observability

---

## Product Observability

---

Semua domain memiliki prioritas yang sama.

---

# 6. System Observability

Mengukur kesehatan sistem.

---

Questions:

* apakah backend sehat?
* apakah database sehat?
* apakah API cepat?

---

# 7. System Metrics

Examples:

---

API Response Time

---

Error Rate

---

Availability

---

Queue Backlog

---

Database Latency

---

Cache Hit Rate

---

# 8. Application Monitoring

Provider:

Sentry

---

Tracks:

* backend exceptions
* mobile crashes
* performance degradation

---

Sentry menjadi source of truth untuk application health.

---

# 9. Logging Architecture

All services produce:

Structured Logs

---

Format:

JSON

---

Required Fields:

* timestamp
* request id
* module
* severity

---

# 10. Correlation IDs

Every request receives:

Request ID

---

Purpose:

Trace request journey.

---

Flow:

```text
Flutter
↓
Backend
↓
AI Layer
↓
Database
```

---

All linked by same ID.

---

# 11. Product Observability

Mengukur nilai yang diterima pengguna.

---

Questions:

* apakah produk digunakan?
* apakah pengguna berhasil memasak?
* apakah fitur memberikan nilai?

---

# 12. Product Metrics

North Star:

AI-Assisted Meals Completed

---

Supporting Metrics:

* cooking completion rate
* recommendation acceptance rate
* save rate
* retention

---

# 13. Product Analytics Platform

Provider:

PostHog

---

Reasons:

* event analytics
* funnels
* cohorts
* session analysis

---

Primary product analytics tool.

---

# 14. Event Tracking Strategy

Every important action becomes an event.

---

Examples:

```text
recipe_search

recipe_view

recipe_saved

cooking_started

cooking_completed
```

---

Events drive product decisions.

---

# 15. Funnel Tracking

Core Funnel:

```text
Recipe Search
↓
Recipe View
↓
Cooking Start
↓
Cooking Complete
```

---

Drop-off analysis becomes possible.

---

# 16. Cohort Analysis

Track:

* Day 1 retention
* Day 7 retention
* Day 30 retention

---

Critical for PMF validation.

---

# 17. AI Observability

Most important domain for Pawona.

---

Questions:

* apakah AI membantu?
* apakah AI akurat?
* apakah AI mahal?

---

# 18. AI Metrics

Recommendation Acceptance Rate

---

Cooking Completion Rate

---

Personalization Lift

---

Hallucination Rate

---

AI Cost Per User

---

AI Cost Per Meal

---

# 19. AI Pipeline Monitoring

Monitor:

---

Retrieval

---

Memory

---

Prompting

---

Model Routing

---

Response Generation

---

Safety Validation

---

Every stage should be observable.

---

# 20. Retrieval Observability

Metrics:

* retrieval latency
* retrieval accuracy
* retrieval recall

---

Supports RAG optimization.

---

# 21. Memory Observability

Metrics:

* preference updates
* personalization coverage
* personalization lift

---

Supports recommendation quality.

---

# 22. Prompt Observability

Metrics:

* prompt version
* prompt failures
* structured output success rate

---

Supports experimentation.

---

# 23. Model Observability

Metrics:

* provider usage
* latency
* token consumption
* cost

---

Tracked by model and provider.

---

# 24. AI Cost Monitoring

Required Metrics:

---

Cost Per Request

---

Cost Per User

---

Cost Per Meal

---

Daily AI Spend

---

AI Budget Utilization

---

# 25. AI Quality Monitoring

Metrics:

---

Recommendation Acceptance

---

Recipe Save Rate

---

Cooking Completion Rate

---

Personalization Success

---

These matter more than benchmark scores.

---

# 26. Alerting Strategy

Critical Alerts:

---

Backend Down

---

Database Unavailable

---

AI Failure Spike

---

Cost Spike

---

Error Rate Spike

---

Alerts must be actionable.

---

# 27. Dashboard Strategy

Three dashboards required.

---

## Engineering Dashboard

System Health

---

## Product Dashboard

User Outcomes

---

## AI Dashboard

AI Performance

---

# 28. Privacy Controls

Never collect:

* passwords
* tokens
* secrets

---

Sensitive user information must be anonymized when possible.

---

# 29. Data Retention

Retention policies must exist for:

* logs
* analytics
* AI telemetry

---

Avoid indefinite retention.

---

# 30. Experimentation Observability

Supports:

* A/B testing
* prompt testing
* ranking experiments
* model comparison

---

Observability powers experimentation.

---

# 31. Incident Investigation

Observability should answer:

---

What happened?

---

When did it happen?

---

Who was affected?

---

What changed?

---

# 32. Operational Reviews

Weekly Reviews:

* product metrics
* AI metrics
* reliability metrics

---

Monthly Reviews:

* trends
* costs
* quality

---

# 33. Success Metrics

Observability Architecture is successful when:

* issues are detected early
* AI quality is measurable
* product decisions are data-driven
* costs remain visible
* incidents are easy to investigate

---

# 34. Future Evolution

Phase 1

Basic Monitoring

---

Phase 2

AI Dashboards

---

Phase 3

Automated Insights

---

Phase 4

Predictive Monitoring

---

# 35. Relationship with Other Documents

Observability supports:

* Backend Architecture
* AI Architecture
* Evaluation Framework
* AI Cost Strategy
* Product Metrics

---

Observability is the measurement layer of the platform.

---

# 36. Summary

Pawona Observability Architecture is built around three pillars:

System Observability.
AI Observability.
Product Observability.

The architecture ensures that engineering teams can monitor system health, AI effectiveness, and user outcomes through a unified measurement strategy.

Core Principle:

If it cannot be observed, it cannot be improved.
