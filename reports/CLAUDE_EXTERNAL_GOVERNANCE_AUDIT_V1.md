# Claude External Governance Audit — SAD-MORON-FRAMEWORK

**Audit Reference:** CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1  
**Audit Date:** 2026-05-26  
**Auditor:** Claude (Sonnet 4.6) — external automated documentation review  
**Audit Type:** External governance architecture review — documentation only  
**Artifact Status:** Append-only governance evidence  

---

## Scope and Methodology

**Repository under review:** `SAD-MORON/sad-moron-framework` (local authoritative copy)  
**GitHub remote status:** Repository found empty at audit time. All findings are based on the local repository, which constitutes the authoritative document set. The remote/local divergence is noted as a finding.

**Documents reviewed:**

- `README.md`
- `docs/architecture-layers.md`
- `docs/janus-adaptation.md`
- `docs/normative-framework.md`
- `docs/scope-and-boundaries.md`
- `protocols/audit-reconstruction-protocol.md`
- `protocols/connector-compliance-protocol.md`
- `protocols/declared-sources-protocol.md`
- `protocols/evidence-classification-protocol.md`
- `protocols/expected-events-protocol.md`
- `protocols/framework-contracts.md`
- `protocols/infrastructure-growth-protocol.md`
- `protocols/institutional-governance-protocol.md`
- `protocols/normative-scope-protocol.md`
- `protocols/omission-detection-protocol.md`
- `protocols/pipeline-planner-protocol.md`
- `protocols/repository-separation-protocol.md`
- `protocols/temporal-boundaries-protocol.md`
- `reports/SAD_MORON_JANUS_ADAPTATION_REVIEW_V1.md`

**Audit constraints applied:**

- Documentation review only
- No runtime execution review
- No security pentest
- No implementation analysis
- No modifications to existing repository structure
- No runtime code created
- No implementation proposals generated
- No CI/CD, APIs, or connectors referenced

---

## 1. Boundary Consistency

**Assessment: STRONG**

The repository maintains an exceptional and consistent documentation-only boundary across all 19 documents examined. The following boundary mechanisms were observed to be functioning:

- Every protocol document includes a dedicated `Boundary` section explicitly stating what the protocol does NOT govern.
- The README, `framework-contracts.md`, and `normative-scope-protocol.md` independently reinforce the governance-only boundary from different structural positions.
- Out-of-scope items are enumerated rather than implied: runtime code, executable connectors, Apps Script, API implementation, generalized AI tooling, and infrastructure orchestration are all named and excluded.
- The `docs/scope-and-boundaries.md` maintains a clear two-column separation (in-scope / out-of-scope) with distinct categories for declared sources, administrative events, temporal periods, and growth.

**Finding B-1 — Boundary enforcement has no review mechanism.**  
The declared boundaries are well-stated but there is no protocol for reviewing whether a proposed addition violates a boundary. The `infrastructure-growth-protocol.md` provides growth tests (five questions to answer before adding a new structural area), but there is no designated review authority or mandatory review step before growth proceeds. This creates an honor-system boundary that depends entirely on the good judgment of future contributors.

