# Goose — source-native S3* C-construction technical contract

**Canonical storage:** opensiro-contributions/goose@opensiro/meta:.opensiro/issues/goose-adversary-audit-20261119/constructor-sufficiency.md.
**Level 1 / Human decision Issue:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md), authoritative for Index vector, case pins, priority and verdict.
**Stage:** PLAN_ONLY / HYPOTHESIS, current v0.18.2 template synchronization; **DRAFT — NOT PUBLISHED**. Native validation NOT_RUN.

## 1. Function-specific construction boundary and methodology checks

**Source and mode boundary:** Original aaif-goose/goose at current original HEAD ca949ba94c0d59679c7e7eeccfaa277076e5b9e9, first-party entrypoints [crates/goose/src/agents/state_machine/session.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/state_machine/session.rs) and [crates/goose/src/agents/platform_extensions/summon.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/platform_extensions/summon.rs). The canonical historical research HEAD remains c77f95b9c5c4242cd1cb83669523d2231da75352; accepted historical Index https://github.com/opensiro/vsm-harness-index/blob/8b6039a92b39e9ac9e02af8c9a99513d632c3684/assessments/go/goose.md reviewed at 50666ae0b9a51e260b52b7efbab2e4e020346e94. The supported local first-party runtime and its explicit optional modes are the unit of analysis. Original project's own CI, third-party provider, external management and parent owner are not silently counted as agent functions.

**Target transition:** S3*=— -> S3*=C

**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1 and S3 are already historically agent-owned. S3* is the independent evidence decision, not token permission or S3 operation itself; S4/S5 remain outside this limited proposal. Reuse historical S1=A · S2=— · S3=A · S3*=— · S4=— · S5=— without changing the Index. Supporting runtime permissions and transport are not themselves autonomous decisions.

**Function witness:** An agent concludes a task succeeded even though the supporting tool trace or independent postcondition is missing, partial, stale or inconsistent. The legitimate independent choice and owner: a separately configured audit actor adjudicates whether a finished Goose turn's claimed real-world task outcome is supported by authoritative tool facts. On independent evidence: accept an actually verified outcome, require bounded source-backed rework, or escalate as explicitly unverified without inventing success. The effect and feedback must be The first-party turn finalization and next action must represent REWORK/UNVERIFIED accurately; the auditor sees the effect and can never silently certify its own evidence..

**Counterfactual owner test:** Remove the optional developer-composed S3* decision actor but keep current source machinery: Goose first-party oi-kit/state-machine owns tool execution/finalization and summon runs isolated subagent context. The historical source review also identifies AdversaryInspector and Stop hooks that govern pre-tool security, not independently verified post-operation outcomes. The specific extra choice would then be missing: A subagent's separate context and a pre-tool security filter are not proof of materially independent post-operation evidence review. Existing Stop denial may be capped; hook-only control cannot be presumed fail-closed.. A mere generic hook or another model call does not count.

**Possible methodological negative control:** If baseline first-party code already closes the exact owner/choice/effect/return at the supported boundary, or only a human parent may choose, report native equivalence and withdraw the new C design rather than regrade.

**Contributor / maintainer priorities:** NOT_STATED as approval of this exact VSM construction; third-party product direction remains the maintainer's.

## 2. Source-pinned baseline and parallel native Track A / on-top Track B

**Original native workflow:** Goose first-party oi-kit/state-machine owns tool execution/finalization and summon runs isolated subagent context. The historical source review also identifies AdversaryInspector and Stop hooks that govern pre-tool security, not independently verified post-operation outcomes. First-party pinned source: [crates/goose/src/agents/state_machine/session.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/state_machine/session.rs) and [crates/goose/src/agents/platform_extensions/summon.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/platform_extensions/summon.rs).

**Closest existing solution:** Compare existing inspection and Stop-hook behavior first; prefer a bounded native hook if it truly enforces the same observable post-turn outcome.

**Relevant original Issues/PRs:** https://github.com/aaif-goose/goose/issues/9708 (CLOSED issue about ground-truth completion); historical #13271 security visibility was a different concern. Original PR status must be checked again before any code change.. Labels such as OPEN or CLOSED are current at this follow-up only where checked; unverified heads are not treated as merged.

| Required C link or operator outcome | Track A: shipped/current source | Track B: minimum integration | Falsifier |
| --- | --- | --- | --- |
| Bounded whole-function decision | Goose first-party oi-kit/state-machine owns tool execution/finalization and summon runs isolated subagent context. The historical source review also identifies AdversaryInspector and Stop hooks that govern pre-tool security, not independently verified post-operation outcomes. | On independent evidence: accept an actually verified outcome, require bounded source-backed rework, or escalate as explicitly unverified without inventing success. | A subagent's separate context and a pre-tool security filter are not proof of materially independent post-operation evidence review. Existing Stop denial may be capped; hook-only control cannot be presumed fail-closed. |
| Lawful downstream effect | Source entrypoints at crates/goose/src/agents/state_machine/session.rs and crates/goose/src/agents/platform_extensions/summon.rs | The first-party turn finalization and next action must represent REWORK/UNVERIFIED accurately; the auditor sees the effect and can never silently certify its own evidence. | Missing evidence, self-review, hook cap, stale credentials or revoked reviewer must not silently become VERIFIED; no-verifier deployment retains original behavior. |

**On-top distinctness:** A subagent's separate context and a pre-tool security filter are not proof of materially independent post-operation evidence review. Existing Stop denial may be capped; hook-only control cannot be presumed fail-closed. First prefer the exact native solution; a copied supervisor abstraction is insufficient.

**Source ambiguity / rights blockers:** Future source HEAD/PR changes, reviewer identity, permission of the original owner, and tests are unverified. A matched fork research write does not authorize external original actions or code changes. No evidence-free demand assumption.

