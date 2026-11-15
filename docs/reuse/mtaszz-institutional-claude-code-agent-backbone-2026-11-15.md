# Institutional Claude Code Agentic Backbone Reuse Contract
Status: PROPOSED; documentation only, not a live agent installation.
Date: 2026-11-15
Sources: visible MTASZZ turns; locally inspected institutional scaffold ZIP.

## Principal agents
Principal architect, requirements analyst, backend engineer, database architect, workflow orchestrator, analytics engineer, transaction-integrity reviewer, security-governance reviewer, observability/operations engineer, QA verifier, deployment engineer, documentation-continuity keeper.
Roles are contracts; do not claim each is installed as a Claude Code subagent.

## Reusable agent methods
- **Initialize** instructions: inspect existing repository and `CLAUDE.md` before mutation; request target repo name before any new-repo creation.
- **Scope** work: assign epic, requirement, story, use case, artifacts, acceptance and precise owned paths.
- **Dispatch** bounded subagent tasks only when tools and permission scopes authorize them.
- **Isolate** each independent chat/task in a unique branch, exact-file ownership set and draft PR.
- **Preflight** file collisions against all open PRs, not merely branch names.
- **Serialize** overlapping shared-file changes through the designated integrator/maintainer.
- **Handoff** with immutable inputs, changed paths, test evidence, failed/not-run status, decision references and NSAR.
- **Verify** in an independent checker role; never let the same producer self-certify its output.
- **Resume** from repository durable records; avoid dependence on chat-only memory.
- **Close** only after review, acceptance and provenance gates.

## Work-package contract
```yaml
work_package_id: WP-EP05-UC0501
source_status: derived_proposal
owner_repo: null
base_ref: null
branch: null
owned_paths: []
read_only_dependencies: []
agent_role: transaction-integrity-reviewer
requirement_ids: [REQ-05]
user_story_ids: [US-05.01]
use_case_ids: [UC-05.01]
diagram_instance_ids: []
acceptance_tests: []
approval_required_for: [production_changes, remote_repo_creation, security_policy]
evidence_refs: []
conflicts_with_open_prs: unknown
```

## Agent vs application runtime
Claude Code is the engineering development backbone. A deployed runtime requiring LLM-backed agents must use an explicitly governed runtime service and must not place the LLM in the critical consistency path for authentication, authoritative transaction commits or recovery.

## PR collision policy
- A unique PR per chat/workstream is default.
- `owned_paths` sets must be pairwise disjoint unless integrator approval is recorded.
- PRs remain draft until tests and independent review complete.
- All new cross-repository contracts are proposals until downstream owner confirms them.
- Do not edit `CLAUDE.md`, common registries or global agent definitions in competing PRs without file ownership reservation.

## NSAR
Validate actual Claude Code subagent/schema/hook compatibility against installed version; create isolated example work package; add collision checker and negative tests; register verified hooks only after local execution.
