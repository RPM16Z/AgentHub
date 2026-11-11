# OWC reusable agent orchestration contracts

Status: PROPOSED, not implemented or verified. Source: November 2026 Operational Workbench Compiler specification. This document is an additive integration proposal and does not alter AgentHub runtime behavior.

## Capability registry
- OWC-09: Versioned action-family orchestration; preserve five-stage ActionSpine and seven-member candidate family separately until authorized adjudication.
- OWC-12: Parallel workstream isolation with immutable task IDs, owner, input manifest, allowed tool scope, branch namespace, protected file paths, dependencies, retry budgets, and resume pointer.
- OWC-15: Independent verification gates with evidence receipts, test artifacts, and maker/checker/referee separation.
- OWC-16: Promotion state machine with discovered, extracted, normalized, reconciled, specified, implemented, tested, independently verified, approved, promoted, blocked, rejected, superseded and deprecated states.
- OWC-18: Weekly written updates, single-column print exports, audit log and recovery receipts.

## Agent contracts
Supervisor allocates bounded work; discovery agents collect immutable source IDs; extraction agents parse evidence; reconciliation agents compare against canonical registry; requirements agents produce atomic contracts; verifier tests implementation; independent referee authorizes eligible promotions; reporting agent records unresolved gaps.

## Collision and security controls
Reject overlapping protected paths or conflicting schemas before parallel execution. Use least-privilege tools and approval gates for writes. Do not mark analysis, simulations or documentation as deployed functionality. Ensure all commands and selector options have durable behavior/state/API/security/accessibility/test contracts.

## Acceptance criteria
Prove isolated concurrent tasks, deterministic conflict detection, idempotent replay, denied-authority handling, independent reviewer separation, versioned state transitions, and traceable evidence for each promotion.

## Cross-project boundary
GitDecompRepo owns source census, decomposition, provenance and GitHub copy reconciliation. AgentHub owns orchestration and workflow contracts only. Workbench frontend and persistence require separately reconciled authority.
