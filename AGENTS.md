# AGENTS.md — Place-Based Governance & Agent Guidelines

> **Notice**: All instructions, schemas, and skills in this repository operate strictly on synthetic fixtures and public reference models. Personal identifiers, private credentials, and real venue claims must never be written into public files.

---

## 1. Role-Based Identity Governance

All reviewer, auditor, and editorial actions within schemas, fixtures, and audit logs must use generic role-based identifiers rather than personal names:

* `role_governance_auditor`: Verifies venue ownership claims and legal representation.
* `role_editor_lead`: Manages factual evidence verification and editorial review.
* `role_system_automated`: Automated validation and schema integrity check agent.
* `role_community_curator`: External or community-submitted contribution reviewer.

---

## 2. Place-Based Discovery Guidelines

Agents interacting with or extending IsleConnect Foundation schemas must adhere to three core rules:

### Rule 1: Orthogonal State Enforcement
Never collapse assurance, ownership, or publication state into a single label. Every place entity must explicitly declare all four lifecycle dimensions:
* `coverageSource`
* `assuranceStatus`
* `publicationStatus`
* `profileClaimStatus`

### Rule 2: Explicit Dispute Taxonomy
When a record is disputed, never swallow or overwrite lifecycle states. Qualify the record using `disputeDetails`, explicitly separating `rightsDispute` (ownership / copyright) from `factualDispute` (historical / geographical accuracy).

### Rule 3: Mandatory Synthetic Metadata
All non-production reference records must carry `fixtureMetadata`:
```json
{
  "fixtureMetadata": {
    "synthetic": true,
    "productionSafe": false,
    "intendedUse": "documentation_and_testing"
  }
}
```

---

## 3. Reusable Skill Integration

Skills within `skills/` provide autonomous validation logic for checking JSON schema compliance, synthetic local grid boundaries, and dispute handling workflows.
