# Goose Capability Roadmap Receipt — 2026-11-19 independent six-function rerun

**Canonical case decision, Upstream v0.18.0, fork metadata only**

- Receipt contract: proposal-gate
- Original repository: aaif-goose/goose
- Original HEAD: bf074d6d114690de6cbe7edc925cb26efdf6f16a
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/394ce776e6945115891b8f7cc459f5a7f7d7aa39/assessments/go/goose.md
- Accepted assessment blob SHA: df07d489a966ff9f16c1e010ba65219afded14c7
- Accepted review ref: 50666ae0b9a51e260b52b7efbab2e4e020346e94
- Accepted reviewed at: 2026-09-15
- System in focus: Supported first-party Goose runtime including parent plus foreground delegated subagents and CLI/ACP lifecycle, excluding arbitrary MCP deployments, CI governance and original maintainers
- Accepted VSM vector: S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—
- Repository-wide source map: Pinned complete 2612-file source tree screened: crates/goose, crates/oi-kit-agent, CLI, ACP, extension and session paths, permissions, security, provider inventory, documentation, examples, UI, tests, CI and contributor guide
- Priority rationale: S3 controller hypothesis ranked first due removed orchestrator, shipped subagent concurrency and session steer primitives, original mid-run steering need and a narrow lawful feedback-complete candidate; other functions deferred with separate reasoning
- S1 disposition: Historical A with direct model and tool operation; no new S1 C target
- S2 disposition: Historical dash; static native subagent concurrency limit is shipped; no separate autonomous coordination target chosen
- S3 disposition: Historical A old orchestrator now removed; proposed parent-scoped developer-composed current management C actor and feedback
- S3* disposition: Historical dash; inspectors and hooks cannot alone certify independent reviewer closure; distinct prior case unchanged
- S4 disposition: Historical dash; live inventory and provider configuration not proven future adaptation decision loop; deferred
- S5 disposition: Historical dash; ultimate permission and identity authority retained by parent and developer; no new S5 controller
- Target transition: S3=A -> S3=C
- P1 dependencies: Maintainer-agreed child-steer design, correct child ownership and live run guard, original Ready gate before code, native tests and matched manual baseline
- P2 optional: NONE
- Proposed C construction: Optional developer-composed autonomous parent-scoped S3 owner with multi-child status input, lawful continue/steer/wrap_up decision, actual child effect and correlated feedback returned to owner
- C sufficiency falsifier: Existing native Goose already exposes equivalent safe autonomously composable multi-child current management, or proposed registered actor has no decisive lawful effect or returned feedback
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: Two simultaneously active children with safe targeted management, distinct lawful alternative, unchanged other child, parent-denial/wrong-child/stale-run negatives, application feedback and same-task native comparator
- Validation state: NOT_RUN
- Proposal falsifier: No state-dependent discretionary S3 choice that reaches a later child turn with attributable feedback under parent rights
- Evaluation object: Autonomous current commitment management for concurrently running delegated Goose subagents, not tool security and Adversary blocking
- Existing-work overlap: Current state-machine and session APIs; merged original PRs 12729 12802 12946 12998; original issue 12852 remains open
- Our on-top contribution: Reuse native session, steer, subagent results and approvals; add minimal optional developer S3 decision registration, parent-scoped child status/effect and action feedback
- Incremental benefit: Hypothetical lawful redirection of one active child without canceling others or losing progress, compared to manual native steering, not measured
- Decision scope: Source-grounded proposal GO for one S3 C hypothesis, not implementation, shipped function claim, Index regrade or another function's verdict
- Result: NEEDS_EVIDENCE
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

## Identity and pins