## 3. Minimal complete S3* first-party C construction

**Required property:** A first-party S3*-specific path to install a legitimate autonomous decision owner, enforce its selected lawful alternative, and return later operational evidence.

| Necessary native component or port | Existing first-party source | Smallest proposed change / integration | Legitimate owner, effect, return |
| --- | --- | --- | --- |
| Decision evidence and invocation | [crates/goose/src/agents/state_machine/session.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/state_machine/session.rs) | Add opt-in source-of-reality task evidence to the actual Goose finalization seam; invoke a separately owned scoped reviewer for PASS / REWORK / UNVERIFIED and bind bounded rework or explicit unverified handoff back to the operational next turn. | a separately configured audit actor adjudicates whether a finished Goose turn's claimed real-world task outcome is supported by authoritative tool facts |
| Bound decision and later feedback | [crates/goose/src/agents/platform_extensions/summon.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/platform_extensions/summon.rs) | The first-party turn finalization and next action must represent REWORK/UNVERIFIED accurately; the auditor sees the effect and can never silently certify its own evidence. | On independent evidence: accept an actually verified outcome, require bounded source-backed rework, or escalate as explicitly unverified without inventing success. |

**Architectural C-sufficiency argument:** Native baseline: Goose first-party oi-kit/state-machine owns tool execution/finalization and summon runs isolated subagent context. The historical source review also identifies AdversaryInspector and Stop hooks that govern pre-tool security, not independently verified post-operation outcomes. The key residual is A subagent's separate context and a pre-tool security filter are not proof of materially independent post-operation evidence review. Existing Stop denial may be capped; hook-only control cannot be presumed fail-closed. The strongest scoped optional solution is Add opt-in source-of-reality task evidence to the actual Goose finalization seam; invoke a separately owned scoped reviewer for PASS / REWORK / UNVERIFIED and bind bounded rework or explicit unverified handoff back to the operational next turn. Alternative one: use native/manual Compare existing inspection and Stop-hook behavior first; prefer a bounded native hook if it truly enforces the same observable post-turn outcome. Alternative two: avoid building if protected authority or actual feedback cannot be established. This proposal claims constructibility, not new implemented grade.

**Explicit non-goals:** No unrelated function upgrades, blanket task guardian, unrequested S5 authority, generic provider dependency, automatic external PR, or forced adoption.

**Implementation dependency graph:** Verify pinned current source and accepted assessment -> resolve P1 native rights/overlap/feedback proof -> implement minimal P0 only with separately authorized product work -> run native positive/negative closure tests -> reconsider adoption based on measured benefit.

## 4. Priorities, optional alternative and stopping rules

**P0 and P1:** P0 is Opt-in first-party evidence adapter + developer-selected independent evidence auditor + bounded verification decision and return-to-S1 via rework or explicitly unverified handoff; see AI contract P1 is verified tool/result evidence provenance, isolated reviewer identity and least-privilege evidence access, cap/resume and durable unverified-result semantics; original-native tests and legitimate policy-owner approval needed prior to implementation. Priorities are inherited, not newly changed.

**P2:** broader cross-session/fleet evidence auditing only after separate source-bound demand and authority analysis. No forced second VSM function.

**Alternative path:** Compare existing inspection and Stop-hook behavior first; prefer a bounded native hook if it truly enforces the same observable post-turn outcome.. Prefer this if it closes the same operator outcome with no independent C need.

**Stop:** Complete native equivalence, impossible independent actor right, no enforced return, policy veto or missing indispensable evidence triggers NO_GO/BLOCKED under the parent protocol. A missing measured saving is not by itself NO_GO.

## 5. Future source-native acceptance — derive tests, do not copy a matrix

**Native test commands and entry points:** Goose first-party Rust agent/state-machine tests are available. No cargo test executed, no verified model or external auditor run.

**Positive functional closure:** Pair claimed success with one authenticated true postcondition and one absent/failed tool result; reviewer forces different completion state and subsequent authorized rework.

**Independent alternative (where applicable):** On independent evidence: accept an actually verified outcome, require bounded source-backed rework, or escalate as explicitly unverified without inventing success. A genuine owner should be able to make two lawful different choices under different bounded contexts, not simply follow an always-grant rule.

**Negative authority and compatibility (where applicable):** Missing evidence, self-review, hook cap, stale credentials or revoked reviewer must not silently become VERIFIED; no-verifier deployment retains original behavior.

**Matched native alternative:** Compare existing inspection and Stop-hook behavior first; prefer a bounded native hook if it truly enforces the same observable post-turn outcome. Execute the same task once with current native behavior and once with conditional construction. No results or economics have yet been collected.

## 6. Proposal verdict, falsification, evidence ownership and handoff

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

**Primary falsifier:** Equivalent shipped first-party independent actual-outcome audit with autonomous reviewer ownership and binding operational feedback, or inability to persist/reify unverified outcome when stop-cap overrides a deny

**Validation state:** NOT_RUN; proposal only, no native tests.

**Ownership of truth:** Profile owns semantics; Skills owns assessment method; Index owns historical accepted classification; original aaif-goose/goose owns product change and maintainer choice; the [roadmap.md](roadmap.md) case receipt owns these decisions.

**Cost status:** NOT_MEASURED.

**Next permitted action:** Source-verify the narrow A/B comparison at current original HEAD and test scope under new explicit permission, or keep this as an unpublished research case.

**Human backlink:** [issue.md](issue.md); **case receipt:** [roadmap.md](roadmap.md).

**AI disclosure:** Drafted with AI; no native execution, maintainer consent, economic proof or independently verified value claimed.
