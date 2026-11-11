# Reusable Method and Process Owner Intake — 2026-11-11

Status: candidate owner-local extraction. This is not approved registry state, installed code, activated tool, production deployment or completed independent verification.
**Repository:** RPM16Z/AgentHub · **Candidates:** 3

**Public repository boundary:** The content here contains generic methods only. No personal or private organization source material, internal repository URLs, connector credentials, or private artifacts are imported.

## Process contracts

### REUSE-20261111-067 — SourceGroundedReviewSkill

**Nature:** skill; **Observed maturity:** FILE_INSPECTED.

**Owned source anchor:** `.knowledge/company/skill-templates/review/SKILL.md`.

**Actioned method:** read exact source → compare specification and code → check tests → issue evidence-qualified review → abstain on gaps.

**Inputs:** file revision and task.

**Outputs:** reusable review skill output.

**Required acceptance:** Public repository skill must contain no private project details.

**Promotion:** Candidate only. Reconcile existing logic, add executable tests and independent review before changing operational state.


### REUSE-20261111-068 — ReusableAgentScaffoldAndTemplates

**Nature:** process; **Observed maturity:** FILE_INSPECTED.

**Owned source anchor:** `.knowledge/company/skill-templates/`.

**Actioned method:** declare role → permitted tools → boundaries → skills → tests → package → review → export.

**Inputs:** agent persona/task specification.

**Outputs:** portable agent template.

**Required acceptance:** No installed running agent claim.

**Promotion:** Candidate only. Reconcile existing logic, add executable tests and independent review before changing operational state.


### REUSE-20261111-069 — SessionCommandSelectionAndGate

**Nature:** method; **Observed maturity:** CODE_PATH_DISCOVERED.

**Owned source anchor:** `src/components/session/SessionAgentSelector.vue`.

**Actioned method:** render eligible agents → filter by capability → validate selection → prepare dispatch → request authorization → log result.

**Inputs:** session task and available agents.

**Outputs:** bounded selection candidate.

**Required acceptance:** Do not equate UI click with execution.

**Promotion:** Candidate only. Reconcile existing logic, add executable tests and independent review before changing operational state.

## Reuse process and boundaries

- Locate and inspect an existing method before naming an implementation successor. Treat names and source pointers as discovery leads, not proof of operational completeness.
- Resolve duplicates, aliases, versions and authority before changing any accepted registry or workflow.
- Keep project or workspace access boundaries: no transitive rights from catalog listing to content read/write.
- Pin source revision and test actual behavior including denial, error, concurrency and recovery conditions.
- Bind each method to a typed input/output contract, idempotency behavior where relevant, evidence receipt and event lineage.
- Stage changes in isolated worktree branches; do not write to protected registries without their policy-gated validation and independent approval.
- Preserve unmet requirements as open action/gap records, not completed implementation.

## Status

The candidate JSONL sidecar and this explanation are intentionally docs-only. Existing owner code was not modified by this intake. The follow-up is owner-scoped source inspection and explicit acceptance testing.
