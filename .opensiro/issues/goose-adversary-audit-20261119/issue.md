# Goose — independent evidence-grounded completion audit (S3*) · OpenSiro PLAN_ONLY

**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

This is an **unimplemented, independently testable architectural proposal**, not a claim that Goose lacks quality or that maintainers should adopt it. [Canonical receipt](roadmap.md) · [AI/developer contract](constructor-sufficiency.md) · [Case index](README.md). **Public fork Issue DRAFT — NOT PUBLISHED.**

## Why this case

Goose's current https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/security/adversary_inspector.rs reviews proposed tool calls using an LLM and may block them. This is not proof that a separately owned auditor verifies what actually happened, e.g., whether purported tests really ran or a claimed commit exists. The opt-in S3* construction would give a developer a way to compose that independent evidence audit *within* the first-party operation/return path, without transferring policy ownership to the reviewer.

Accepted Index https://github.com/opensiro/vsm-harness-index/blob/8b6039a92b39e9ac9e02af8c9a99513d632c3684/assessments/go/goose.md (included, reviewed 2026-09-15, profile 0.2.1 / methodology 0.3.1, review_ref `50666ae0b9a51e260b52b7efbab2e4e020346e94`); historical vector **S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—**. Original pinned `main@c77f95b9c5c4242cd1cb83669523d2231da75352` (2026-11-20). The historical vector is **not** a new current-HEAD assessment.

| Function | Historical Index | Current source reading / proposal priority |
| --- | --- | --- |
| **S1 · Operations** | A | oi-kit/Goose state machine executes tools, retains messages and returns feedback; no new S1 constructor |
| **S2 · Coordination** | — | subagents and concurrency are not sufficient evidence for conflict attenuation and closure |
| **S3 · Current management** | A | older orchestrator witness; the current platform registry changed, so fresh Index review needed before any current claim |
| **S3* · Complementary audit** | — | P0: independently owned, source-of-reality verification and bounded corrective return; proposed C only |
| **S4 · Future intelligence** | — | roaming/provider support does not establish a whole-system prospective learning loop |
| **S5 · Policy and identity** | — | legitimate policy remains with user/developer/parent, not an invented autonomous governing agent |

## What changes for the user if the design is later implemented

A Goose task may end with a confident success statement despite an independent tool-result or repository probe not supporting it (reported as an issue in [original #9708](https://github.com/aaif-goose/goose/issues/9708), now closed). An opt-in independent reviewer could distinguish **VERIFIED / REWORK / UNVERIFIED**, return a specific evidence-backed correction for another operative attempt, and on exhausted retries surface **UNVERIFIED** rather than silently allow a stop-hook cap to turn an audit failure into success.

**Proposal-stage GO / NEEDS_EVIDENCE** means this first-party C chain is architecturally constructible if implemented and validated. It says nothing about whether the original maintainers want it, current necessity, or actual outcome improvements.

## Shipped paths, original work and alternatives

- Goose currently ships first-party AdversaryInspector, tool inspection/permission routing, configurable before/after tool hooks, and https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine/ops_stop_hook.rs stop/rework (with a bounded cap). These are important reuse points but not an established closed independent evidence audit at the declared boundary.
- [Original #13271](https://github.com/aaif-goose/goose/issues/13271) is OPEN and addresses BLOCK reason/permission behavior. [PR #13272](https://github.com/aaif-goose/goose/pull/13272) is CLOSED UNMERGED. Fixing that issue is useful **independently**; it neither proves nor vetoes the S3* constructor.
- [Original #9708](https://github.com/aaif-goose/goose/issues/9708) is CLOSED and [PR #10361](https://github.com/aaif-goose/goose/pull/10361) for tool trace/advise was CLOSED UNMERGED. Treat their proposals as design context, not shipped behavior. Original [#13397](https://github.com/aaif-goose/goose/issues/13397) and [PR #13405](https://github.com/aaif-goose/goose/pull/13405) concern security decision telemetry (PR OPEN).
- Minimal user-authored Stop hook with live probes remains baseline A. B adds a reusable, developer-composable independent decision actor, trusted provenance and explicit bounded effect; the future side-by-side test decides whether it is materially different.

## P0, P1, P2 and acceptance

**P0:** Optional first-party adapter between trusted execution facts and independent reviewer with binding audit feedback into following S1 operation; complete developer contract in [constructor-sufficiency.md](constructor-sufficiency.md). No product work authorized.

**P1:** Evidence trust boundary, distinct auditor identity, cap/resume/unverified status semantics, legitimate owner scope and native tests. Negative: a false claimed test/commit cannot become VERIFIED; auditor absence or stale evidence does not fabricate PASS; existing user permission or security denial is never silently relaxed.

**P2:** None for this scoped case.

**Falsifier:** current code already ships equivalent first-party independent outcome-audit ownership/closure, or the proposed adapter cannot lawfully get trusted evidence and make a negative decision change subsequent completion. Native tests **NOT_RUN**; product desirability, cost and measured benefit **UNKNOWN / NOT_MEASURED**.

## Historical comparison and publication

Source-first new-wave decision sealed in [Upstream #58](https://github.com/opensiro/upstream/issues/58#issuecomment-7042861025) before full historical case review. The [frozen 2026-11-19 NO_GO receipt](https://github.com/opensiro-contributions/goose/blob/fabfcf43e1652aceefa6042f0b870ba36c512455/.opensiro/issues/goose-adversary-audit-20261119/roadmap.md) excluded a new constructor largely on missing benefit and overlap with a native visibility fix; the published v0.18.0 neutrality rule now distinguishes *architectural constructibility* from *maintainer product decision*. This is **NO_GO → GO** on the scoped proposal, **not** an assessment grade change or automatic product recommendation.

Working fork: https://github.com/opensiro-contributions/goose, verified parent aaif-goose/goose, .opensiro on separate metadata branch with ACTIVE/ALLOW. Original maintainers decide adoption. No external original Issue/PR, public fork Issue or code patch is authorized. **This complete text is a draft for an optional public fork Issue and requires its own exact current-conversation publication approval; not published.**
