# Goose Capability Roadmap — Wave 4 neutral independent rerun (2026-11-20)

> New source-first analysis under published Upstream v0.18.0. This supersedes the previous proposal disposition for this *same* case, while preserving the prior NO_GO in Git history. PLAN_ONLY, not implementation, accepted Index regrading, or maintainer product adoption.

## Identity and pins

- Original repository: aaif-goose/goose
- Original HEAD: c77f95b9c5c4242cd1cb83669523d2231da75352
- Observed at: 2026-11-20
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/8b6039a92b39e9ac9e02af8c9a99513d632c3684/assessments/go/goose.md
- Accepted assessment blob SHA: df07d489a966ff9f16c1e010ba65219afded14c7
- Accepted review ref: 50666ae0b9a51e260b52b7efbab2e4e020346e94
- Accepted reviewed at: 2026-09-15
- System in focus: First-party Goose CLI/desktop agent runtime and supported oi-kit state machine, built-in inspectors/hooks; no third-party plugins, repository contributor workflow, or maintainer decision rights as runtime components
- Index commit: 8b6039a92b39e9ac9e02af8c9a99513d632c3684
- Catalog: https://github.com/opensiro/vsm-harness-index/blob/8b6039a92b39e9ac9e02af8c9a99513d632c3684/data/catalog.psv, row goose (exact repository and review_ref match).
- Accepted Profile/Methodology: 0.2.1 / 0.3.1; reviewed 2026-09-15, last checked 2026-09-17. Freshness is not assumed.
- Source snapshot: https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/README.md and https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/AGENTS.md.
- Historical frozen prior case: https://github.com/opensiro-contributions/goose/blob/fabfcf43e1652aceefa6042f0b870ba36c512455/.opensiro/issues/goose-adversary-audit-20261119/roadmap.md (2026-11-19, NO_GO; compared only after first-pass decision was sealed at https://github.com/opensiro/upstream/issues/58#issuecomment-7042861025).
- Working fork: https://github.com/opensiro-contributions/goose; verified fork=true and parent aaif-goose/goose; metadata branch opensiro/meta.

## Rights and authority

Apache-2.0 license; first-party https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/CONTRIBUTING.md and https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/AGENTS.md require original Ready issue for non-exempt upstream code PR. These restrictions do not veto plan-only architectural evaluation but preclude unauthorized product work or original communication. Original maintainer owns product choice and original Issue/PR workflow. User/developer/legitimate parent owns audit policy and delegation; independent reviewer only receives bounded execution-verification rights; it cannot rewrite identity or policy. Fork .opensiro/state.json independently read ACTIVE / ALLOW on 2026-11-20; this authorizes fork metadata maintenance, **not** public fork Issue, original outreach or implementation. Check again before effects.

## Existing work / overlap

**Current source-first reconciliation (2026-11-20; Upstream v0.18.2)**

