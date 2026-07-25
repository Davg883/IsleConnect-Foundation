# ACCEPTANCE_CRITERIA.md — Verifiable Compliance Criteria

> **Scope**: Testable criteria for verifying that an implementation complies with the IsleConnect Foundation reference specification.

---

## 1. Compliance Test Matrix

| Category | Test Case | Expected Behavior |
| :--- | :--- | :--- |
| **Data Integrity** | `TEST-DATA-01` | All fixtures validate against `schemas/venue.schema.json` without schema errors. |
| **Orthogonal State** | `TEST-STATE-01` | Record must contain all 4 state fields (`coverageSource`, `assuranceStatus`, `publicationStatus`, `profileClaimStatus`). |
| **Dispute Handling** | `TEST-DISPUTE-01` | Records with `assuranceStatus == "disputed"` must include valid `rightsDispute` and `factualDispute` sub-objects. |
| **Synthetic Policy** | `TEST-SYNTHETIC-01` | Automated string audit checks pass cleanly against prohibited place/coastal names and coordinate range boundaries. |
| **Coordinate Bounds** | `TEST-COORD-01` | Coordinates must not fall within real-world populated bounding boxes (e.g. prohibited lat 50.55-50.85, long -1.65 to -0.90). |
