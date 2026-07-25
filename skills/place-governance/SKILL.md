---
name: place-governance
description: Validates IsleConnect Foundation place-based discovery entities, orthogonal lifecycle states, and synthetic local grid compliance.
---

# Place Governance Skill

This skill provides autonomous validation instructions for place-based discovery schema compliance, synthetic grid coordinate boundaries, and dispute handling workflows.

## Validation Tasks

### 1. Schema Validation
Ensure all venue JSON objects conform to `schemas/venue.schema.json` and contain the required four orthogonal state fields:
- `coverageSource`
- `assuranceStatus`
- `publicationStatus`
- `profileClaimStatus`

### 2. Synthetic Local Grid Coordinate Bounds
Verify that all coordinate entries specify `coordinateSystem: synthetic_local_grid` with non-negative `xMetres` and `yMetres` values.

### 3. Extended Prohibited Word & Geography Scan
Perform a strict case-insensitive string audit blocking prohibited geographical, coastal, personal, and real venue terms across all project files.

### 4. Synthetic Metadata Verification
Verify that every reference fixture carries the required `fixtureMetadata` object:
```json
{
  "fixtureMetadata": {
    "synthetic": true,
    "productionSafe": false,
    "intendedUse": "documentation_and_testing"
  }
}
```
