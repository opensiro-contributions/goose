# Goose — developer C-sufficiency contract for independent S3* audit

**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

[Canonical roadmap receipt](roadmap.md) · [Human issue draft](issue.md) · [Case index](README.md). New independent proposal-stage assessment under Upstream v0.18.0; **no native implementation or Index regrade**. Original pinned `c77f95b9c5c4242cd1cb83669523d2231da75352`, accepted historical `S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—` at [included Index](https://github.com/opensiro/vsm-harness-index/blob/8b6039a92b39e9ac9e02af8c9a99513d632c3684/assessments/go/goose.md), review ref `50666ae0b9a51e260b52b7efbab2e4e020346e94`, reviewed 2026-09-15. No duplication of the Human six-function table.

## Decision, independent evidence and ownership

**P0 scope:** not the BLOCK→approval policy issue in #13271. It is a developer-composable **complementary operational reality audit** of claimed output, based on tool effects plus bounded source-of-truth probes independently of the primary LLM's narration. **Function:** S3*; **reviewer** owns the audit judgment and evidence-return, **Goose runtime** supplies trusted evidence and enforces bounded continuation/terminal disposition, **developer/user/parent** sets policy/allowed probes and final unresolved disposition. A tool filter or prompt without independent factual access does not prove S3*.

**Current Track A:** https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/security/adversary_inspector.rs receives original task/recent messages/proposed tool call through the same provider manager, with `Deny` or fail-open; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/tool_inspection.rs combines inspection results; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine/tool_approval.rs maps to tool permission; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/hooks/mod.rs has hook context and blocking protocols; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine/ops_stop_hook.rs returns hidden corrective message on denial but on `denials > block_cap` ends the turn. https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine_builder.rs assembles oi-kit operations. This creates credible first-party attachment points, **not** a shipped independent audit guarantee.

**Alternative baseline A:** user-authored Stop command reading local repo state; or correct #13271 visible denial. They may help narrower tasks but a generic hook alone is not an independently owned, attributable, durable audit constructor, and stop-cap override is not verified completion. Original https://github.com/aaif-goose/goose/issues/9708 reported false completion claims and proposed a ground-truth check; closed Issue/PR #10361 not counted as product implementation.

## Minimal first-party Track B architecture (hypothesis, not API declaration)

1. **Source facts:** on tool effect application capture `session_id, run_id, tool_call_id, operation, arguments digest, completion status, bounded output digest, git/file/test probe receipt` in trustworthy runtime-owned evidence. Do not accept the executing model's text as the evidence source. Make privacy and retention explicit; no secret content in public records.
2. **Separate reviewer:** developer opts in to an isolated verifier process/provider and scoped read-only probes. The verifier can choose `PASS`, `REWORK(reason,evidence_ids)` or `ESCALATE_UNVERIFIED(reason,evidence_ids)`; an agent may not choose or revise its own reviewer policy. Claims without evidence become UNKNOWN, not PASS.
3. **Closure:** first-party oi-kit/Goose operation integrates after effects and before recognized verified completion, returning REWORK to the next agent step through the existing corrective-message pattern; an exhausted cap, crash or stale evidence becomes an explicit durable UNVERIFIED terminal/parent decision, never a silent PASS. Existing stop-hook cap override must be guarded with independent completion-status semantics.
4. **Return feedback:** subsequent S1 turn sees the attributable outcome and may run actual missing action or retract the claim; user sees evidence-backed final disposition. Reviewer cannot waive pre-existing binding security Deny, execute tools without scope, or change the parent S5 policy.

**Required VSM C chain:** disturbance = output claim inconsistent with independently observed operation; choices = PASS/REWORK/UNVERIFIED; actor = developer-composed autonomous independent auditor; authority = parent-approved read-only review + bounded hold/return (not a new S5 policy); effect = state-machine completion gating / recorded unverified status; feedback = evidence-backed next operative turn or explicit parent escalation. With no independent reviewer installed or no trustworthy facts, no `S3*=C` claim.

## Counterfactuals and falsifiers

- Remove auditor while retaining hooks: same evidence-grounded audit judgment must **not** still be made; if it is, reviewer was cosmetic and the proposed `C` owner is wrong.
- Missing/forged/stale tool facts: never mark verified; deterministic unknown/rework/parent handoff.
- Stop blocked repeatedly: after `GOOSE_STOP_HOOK_BLOCK_CAP` is exceeded the turn may be closed, but its outcome cannot be marked VERIFIED; if closure cannot be separated, proposed C construction **fails**.
- Parent has not delegated access: no probe or tool execution, return BLOCKED/UNVERIFIED according to legitimate policy, never invent authorization.
- Existing current shipped first-party equivalent function-level evidence-audit owner and closure: independent proposed new constructor is redundant and this GO must be revised.
- Reviewer loop relies only on the same model's plan/current messages without independent reality: does not close S3* as proposed.

## Proposed native acceptance (not executed)

| Case | Expected | Fail |
| --- | --- | --- |
| AC-01 | Claimed tests PASS but no executed test tool/result → REWORK/UNVERIFIED | VERIFIED |
| AC-02 | Tool result and authoritative probe support claimed action → PASS | false REWORK |
| AC-03 | Auditor output denies completion and next S1 turn receives concrete evidence IDs | model ends as verified without correction |
| AC-04 | Eight plus repeated Stop denials hit configured cap → UNVERIFIED/parent escalation | cap implicitly changes negative audit to VERIFIED |
| AC-05 | Original permission Deny persists irrespective of reviewer PASS | audit bypasses Deny |
| AC-06 | Probe permission absent, stale evidence or reviewer timeout → bounded unknown state | hidden false PASS or unbounded hang |
| AC-07 | Auditor unavailable, same-model-only prompt and wrong recursion boundary do not count as C | false autonomy regrade |
| AC-08 | Resume/reload preserves evidence attribution and decision | fresh turn loses unresolved negative audit |

Run after **separate authorized implementation** using Goose native targeted `cargo test -p goose`, `cargo test -p oi-kit-agent`, formatting and hook/operation integration checks appropriate to changed files; do not assert they passed now. Native tests NOT_RUN, adversarial reliability, integration cost and operator benefit NOT_MEASURED. P1 authority/provenance/cap is mandatory; P2 NONE.

## Historical comparison / constraints

Independent result sealed first: https://github.com/opensiro/upstream/issues/58#issuecomment-7042861025. Afterward [historical NO_GO receipt](https://github.com/opensiro-contributions/goose/blob/fabfcf43e1652aceefa6042f0b870ba36c512455/.opensiro/issues/goose-adversary-audit-20261119/roadmap.md) read; that decision emphasized a narrow native visibility problem, unmeasured extra benefit and maintainer's issue choice. Under published v0.18.0, those do not alone disprove a distinct **constructible** S3* chain. New verdict GO/NEEDS_EVIDENCE is narrow, hypothetical and reversible, not a demand to replace shipped Goose inspector or an accepted Index grade. Original https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/CONTRIBUTING.md / https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/AGENTS.md Ready/publication rights still apply. Fork owner ACTIVE/ALLOW is metadata permission only. No original/fork GitHub Issue/PR or outward communication has been published.
