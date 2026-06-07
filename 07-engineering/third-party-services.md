# Third-Party Services

**Document:** Third-Party Services Registry
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan seluruh layanan pihak ketiga yang digunakan oleh Pawona.

Tujuan utama dokumen ini adalah:

* menjaga konsistensi teknologi
* mengurangi vendor sprawl
* mempercepat onboarding engineer
* mendokumentasikan keputusan vendor

Dokumen ini menjadi source of truth untuk seluruh integrasi eksternal.

---

# 2. Vendor Strategy

Pawona mengadopsi pendekatan:

> Buy Before Build.

Prioritas:

```text
Managed Service
↓
Hosted Service
↓
Self Managed
↓
Custom Built
```

---

Fokus utama tim adalah membangun Culinary Intelligence.

Bukan mengelola infrastruktur.

---

# 3. Vendor Selection Principles

## Principle 1

Developer Experience First

---

## Principle 2

Cost Awareness

---

## Principle 3

Reliability

---

## Principle 4

Scalability

---

## Principle 5

Vendor Independence When Possible

---

# 4. Service Categories

Vendor dibagi menjadi kategori berikut:

---

Infrastructure

---

Database

---

Authentication

---

Storage

---

AI

---

Analytics

---

Monitoring

---

Communications

---

Payments

---

Product Operations

---

# 5. Infrastructure Providers

## Primary Platform

Recommended:

Railway

---

Purpose:

Backend hosting

---

Responsibilities:

* NestJS deployment
* environment variables
* service management

---

Status:

MVP Standard

---

# 6. CDN & Edge Layer

Provider:

