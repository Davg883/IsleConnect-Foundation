# IsleConnect Foundation

> **IsleConnect Foundation is an open reference implementation for permissioned, place-based discovery systems. All sample organisations, places, claims and coordinates are fictional.**

---

## Strategic Purpose

IsleConnect Foundation provides the public reference architecture, JSON schemas, governance taxonomies, and validation skills behind the IsleConnect method.

It defines an open framework for building permissioned, place-based discovery platforms while maintaining clear operational boundaries between public reference methods and commercial implementation code.

---

## Synthetic Data Policy & Disclaimers

> [!IMPORTANT]
> **ALL FIXTURE DATA IS SYNTHETIC**
> Every venue name, organisation, local grid coordinate, historical claim, and media reference within this repository is entirely fictional and provided strictly for demonstration, validation, and testing purposes. All spatial coordinates use a **synthetic local grid system** to eliminate real-world geographical collisions.

---

## Architectural Lifecycle Model

IsleConnect Foundation models place-based discovery records using four orthogonal state dimensions alongside structural dispute handling:

1. **`coverageSource`**: Origin of the record (`operator_submitted` | `public_source` | `curated_editorial`)
2. **`assuranceStatus`**: Review lifecycle (`unverified` | `pending_review` | `verified` | `disputed`)
3. **`publicationStatus`**: Visibility lifecycle (`draft` | `published` | `archived`)
4. **`profileClaimStatus`**: Ownership lifecycle (`unclaimed` | `claim_pending` | `claimed` | `claim_rejected`)

---

## Reference Fixtures Included

This repository provides 5 synthetic reference fixtures demonstrating core governance scenarios:

1. `fixtures/verified-venue.json`: *Northmere Maritime Centre* (`assuranceStatus: verified`).
2. `fixtures/unclaimed-listing.json`: *Lantern Quay Café* (`profileClaimStatus: unclaimed`).
3. `fixtures/pending-claim.json`: *Greyhaven Signal Archive* (`profileClaimStatus: claim_pending`).
4. `fixtures/contested-claim.json`: *Old Harbor Lightstation* (`assuranceStatus: disputed`).
5. `fixtures/synthetic-route.json`: *Harbourglass Visitor Trail* (Multi-stop local grid discovery trail).

---

## Documentation Suite

* [`GOVERNANCE.md`](./GOVERNANCE.md): Permissioned discovery rules & agent action policy.
* [`DATA_MODEL.md`](./DATA_MODEL.md): Technical specification of venue schemas & dispute taxonomies.
* [`ARCHITECTURE.md`](./ARCHITECTURE.md): Reference architecture & platform decoupling boundaries.
* [`ANALYTICS.md`](./ANALYTICS.md): Privacy-first event telemetry schemas.
* [`ACCEPTANCE_CRITERIA.md`](./ACCEPTANCE_CRITERIA.md): Testable compliance verification criteria.

---

## License

Licensed under the **Apache License, Version 2.0**. See [`LICENSE`](./LICENSE) for full details.
