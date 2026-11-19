# Goose — complementary audit and Adversary BLOCK handling: architecture roadmap (OpenSiro plan-only)

**OpenSiro pilot · PLAN_ONLY / DECISION_READY · Decision: NO_GO · DRAFT — NOT PUBLISHED.**

**Two-level package:** This Human-facing roadmap and [AI/developer constructor-sufficiency contract](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/constructor-sufficiency.md). [Receipt](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/roadmap.md) · [Case index](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/README.md). **Working fork:** https://github.com/opensiro-contributions/goose (verified parent: aaif-goose/goose). No GitHub Issue has been published.

## 1. Why OpenSiro and central accepted VSM assessment

OpenSiro tests whether reusable, VSM-informed organizational specifications can standardize agent-harness development and reduce total implementation, integration, review, and maintenance cost. This is an *unproven cost hypothesis*, not a claim that Goose needs VSM or a request that its maintainers adopt it.

**STARTING POINT — accepted historical Index, not a target or an assessment of current main:** **S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—**. [Accepted assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/go/goose.md); review_ref `50666ae0b9a51e260b52b7efbab2e4e020346e94`, reviewed 2026-09-15, last successful freshness check 2026-09-17, assessment blob `df07d489a966ff9f16c1e010ba65219afded14c7`; Profile 0.2.1, Methodology 0.3.1. Current original [HEAD](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/README.md): `e1967811310595f1998c962cfe3a0d4a62fa3443` (observed 2026-11-19). Review age exceeds 30 days: a separate Index-owned reassessment is recommended before any new VSM classification.

| Function | Historical Index | Meaning / present research focus |
| --- | --- | --- |
| S1 · Operations | **A** | Agent chooses and performs its own tool work; no mandatory constructor target |
| S2 · Coordination | **—** | No established inter-S1 interference-regulation witness; not inferred from messaging |
| S3 · Current management | **A** | First-party top-level session orchestrator can change current session commitments; no forced A→C conversion |
| S3* · Complementary audit | **—** | No sufficiently independent audit established at the reviewed ref; current Adversary inspector merits fresh evidence, not an automatic changed grade |
| S4 · Future intelligence | **—** | No proven externally prospective adaptation/return loop in the historical record |
| S5 · Policy/identity | **—** | User/developer security policy and ultimate authority are not automatically agent-owned S5 |

**Boundary:** first-party supported Goose agent, tool-inspection and orchestrator modes, not arbitrary user MCP plugins, original project maintainers or a fictional new governance agent. License: Apache-2.0; [contributor rules](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/CONTRIBUTING.md) require an issue in **Ready** before a non-exempt PR and contributor review of AI-generated work.

## 2. Operator outcome and terminal decision

**Current need (verified):** make an Adversary reviewer BLOCK understandable to a human and to the agent without silently losing reviewer provenance. [Original issue #13271](https://github.com/aaif-goose/goose/issues/13271) documents an actual denied `curl | bash` tool invocation. The reviewer currently returns `InspectionAction::Deny`; this is a *binding* block.

**Decision: NO_GO now on a new OpenSiro S3*=C constructor or an approval-override feature.** The native Goose issue already owns the narrower user problem. In its 2026-11-12 comment the maintainer explicitly chose to keep BLOCK binding, expose the reason to users and agents, and discuss any override separately. [PR #13272](https://github.com/aaif-goose/goose/pull/13272) proposed `RequireApproval` but was **closed without merge**. Review identified a headless Auto-mode auto-approval path and potential loss of reason when EgressInspector precedes AdversaryInspector. Adding a second review architecture now would duplicate work and risk changing the intended security authority.

**P0:** proposed generic independent S3* reviewer constructor — **NOT ADMITTED**, no demonstrated extra operator outcome beyond the existing native work.  
**P1:** keep the source-native issue #13271 as the only tracked design route for binding BLOCK + visible reason; *no OpenSiro implementation or PR authorized*.  
**P2:** NONE; no independent second capability justified.

## 3. Native coverage vs actual gap

- **SHIPPED at current HEAD:** [AdversaryInspector](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/security/adversary_inspector.rs) with a model reviewer and `Deny` for BLOCK; [inspector-result routing](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/tool_inspection.rs); [service registration](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/agents/services.rs); first-party [tests](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/tests/adversary_inspector_tests.rs).
- **ISSUE_ONLY:** #13271 has maintainer-supported binding-block-with-visible-reason direction, but is not an accepted implementation.
- **CLOSED_UNMERGED:** #13272 cannot be counted as shipped or an active implementation candidate.
- **Residual need:** the visibility/attribution of a lawful block in interactive and headless modes; not evidence of a new independent developer-composable audit decision owner.

## 4. Minimum sufficient next action and stop gates

Use the original issue's **Accepted / design → Ready** workflow. Any later native patch must preserve non-overridable BLOCK, present its reviewer reason to the user, return a distinguishable rejection to the agent, respect inspector precedence, and prove that headless Auto mode cannot execute a blocked call. See [AI test/authority contract](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/constructor-sufficiency.md). Do not ship a generic C constructor, force an override, publish a new original issue, reopen #13272, or claim a new Index grade on the strength of this plan.

**Independent choices:** (a) resolve the native design in #13271 if maintainers later move it to Ready; (b) separately reassess current Goose evidence through Index/Skills; (c) evaluate a domain fork only under another explicit scope and rights decision. These are alternatives, not concurrent tasks.

**Cost hypothesis:** compare equal native vs VSM-informed solutions by implementation + review + tests + maintenance and acceptance quality. **NOT_MEASURED**, no cost savings established.

**Publications:** fork Issue and third-party original Issue/PR **NOT PUBLISHED**. This exact Human text is a proposed public fork Issue body only, pending *separate current-conversation owner approval*. Fork metadata is stored on the isolated `opensiro/meta` branch and starts at **PAUSE/DORMANT**; no RESUME or product work follows.
