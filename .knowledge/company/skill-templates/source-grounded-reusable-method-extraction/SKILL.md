---
name: source-grounded-reusable-method-extraction
description: Extract and reconcile reusable methods from authorized sources while preserving identity, evidence, permissions, code maturity, and approval boundaries
allowed-tools: Read, Glob, Grep
---

# Source-Grounded Reusable Method Extraction

Use this template for READ-ONLY extraction and proposal compilation. This skill does not grant write, execution, deployment, credential, network, or repository permissions. An approved implementation workflow must separately authorize any effectful operations.

## Preconditions

- Identify an authorized source set and distinguish read-access from mutation authority.
- Pin each repository/file to a revision or record the explicit absence of a stable revision.
- Identify the existing module, accepted component catalog and code-owner contract.
- Record source coverage: exact bytes, partial excerpt, source metadata, prior summary, inaccessible, or not searched.

## Action method

1. **Discover** each authorized source, exact path, revision, source type, and access boundary.
2. **Extract** every distinct method/routine/process, its input, output, action statements, option semantics, errors, side effects and external dependencies.
3. **Preserve** source occurrences, aliases, original names and historical differences; avoid mutating the source.
4. **Normalize** canonical candidate names, atomic steps, typed contracts, dependencies and linked tests.
5. **Reconcile** against implemented modules and candidate catalogs, including current code revision, source owner, release scope and tests.
6. **Classify** as existing verified, bounded implementation, skeleton, specified-only, unsupported, duplicate or unverified.
7. **Decide** Adopt, Wrap, Extend, Compose, Replace, Build New, Defer or Reject with an evidence-backed rationale.
8. **Compile** read-only CandidateMethodContract objects including source, version, process stages, input/output, authorization, negative tests, status and outstanding evidence.
9. **Dispatch-plan** only when explicitly authorized; assign independent owners, immutable inputs, owned paths, branch collisions, review and rollback.
10. **Verify** original source and generated candidate by exact readback and per-contract tests, and preserve outstanding work without claiming closure.

## Candidate method record

- candidate_id, canonical_name, kind and aliases
- original source ID, source path, hash/revision, access and completeness
- owning repository/module and **evidence maturity**
- action_steps with preconditions, data contracts, errors, retry and optional compensation
- downstream API/GUI/agent/MCP or artifact consumer
- acceptance tests, negative tests and independent review requirement
- reuse decision, existing capability match, gaps, dependency and next re-entry pointer
- explicit no-promotion status until appropriate authority review

## Critical controls

- **A code pointer is not a passing integration test.**
- **A candidate catalog is not a new authoritative component registry.**
- **A source reference is not independent factual proof.**
- **A link to an artifact is not proof it exists or that its viewer is authorized.**
- **A workflow plan is not evidence that the workflow was executed.**
- **A self-check is not independent review.**
- **Never add sensitive or private source content to a public repository merely because it is accessible in another workspace.**
- **Never create a scheduled monitor, daemon, cross-project write, API deployment, or automatic promotion unless separately authorized.**

## Output expectations

Produce a source inventory and gap list, reusable candidate method contracts, duplicate/alias decisions, module ownership recommendations, a dependency-aware and collision-free implementation plan, and an explicit execution-status receipt. When write permissions are unavailable, output proposed changes without saying they were saved.

## Acceptance checklist

- [ ] Every emitted candidate has a source occurrence/revision or explicit unverified-source state.
- [ ] No duplicate source record is lost during semantic normalization.
- [ ] All methods have at least one input, one output, and several actionable steps.
- [ ] Every planned mutation carries authority, tests and an independent approval requirement.
- [ ] Existing owners and candidates are searched before proposing a new implementation.
- [ ] Unavailable source coverage is preserved as a gap.
- [ ] Public and private source boundaries remain intact.