The [accepted Index Goose assessment](https://github.com/opensiro/vsm-harness-index/blob/394ce776e6945115891b8f7cc459f5a7f7d7aa39/assessments/go/goose.md) has status included, blob df07d489a966ff9f16c1e010ba65219afded14c7, review 2026-09-15 under Profile 0.2.1/Methodology 0.3.1 and original review_ref 50666ae0b9a51e260b52b7efbab2e4e020346e94. The present original [HEAD](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/README.md) is a separate point-in-time fact, not an Index regrade. Original licensed Apache-2.0 and fork identity verified. [Upstream v0.18.0](https://github.com/opensiro/upstream/blob/4db2e1cd8666afd4981afb6c2270c37e96c36ead/docs/CAPABILITY_ROADMAP.md) governs research. The [Human issue](issue.md) and [AI constructor contract](constructor-sufficiency.md) are derived companions. [Case index](README.md).

## Rights and authority

Original [CONTRIBUTING](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/CONTRIBUTING.md) requires original Ready issue before a non-exempt implementation PR, human responsibility for AI output and maintainer control of design. Verified fork parent aaif-goose/goose, opensiro/meta previously f51beea140e769d5e91c88fbe31ca7dcbaa04412 with owner PAUSE, attention DORMANT. Explicit current-conversation owner RESUME/ALLOW is represented in [append-only event](../../events/2026-11-19T175625Z--goose-resume-allow.json); owner control ALLOW, attention kept DORMANT, no scheduled research. No public Issue, maintainer comment, original PR or product branch change is consented to by this record. Contributor formalities beyond root Apache-2.0 are not assumed satisfied.

## Existing work / overlap

[PR #12729](https://github.com/aaif-goose/goose/pull/12729) MERGED removes the earlier orchestrator and background subagent path; [PR #12802](https://github.com/aaif-goose/goose/pull/12802) MERGED binds child permissions; [PR #12946](https://github.com/aaif-goose/goose/pull/12946) MERGED adds default five-child cap; [PR #12998](https://github.com/aaif-goose/goose/pull/12998) MERGED makes child UI view-only. [Issue #12852](https://github.com/aaif-goose/goose/issues/12852) OPEN, requested mid-run child steering; its discussion narrows remaining concern after output-loss improvement. Original [SubagentOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/subagent.rs), [StateMachineServices](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/services.rs), [SessionRuntime](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/goose/src/agents/session_runtime.rs), [SteerOperation](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/crates/oi-kit-agent/src/steer.rs) are shipped reusable primitives, not a finished cross-child autonomous manager.

## Function ownership

Whole-tree screen before deciding P0: S1 tool execution is first-party; S2 includes a non-autonomous concurrent child cap; S3 former native orchestrator gone while current session/steer lifecycle exists; S3* inspectors are not independent composed audit closure by mere registration; S4 provider metadata refresh is not a proven autonomous prospective process; S5 remains parent/user permissions. Historical grades shown in [Human six-row table](issue.md) are immutable until independent Index assessment; current remarks are hypotheses, not replacements. No unsupported claim of deliberate omission.

## Capability priority

**P0** S3=A -> S3=C as a narrow developer-composed autonomous parent-scoped manager of current multi-child commitments, decisions and returned outcomes. **P1** original maintainer design and Ready gate, parent-child authorization, live-run/apply status, source-native validation and baseline. **P2** NONE. This is architecturally a PROPOSED_C_SUFFICIENT path only if all proposed state, discretion, lawful effect and feedback links become real.

## Parallel contribution-on-top review

| Requirement | Track A existing / native issue | Track B minimal source-native on-top construction | Falsifier |
| --- | --- | --- | --- |
| Current child workload status | Session records and SubagentOperation notifications | Bounded parent-scoped live child snapshot | Equivalent native S3 state/decision already available |
| Decisive choice | Parent waits, manual steer, static concurrency; #12852 requests child steering | Optional developer autonomous S3 actor chooses continue/steer/wrap_up | Only a relay/static rule; no autonomous decision |
| Safe action | StateMachineServices steer queue, SteerOperation, inherited parent permissions | Check same parent, live run and approval before targeted child instruction | Wrong parent or denied actor can steer |
| Closure and feedback | SubagentUpdate returns child outcome | Correlate queued/applied/superseded instruction and next child result to S3 | No later effect or closed receipt |

**Reuse unchanged** is the manual steering/restart baseline. **Integrate/extend** is a bounded new developer actor over native components, only if this distinct owner provides value. **Adjacent** S3* security or S4 model adaptation are separate unselected functions. Same user task and pinned original are the comparator, not a second abstract orchestration product.

## Implementation options

Preferred preliminary original-native route is agreement on #12852's safe child-steer semantics; only if separate autonomous management is justified would Goose add an optional source-native S3 registration and parent-scoped observation/intervention/feedback bridge. Preserve #12802 parent approval and the original C limits; do not bring back the deleted orchestrator, invent a new global controller or grant S5. A controller that merely broadcasts messages without its own decision is insufficient.

## Specification and domain alternatives

Historic S3 A witness disappearance is a question for **separate Index-owner reassessment**, not automatic changed VSM grade. Parent-governed S5 is legitimate and should not be forced into a C target. Unrelated Profile/Skills or domain fork changes have no demonstrated need in this bounded case. The prior [Goose S3* Adversary roadmap](../goose-adversary-audit-20261119/roadmap.md) remains intact with distinct historical NO_GO; this new S3 case was selected independently before comparing that history.

## Cost experiment

**NOT_MEASURED.** Later compare a deterministic two-child task with native await/user steering/cancel against the new S3 actor on scope correctness, intervention success, unaffected child outcome, run time, tokens and engineering/review/maintenance effort. Future [cargo workspace tests](https://github.com/aaif-goose/goose/blob/bf074d6d114690de6cbe7edc925cb26efdf6f16a/Cargo.toml) and dedicated tests in goose and oi-kit-agent must run; they did not run here.

## Delivery and publication

**GO (proposal only) + NEEDS_EVIDENCE (research), NOT_RUN validation.** Fork-local metadata only, with Human/AI/Receipt and owner event, no new .opensiro/contributions record for a plan. No product code, CI execution, public fork Issue, original maintainer communication, original PR, independent human verification or accepted Index modification. Public GitHub Issues/PRs require separate exact approval.