A source-first same-case check was sealed at [Upstream #58](https://github.com/opensiro/upstream/issues/58#issuecomment-7047329680) before the prior fork record was read. Current public original default HEAD ca949ba94c0d59679c7e7eeccfaa277076e5b9e9 (distinct from receipt historical Original HEAD c77f95b9c5c4242cd1cb83669523d2231da75352) was read at [crates/goose/src/agents/state_machine/session.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/state_machine/session.rs) and [crates/goose/src/agents/platform_extensions/summon.rs](https://github.com/aaif-goose/goose/blob/ca949ba94c0d59679c7e7eeccfaa277076e5b9e9/crates/goose/src/agents/platform_extensions/summon.rs); status of issue/PR overlap: https://github.com/aaif-goose/goose/issues/9708 (CLOSED issue about ground-truth completion); historical #13271 security visibility was a different concern. Original PR status must be checked again before any code change.

**Deep terminal-control falsifier:** Goose main advanced from the previous `ca949ba` source observation to [`36b2911`](https://github.com/aaif-goose/goose/commit/36b29113aff691e1a46a21a5c25900824caf9949) by one Ollama/provider-context-only commit; the Stop-hook code remains material. First-party [ops_stop_hook.rs](https://github.com/aaif-goose/goose/blob/36b29113aff691e1a46a21a5c25900824caf9949/crates/goose/src/agents/state_machine/ops_stop_hook.rs) has default denial cap 8 and returns a warning plus terminal yield when exceeded. Its [hooks_lifecycle.rs tests](https://github.com/aaif-goose/goose/blob/36b29113aff691e1a46a21a5c25900824caf9949/crates/goose/src/agents/state_machine/tests/hooks_lifecycle.rs) explicitly assert this bypass. Therefore bare configurable Stop Deny is **not** fail-closed S3*: the optional independent result auditor needs a durable `UNVERIFIED` terminal disposition/owner escalation when the cap or evidence fails, rather than silently treating completion as PASS. Original [#9708](https://github.com/aaif-goose/goose/issues/9708) remains a CLOSED request, not evidence of shipped audited completion. Acceptance NOT_RUN; no first-party change or Index regrade.

The scoped new-source first pass asks: A subagent's separate context and a pre-tool security filter are not proof of materially independent post-operation evidence review. Existing Stop denial may be capped; hook-only control cannot be presumed fail-closed. **No newly demonstrated changed C ownership or Index regrade** is asserted. Previous canonical proposal remains **GO / NEEDS_EVIDENCE**, `S3*=— -> S3*=C`, with native tests `NOT_RUN`, cost `NOT_MEASURED`. This is a Human/AI template-compliance repair and bounded current-source note, **not a duplicate independent original research case, code implementation, or public outreach**. The old receipt/head and first-attempt lineage remain readable in Git history and in the existing fields above.


- Track A SHIPPED: https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/security/adversary_inspector.rs independently invokes a reviewer *request* but uses the session's provider/model, conversation and proposed tool call; BLOCK maps to Deny; errors fail open. https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/tool_inspection.rs maps Deny/RequireApproval to tool outcomes; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine/tool_approval.rs applies permission decisions. https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/services.rs supplies first-party inspectors. This is a security pre-tool filter, not proven complementary audit of actual completed work.
- Track A SHIPPED: https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/hooks/mod.rs supports PreToolUse/PostToolUse/Stop command hooks; https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine/ops_stop_hook.rs converts Stop denial into model rework, but **overrides denial after the configured stop-block cap**. The generic hook is a reuse seam, not on its own a separately owned, evidence-grounded audit and verified-completion return path. New https://github.com/aaif-goose/goose/blob/c77f95b9c5c4242cd1cb83669523d2231da75352/crates/goose/src/agents/state_machine_builder.rs assembles oi-kit operations; older agent.rs examples are stale.
- Original https://github.com/aaif-goose/goose/issues/13271 OPEN: binding adversary BLOCK reason/visibility and mode interaction. PR https://github.com/aaif-goose/goose/pull/13272 CLOSED UNMERGED; RequireApproval is not shipped. No claim an existing fix is final or temporary.
- Original https://github.com/aaif-goose/goose/issues/9708 CLOSED: reported unsupported completion claims and external evidence check idea. Related https://github.com/aaif-goose/goose/pull/10361 CLOSED UNMERGED; proposed tool_trace/advisory hook changes are not present in pinned current HookContext/Stop. Original https://github.com/aaif-goose/goose/issues/13397 OPEN and https://github.com/aaif-goose/goose/pull/13405 OPEN concern security finding decision telemetry, not first-party audit ownership. Exact status read, not inferred merge.
- Track A bounded alternative: ordinary tool-security explanation repair, generic hook script, and optional off-process verifier can help individual tasks, but none is evidence of an installed/validated first-party S3* closure with independently observed task-completion proof.

## Function ownership

- Accepted VSM vector: S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—
- S1 disposition: Historical A; current oi-kit machine, Goose tool execution and session results are S1 operation, not a new S1=C target.
- S2 disposition: Historical —; current subagent decomposition and concurrency limit do not alone identify a specific inter-S1 interference with coordination feedback. No S2 priority asserted.
- S3 disposition: Historical A from older first-party orchestrator mode; current platform-extension registry no longer lists that old extension, so do not silently project the same current grade. Requires Index-owned reassessment, no forced downgrade.
- S3* disposition: Historical —; opt-in separate audit of actual execution outcomes has a source-native first-party composition path proposed below, not current shipped capability.
- S4 disposition: Historical —; roam/providers/context/session mechanisms do not by themselves establish a distinct prospective outside-and-then intelligence loop and return.
- S5 disposition: Historical —; user/developer approval/security rules and original maintainer decisions are not autonomous legitimate identity/ultimate policy closure at the runtime boundary.
- Parent and recursion boundary: subagents are operational delegation under user-configured rights, not their own legitimate S5. Proposed reviewer must not choose the policy or expand authority.

## Capability priority

- Receipt contract: proposal-gate
- Repository-wide source map: oi-kit agent/state machine + tool approval + original Goose security inspectors + hooks + CLI/ACP/desktop + recipe/scheduler + subagent runtime + docs/tests/CI/contributor governance surveyed at pinned HEAD
- Priority rationale: Unique complementary S3* decision right: independent post-operation evidence audit, not pre-call danger prediction or a generic new safety prompt; source-native operations and stop-hook/rework paths make a minimal bounded adapter conceivable
- Accepted VSM vector: S1=A · S2=— · S3=A · S3*=— · S4=— · S5=—
- Target transition: S3*=— -> S3*=C
- P1 dependencies: verified tool/result evidence provenance, isolated reviewer identity and least-privilege evidence access, cap/resume and durable unverified-result semantics; original-native tests and legitimate policy-owner approval needed prior to implementation
- P2 optional: broader cross-session/fleet evidence auditing only after separate source-bound demand and authority analysis
- Proposed C construction: Opt-in first-party evidence adapter + developer-selected independent evidence auditor + bounded verification decision and return-to-S1 via rework or explicitly unverified handoff; see AI contract
- C sufficiency falsifier: Equivalent shipped first-party independent actual-outcome audit with autonomous reviewer ownership and binding operational feedback, or inability to persist/reify unverified outcome when stop-cap overrides a deny
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: paired native tests with real tool facts vs narrated claims; independent reviewer removal, stale/corrupt evidence, no-tool falsely claimed tests, partial completion, stop cap, resume, negative permission and parent authority cases
- Validation state: NOT_RUN
- Proposal falsifier: If independent audit cannot read trustworthy execution reality or its negative verdict cannot change subsequent completion/operation without bypass by caps/permissions, downgrade to NO_GO; if truly equivalent first-party C exists, this particular additive proposal is redundant
- Proposal confidence: moderate structural, not empirical; current product desirability unknown and left entirely to original maintainers
- P0: the single target S3*=— -> S3*=C above. Do not claim an already achieved C grade.
- P1: source provenance, durable bounded closure and first-party tests; no present implementation permission.
- P2: NONE in this case.

## Parallel contribution-on-top review

- Evaluation object: Independent evidence-grounded post-operation S3* completion audit constructor, not adversary BLOCK→approval override, nor the existing reported security visibility bug
- Existing-work overlap: Native AdversaryInspector/Deny and configurable hooks handle pre-tool security/commands; #13271 / #13272 address narrower visibility/authority and cannot be used as a permanent maintainer-intent or value veto
- Our on-top contribution: Minimal opt-in first-party oi-kit Goose operation adapter to bind external verified facts to separately owned audit decision, bounded rework and explicit unverified terminal/human escalation
- Incremental benefit: Hypothetically distinguish unsupported success claims and make an independent source-of-reality finding change completion status, which pre-tool reviewer and generic denial alone do not prove; no quantified effect claimed
- Decision scope: Architectural constructibility GO only, first-party module/ported seams named as candidate design; owner retains original product decision and published Issue/PR rights

## Implementation options

1. Track B minimum: capture stable per-turn tool-call IDs, exit/results and selected read-only postcondition probes as source-of-reality facts in the first-party runtime; label any missing facts UNKNOWN, never silently PASS. Keep audit provider/credentials/decision actor separate from primary executor (two calls to the same session model alone do not establish independence).
2. Developer opt-in binds an auditor with scoped rights to review immutable evidence and answer PASS / REWORK / ESCALATE_UNVERIFIED with attributable evidence IDs. Production action is still owned by S1; auditor cannot invoke unrestricted tools or rewrite S5 policy.
3. Integrate at oi-kit operation/Goose state-machine completion and approval seam: on REWORK inject source-backed correction for the next S1 turn; on cap/unverifiable or exhausted retries return durable UNVERIFIED requiring legitimate user/parent decision, rather than label the turn verified. StopHookOperation's current cap override makes **raw hook-only** implementation insufficient without that specific closure fix.
4. Native smaller alternatives: user-authored Stop hook with filesystem/git probe, ordinary #13271 visible Deny reason, #9708 proposed stop gate; try these as baseline in validation, not a veto of distinct C ownership. No default-on engine or unconditional security architecture required.

## Specification and domain alternatives

Profile/Skills own S3* semantic/assessment method. The current Index included historical vector is frozen, and current Goose architecture differs materially (no old orchestrator in the pinned registry); a separate Index fresh assessment is suitable but is **not** the implementation test or automatic authorization. A domain fork or local Goosed extension may trial the hypothesis under separate rights; no new meta-control plane, mandatory six-function construction, or maintainers' product intent asserted.

## Cost experiment

Paired A = current first-party security + hook script baseline; B = opt-in independent evidence reviewer and closure adapter on the same replayed original-native tasks. Measure unsupported-completion catch rate, verified output, false blocks, bounded rework turns, latency, API/CPU cost, time to maintain evidence probes and role boundaries. Benefits and implementation costs unmeasured, expected positive delta hypothetical only.

## Delivery and publication

- Result: PLAN_ONLY
- Decision: GO
- Research disposition: NEEDS_EVIDENCE
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED
- Canonical Human: [issue.md](issue.md); separately readable AI: [constructor-sufficiency.md](constructor-sufficiency.md); case index: [README.md](README.md).
- Wave 4 new source-first verdict was recorded before the historical fork-case was opened: https://github.com/opensiro/upstream/issues/58#issuecomment-7042861025.
- Historical comparison (post-verdict): previous proposal-stage NO_GO / DECISION_READY rejected an additional reviewer **because there was no incremental verified outcome and because a narrower native issue/maintainer preferred design existed**. Current v0.18.0 assessment-neutral rule does not treat missing measurement or presumed final maintainer intent as a standalone veto. Therefore scoped decision changes **NO_GO → GO**, separate research **DECISION_READY → NEEDS_EVIDENCE**. Preserve prior report at frozen commit and do not claim demonstrated benefit.
- Fork metadata record only; NO product-code changes, native tests NOT_RUN, cost NOT_MEASURED, no Index regrade, no third-party/fork GitHub Issue or PR and no original communication. Public fork Issue full draft in issue.md is READY_FOR_FORK_ISSUE_APPROVAL — NOT PUBLISHED, subject to exact new approval.
