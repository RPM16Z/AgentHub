# CLAW agent-work-package and noncollision workflow contract
Status: CANDIDATE / DOCS ONLY. Source scope is accessible MTASZZ project-turn excerpts (2026-11-15); full project chat extraction is not claimed.

## Ownership
AgentHub owns reusable agent roles, work package lifecycle, delegation permissions and maker-checker-reviewer-referee workflow. Shared compiler identifiers and GAR/EGAR traceability are owned by RPM16Z/RPMrepo. Claude Code policy startup gates are owned by RPM16Z/claude-config.

## Reusable action requirements
- AHW-001 **Receive** one canonical, versioned work package from an owning requirements/compiler stream.
- AHW-002 **Verify** repository ownership, target branch, active PRs, base commit, file path set and access constraints before assigning work.
- AHW-003 **Partition** work into nonoverlapping files/interfaces with explicit shared dependency contracts.
- AHW-004 **Assign** maker, checker, reviewer and optional referee roles according to risk, rather than creating multiple agents automatically.
- AHW-005 **Constrain** tool permissions and credentials per role; use read-only reviewers by default.
- AHW-006 **Record** preconditions, inputs, expected outputs, tests, exception paths, evidence and resource limits.
- AHW-007 **Execute** only authorized mutations on feature branches; protect shared branches.
- AHW-008 **Run** deterministic test and security gates where meaningful, with a clear distinction between attempted and passed tests.
- AHW-009 **Compare** proposed diffs with active PR path reservations and require handoff or integration review for overlaps.
- AHW-010 **Escalate** conflicting interpretations and failed controls instead of silently reconciling them.
- AHW-011 **Require** reviewer evidence, action-to-test traceability and acceptance before closure.
- AHW-012 **Record** unresolved dependencies, deferred tool/plugin needs, rollback directions and next safe action.
- AHW-013 **Stop** recursive reassignment when a blocker requires human approval or no new verified progress is possible.
- AHW-014 **Publish** a compact work package handoff without claiming a merged or deployed result.

## Lifecycle
Classify -> Link -> Authorize -> Work -> Verify -> Record -> Repeat (CLAW). Distinguish planning, active implementation, review, deferred and blocked states. Re-entry must revalidate branch head and reserved paths.

## Data contract
`work_package_id, source_ids, canonical_requirement_ids, owning_repo, branch, base_ref, reserved_paths, actor_roles, agent_permissions, dependencies, inputs, outputs, acceptance_tests, evidence_refs, failure_policy, rollback, state`.

## Conflict scenarios
- Two chats attempt the same path: **Block** one mutation and **route** its requirements to the owning PR.
- Shared interface change: **Create** a separate integration work package and **require** dependent-owner review.
- Missing PR state: **Inspect** live GitHub state before assignment.
- Unauthorized plugin/MCP exposure: **Defer** capability and **escalate** decision.
- Reviewer disputes maker result: **Escalate** to referee and **record** resolution.
- Unavailable sources: **Mark** incomplete and **preserve** source census gap.

## Proposed tests (not executed)
- Reject overlapping file reservations with concurrent active PRs.
- Preserve role permission separation across retries and context compaction.
- Reject work-package closure without passing tests and evidence.
- Reconcile a moved base branch without overwriting another chat's changes.
- Terminate agent loop on human authorization blocker or iteration ceiling.

This document records reusable requirements only; integration into AgentHub runtime is a distinct, test-gated work package.


## Second-pass agent orchestration hardening (2026-11-15)

| ID | Reusable method | Explicit action requirement | Evidence |
|---|---|---|---|
| AHW-015 | Per-chat PR isolation | **Assign** distinct PRs and bounded file path reservations to independent chat/project workstreams | reservation manifest |
| AHW-016 | Live branch revalidation | **Refresh** target branch, base SHA and PR state immediately before write operations; **abort** stale work | ref snapshot |
| AHW-017 | Conflict owner arbitration | **Route** overlap to the owning workstream rather than duplicating code or overwriting other PRs | conflict resolution |
| AHW-018 | Capability-to-agent mapping | **Select** a specialized agent only when isolation, parallelism or expertise materially improves the task | selection rationale |
| AHW-019 | Work-package replay | **Resume** partially executed work from durable state; **avoid** replaying successful non-idempotent operations | checkpoint record |
| AHW-020 | Proof-directed completion | **Mark** a task complete only after required tests and reviewer evidence correspond to the exact revision | result-to-SHA link |
| AHW-021 | Mutation isolation | **Keep** reviewers and source researchers read-only by default, and reserve write permissions for the owning maker | role policy |
| AHW-022 | Structured handoff | **Transfer** identifiers, branch refs, input/output contracts, changed paths, blockers, tests and evidence to downstream agents | handoff record |
| AHW-023 | Inter-repository integration | **Coordinate** cross-repo schema revisions through versioned interfaces and an explicit integration owner | dependency decision |
| AHW-024 | Convergence controls | **Bound** agent delegation depth, iteration count, resource use and retries; **escalate** when no verified progress occurs | stop reason |
| AHW-025 | Adversarial review | **Test** conflicting assumptions, malformed tool responses, branch drift, denied permissions and incomplete source context | failure test report |

### Proposed routing map

- `RPM16Z/claude-config`: project bootstrap, real command detection, permission configuration, plugin/MCP/skill/hook policy.
- `RPM16Z/RPMrepo`: canonical source-to-action compiler, GAR/EGAR, diagram/action/test/evidence graph.
- `RPM16Z/AgentHub`: work package scheduling, agent delegation, maker/checker/reviewer/referee, concurrency control.

### Parallel PR reservation algorithm

```text
Read source work-package identity.
Resolve owning repository and live PRs.
Resolve base commit, changed paths and declared reservations.
If path overlap or incompatible interface changes:
    block competing write; notify integration owner.
Else:
    reserve paths for one work package and delegate.
Before each mutation:
    recheck branch/ref and permissions.
After completion:
    record test evidence at exact commit and release reservations.
```

### Proposed negative tests

- Two chat workstreams request a write to the same file: only the authorized owning branch proceeds.
- Reviewer agent attempts source mutation: deny and log.
- Branch head advances during an agent's work: block stale update and require fresh comparison.
- Retried work package would recreate a GitHub issue or PR: detect existing idempotency key and skip duplicate creation.
- Agent proposes installing a new MCP: route decision to claude-config permission owner.
- Agent reports successful merge without GitHub evidence: reject closure.
- A cross-repository contract changes without downstream compatibility review: hold integration.

No actual agent scheduling, permission policy changes or runtime tests are introduced by this document.
