# Security Architecture

**Document:** Security Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur keamanan Pawona.

Tujuan utama Security Architecture adalah melindungi:

* pengguna
* data
* sistem AI
* infrastruktur
* intellectual property

tanpa mengorbankan kecepatan pengembangan dan operasional.

---

# 2. Security Vision

Pawona mengadopsi pendekatan:

> Security by Default.

Keamanan bukan fitur tambahan.

Keamanan menjadi bagian dari seluruh sistem sejak awal.

---

# 3. Security Principles

## Principle 1 — Least Privilege

Setiap sistem hanya memiliki akses minimum yang dibutuhkan.

---

## Principle 2 — Defense in Depth

Tidak ada satu lapisan keamanan yang dianggap cukup.

---

## Principle 3 — Secure by Design

Keamanan dipertimbangkan sejak tahap desain.

---

## Principle 4 — Privacy First

Data pengguna diperlakukan sebagai aset yang harus dilindungi.

---

## Principle 5 — Simplicity Over Complexity

Solusi keamanan yang sederhana dan konsisten lebih baik daripada sistem kompleks yang sulit dipelihara.

---

# 4. Security Scope

Architecture ini melindungi:

---

Application Layer

---

AI Layer

---

Database Layer

---

Infrastructure Layer

---

Storage Layer

---

User Data Layer

---

# 5. Security Domains

Security dibagi menjadi enam domain utama.

---

Identity Security

---

Application Security

---

Data Security

---

AI Security

---

Infrastructure Security

---

Operational Security

---

# 6. Threat Model

Primary Threats:

---

Unauthorized Access

---

Credential Theft

---

Data Leakage

---

Prompt Injection

---

API Abuse

---

Storage Exposure

---

Misconfigured Infrastructure

---

# 7. Authentication Architecture

Provider:

Supabase Auth

---

Supported Methods:

* Google Sign In
* Apple Sign In
* Email Login (optional)
* Guest Mode

---

Authentication tidak diimplementasikan sendiri.

---

# 8. Authorization Architecture

Authorization dilakukan di Backend Layer.

---

Rules:

Users may access only their own resources.

---

Examples:

* profile
* preferences
* cooking history
* uploads

---

Authorization never relies on frontend validation.

---

# 9. Session Security

Access Tokens:

Short-lived

---

Refresh Tokens:

Managed securely

---

Tokens never stored in plain text.

---

# 10. API Security

All APIs require:

---

HTTPS

---

Authentication

---

Input Validation

---

Rate Limiting

---

Audit Logging

---

No public write endpoints.

---

# 11. Input Validation

Validation occurs:

Before business logic.

---

Tools:

class-validator

class-transformer

---

Never trust client input.

---

# 12. Rate Limiting

Required for:

---

Authentication

---

AI Endpoints

---

Search Endpoints

---

Recommendation Endpoints

---

Purpose:

Prevent abuse and cost explosions.

---

# 13. Data Classification

Pawona classifies data into categories.

---

## Public Data

Examples:

* recipes
* ingredient information

---

## Internal Data

Examples:

* analytics

---

## Sensitive Data

Examples:

* preferences
* behavior signals
* cooking history

---

## Restricted Data

Examples:

* authentication data
* provider secrets

---

# 14. Data Encryption

Encryption In Transit:

TLS

---

Encryption At Rest:

Provider-managed encryption

---

Required for:

* database
* storage
* backups

---

# 15. User Data Protection

Protected Data:

* profile information
* preferences
* cooking history
* saved recipes
* behavioral signals

---

Users only access their own data.

---

# 16. Privacy Architecture

Principles:

---

Data Minimization

---

Purpose Limitation

---

Transparency

---

User Control

---

Only collect data required to improve product experience.

---

# 17. Storage Security

Provider:

Supabase Storage

---

Rules:

Private buckets by default.

---

Public URLs only for approved assets.

---

User uploads are never exposed directly.

---

# 18. Image Upload Security

Flow:

```text
User Upload
↓
Validation
↓
Storage
↓
Access Control
```

---

Validation Required:

* file type
* file size
* upload ownership

---

# 19. Secrets Management

Secrets stored only in:

* Railway Environment Variables
* Supabase Secrets
* CI/CD Secrets

---

Never:

* source code
* Git repository
* mobile application

---

# 20. Database Security

Principles:

---

Least Privilege Access

---

Parameterized Queries

---

ORM Protection

---

Auditability

---

Prisma becomes standard access layer.

---

# 21. AI Security

AI introduces unique security risks.

---

Protected Areas:

* prompts
* memory
* provider keys
* retrieved context

---

AI security is mandatory.

---

# 22. Prompt Injection Protection

System must ignore attempts to:

* override instructions
* access internal prompts
* expose user data

---

Examples:

```text
Ignore previous instructions.
```

---

Must be rejected.

---

# 23. Memory Security

Memory only stores:

Culinary Preference Data.

---

Never stores:

* passwords
* payment information
* unrelated personal information

---

Memory access is restricted.

---

# 24. RAG Security

Knowledge Sources:

Verified only.

---

No direct retrieval from arbitrary user content.

---

Retrieved context must pass validation.

---

# 25. Provider Security

AI Providers:

* OpenAI
* Anthropic
* Gemini

---

Provider credentials isolated.

---

Provider failures must not expose data.

---

# 26. Logging Security

Never log:

* tokens
* passwords
* secrets

---

Sensitive data must be masked.

---

# 27. Monitoring & Alerting

Security-relevant events monitored:

* failed logins
* unusual API usage
* excessive AI requests
* storage abuse

---

Alerts routed to engineering team.

---

# 28. Dependency Security

Practices:

* dependency updates
* vulnerability scanning
* package reviews

---

Avoid abandoned packages.

---

# 29. Infrastructure Security

Infrastructure protected through:

---

Cloudflare

---

HTTPS

---

Network Isolation

---

Managed Services

---

No direct database exposure.

---

# 30. Backup Security

Backups inherit:

* encryption
* access controls
* retention policies

---

Backups treated as sensitive assets.

---

# 31. Incident Response

Standard Process:

```text
Detection
↓
Investigation
↓
Containment
↓
Remediation
↓
Postmortem
```

---

Every security incident documented.

---

# 32. Security Logging

Required Events:

* login
* logout
* profile updates
* permission failures
* AI abuse attempts

---

Provides auditability.

---

# 33. Compliance Philosophy

MVP Focus:

Reasonable Security

---

Not:

SOC 2

ISO 27001

HIPAA

---

Enterprise compliance deferred until justified.

---

# 34. Security Review Process

Required Reviews:

---

Major Infrastructure Changes

---

Authentication Changes

---

AI Architecture Changes

---

Storage Changes

---

Security becomes part of engineering workflow.

---

# 35. Future Security Evolution

Phase 1

Basic Security Controls

---

Phase 2

Advanced Monitoring

---

Phase 3

Security Automation

---

Phase 4

Compliance Readiness

---

# 36. Architecture Success Metrics

Security Architecture is successful when:

* user data remains protected
* no major security incidents occur
* AI abuse is minimized
* engineering velocity remains high
* operational burden remains manageable

---

# 37. Summary

Pawona Security Architecture follows a Security by Default approach built around managed services, least privilege access, privacy-first design, and AI-specific protections.

The architecture protects:

Users.
Data.
AI Systems.
Infrastructure.

while remaining practical and maintainable for a small engineering team.

Core Principles:

Least Privilege.
Defense in Depth.
Privacy First.
Secure by Design.
Simplicity Over Complexity.
