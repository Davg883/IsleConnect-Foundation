# GOVERNANCE.md — Permissioned Discovery & Agent Decision Policy

> **Scope**: Explains why and under what authorization conditions autonomous agents may query, display, or execute actions against place-based entities.

---

## 1. Core Operating Principle

Autonomous agents must never infer venue ownership, endorsement, or authority from raw presence. Every entity interaction is governed by **four orthogonal lifecycle dimensions**:

1. `coverageSource` (`operator_submitted` | `public_source` | `curated_editorial`)
2. `assuranceStatus` (`unverified` | `pending_review` | `verified` | `disputed`)
3. `publicationStatus` (`draft` | `published` | `archived`)
4. `profileClaimStatus` (`unclaimed` | `claim_pending` | `claimed` | `claim_rejected`)

---

## 2. Agent Action Matrix

| Agent Action | Required `assuranceStatus` | Required `profileClaimStatus` | Allowed Behavior |
| :--- | :--- | :--- | :--- |
| **Public Search Display** | `verified` OR `unverified` | Any | Render venue listing with visible assurance badge. |
| **Operator Action Trigger** | `verified` ONLY | `claimed` ONLY | Execute booking, menu update, or direct message on behalf of venue. |
| **Draft / Preview Render** | `pending_review` | `claim_pending` | Render preview mode for venue applicant only. Block public indexing. |
| **Dispute Hold** | `disputed` | Any | Freeze automated profile updates. Require human role intervention (`role_editor_lead`). |

---

## 3. Role-Based Governance Identifiers

Autonomous decisions and human verification logs must reference generic role-based identifiers:

* `role_governance_auditor`: Verifies legal ownership, property lease proof, and business registration.
* `role_editor_lead`: Manages factual evidence verification, historical claims, and editorial disputes.
* `role_system_automated`: Automated schema validation and programmatic coordinate boundary checks.
* `role_community_curator`: External contribution review and public data suggestion evaluation.

---

## 4. Synthetic Local Grid Policy

To eliminate privacy leakage and avoid real-world geospatial collision, all reference records use a **synthetic local grid coordinate system** (`coordinateSystem: synthetic_local_grid`) bounded strictly within positive local grid dimensions (`xMetres`, `yMetres`). Real-world latitude/longitude coordinates falling within inhabited regions are strictly prohibited.
