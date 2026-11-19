# Goose — AI/developer source-native S3* sufficiency and blocking-review contract

**PLAN_ONLY / DECISION_READY — Decision: NO_GO.** This is the technical companion to [the Human roadmap](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/issue.md), not a product change or new assessment. **Historical Index vector: S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—**; https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/go/goose.md, reviewed 2026-09-15, review_ref `50666ae0b9a51e260b52b7efbab2e4e020346e94`, assessment blob `df07d489a966ff9f16c1e010ba65219afded14c7`; current Goose `e1967811310595f1998c962cfe3a0d4a62fa3443`, observed 2026-11-19. **Priorities identical to Human:** P0 generic S3* constructor **NOT ADMITTED**; P1 original issue #13271 only, pending maintainer design; P2 **NONE**.

## Functional boundary (S2 / S3 / S3* / S4 / S5)

- **S2:** inter-agent conflict regulation is not proven by communication or the present security inspector.
- **S3 (historical A):** orchestrator controls current top-level sessions; not the owner of a BLOCK override.
- **S3* (historical —):** complementary, sufficiently independent operational review is not established at old review_ref. Current [AdversaryInspector](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/security/adversary_inspector.rs) calls an LLM reviewer, but whether its access, rights and return path qualify as separate S3* requires new formal Index evidence. Neither a model call nor an extra test alone establishes C.
- **S4 (historical —):** no externally prospective adaptation loop is added by tool inspection.
- **S5 (historical —):** binding denial vs user override is a legitimate owner-policy choice. Do not invent automatic agent S5 legitimacy from configured permissions.

## 1. Boundary, stimulus, current decision owner and counterfactual

**Boundary:** current first-party Goose runtime and built-in inspection pipeline, configuration-supported modes and headless CLI. Exclude unrelated external MCP services and original maintainers as runtime agents. **Trigger:** model attempts a potentially harmful tool call such as the real `curl | bash` case in [#13271](https://github.com/aaif-goose/goose/issues/13271). **Current decision:** the separate LLM-based Adversary inspector returns BLOCK or ALLOW; [tool inspection](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/tool_inspection.rs) enforces `InspectionAction::Deny`. **Feedback gap:** in reported cases reviewer reasons are not exposed with sufficiently distinct provenance to agent and user.

The source-native counterfactual is already simple: preserve `Deny` and improve surfacing/attribution; no developer-provided extra reviewer constructor is necessary to meet this known user task. The maintainer's [2026-11-12 choice](https://github.com/aaif-goose/goose/issues/13271) is binding reviewer BLOCK + visible reason, with user overrides a separate future policy discussion. This rejects treating a configurable approval dialog as equivalent to an independent audit.

## 2. Current shipped paths, issue and competing PR

**SHIPPED:** [adversary_inspector.rs](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/security/adversary_inspector.rs) maps BLOCK to `Deny`; [tool_inspection.rs](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/tool_inspection.rs) applies and reports inspection actions; [agents/services.rs](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/agents/services.rs) registers the inspector. [Unit/integration tests](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/tests/adversary_inspector_tests.rs) exist but are not here claimed to meet the missing visibility acceptance.

**ISSUE_ONLY:** [#13271](https://github.com/aaif-goose/goose/issues/13271) remains open in design. **CLOSED_UNMERGED:** [#13272](https://github.com/aaif-goose/goose/pull/13272) proposed `RequireApproval`; first-party review flagged (1) Ready gate violation, (2) competing EgressInspector result hiding reviewer reason, (3) headless Auto effectively allowing a formerly blocked command. Original maintainers have not adopted that implementation. No new open adversary PR was identified in bounded search on 2026-11-19.

## 3. No qualified S3*=C constructor ports at this time

A candidate reusable complementary review constructor would need *all* of: a distinct, developer-composed autonomous reviewer with demonstrably independent operational evidence; a scoped first-party registration and state/input port; legitimate configurable rights that do not silently waive binding BLOCK; a reviewer choice protocol and durable result attribution; enforcement into the actual tool path; feedback to human/agent and subsequent operations; supported shipped mode and negative tests. **These are requirements for a future hypothesis, not shipped or approved interface names.**

**Why not sufficient now:** an LLM inspector exists already, the accepted Index is stale, no separate user/operator task requiring another reviewer-composition capability was verified, and the maintainer has chosen the simpler native design. Do not implement an abstract `AuditController`, new runtime actor, or grades as substitute evidence. P0 remains **NOT ADMITTED**; P1 is the existing original issue route, P2 **NONE**.

## 4. Native acceptance and falsification — conditional on original design reaching Ready

| Case | Reproducible proposed behavior | Rejection condition |
| --- | --- | --- |
| AC-01 binding BLOCK | Stub reviewer returns BLOCK for sensitive tool request; tool does not execute in interactive or headless modes | Any `AllowOnce` fallback executes the request |
| AC-02 visible reason | User receives reviewer reason with distinct reviewer attribution; agent observes an explicit blocked result | Silent or generic human-decline text |
| AC-03 inspector precedence | Egress ALLOW and Adversary BLOCK both apply; BLOCK and reason survive combination | First matching ALLOW hides security reason |
| AC-04 positive control | Reviewer ALLOW, permitted request proceeds under ordinary permission rules | Reviewer changes unrelated permission semantics |
| AC-05 policy boundaries | Reviewer error behavior stays at maintainer-agreed policy; downstream `NeverAllow` is never weakened | Fail-open/fail-closed silently changed |
| AC-06 constructor falsification | With no developer-composed S3* actor installed, do not claim C solely from generic tool hooks | Classification promoted without decision actor/feedback witness |

**Commands once a patch is authorized:** use repository-native `cargo test` for targeted inspector/permission tests, `cargo check`, `cargo fmt` and `cargo clippy --all-targets -- -D warnings` as applicable. **No tests executed; no patch produced; no test pass asserted.**

## 5. Independent choices, rights and future unlock

**Path A (preferred):** follow original Goose [CONTRIBUTING.md](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/CONTRIBUTING.md): issue moves Accepted/design → Ready under maintainer decision; implementation in same source under a later separate Upgrade/publication request. **Path B:** separate Index-owned current-HEAD reassessment (old review 2026-09-15, last successful check 2026-09-17); no grade adjustment here. **Path C:** experimental domain fork only after independently specified purpose and rights. No P2 independent constructor justified.

**Authority:** Original maintainers own issue/PR design and acceptance; user/operator owns ultimate allowed policy; review model cannot grant itself user override. Public fork Issue needs exact consent; no consent granted; working fork metadata begins PAUSE/DORMANT. **Cost status NOT_MEASURED.** Decision **NO_GO** on speculative constructor and approval override; do not treat this as a rejection of the narrower source-native visibility repair.
