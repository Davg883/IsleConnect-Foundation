# ANALYTICS.md — Privacy-First Measurement & Event Schemas

> **Scope**: Schema definitions for place-based discovery interaction events without tracking user personal data.

---

## 1. Event Telemetry Schema

All telemetry events operate on anonymized session tokens and synthetic entity identifiers:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Discovery Event Schema",
  "type": "object",
  "required": ["eventId", "eventType", "venueId", "timestamp", "assuranceStatusAtTime"],
  "properties": {
    "eventId": { "type": "string" },
    "eventType": {
      "type": "string",
      "enum": ["venue_impression", "route_milestone_reached", "action_clicked", "claim_prompt_viewed"]
    },
    "venueId": { "type": "string" },
    "timestamp": { "type": "string" },
    "assuranceStatusAtTime": { "type": "string" }
  }
}
```