[Cloudflare](https://www.cloudflare.com?utm_source=chatgpt.com)

---

Responsibilities:

* CDN
* SSL
* DDoS protection
* DNS

---

Status:

Required

---

# 7. Database Provider

Provider:

[Supabase](https://supabase.com?utm_source=chatgpt.com)

---

Services Used:

* PostgreSQL
* Auth
* Storage
* pgvector

---

Services Not Used as Core:

* Edge Functions
* Business Logic

---

Status:

Required

---

# 8. Authentication Provider

Provider:

[Supabase Auth](https://supabase.com/authentication?utm_source=chatgpt.com)

---

Responsibilities:

* user authentication
* OAuth
* session management

---

Supported:

* Google Login
* Apple Login
* Guest Mode

---

# 9. Storage Provider

Provider:

[Supabase Storage](https://supabase.com/storage?utm_source=chatgpt.com)

---

Stores:

* recipe images
* profile images
* ingredient uploads

---

Status:

Required

---

# 10. AI Providers

Architecture:

Multi Provider

---

Default:

[OpenAI](https://openai.com?utm_source=chatgpt.com)

---

Secondary:

[Anthropic](https://www.anthropic.com?utm_source=chatgpt.com)

---

Secondary:

[Google Gemini](https://deepmind.google/technologies/gemini/?utm_source=chatgpt.com)

---

Purpose:

* reasoning
* recommendation
* generation
* vision

---

Managed through AI Gateway.

---

# 11. Embedding Providers

Initial Strategy:

Use provider-native embeddings.

---

Potential Providers:

* OpenAI Embeddings
* Gemini Embeddings

---

Status:

MVP

---

Future:

Evaluate dedicated embedding providers.

---

# 12. Analytics Provider

Provider:

[PostHog](https://posthog.com?utm_source=chatgpt.com)

---

Responsibilities:

* funnels
* retention
* events
* experiments

---

Source of Truth:

Product Analytics

---

# 13. Monitoring Provider

Provider:

[Sentry](https://sentry.io?utm_source=chatgpt.com)

---

Responsibilities:

* crash monitoring
* exception tracking
* performance monitoring

---

Source of Truth:

Application Health

---

# 14. Email Provider

Provider:

[SpaceMail](https://www.spacemail.com/?utm_source=chatgpt.com)

---

Responsibilities:

* transactional emails
* account emails

---

Examples:

* welcome email
* verification email
* password reset

---

Status:

Preferred

---

# 15. Push Notification Provider

Phase 1:

Firebase Cloud Messaging (FCM)

---

Provider:

[Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging?utm_source=chatgpt.com)

---

Responsibilities:

* mobile push notifications

---

Status:

Future

---

# 16. Queue & Background Jobs

Technology:

BullMQ

---

Dependency:

Redis

---

Redis Provider:

Managed Redis Service

---

Purpose:

* embeddings
* analytics jobs
* notifications

---

# 17. Mobile Analytics SDKs

Primary:

PostHog SDK

---

Secondary:

None

---

Avoid duplicate analytics systems.

---

# 18. Payments Provider

Phase 1

No Payments

---

Phase 2

Mobile Subscription

---

Recommended:

[RevenueCat](https://www.revenuecat.com?utm_source=chatgpt.com)

---

Responsibilities:

* subscriptions
* entitlement management

---

Status:

Future

---

# 19. Maps Provider

Future Feature:

Regional Culinary Explorer

---

Recommended:

[Mapbox](https://www.mapbox.com?utm_source=chatgpt.com)

---

Reason:

Flexible pricing and mobile support.

---

Status:

Future

---

# 20. Search Infrastructure

MVP:

PostgreSQL + pgvector

---

Dedicated Search Engine:

Not Required

---

Avoid:

* Elasticsearch
* OpenSearch

during MVP.

---

# 21. CI/CD Platform

Recommended:

[GitHub Actions](https://github.com/features/actions?utm_source=chatgpt.com)

---

Responsibilities:

* testing
* build
* deployment

---

Status:

Required

---

# 22. Source Control

Provider:

[GitHub](https://github.com?utm_source=chatgpt.com)

---

Responsibilities:

* code hosting
* pull requests
* issue tracking

---

Status:

Required

---

# 23. Documentation Platform

Phase 1

Git Repository

---

Phase 2

Recommended:

[GitBook](https://www.gitbook.com?utm_source=chatgpt.com)

---

Purpose:

* internal documentation
* onboarding

---

# 24. Design Collaboration

Provider:

[Figma](https://www.figma.com?utm_source=chatgpt.com)

---

Purpose:

* design system
* UI design
* collaboration

---

Status:

Required

---

# 25. Vendor Risk Management

Every vendor should be evaluated for:

* reliability
* cost
* security
* lock-in risk

---

Critical vendors require fallback strategies.

---

# 26. Vendor Dependency Matrix

Tier 1 Critical:

* Supabase
* OpenAI
* Railway
* Cloudflare

---

Tier 2 Important:

* PostHog
* Sentry

---

Tier 3 Optional:

* RevenueCat
* Mapbox

---

# 27. Vendor Exit Strategy

Where possible:

* maintain abstraction layers
* avoid provider-specific business logic
* preserve portability

---

Most important:

AI Providers remain replaceable.

---

# 28. Cost Ownership

Every vendor must have:

* owner
* purpose
* budget

---

Unused vendors should be removed.

---

# 29. Future Vendor Evaluation

Potential Future Categories:

* vector databases
* recommendation engines
* experimentation platforms

---

Only introduced when justified.

---

# 30. Non-Goals

Pawona does not aim to:

* minimize vendor usage
* self-host everything
* build infrastructure from scratch

during MVP.

---

# 31. Success Metrics

Third-Party Strategy is successful when:

* operational burden remains low
* engineering velocity remains high
* vendor costs remain predictable
* integrations remain maintainable

---

# 32. Summary

Pawona adopts a Buy Before Build strategy focused on managed services and operational simplicity.

Core vendors:

* Supabase
* Railway
* Cloudflare
* OpenAI
* Anthropic
* Gemini
* PostHog
* Sentry
* GitHub

These services enable the team to focus on building Culinary Intelligence rather than managing infrastructure.

Core Principle:

Buy Before Build.