**Finding B-2 — GitHub remote is empty.**  
The public repository (https://github.com/SAD-MORON/sad-moron-framework) contains no files. The authoritative governance content exists only locally. This is an unresolved state: the declared governance layer has no published, versioned, external anchor. This is not a boundary violation, but it prevents the framework from functioning as a genuine external reference for any future operational or audit repositories that may cite it.

---

## 2. Layer Separation

**Assessment: STRONG**

The four-layer model defined in `docs/architecture-layers.md` is clear, non-overlapping, and correctly scoped:

- Layer 1 (Governance / Framework): `sad-moron-framework` — currently instantiated
- Layer 2 (Implementation / Adapters): future repos `sad-moron-connectors`, `sad-moron-runtime`, `sad-moron-appscript` — named but not created
- Layer 3 (Operations / Institutional Use): real administrative workflows — not yet instantiated
- Layer 4 (Audit / Reconstruction): future repo `sad-moron-audit` — named but not created

Four layer rules are stated and internally consistent: governance precedence, no downward redefinition, separation of implementation and governance, audit independence.

**Finding L-1 — No canonical governance core document exists.**  
The Janus Adaptation Review (the framework's primary conceptual source) recommended a `core/SAD_MORON_GOVERNANCE_CORE_V1.md` as the anchoring artifact for Layer 1. This canonical core has not been created. The normative kernel is currently distributed across five separate documents (`normative-framework.md`, `scope-and-boundaries.md`, `framework-contracts.md`, `architecture-layers.md`, `janus-adaptation.md`) without a single authoritative document that a future Layer 2 or Layer 4 repository could cite as the definitive governance reference. This creates fragmentation risk as the framework grows.

**Finding L-2 — Structural deviation from Janus Review recommendation is undocumented.**  
The Janus Adaptation Review explicitly recommended a specific repository structure including `core/`, `rfcs/`, and `examples/` directories. The actual implementation instead uses `docs/`, `protocols/`, and `reports/`. This is a legitimate design choice, but the deviation from the recommended structure is nowhere documented or justified within the repository. Under the framework's own normative discipline (which requires changes to be explicit and documented), this represents a gap in the governance evidence trail.

---

## 3. Protocol Coherence

**Assessment: VERY STRONG**

All 11 protocol documents follow an identical structural convention: Purpose → Boundary → Responsibilities → Exclusions → Enforcement Rules → Summary. This structural consistency enables rapid coherence checking and is itself a governance discipline.

**Cross-protocol dependency map (inferred from content):**

```
declared-sources-protocol
    ← referenced by: connector-compliance, omission-detection, evidence-classification

evidence-classification-protocol
    ← referenced by: audit-reconstruction, omission-detection

expected-events-protocol
    ← referenced by: omission-detection, pipeline-planner

temporal-boundaries-protocol
    ← referenced by: omission-detection, evidence-classification

omission-detection-protocol
    ← references: declared-sources, expected-events, temporal-boundaries, evidence-classification

pipeline-planner-protocol
    ← references: declared-sources, expected-events, omission-detection, audit-reconstruction

framework-contracts.md (meta-protocol)
    ← governs: all other protocols
```

No circular dependencies were detected. Protocol boundaries are mutually consistent: each protocol defers to others where appropriate rather than duplicating enforcement.

**Finding P-1 — `framework-contracts.md` has a mild self-referential quality.**  
This document describes what the framework layer is responsible for, including that it must define its own normative boundaries. This is architecturally correct but creates a situation where the framework governs itself without an external review step. This is acceptable at the current scaffold stage but should be considered when a formal governance review process is established.

**Finding P-2 — No change control protocol.**  
The `normative-framework.md` states that changes to the normative framework "should be explicit, documented, reviewable, and compatible with declared SAD Moron scope." The Janus Adaptation Review explicitly recommended a change-control protocol as one of the five recommended protocol families. This protocol was not implemented. Currently, normative updates have no procedural gate beyond the commit message.

---

## 4. Governance Integrity

**Assessment: STRONG**

Governance integrity is maintained through several well-constructed mechanisms:

- The normative-operational distinction is consistently enforced: normative documents define institutional meaning; operational documents define application of that meaning.
- `normative-framework.md` explicitly states that where an operational document appears to change institutional meaning, the normative layer takes precedence.
- Human accountability is preserved in `institutional-governance-protocol.md` with four enforcement rules that collectively prevent software outputs from substituting for authorized human review.
- The evidence model (E+ / E-) explicitly separates detection from verdict across two documents (`evidence-classification-protocol.md` and `omission-detection-protocol.md`).
- Append-only orientation is declared in `audit-reconstruction-protocol.md` and referenced in `janus-adaptation.md`.

**Finding G-1 — No registry of normative authority.**  
The `normative-framework.md` states that "normative intent begins in the documents that explicitly define scope and boundaries" but does not enumerate which documents hold normative authority and which are explanatory. A future reviewer cannot determine from repository metadata alone which of the 19 documents are normative vs. non-normative. This creates an interpretive ambiguity that should be resolved before operational repositories cite this framework.

**Finding G-2 — No version history for protocol documents.**  
Protocol documents carry no version identifiers or date stamps. Given that this framework declares append-only institutional history as a core principle (adapted from Janus), the framework's own documents do not yet implement that principle for their own revision history. Git commit history partially addresses this, but only if the GitHub remote is populated and the commit history is maintained.

---

## 5. Institutional Viability

**Assessment: ADEQUATE with significant pending gap**

The framework is correctly bounded to the SAD Morón institutional context, referenced to Provincia de Buenos Aires educational regulations in `normative-scope-protocol.md`. The administrative event taxonomy (receipt, registration, assignment, authorization, publication, notification, archival closure) maps authentically to real municipal administrative processes and reflects institutional knowledge rather than generic governance templates.

The Janus adaptation is clean: the framework does not import inappropriate AI governance machinery, development workflow tools, or generic observability layers that would be irrelevant to a municipal educational administration context.

**Finding I-1 — CRITICAL: No actual declared source catalog.**  
The `declared-sources-protocol.md` correctly defines how sources become declared (the governance mechanism), but the framework contains no actual declared source catalog — no concrete enumeration of specific SAD Morón institutional sources with their institutional origin, document class, intended governance use, temporal relevance, and known limitations, as required by the protocol itself. The Janus Adaptation Review identified the declared source catalog as "the most important institutional specialization." Without it, the omission detection protocol cannot function: omission review requires declared sources, and none have been formally declared. This is the most operationally significant gap in the current framework state.

**Finding I-2 — Administrative event taxonomy is illustrative, not normative.**  
The event families listed in `scope-and-boundaries.md` and `expected-events-protocol.md` are explicitly labeled "intentionally narrow at the scaffold stage" and "illustrative." No document formally promotes any event definition to normative status. An operational repository that needs to cite the expected event for a given administrative process would find no authoritative definition to reference.

---

## 6. Janus Adaptation Quality

**Assessment: EXCELLENT**

The framework demonstrates a disciplined and selective adaptation of Janus concepts. Every concept imported from Janus is appropriate to the SAD Morón institutional context, and every Janus element excluded was correctly identified as inappropriate.

**Adapted correctly:**
- E+/E- evidence distinction — implemented across two coherent protocol documents
- Append-only institutional history — declared as a governance principle
- Deterministic reconstruction — defined in `audit-reconstruction-protocol.md` with clear reconstruction requirements
- Omission detection under declared scope — five required inputs, five review rules, clear non-goals section
- Human accountability boundaries — four enforcement rules in `institutional-governance-protocol.md`
- Clean implementation rather than fork — the framework is genuinely independent of Janus code

**Excluded correctly:**
- Demo runtimes, watcher/bridge patterns, SDK assumptions, execution pipelines, generic agent tooling, experimental modules, frontend product layer protocols, developer tooling layers — none of these appear in the repository

**Finding J-1 — Recommended `rfcs/` directory not instantiated.**  
The Janus Adaptation Review recommended an `rfcs/` directory for formal governance decisions. No RFC structure exists. This is a controllable gap but means formal architectural decisions — including the choice to use `protocols/` instead of `protocol/` and `docs/` instead of `core/` — lack a traceable decision record. An RFC for governance decisions before operational repos are created would strengthen the adaptation evidence.

---

## Cross-Cutting Review

### Omission Detection

**STRONG.** The `omission-detection-protocol.md` is one of the most complete documents in the repository. It correctly defines five required inputs, models E+/E- with bounded scope requirements, distinguishes detection from decision, and includes a reconstruction rule. The "no timeless omission" principle (temporal-boundaries-protocol.md Rule 4) correctly prevents unbounded absence claims.

**Gap:** The protocol cannot currently be applied because no declared source catalog and no formally normative event definitions exist (see Findings I-1 and I-2).

### Evidence Classification

**STRONG.** E+ and E- are consistently defined across `evidence-classification-protocol.md` and `omission-detection-protocol.md`. The separation of evidence from verdict is maintained in both documents. Reconstruction readiness is stated as a Rule 4 requirement in the evidence classification protocol.

### Repository Separation

**STRONG.** The `repository-separation-protocol.md` provides clear and enforceable rules for all five repository types. The five rules map cleanly to each repository role. The actual repository structure (framework only, future repos named but not created) correctly implements the intended separation.

### Pipeline / Planner

**STRONG.** The `pipeline-planner-protocol.md` correctly defines the seven-stage governance sequence as a conceptual planner model rather than an implementation instruction. Rule 3 ("Ingestion does not define meaning") is particularly important and correctly stated. The pipeline is reinforced in `docs/architecture-layers.md` with a consistent representation. Both documents avoid collapsing the pipeline into a single repository.

### Infrastructure Growth

**STRONG.** The `infrastructure-growth-protocol.md` is sophisticated and operationally useful. The five growth-test questions, restricted-growth list, safe-growth list, and four boundary-preservation rules collectively create a strong gate against scope creep. Rule 2 ("No architecture copy-forward") directly addresses the risk of importing Janus structural complexity unnecessarily.

### Declared Sources

**CRITICAL GAP.** The declared-sources-protocol.md is a well-formed governance mechanism document but the catalog it governs has not been created. Every evidence-facing protocol in the framework depends on declared sources as the entry condition for trustworthy review.

### Temporal Boundaries

**STRONG.** The `temporal-boundaries-protocol.md` correctly prevents timeless omission claims through four enforcement rules. The "Defined period required" and "No timeless omission" rules are clear and unambiguous.

### Normative Scope

**STRONG.** The `normative-scope-protocol.md` grounds the framework in Provincia de Buenos Aires educational regulations and explicitly excludes "undefined institutional domains outside SAD scope" and "generic platform growth disconnected from educational administration." This is the correct institutional anchor.

---

## Strengths

1. **Protocol structural consistency** — All 11 protocol documents follow the same format, enabling rapid coherence review and demonstrating disciplined documentation governance.

2. **Boundary discipline** — Every document explicitly states what it does not govern, creating a strong negative-boundary culture that is rare and valuable.

3. **Clean Janus adaptation** — The framework took exactly what it needed from Janus and no more. No Janus runtime complexity, no agent tooling, no development workflow machinery was imported.

4. **E+/E- coherence** — The evidence model is consistently defined, properly constrained, and correctly separated from institutional verdict across multiple documents.

5. **Human accountability preservation** — The institutional governance protocol contains multiple enforceable rules ensuring that software outputs cannot substitute for authorized human review.

6. **Layer model clarity** — The four-layer architecture and the five-rule repository separation protocol create a clear governance topology for future repository creation.

7. **Infrastructure growth controls** — The growth-test questions and restricted-area lists in `infrastructure-growth-protocol.md` provide effective gates against scope drift.

8. **Non-goals discipline** — The README includes a substantial non-goals section that is unusual and valuable for a governance framework at scaffold stage.

9. **Pipeline governance interpretation** — The pipeline planner correctly frames a seven-stage governance sequence as a conceptual governance flow, not as an implementation mandate.

10. **Append-only orientation** — The principle is declared consistently and positioned correctly as a governance discipline rather than a technical requirement.

---

## Inconsistencies

**IC-1 — Undocumented structural deviation from Janus Review recommendation.**  
The Janus Adaptation Review recommended `core/`, `protocol/`, `rfcs/`, and `examples/` directories. The implementation uses `docs/`, `protocols/`, and `reports/` without documenting this deviation. Under the framework's own normative rule that changes must be "explicit, documented, reviewable," this represents a consistency gap.

**IC-2 — No canonical governance core document despite being recommended.**  
The Janus Review recommended `core/SAD_MORON_GOVERNANCE_CORE_V1.md` as the anchor for Layer 1. This artifact was not created. The normative kernel is fragmented across five documents without a single authoritative entry point.

**IC-3 — Change control protocol absent despite being recommended.**  
The Janus Review listed "change control protocol for governance definitions" as one of five recommended protocol families. The `normative-framework.md` requires that normative changes be documented, but no protocol governs how that documentation obligation is fulfilled.

**IC-4 — GitHub remote does not match local repository state.**  
The public GitHub repository is empty while the local repository contains 19 governance documents. The framework cannot serve as an external governance anchor until this divergence is resolved.

---

## Ambiguity Risks

**AR-1 — Normative authority is distributed without enumeration.**  
No document states which of the 19 documents are normative and which are explanatory. A future operational repository cannot determine from the repository alone which documents bind it.

**AR-2 — "Scaffold stage" is temporally undefined.**  
Multiple documents describe the current state as a "base scaffold" or note that normative intent will develop. The end condition for the scaffold stage is not defined. Without a stated transition condition, the scaffold stage could persist indefinitely, and decisions about what the framework permits could remain ambiguous.

**AR-3 — Boundary enforcement authority is unnamed.**  
The `infrastructure-growth-protocol.md` defines who must answer growth-test questions before adding new structural areas, but does not define who evaluates the answers or has authority to reject a proposed growth. This is an honor-system control.

**AR-4 — "Framework contract" vs. "protocol" distinction is not fully resolved.**  
`framework-contracts.md` is a meta-protocol that describes what the framework layer does. Its relationship to the 10 other protocols — whether it governs them, supplements them, or duplicates them — is not formally defined. A future reader could treat it as redundant with `normative-framework.md`.

---

## Over-Expansion Risks

**OE-1 — Connector compliance protocol creates implicit pressure for early connector creation.**  
The `connector-compliance-protocol.md` governs future connector repositories in significant detail. This is appropriate governance forward-planning. However, the level of specificity (four enforcement rules for connector behavior) could be misread as authorization to begin connector work before the framework is stable. The protocol should be understood as a constraint document for future connectors, not a permission for current connector development.

**OE-2 — Pipeline planner's six-stage model could be misread as an implementation roadmap.**  
The seven-stage sequence in `pipeline-planner-protocol.md` is explicitly labeled as "conceptual sequencing only" but its resemblance to an implementation pipeline is strong. A future contributor unfamiliar with the governance-only intent of this repository could interpret it as an instruction to begin building runtime ingestion, normalization, and validation systems within this repository.

**OE-3 — Infrastructure growth protocol has no mandatory review gate.**  
The five growth-test questions in `infrastructure-growth-protocol.md` are well-designed but purely advisory. There is no procedural requirement that anyone other than the contributor answers them before a structural change is made.

---

## Protocol Conflicts

No direct conflicts were detected between protocols. Protocol boundaries are mutually consistent and complementary.

**Minor tension — PT-1:** `normative-scope-protocol.md` excludes "generic platform growth disconnected from educational administration," while `docs/architecture-layers.md` references generic layer names (`sad-moron-connectors`, `sad-moron-runtime`, `sad-moron-appscript`) that could be read as platform infrastructure. This tension is resolved by context: the architecture document explicitly subordinates those future layers to the governance framework and provides them as examples of permitted future repo names, not as authorized development work.

---

## Governance Integrity Verdict

**VERDICT: GOVERNANCE INTEGRITY PRESERVED — WITH MATERIAL GAPS**

The framework successfully maintains a bounded governance-only architecture inspired by Janus Governance principles while remaining institutionally scoped to SAD Morón. The core governance concepts are correctly adapted, the boundary disciplines are well-stated, the layer model is sound, and the protocol set is internally coherent.

The framework does not violate its own declared boundaries. It does not contain runtime code, executable connectors, implementation proposals, API specifications, or agent workflows.

However, the framework has not yet completed its own minimum viable governance surface. The three most significant gaps are:

1. No declared source catalog (the entry condition for all evidence-based review)
2. No canonical governance core document (the anchor for Layer 1 in the multi-layer architecture)
3. No change control protocol (the mechanism for maintaining normative integrity over time)

These gaps do not invalidate the existing governance architecture. They do mean that no operational or audit repository should be created before these gaps are addressed.

---

## Recommendations Before Operational Repositories Are Created

**R-1 [CRITICAL] — Create the declared source catalog.**  
Produce a document (e.g., `docs/declared-sources-catalog.md`) that formally enumerates specific SAD Morón institutional sources with: institutional origin, document/record class, intended governance use, temporal relevance, and known limitations, as required by `declared-sources-protocol.md`. This is the single most operationally critical missing artifact.

**R-2 [CRITICAL] — Create the canonical governance core document.**  
Produce a single authoritative document (e.g., `core/SAD_MORON_GOVERNANCE_CORE_V1.md` or equivalent within the existing `docs/` structure) that serves as the definitive Layer 1 reference. Future operational and audit repositories should be able to cite a single document as their normative anchor.

**R-3 [HIGH] — Implement a change control protocol.**  
Create a protocol document governing how normative framework changes are proposed, evaluated, documented, and approved. At minimum, this should define who can propose normative changes, what documentation is required, and what the approval mechanism is.

**R-4 [HIGH] — Populate the GitHub remote.**  
Push the current repository content to the public GitHub repository so the governance layer has an external, versioned, publicly citable anchor. The framework cannot function as an external governance reference while it exists only locally.

**R-5 [HIGH] — Enumerate the normative document registry.**  
Add to `normative-framework.md` (or to a new dedicated document) an explicit list of which documents hold normative authority and which are explanatory. This is required for future operational repositories to correctly identify their governing inputs.

**R-6 [MEDIUM] — Promote the administrative event taxonomy to normative status.**  
The event families described in `expected-events-protocol.md` and `scope-and-boundaries.md` are currently illustrative. At minimum one small set of expected events should be formally promoted to normative status so omission detection protocols can be applied.

**R-7 [MEDIUM] — Document structural deviations from the Janus Review.**  
Add a brief governance decision note (in a future `decisions/` or `rfcs/` directory, or appended to `reports/`) explaining why `core/`, `rfcs/`, and `examples/` directories were not implemented, and whether the `docs/` + `protocols/` structure is the intended permanent alternative.

**R-8 [MEDIUM] — Add version identifiers and date stamps to all protocol documents.**  
The framework declares append-only governance history as a core principle. Protocol documents should carry version identifiers and date-of-authoring so their own revision history can be reconstructed — implementing in the framework layer the discipline it requires of future operational layers.

**R-9 [LOW] — Define the scaffold stage exit condition.**  
State explicitly what conditions must be met before the repository transitions from "base scaffold" to full normative status. This prevents the scaffold label from becoming a permanent ambiguity shield.

**R-10 [LOW] — Clarify the governance role of `framework-contracts.md`.**  
Add a note in `framework-contracts.md` clarifying its relationship to `normative-framework.md` — whether it is subordinate, coordinate, or superseding — to prevent future interpretive conflicts.

---

## Major Findings Summary

| Finding | Severity | Category |
|---|---|---|
| No declared source catalog | Critical | Institutional Viability |
| No canonical governance core document | High | Layer Separation |
| GitHub remote empty (local/remote divergence) | High | Boundary Consistency |
| No change control protocol | High | Governance Integrity |
| Administrative event taxonomy not normative | High | Institutional Viability |
| No normative document registry | Medium | Governance Integrity |
| Structural deviation from Janus Review undocumented | Medium | Inconsistency |
| Boundary enforcement has no review mechanism | Medium | Boundary Consistency |
| No version identifiers on protocol documents | Medium | Governance Integrity |
| Scaffold stage exit condition undefined | Low | Ambiguity |

---

## Audit Verdict

**The governance boundaries of `SAD-MORON-FRAMEWORK` remain preserved.**

The framework is correctly conceived, correctly bounded, and correctly separated from the Janus runtime complexity it chose not to inherit. The Janus adaptation is disciplined and appropriate for the SAD Morón institutional context.

The framework is not ready to govern operational repositories because the minimum viable declared governance objects — specifically, the declared source catalog and the canonical governance core document — have not yet been produced. Operational or audit repositories created before these artifacts exist would have no authoritative governance anchor to inherit.

Subject to resolution of Findings I-1, L-1, G-1, and P-2 (declared sources, governance core, normative registry, change control), the architecture of this framework is sound and may proceed to operational repository creation.

---

*This document is an external governance audit artifact produced by Claude (Sonnet 4.6) on 2026-05-26. It is append-only and versioned as part of the governance evidence layer. Future governance assessments should append subsequent versions rather than modifying this document.*
