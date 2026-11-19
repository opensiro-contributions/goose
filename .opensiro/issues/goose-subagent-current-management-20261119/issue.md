# Goose — compose an S3 owner for concurrent subagent commitments

**PLAN_ONLY / Human-facing fork-local Issue draft / DRAFT — NOT PUBLISHED**

**Canonical decision:** [roadmap.md](roadmap.md) · **AI developer contract:** [constructor-sufficiency.md](constructor-sufficiency.md).

**Target transition:** S3=A -> S3=C

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

## User task and why investigate

A Goose parent delegates simultaneous long-running tasks; their priority changes while the parent is waiting. The operator needs to change the course of one child without canceling or delaying another child. [Original #12852](https://github.com/aaif-goose/goose/issues/12852) documents a request for steering a child during a run. Its discussion clarifies that one earlier lost-result concern has improved, but change of focus while running is still requested. **Autonomous multi-child management by a developer-composed actor is a separate HYPOTHETICAL extension**, not a proven maintainer demand.

OpenSiro applies a VSM-derived ownership vocabulary as a research method, not a certification or mandatory requirement for Goose. Accepted [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/394ce776e6945115891b8f7cc459f5a7f7d7aa39/assessments/go/goose.md) has review_ref 50666ae0b9a51e260b52b7efbab2e4e020346e94, reviewed 2026-09-15, Profile 0.2.1, Methodology 0.3.1. The vector below is **historical**; none of its cells is a new current-HEAD grade. Source audit considered the complete original tree (2,612 tracked paths) including first-party crates, CLI/ACP/UI, extensions, modes, tests, docs and CI; CI and maintainers are not automatically runtime governance.

| Function and role | Historical Index state | Current source and decision/feedback evidence | Candidate and priority |
| --- | --- | --- | --- |
| **S1 · Operations** | A | [Goose agent state machine](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/state_machine_builder.rs) selects work; tools act and return results | Existing operational function; no new target |
| **S2 · Coordination** | — | [SubagentOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/subagent.rs) plus configured concurrent execution cap regulates child admission | Defer: real native interference control already shipped |
| **S3 · Current management** | A | Former orchestrator removed by [merged #12729](https://github.com/aaif-goose/goose/pull/12729); [service](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/services.rs) provides session/steer primitives but no verified autonomous developer-composed cross-child decision owner | **P0**: proposed scoped S3=C constructor |
| **S3* · Complementary audit** | — | [Adversary inspector](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/security/adversary_inspector.rs) and hooks are not proof of an independently composed audit closure | Defer: distinct previous S3* case |
| **S4 · Future adaptation** | — | [Model/provider inventory](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/providers/inventory/mod.rs) refreshes configuration, not proven full prospective adaptation ownership | Defer until a separate future disturbance is substantiated |
| **S5 · Ultimate policy** | — | [Permissions](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/config/permission.rs) and inherited approvals preserve user/parent authority | No authority transfer or S5 constructor proposed |

**Priority choice:** S3 ranks first after the full six-function screen because the historical native orchestrator has been removed, concurrent children and a session-steer queue already exist, and one missing bounded decision-to-feedback link is a falsifiable design. An A-to-C proposal does not mean A is inferior or that a C is mandatory. We do not claim any missing S4/S5 feature is deliberately omitted without first-party evidence. Original maintainer/source interests: issue #12852 and Goose's contributor guide; OpenSiro contributor commercial interests: NOT_STATED.

## Track A — actual native paths

The [state-machine builder](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/state_machine_builder.rs) already configures a default 5 concurrent subagent limit and [SteerOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/steer.rs). [SessionRuntime](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/session_runtime.rs) has per-session steer queues; [SubagentOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/subagent.rs) returns child notifications and final results. [Merged #12802](https://github.com/aaif-goose/goose/pull/12802) binds a child's mode/hooks/approvals to its parent; [merged #12946](https://github.com/aaif-goose/goose/pull/12946) imposes the cap; [merged #12998](https://github.com/aaif-goose/goose/pull/12998) makes child UI view-only. Original [#12852](https://github.com/aaif-goose/goose/issues/12852) remains an Issue, **not** a shipped general S3 constructor. Manual parent/child steering or restart is the least costly baseline.

## Track B — on-top proposed constructor

The smallest additional **first-party optional** integration would let a developer register an autonomous **parent-scoped S3 choice owner**. It observes bounded live status of that parent's multiple children, independently chooses among continue, steer specific child, or request graceful wrap-up, and lawfully routes the command through existing first-party queues. The actor must receive a correlated application/result signal before making a later decision. A simple external event logger, a hardcoded concurrency cap, or relaying a person's instruction is **not S3=C**.

| C link | Reused native baseline | Required extra proposed link |
| --- | --- | --- |
| Current state of multiple active S1 children | SessionManager, SubagentOperation, current-run records | Parent-scoped sanitized multi-child snapshot for a composed actor |
| Real management choice | Parent user/manual steer; configurable static concurrency | Registered independent S3 actor deciding continue/steer/wrap_up |
| Legitimate downstream action | SessionRuntime queue; SteerOperation between turns | Verify parent-child ownership, live run and parent approval; no cross-parent control |
| Later feedback | SubagentUpdate to parent and persisted child outcome | Correlate decision with applied/superseded child instruction and next result back to S3 |

## P0, dependencies and alternatives

**P0:** minimal developer-composed S3=A -> S3=C complete organizational decision, effect and feedback chain. **P1:** agree the child steering lifecycle and permission scope with original maintainers; wait for Ready before implementation; run source-native acceptance and matched baseline. **P2:** NONE. Alternative **reuse unchanged**: manual steering or cancellation. Alternative **integrate existing**: implement only the user-facing child steer requested by #12852, with no new autonomous manager, if it solves actual needs. Adjacent S3* or S4 changes are not justified by this case.

## Future acceptance and falsification

Positive: on a deterministic two-child run, a developer-composed S3 actor sees both, chooses lawful direction for child A, A changes its next turn, B continues unaffected, and the parent/S3 receives the correlated result. Distinct alternative: same constructor can choose continue or differently target another child depending on state. Negative: missing actor, wrong-parent target, denied parent approval or stale run cannot send a child command; a queued command must never be misreported as applied. Native comparator executes the same workload by manual steering or cancel/restart.

**Falsifier:** equivalent autonomous developer-composable S3 decision and returned feedback already shipped; or no parent-safe child effect between turns; or no discretionary management choice; or measured benefit disappears against the native alternative.

**Validation state:** NOT_RUN. **Cost status:** NOT_MEASURED. Design GO is not shipping, test success, a new Index rating or an implementation right.

## Delivery, rights and original repository

Original [Apache-2.0 license](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/LICENSE); [Goose contribution rules](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/CONTRIBUTING.md) require a non-exempt original PR to follow an issue in Ready and place responsibility for AI assistance on the human contributor. Owner approved RESUME/ALLOW **for fork-local metadata**; no exact approval for publishing a public fork Issue, original maintainer contact, code patch, PR, or ongoing monitoring was given. New case stays on opensiro/meta only. The [separate historical S3* case](../goose-adversary-audit-20261119/README.md) is unchanged.

AI-assisted draft; no original-native tests or independent human review claimed.
