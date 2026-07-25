# ARCHITECTURE.md — Reference Architecture & System Boundaries

> **Scope**: Structural breakdown of permissioned discovery systems, boundary decoupling between reference specifications and production platforms, and coordinate adapter design.

---

## 1. System Architecture Layers

```text
┌─────────────────────────────────────────────────────────────┐
│                 Client Applications / UI                    │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│            Permissioned Discovery Engine                    │
│   - Validates Orthogonal Lifecycle Dimensions               │
│   - Filters Disputed & Pending Profile Claims               │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│           Geospatial & Synthetic Grid Adapter               │
│   - Translates local grid coordinates to map datums         │
│   - Enforces prohibited bounding box coordinate filters     │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│           Schema Store & Synthetic Fixture Engine           │
│   - Apache 2.0 Licensed JSON Schemas                        │
│   - Strict fixtureMetadata Validation                       │
└─────────────────────────────────────────────────────────────┘
```

---

## 2. Decoupling & Security Boundaries

1. **Public Reference Methods (`IsleConnect-Foundation`)**:
   * Contains open JSON schemas, taxonomy definitions, governance policies, and synthetic local grid test fixtures.
   * Contains zero commercial code, zero production API keys, and zero private organizational data.

2. **Private Commercial Implementation (`IsleConnect-Platform`)**:
   * Consumes schemas and governance policies from Foundation.
   * Maintains live partner relationships, commercial monetization logic, and deployment configurations.
