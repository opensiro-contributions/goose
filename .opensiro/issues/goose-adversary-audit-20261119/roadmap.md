# Goose Capability Roadmap Receipt — 2026-11-19 (PLAN_ONLY)

## Identity and pins

- Original repository: aaif-goose/goose
- Original HEAD: e1967811310595f1998c962cfe3a0d4a62fa3443
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/go/goose.md
- Accepted assessment blob SHA: df07d489a966ff9f16c1e010ba65219afded14c7
- Accepted review ref: 50666ae0b9a51e260b52b7efbab2e4e020346e94
- Accepted reviewed at: 2026-09-15
- System in focus: First-party Goose agent runtime including supported tool inspection and orchestrator modes; original maintainers and external MCP projects excluded
- Latest successful accepted freshness check: 2026-09-17 (`d213a3b13545b4e85524a572ac695b2181728e3b`); 63 days before observation; recommend **separate Index reassessment**, not a grade change or automatic prerequisite.
- Index commit: 34e11ec4dd52e1ba3ee0111d8bca73f13918f54f; Profile 0.2.1; Methodology 0.3.1; historical vector **S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—**.
- Verified fork: https://github.com/opensiro-contributions/goose; matching parent aaif-goose/goose; pinned bootstrap default HEAD e1967811310595f1998c962cfe3a0d4a62fa3443.
- Human: https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/issue.md
- AI contract: https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/constructor-sufficiency.md

## Rights and authority

Apache-2.0; [Goose contribution guide](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/CONTRIBUTING.md) requires **Ready** source issue before non-exempt PR; AI output must be human-reviewed, and original maintainer retains design/acceptance. No independent CLA waiver or new implementation rights inferred. Fork `opensiro/meta` is initially **PAUSE/DORMANT**, without RESUME; metadata bootstrap only. Source review is permitted, but a public GitHub Issue (even on the fork) needs explicit current-conversation approval.

## Existing work / overlap

- Current first-party implementation: [Adversary inspector](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/security/adversary_inspector.rs) maps BLOCK to `Deny`; [tool inspection routing](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/tool_inspection.rs) enforces it; [service](https://github.com/aaif-goose/goose/blob/e1967811310595f1998c962cfe3a0d4a62fa3443/crates/goose/src/agents/services.rs) registers reviewer.
- [Original #13271](https://github.com/aaif-goose/goose/issues/13271) **OPEN / Accepted design**, actual BLOCK obscures reason. Maintainer comment 2026-11-12 explicitly prefers keeping BLOCK binding and making reviewer reason visible.
- [Original PR #13272](https://github.com/aaif-goose/goose/pull/13272) **CLOSED_UNMERGED**, proposed `RequireApproval`; review found headless auto-approval risk and reviewer-reason precedence bug.
- Original-native option already exists: improve visible binding refusal in #13271 once Ready. No separate duplicate issue, C constructor or original PR justified now.

## Function ownership

**Historical Index**: S1 A (agent operations); S2 — (no proven inter-S1 conflict regulation); S3 A (first-party whole-session orchestrator current control); S3* — (independent review not established at review ref); S4 — (no prospective adaptation loop); S5 — (configured user/parent ultimate policy, not agent-controlled identity). Current Adversary LLM reviewer is **SHIPPED** but whether it independently establishes current S3* demands new Index evidence; neither claim current A nor C. Decision owner for binding BLOCK: Goose configured inspector plus developer/user policy; denied request returns to agent, but reason attribution has the reported gap.

## Capability priority

**Decision: NO_GO** on a new standalone reusable S3*=C constructor or a universal adversary BLOCK→approval override. **Result: DECISION_READY.** P0 generic C proposal **NOT ADMITTED** (no incremental evidenced user outcome). P1 reuse original #13271 and maintainer's binding-block + visible-reason direction, *not an authorized OpenSiro implementation backlog*. P2 **NONE**. C sufficiency is **not established**: no new independently developer-composed reviewer, unique need, lawful new authority, feedback closure and end-to-end negative acceptance. Not a claim that all possible future C proposals lack value.

## Implementation options

**Preferred smallest native path (not authorized here):** once #13271 is Ready, provide explicit user-visible reviewer reason and agent-visible reviewer BLOCK while preserving `Deny`, precedence and headless safety. Proposed test cases: BLOCK in interactive/headless never executes; visible attributable reason; competing Egress ALLOW cannot erase Adversary BLOCK; ALLOW path unchanged; policy error behavior preserved. The alternative `RequireApproval` change in #13272 is not accepted and not safe to transplant. **No product code, tests or original PR performed.**

## Specification and domain alternatives

A new current-HEAD Index assessment may revisit historical S3* evidence without changing Upstream's grading authority. A separately scoped domain fork may test developer-composable complementary review only after an actual distinct task and rights; it is not the current recommendation. Source-native design in #13271 is the least costly plausible path pending measurement.

## Cost experiment

Paired outcomes: (A) native Goose binding-block visibility fix; (B) an additional VSM-informed S3* constructor solving *the same user task*. Measure engineering time, integration, first-party test time, review cycles, regression/maintenance burden and user-visible BLOCK quality. No paired implementation occurred. **Cost status: NOT_MEASURED**.

## Delivery and publication

- Result: PLAN_ONLY
- Decision: NO_GO
- Research disposition: DECISION_READY
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED
- Working fork issue: **READY_FOR_FORK_ISSUE_APPROVAL — NOT PUBLISHED**; exact title and body are in [issue.md](https://github.com/opensiro-contributions/goose/blob/opensiro/meta/.opensiro/issues/goose-adversary-audit-20261119/issue.md). No original Issue/PR, no fork Issue/PR published.
- No contribution record, product branch, code implementation, runtime test or new Index grade. Owner-control bootstrap PAUSE/DORMANT; no implied future autonomous work.
