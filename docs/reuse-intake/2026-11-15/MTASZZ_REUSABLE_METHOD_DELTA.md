# Public-Safe Reusable Method Delta — Requirement/Diagram Action Stream — 2026-11-15

Status: PUBLIC_GENERIC_ONLY / CANDIDATE / NOT_INSTALLED.

## RequirementDiagramActionStreamSkill

Purpose: Provide a read-only generic skill pattern for decomposing a requirement into User Story, Use Case, Scenario, Diagram and verb-first Action relationships.

Action:
1. Read only explicitly authorized/public source material.
2. Preserve source identity and uncertainty.
3. Normalize requirement/user-story/use-case relationships without inventing native IDs.
4. Select applicable diagram families.
5. Emit verb-first action strings.
6. Bind actions to generic component/interface/data/test/evidence placeholders.
7. Flag unresolved applicability or provenance as gaps.
8. Do not install, execute external side effects, or expose private source content.

Inputs: public or explicitly authorized requirement text and optional architecture contracts.
Outputs: candidate requirement/action-stream package.
Acceptance: no secrets/private URLs, no unsupported identity claims, no canonical promotion, no runtime execution claim.
