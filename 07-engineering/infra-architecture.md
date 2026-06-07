# Infrastructure Architecture

**Document:** Infrastructure Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Platform Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur infrastruktur Pawona.

Infrastructure Architecture bertanggung jawab menyediakan fondasi yang:

* scalable
* reliable
* secure
* cost-efficient

untuk mendukung seluruh platform Pawona.

---

# 2. Infrastructure Vision

Pawona menggunakan pendekatan:

> Lean Cloud Infrastructure

Tujuan utama:

* mempercepat delivery
* meminimalkan operational burden
* menjaga biaya tetap rendah
* mendukung pertumbuhan bertahap

---

# 3. Infrastructure Principles

## Principle 1 — Managed Services First

Gunakan layanan terkelola sebelum membangun sendiri.

---

## Principle 2 — Cost Awareness

Setiap resource harus memiliki justifikasi bisnis.

---

## Principle 3 — Operational Simplicity

Kurangi jumlah komponen yang harus dikelola tim.

---

## Principle 4 — Progressive Scaling

Scale hanya ketika dibutuhkan.

---

## Principle 5 — Security by Default

Seluruh resource harus mengikuti prinsip keamanan standar.

---

# 4. High-Level Infrastructure Architecture

```text
Flutter App
      │
      ▼

Cloudflare
      │
      ▼

NestJS Backend
      │

 ┌────┼──────────┐
 ▼    ▼          ▼

Supabase Redis AI Providers

      │
      ▼

PostHog
Sentry
```

---

# 5. Infrastructure Stack

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

## Vector Search

pgvector

---

## Cache

Redis

---

## CDN

Cloudflare

---

## Monitoring

Sentry

---

## Product Analytics

PostHog

---

## AI Providers

OpenAI
Anthropic
Gemini

---

# 6. Environment Strategy

Three environments:

---

Development

---

Staging

---

Production

---

No shared databases between environments.

---

# 7. Development Environment

Purpose:

Daily development.

---

Characteristics:

* low cost
* disposable
* rapid iteration

---

Can use:

* Supabase Free
* Railway Free (if available)
* Local Docker

---

# 8. Staging Environment

Purpose:

Testing before production.

---

Characteristics:

* mirrors production
* lower scale
* controlled access

---

Used for:

* QA
* release validation
* AI testing

---

# 9. Production Environment

Purpose:

Real users.

---

Requirements:

* monitoring enabled
* backups enabled
* alerting enabled

---

Single production environment.

---

# 10. Backend Hosting Strategy

MVP Recommendation:

Railway

---

Benefits:

* simple deployment
* developer friendly
* minimal DevOps overhead

---

Alternative:

Fly.io

---

Future:

AWS

---

# 11. Why Not AWS Initially

AWS is powerful.

---

But:

* higher complexity
* slower onboarding
* higher operational burden

---

For MVP:

Speed is more important.

---

# 12. Database Strategy

Provider:

Supabase

---

Services Used:

* PostgreSQL
* Auth
* Storage
* pgvector

---

Not Used:

* business logic
* heavy edge functions

---

NestJS remains application layer.

---

# 13. Database Scaling Strategy

Phase 1

Single PostgreSQL Instance

---

Phase 2

Performance Optimization

---

Phase 3

Read Replicas

If needed.

---

# 14. Redis Architecture

Purpose:

Caching and queues.

---

Use Cases:

* recommendation cache
* retrieval cache
* BullMQ jobs

---

No session storage.

---

# 15. File Storage Architecture

Provider:

Supabase Storage

---

Stores:

* recipe images
* user uploads
* ingredient scans
* profile images

---

Storage remains centralized.

---

# 16. CDN Strategy

Provider:

Cloudflare

---

Responsibilities:

* caching
* DDoS protection
* image delivery
* SSL termination

---

Cloudflare sits in front of backend services.

---

# 17. AI Infrastructure

Provider-Agnostic Design.

---

Default:

OpenAI

---

Fallbacks:

Anthropic

Gemini

---

AI infrastructure remains external.

No self-hosted models for MVP.

---

# 18. Background Processing Architecture

Technology:

BullMQ

Redis

---

Use Cases:

* embedding generation
* notifications
* analytics aggregation
* evaluation jobs

---

Not required for synchronous requests.

---

# 19. Analytics Infrastructure

Provider:

PostHog

---

Tracks:

* feature usage
* recommendation acceptance
* cooking completion

---

Supports product decision making.

---

# 20. Monitoring Infrastructure

Provider:

Sentry

---

Tracks:

* backend exceptions
* mobile crashes
* performance issues

---

Critical for production readiness.

---

# 21. Logging Strategy

Application Logs

---

AI Logs

---

Audit Logs

---

Structured logging only.

---

No console logging in production.

---

# 22. Secret Management

Secrets stored in:

* Railway Environment Variables
* Supabase Secrets
* CI/CD Secrets

---

Never stored in source code.

---

# 23. Backup Strategy

Database:

Daily backups

(Enabled once upgraded to paid plan)

---

Storage:

Provider-managed redundancy

---

Critical exports scheduled regularly.

---

# 24. Disaster Recovery Philosophy

MVP Goal:

Recover within hours.

---

Not minutes.

---

Operational simplicity preferred.

---

# 25. Networking Strategy

HTTPS only.

---

All communication encrypted.

---

No direct database access from clients.

---

Clients only communicate with backend APIs.

---

# 26. Cost Optimization Strategy

Priority:

```text
Managed Services
↓
Caching
↓
Efficient Queries
↓
AI Optimization
```

---

Avoid premature infrastructure scaling.

---

# 27. Infrastructure Cost Targets

MVP Phase:

Infrastructure costs should remain minimal.

---

Primary cost center:

AI

---

Not infrastructure.

---

# 28. Scaling Roadmap

Phase 1

Lean Infrastructure

---

Phase 2

Production Hardening

---

Phase 3

Growth Optimization

---

Phase 4

Dedicated Platform Team

Future.

---

# 29. Non-Goals

Infrastructure MVP does not include:

* Kubernetes
* Multi-region deployment
* Multi-cloud strategy
* Service mesh
* Dedicated SRE tooling
* Self-hosted databases

---

Reason:

Complexity exceeds business value.

---

# 30. Future Evolution

Expected Evolution:

```text
Railway
↓
Railway Pro
↓
AWS Migration
↓
Dedicated Platform Infrastructure
```

Migration only happens when justified by growth.

---

# 31. Success Metrics

Infrastructure is successful when:

* uptime remains high
* deployments are simple
* operational burden remains low
* costs remain predictable
* engineering velocity stays high

---

# 32. Summary

Pawona Infrastructure Architecture follows a Lean Cloud Infrastructure strategy built around managed services.

Core stack:

Flutter → Cloudflare → NestJS → Supabase → AI Providers

The architecture prioritizes speed, simplicity, maintainability, and cost efficiency while supporting future evolution into a larger Culinary Intelligence Platform.

Principles:

Managed Services First.
Progressive Scaling.
Operational Simplicity.
Cost Awareness.
