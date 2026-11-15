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
