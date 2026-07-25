# DATA_MODEL.md — Data Model & Lifecycle Specification

> **Scope**: Technical specification of venue entities, discovery routes, orthogonal lifecycle dimensions, and dispute taxonomy schema definitions.

---

## 1. Orthogonal Lifecycle Dimensions

Place-based entities decouple data origin, verification review, visibility, and legal profile claim status:

```text
               ┌───────────────────────┐
               │    coverageSource     │
               └───────────┬───────────┘
                           │
  ┌────────────────────────┼────────────────────────┐
  ▼                        ▼                        ▼
public_source      operator_submitted      curated_editorial
  │                        │                        │
  ▼                        ▼                        ▼
unverified           pending_review             verified
  │                        │                        │
  └────────────────────────┼────────────────────────┘
                           │
               ┌───────────┴───────────┐
               │    assuranceStatus    │
               └───────────┬───────────┘
                           │
             (If evidence conflict occurs)
                           │
                           ▼
                        disputed
```

---

## 2. Dispute Taxonomy Schema (`disputeDetails`)

Disputes qualify records rather than overriding their core lifecycle state. The schema explicitly separates **Rights Disputes** from **Factual Disputes**:

```json
{
  "disputeDetails": {
    "rightsDispute": {
      "isDisputed": true,
      "category": "image_reproduction_rights",
      "resolutionStatus": "open",
      "reviewedBy": "role_editor_lead",
      "reviewedAt": "2026-07-25T12:00:00Z",
      "note": "Licensing rights for historic archive photograph undergoing legal verification."
    },
    "factualDispute": {
      "isDisputed": true,
      "category": "historical_confidence",
      "confidenceScore": 0.5,
      "resolutionStatus": "under_review",
      "evidenceReferences": [
        "https://example.org/synthetic-archives/doc-10492"
      ],
      "note": "Conflicting local archive records regarding structure construction date."
    }
  }
}
```

---

## 3. Coordinate System Specification

Reference fixtures implement the `synthetic_local_grid` coordinate system:

```json
{
  "coordinateSystem": "synthetic_local_grid",
  "xMetres": 1250,
  "yMetres": 840,
  "elevationMetres": 15
}
```

For applications integrating real-world geospatial providers, adapter software converts local grid displacements relative to an arbitrary non-populated reference datum.
