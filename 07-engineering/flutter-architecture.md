# Flutter Architecture

**Document:** Flutter Architecture
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Mobile Engineering Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan arsitektur aplikasi Flutter Pawona.

Tujuan utama arsitektur mobile adalah:

* pengembangan cepat
* maintainability tinggi
* pengalaman pengguna yang konsisten
* integrasi AI yang mulus

Flutter menjadi platform utama untuk Android dan iOS pada fase MVP dan Growth.

---

# 2. Architecture Vision

Pawona dibangun sebagai:

> AI-Native Mobile Experience

Aplikasi harus terasa:

* cepat
* sederhana
* personal
* conversational

tanpa mengorbankan performa dan maintainability.

---

# 3. Mobile Engineering Principles

## Principle 1 — Feature First

Organisasi kode mengikuti domain bisnis.

Bukan layer teknis.

---

## Principle 2 — Simplicity Over Purity

Pilih solusi yang mudah dipahami dibanding pola arsitektur yang terlalu kompleks.

---

## Principle 3 — Offline Friendly

Aplikasi tetap memberikan pengalaman yang baik meskipun koneksi tidak sempurna.

---

## Principle 4 — Design System Driven

Seluruh UI dibangun di atas Design System Pawona.

---

## Principle 5 — AI-Native UX

AI merupakan bagian inti dari user experience.

---

# 4. Technology Stack

Framework:

Flutter

---

State Management:

Riverpod

---

Routing:

GoRouter

---

Networking:

Dio

---

Local Storage:

Hive

---

Secure Storage:

Flutter Secure Storage

---

Analytics:

PostHog

---

Crash Monitoring:

Sentry

---

# 5. High-Level Mobile Architecture

```text
Presentation Layer
        │
        ▼
Feature Layer
        │
        ▼
Application Layer
        │
        ▼
Data Layer
        │
        ▼
Backend API
```

---

Arsitektur bersifat pragmatic.

Bukan strict Clean Architecture.

---

# 6. Project Structure

Recommended Structure:

```text
lib/

core/

design_system/

features/

shared/

services/

app/
```

---

# 7. Core Folder

Contains:

```text
core/

constants/

config/

utils/

extensions/

errors/
```

---

Shared infrastructure.

---

# 8. Design System Folder

Contains:

```text
design_system/

theme/

tokens/

components/

patterns/
```

---

Single source of UI truth.

---

# 9. Features Folder

Feature-first organization.

---

Examples:

```text
features/

auth/

home/

recipe/

cooking/

kitchen/

profile/

ai/
```

---

Each feature is self-contained.

---

# 10. Feature Structure

Example:

```text
recipe/

screens/

widgets/

providers/

models/

repositories/
```

---

Feature owns its implementation.

---

# 11. State Management Strategy

Selected:

Riverpod

---

Reasons:

* type safe
* scalable
* testable
* simple

---

Avoid:

* Provider
* GetX
* complex Bloc usage

---

# 12. State Categories

## UI State

Examples:

* selected tab
* loading

---

## Feature State

Examples:

* recipe list
* cooking session

---

## App State

Examples:

* authentication
* user profile

---

# 13. Navigation Strategy

Selected:

GoRouter

---

Benefits:

* declarative
* deep linking support
* scalability

---

Example Routes:

```text
/

/recipe

/recipe/:id

/cooking/:id

/profile
```

---

# 14. Networking Layer

Selected:

Dio

---

Responsibilities:

* API calls
* interceptors
* retry handling
* token injection

---

Backend remains single source of business logic.

---

# 15. API Layer

Recommended Structure:

```text
services/

api/

clients/
```

---

Dio Client

↓

API Services

↓

Feature Providers

---

# 16. Authentication Flow

```text
App Launch
↓
Token Check
↓
Supabase Auth
↓
Backend Validation
↓
Session Ready
```

---

Supports:

* Google Login
* Apple Login
* Guest Mode

---

# 17. Local Storage Strategy

Hive

---

Used For:

* cached recipes
* onboarding status
* user preferences
* recent searches

---

Not used as source of truth.

---

# 18. Secure Storage Strategy

Flutter Secure Storage

---

Used For:

* auth tokens
* sensitive credentials

---

Never stored in Hive.

---

# 19. Offline Strategy

MVP supports:

---

Cached Recipes

---

Recent Searches

---

User Preferences

---

Saved Recipes

---

Offline-first architecture is not required.

---

Offline-friendly architecture is sufficient.

---

# 20. AI UX Architecture

AI interactions are feature-driven.

---

Flow:

```text
User Input
↓
Feature Provider
↓
Backend
↓
AI Layer
↓
Response
```

---

No direct AI provider access from mobile.

---

# 21. Image Upload Flow

```text
Camera
↓
Compression
↓
Upload
↓
Backend
↓
Storage
```

---

Required for future Vision AI.

---

# 22. Error Handling Strategy

Standard UI States:

---

Loading

---

Success

---

Empty

---

Error

---

Every screen must support all states.

---

# 23. Analytics Strategy

Tracked Events:

```text
recipe_generated

recipe_saved

cooking_started

cooking_completed
```

---

Integrated via PostHog.

---

# 24. Push Notification Architecture

Future.

---

Supported Categories:

* meal reminders
* recommendation reminders
* engagement campaigns

---

# 25. Performance Principles

Goals:

---

Cold Start < 3 seconds

---

Smooth 60 FPS

---

Minimal Rebuilds

---

Efficient Image Loading

---

# 26. Design System Integration

Every screen must use:

---

Design Tokens

---

Design Components

---

Design Patterns

---

No custom styling outside Design System.

---

# 27. Testing Strategy

Unit Tests

---

Provider Tests

---

Widget Tests

---

Critical Flow Tests

---

Focus on high-value journeys.

---

# 28. Accessibility

Requirements:

* scalable text
* semantic labels
* contrast compliance

---

Accessibility is not optional.

---

# 29. Scalability Strategy

Phase 1

Single App

---

Phase 2

Feature Expansion

---

Phase 3

Advanced AI Features

---

No major architecture rewrite expected.

---

# 30. Non-Goals

Flutter architecture MVP does not include:

* micro-frontends
* plugin architecture
* offline-first sync engine
* advanced state machines

---

Reason:

Complexity outweighs value.

---

# 31. Success Metrics

Mobile Architecture is successful when:

* new features ship quickly
* onboarding is simple
* UI remains consistent
* bugs are easy to diagnose
* AI features integrate easily

---

# 32. Summary

Pawona Mobile Application uses a Feature-First Flutter Architecture built with Riverpod, GoRouter, Dio, Hive, and Flutter Secure Storage.

The architecture prioritizes simplicity, maintainability, and rapid product iteration while supporting AI-native experiences and future platform growth.

Core principles:

Feature First.
Design System Driven.
AI-Native UX.
Simplicity Over Complexity.
