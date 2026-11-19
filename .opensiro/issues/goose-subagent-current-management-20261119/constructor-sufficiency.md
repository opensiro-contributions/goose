# Goose — S3 current-management constructor: technical sufficiency contract

**PLAN_ONLY / HYPOTHETICAL / NOT_RUN / DRAFT — NOT PUBLISHED**

**Human issue:** [issue.md](issue.md). **Canonical receipt:** [roadmap.md](roadmap.md). The receipt owns the accepted historical vector, target and priorities; no current Index grade is assigned here.

**Target transition:** S3=A -> S3=C

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

## Function-specific scope and counterfactual

Pinned first-party runtime [aaif-goose/goose@bf074d6d114690de6cbe7edc925cb26efdf6f16a](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/README.md): Goose state-machine execution, oi-kit/GDK, Summon/foreground children, session manager, ACP/CLI, hooks and permissions; not arbitrary MCP deployments, developer GitHub workflows or a new S5. Disturbance: priorities change while two or more child agents execute and the parent awaits the batch. This particular new autonomous management benefit is **HYPOTHETICAL**; user-directed mid-run child steering is an observed request [#12852](https://github.com/aaif-goose/goose/issues/12852).

S1 executes child work; S2 caps concurrent child starts; S3 should own current commitments across running children, *without* replacing the user. S3* independent audit, S4 external future intelligence, S5 ultimate policy are neither automatically upgraded nor part of this constructor. The historical S3 A witness, the old orchestrator, was removed in [merged #12729](https://github.com/aaif-goose/goose/pull/12729), and must not be silently cited as present.

**Absent-actor counterfactual:** with the native queue and subagent outcome transport but no developer-composed S3, no autonomous owner makes a fresh current-management choice while the parent waits. The parent/manual control continues. A transport/permission hook with no discretion would not qualify as C.

## Track A — first-party overlap

- **SHIPPED:** [SubagentOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/subagent.rs) selects pending children and returns their notices, results and completion; [state-machine builder](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/state_machine_builder.rs) supplies a configurable limit defaulting to five and a SteerOperation.
- **SHIPPED:** [SessionRuntime](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/session_runtime.rs) holds queues per session, [StateMachineServices::steer](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/services.rs) enqueues to an existing session; existing-session lookup alone is not enough for the proposed parent-to-child authorization; [SteerOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/steer.rs) handles messages between turns.
- **SHIPPED:** [SessionManager](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/session/session_manager.rs) stores parent child identity/history; no general unscoped query should be exposed to a newly composed controller.
- **MERGED:** [#12729](https://github.com/aaif-goose/goose/pull/12729) deleted orchestrator; [#12802](https://github.com/aaif-goose/goose/pull/12802) child permissions/hooks; [#12946](https://github.com/aaif-goose/goose/pull/12946) concurrency limit; [#12998](https://github.com/aaif-goose/goose/pull/12998) view-only child UI.
- **ISSUE_ONLY:** [#12852](https://github.com/aaif-goose/goose/issues/12852) addresses child steer/wrap-up; not an autonomous S3 constructor. Current comments clarify lost-output symptom improved, still ask for mid-flight changed focus.
- **Baseline:** native parent awaiting child results plus human/parent steering, or a smaller solution adding manual child steering only. No separate feature is required if that alone meets the operator need.

## Track B — minimum complete proposed S3 C chain

| Organizational requirement | Real source to reuse | Minimal additional first-party change |
| --- | --- | --- |
| S3 input: reliable status across this parent's live children | SessionManager, SubagentUpdate, active run state | Bounded, sanitized, parent-scoped live child snapshot; distinguish pending/running/finished and do not leak other sessions |
| Developer-composable discretionary decision | Existing hooks execute effects; current cap is fixed | Optional registration/invocation seam for a **developer-supplied autonomous S3 actor**, taking snapshot/objectives and selecting continue, steer child, or graceful wrap-up |
| Legitimate effect on a subsequent S1 turn | StateMachineServices::steer, SessionRuntime queue, SteerOperation | Verify child belongs to parent, active run, and approval/policy; route only to selected child, preserving native queues and permissions |
| Returned closure and repeat choice | SubagentOperation returns outcomes to parent | Attribute action acceptance, application/supersession and later result to S3; allow the owner to update its next choice |

**Complete hypothetical witness:** runtime disturbance → current multi-child state → developer-registered autonomous S3 decision → parent-scope/approval check → target child's later action → correlated result/failed-application notice back to S3 → possible subsequent revised choice. This is *not* shipped. Interface names are proposals until reconciled with Goose's actual code and maintainer design.

**Ownership constraints:** no cross-parent child, no override of parent Approve mode, no fake tool approval, no global session enumeration, no unrelated credential access, no new S5 policy owner. Do not recreate the removed orchestrator. Respect [#12802](https://github.com/aaif-goose/goose/pull/12802).

**On-top distinctness:** user-directed child steer (#12852) is a smaller native feature and would falsify the need for autonomous composition if it suffices. S3 C requires the **decision owner**, not just an event bus. Keep separate the old S3* Adversary case.

## P0, P1, P2 and stop

P0 is the bounded S3 constructor path above. P1: maintainer-approved child-steer and lifecycle interface, owner/parent gate, correlation semantics, Ready issue before any non-exempt code PR, and native tests. P2 NONE. Stop if current core already supports equivalent autonomous S3, feedback cannot reach actor, user authority cannot remain intact, or child action is not executable during a live run.

## Future native tests, not yet run

The original workspace includes packages **goose** and **oi-kit-agent**. Proposed genuine commands after an approved implementation are **cargo test -p oi-kit-agent** and **cargo test -p goose --lib**, with dedicated tests beside [Goose state-machine tests](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/state_machine/tests/agent_reply.rs) and [GDK subagent](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/subagent.rs). Neither command was executed in this work.

| Proposed native case | Expected lawful effect and receipt | Failure / falsifier |
| --- | --- | --- |
| Two-child autonomous decision | Child A changes next inference as requested by registered S3; child B continues; S3 and parent see correlated result | Controller cannot act before batch returns or changes B |
| Alternative discretionary choice | Same builder selects continue or a different child when snapshot changes; distinct result | Static policy/relay, no real choice |
| Authority negative | Wrong-parent child, stale run or parent-denied action rejected before child execution | Permission bypass or wrong child receives command |
| Disabled compatibility | No S3 actor: existing parent/subagent execution and approvals unchanged | Native baseline regresses |
| Delivery correctness | Queued vs applied vs superseded outcome distinguished; canceled child does not fabricate completion | False acknowledgment accepted as closed loop |

**Matched counterfactual:** compare exactly the same two-child operator task using present native manual guidance/cancel, including failure risk, latency, engineering time, reviewer effort and maintenance. All cost and utility results remain **NOT_MEASURED**.

**Primary falsifier:** no distinct lawful autonomous management choice and actual returned effect beyond native manual steering, or equivalent already supported C. **Validation state: NOT_RUN**. No PR, public Issue, code change, Index grade change or external publication authorized by this document. AI-assisted research; human review not presumed.
