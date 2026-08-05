# SAD Audit Surfaces and Prepublication Gates Protocol V1

## Status

**DRAFT — CANDIDATE FOR HUMAN RATIFICATION**

This document is a normative governance protocol governing evidence collection, audit surfaces, independent interconsultation, and prepublication validation. It is NOT canonical until ratified through the discipline it defines.

**Candidate Distribution State:** PUBLISHED_CANDIDATE_BRANCH

**Canonical Status:** NOT CANONICAL

**Ratification Status:** NOT RATIFIED

**Institutional Adoption Status:** NOT ADOPTED

**Reference:** Candidate SHA `cdecbbac658d3cc4c66a04dcd3f3d816a8216b4f` (exact audited commit)

---

## SECTION 1 — PURPOSE

This protocol governs:

- **Evidence collection** from multiple independent sources
- **Audit surfaces** as bounded observation domains
- **Independent interconsultation** to prevent siloing
- **Prepublication validation** before canonical promotion
- **Audit divergence** reconciliation
- **Human publication gates** as sole canonical authority
- **Post-publication verification** integrity checks

### Core Purpose

Prevent a candidate from becoming canonical merely because it passed checks on the same technical surface where it was produced.

### Scope

This protocol applies to SAD governance, architecture, and critical documentation candidates intended for public or authorized canonical destinations. It establishes reusable audit discipline across:

- SAD-MORON repositories
- Future SAD systems
- Other governed software/data projects
- Regardless of implementation toolchain or auditor technology

---

## SECTION 2 — EVIDENCE IS SURFACE-BOUND

### Core Principle: `EVIDENCE_IS_SURFACE_BOUND`

Evidence obtained on one audit surface does not automatically authorize claims about another audit surface.

### Examples

**Local Git Surface:**
- CAN demonstrate: commit ancestry, dirty/clean state, exact diff, branch history
- CANNOT demonstrate: public discoverability, unauthenticated rendering, external comprehension

**Public GitHub Observation Surface:**
- CAN demonstrate: public visibility, rendered documentation, public navigation, externally observable contradictions
- CANNOT demonstrate: private Labs content, local unpublished implementation, runtime behavior

**Runtime Observation Surface:**
- CAN demonstrate: actual execution behavior, controlled telemetry, response sequences
- CANNOT automatically prove: administrative authority, canonical publication, institutional ratification

**Human Institutional Surface:**
- CAN demonstrate: formal ratification, promotion decision, institutional authority
- CANNOT demonstrate: implementation completeness, runtime correctness, public clarity

---

## SECTION 3 — AUDIT SURFACE TAXONOMY (R10 - Toolchain-Neutral Conceptual Core)

The audit surfaces define bounded observation domains. The following taxonomy is toolchain-neutral and implementation-independent. Current Git/GitHub implementation examples are provided for guidance.

### S1 — LOCAL_WORKSPACE

**Conceptual Scope:**
- Local development/authorship files
- Work-in-progress state
- Uncommitted changes
- Local configuration boundaries
- Private/personal artifacts not synchronized to version control

**Authority:** Authorship/development view

**Limitations:**
- Cannot establish public/remote state
- Cannot determine remote publication status
- Cannot observe third-party interpretation

**Current Implementation (Git/GitHub):**
- Working directory files
- Local filesystem changes
- Untracked artifacts
- `.gitignore` scope

---

### S2 — LOCAL_VERSION_CONTROL

**Conceptual Scope:**
- Committed version history
- Branch structure and ancestry
- Local change tracking
- Committed state differentials
- Local version control metadata

**Authority:** Local repository history of record

**Limitations:**
- Cannot establish external/remote interpretation
- Cannot verify what remote state actually is (must fetch)
- Does not demonstrate public/external visibility

**Current Implementation (Git/GitHub):**
- Git commits
- Local branch structure
- Diff content
- Local commit messages
- Ahead/behind tracking relative to remote

---

### S3 — REMOTE_VERSION_CONTROL_OF_RECORD

**Conceptual Scope:**
- Published version control state
- Canonical remote branch refs
- Published commit ancestry
- Remote branch HEAD state
- Version-controlled diff on remote

**Authority:** Remote repository state of record (primary for canonical publication claims)

**Critical Distinction:**

`PUBLISHED_TO_BRANCH` ≠ `PUBLISHED_TO_CANONICAL_DESTINATION`

A branch can be published to remote without being merged to the canonical destination.

**Limitations:**
- Does not demonstrate public unauthenticated visibility
- Does not verify external link resolution
- Does not establish public comprehension

**Current Implementation (Git/GitHub):**
- origin/main (or equivalent canonical branch)
- Remote candidate branches
- Published branch HEAD
- Remote refs metadata

---

### S4 — CANDIDATE_REVIEW_SURFACE

**Conceptual Scope:**
- Candidate proposal state
- Exact candidate diff (proposed vs base)
- Review/approval metadata
- Candidate scope boundary
- Review checks and status

**Authority:** Candidate proposal state (not canonical)

**Important:** A candidate review surface is a PROPOSAL surface, not canonical publication.

**Limitations:**
- Candidate HEAD may change (invalidates prior audits)
- Candidate review status does not determine canonical status
- Review completion authority differs from merge authority

**Current Implementation (Git/GitHub):**
- GitHub Pull Request
- PR diff (base vs head)
- PR checks status
- PR metadata (title, description)
- PR review/approval status

---

### S5 — PUBLIC_UNAUTHENTICATED_SURFACE

**Conceptual Scope:**
- Observable public state without authentication
- What an unauthenticated third party can see
- Public documentation rendering
- Public navigation and discoverability
- Public repository visibility status
- Externally observable state

**Authority:** PRIMARY for claims about:
- public visibility/discoverability
- external third-party experience
- public documentation accuracy
- public link navigation
- public-surface contradictions
- external observer perspective

**Limitations:**
- Cannot observe private/authenticated content
- Cannot infer private absence from public absence
- Cannot determine private implementation from public visibility

**Current Implementation (Git/GitHub):**
- GitHub repository landing page
- Public README rendering
- Public branch visibility
- Public documentation files
- Public link resolution
- unauthenticated user experience

**Important:** Public ≠ unrestricted operational disclosure. Governance and policy may be public while operational configuration stays private.

---

### S6 — PRIVATE_AUTHORIZED_SURFACE

**Conceptual Scope:**
- Authorized observation of governed/restricted content
- Private/confidential repositories
- Access-controlled governance surfaces
- Restricted evidence sources
- Authorized-only implementation details
- Institutional private records

**Authority:** PRIMARY for claims about:
- private artifact status within authorized scope
- restricted-access governance content
- confidential implementation correctness
- authorized-only audit results

**Important Distinction:** Private ≠ unaudited. Private ≠ unreviewed.

**Limitations:**
- Absence from S5 does NOT imply S6 absence
- S5 invisibility is not evidence against S6 existence
- Public absence cannot be used to infer private state

**Current Implementation (Git/GitHub):**
- Private GitHub repositories
- Restricted-access branches
- Authorization-gated documentation
- Private institutional repositories

**Important:** Auditability does NOT require violating confidentiality. Authorized independent audit on S6 is as rigorous as S5 audit.

---

### S7 — RUNTIME_SURFACE

**Conceptual Scope:**
- Observable execution behavior
- Controlled test/runtime observation
- Telemetry and event data
- Actual runtime effects
- Observable state changes
- Performance characteristics

**Authority:** PRIMARY for claims about:
- runtime execution behavior
- technical correctness (execution, not institutional)
- observable effects and outcomes
- performance characteristics

**Important:** Must remain separate from Administrative Audit surface (S8).

**Limitations:**
- Does not establish institutional authority
- Does not prove administrative approval
- Success does not imply authorized deployment
- Does not demonstrate compliance with procedures

**Current Implementation (Git/GitHub):**
- Test execution results
- CI/CD pipeline runs
- Application runtime monitoring
- Performance benchmarks
- User acceptance testing results

---

### S8 — HUMAN_AUTHORITY_SURFACE (R11 - Authority Type Distinction)

**Observation Scope:**
- human ratification decision
- promotion authorization
- institutional authority
- administrative decision
- approval/rejection
- formal governance act
- institutional accountability

**Important:** Not all human authority types are equivalent. Distinguish:

- **Project Governance Authority** — authorized to guide project direction and merge decisions
- **Institutional Authority** — authorized to commit institution to formally adopt a capability
- **Administrative Authority** — authorized to manage operational instances
- **Production Authorization** — authorized to deploy/run software
- **Official Adoption Authority** — authorized to make organization-wide adoption decisions

**Authority Principle:** No authority type implies another automatically.

- A project reviewer approving a merge does NOT imply institutional adoption authority
- An administrator deploying a feature does NOT imply ratification authority
- Institutional adoption does NOT automatically imply production deployment

**Authority for Claims:**
- CANONICAL_PROMOTION — Project Governance Authority (merge authority)
- INSTITUTIONAL_ADOPTION — Institutional Authority (commitment authority)
- FORMAL_RATIFICATION — Governance Authority (framework authority)
- PRODUCTION_DEPLOYMENT — Production Authorization (operations authority)
- ADMINISTRATIVE_AUDIT_COMPLETION — Administrative Authority (oversight authority)

**Authority Must Be Explicit and Traceable:**

- Git status cannot manufacture human authority
- Merge permission does not guarantee ratification
- Authority decisions must be recorded with identity, timestamp, scope, and any conditions

---

## SECTION 4 — NO_CROSS_SURFACE_INFERENCE

### Core Rule: `NO_CROSS_SURFACE_INFERENCE`

An auditor must not claim authority outside the evidence surface relevant to the claim.

### Correct Inference Patterns

| If | Say | NOT |
|---|---|---|
| Private repo invisible from S5 | NOT_PUBLICLY_OBSERVABLE | DOES_NOT_EXIST |
| File exists in Git (S2) | PRESENT_IN_GIT | EXTERNALLY_DISCOVERABLE |
| Execution succeeds (S7) | RUNTIME_E+ | ADMINISTRATIVELY_APPROVED |
| Branch is pushed (S3) | PUBLISHED_TO_ORIGIN_BRANCH | CANONICAL |
| Content visible in S5 | PUBLICLY_VISIBLE | INSTITUTIONALLY_APPROVED |

### Examples of Invalid Inference

**Invalid:** "Since the Labs repository is not visible on GitHub, Labs is not implemented."
- **Correct:** "Labs is not publicly observable from S5. Authorized S6 observers can determine S6 state."

**Invalid:** "The code ran successfully, so this change is approved for production."
- **Correct:** "Runtime execution was successful (S7 E+). Institutional approval is a separate S8 determination."

**Invalid:** "The documentation is on public main, so everyone understands it."
- **Correct:** "Documentation is publicly present on origin/main (S3/S5). Public comprehension requires independent S5 user testing or observation."

**Invalid:** "Two different AI models audited the same local worktree, so the audit is independent."
- **Correct:** "Two agents auditing the same S2 local worktree are not equivalent to independent surface audit. Independent audit requires S5, S6, or S7 observation by different surfaces."

---

## SECTION 5 — AUDIT CLAIM CONTRACT (CANONICAL AUDIT RECORD TEMPLATE)

Every material audit finding should identify:

```text
Audit_ID:                          [unique identifier]
Artifact:                          [what is being audited]
Artifact_Ref / SHA:                [version/commit/reference]
Claim_ID:                          [standardized claim type per R5 convention]
Claim:                             [specific assertion]
Claim_Surface_ID:                  [primary surface authoritative for this specific claim]
Declared_Audit_Surface_ID:         [surface(s) authorized/declared for this audit]
Actual_Audit_Surface_ID:           [surface(s) actually used by auditor]
Auditor_Role:                      [role, not vendor/model name]
Evidence_Type:                     [documentary/technical/observational/etc]
Evidence_Result:                   [E+ / E- / NO_DEMOSTRADO / STALE]
Claim_Reconciliation_State:        [CONTRADICTORY if multiple incompatible findings exist]
Audit_Execution_State:             [AUDIT_SCOPE_COMPLIANT / AUDIT_SCOPE_BREACH]
Evidence_Admissibility:            [OUT_OF_SCOPE_EVIDENCE / CLAIM_EVIDENCE_ADMISSIBLE / CLAIM_REQUIRES_REAUDIT]
Timestamp:                         [when audit occurred]
Scope:                             [what is and is not included]
Limitations:                       [what this audit does NOT cover]
Reconciliation_Notes:              [notes on conflicts with other audits / resolution approach]
Gate_Impact:                       [impact on prepublication gate: PASS / CONDITIONAL / FAIL]
```

### Field Definitions (R3 - Surface Identifiers)

**Claim_Surface_ID:** The audit surface whose observation is relevant and authoritative for this specific bounded claim. Different claims within the same artifact may have different primary surfaces.

**Declared_Audit_Surface_ID:** The surface(s) the auditor was authorized or declared to use. Multiple surfaces may be declared.

**Actual_Audit_Surface_ID:** The surface(s) actually used by the auditor during evidence collection. If this differs from Declared, mark `AUDIT_SCOPE_BREACH`.

### Example Audit Record

```text
Audit_ID:                          AUD-2026-08-05-SAP-001
Artifact:                          SAD_AUDIT_SURFACES_AND_PROMOTION_GATES_V1.md
Artifact_Ref:                      cdecbbac658d3cc4c66a04dcd3f3d816a8216b4f
Claim_ID:                          PROTOCOL-STATUS-CLARITY
Claim:                             Protocol status terminology is clear and unambiguous
Claim_Surface_ID:                  S5 (public candidate) + S2 (artifact review)
Declared_Audit_Surface_ID:         S5
Actual_Audit_Surface_ID:           S5, S2 (scope breach for provenance clarification)
Auditor_Role:                      independent external observer
Evidence_Type:                     documentary / textual analysis
Evidence_Result:                   E- (protocol used stale terminology LOCAL_COMMIT_ONLY after publication)
Claim_Reconciliation_State:        —
Audit_Execution_State:             AUDIT_SCOPE_BREACH (used S2 to verify source, was not declared)
Evidence_Admissibility:            OUT_OF_SCOPE_EVIDENCE (S2 evidence for S5 claim requires reconciliation)
Timestamp:                         2026-08-05T14:30:00Z
Scope:                             terminology clarity for publication state only
Limitations:                       did not audit governance logic or protocol completeness
Reconciliation_Notes:              S2 observation of source document confirms finding; evidence is admissible for this specific claim despite scope breach
Gate_Impact:                       CONDITIONAL (finding is true but minor; reconciliation through terminology update is straightforward)
```

### Evidence Result Taxonomy

Describes the outcome of observing a single piece of evidence:

- `E+` — Explicit evidence of presence in declared source or review artifact
- `E-` — Verified absence of expected record under declared scope
- `NO_DEMOSTRADO` — Cannot determine (evidence insufficient, surface inaccessible, scope unclear)
- `STALE` — Evidence was valid at timestamp but may be invalidated by subsequent change

**Important Principle:** Absence of evidence is NOT evidence of absence. Do not collapse E-, NO_DEMOSTRADO, or STALE.

### Claim Reconciliation State

Describes the relationship between multiple audit findings about the same claim:

- `CONTRADICTORY` — Two or more materially incompatible findings about the same sufficiently-bounded claim observed on different surfaces or by different auditors

**Definition:** A relationship between findings, not a result of a single evidence observation. CONTRADICTORY requires at least two incompatible claims to exist; it cannot describe a single finding.

### Audit Execution State

Describes whether the audit stayed within its declared scope:

- `AUDIT_SCOPE_COMPLIANT` — Evidence stayed entirely within declared audit scope
- `AUDIT_SCOPE_BREACH` — Audit used undeclared evidence surface, source, permission context, or other scope violation

### Evidence and Claim Admissibility State

Describes whether evidence can reliably support the claim in question:

- `OUT_OF_SCOPE_EVIDENCE` — Evidence obtained outside the declared scope and cannot support the audited claim without re-scoping
- `CLAIM_EVIDENCE_ADMISSIBLE` — Claim is supported entirely by authorized evidence within declared scope
- `CLAIM_REQUIRES_REAUDIT` — Claim cannot be relied on until scoped audit is repeated under corrected parameters

### Audit Scope Provenance

An audit must preserve evidence provenance by recording both the declared scope and the actual evidence used.

Required scope provenance fields:

- `Declared_Surface_ID`
- `Actual_Surface_ID`

## SECTION 5A — CLAIM_ID GOVERNANCE CONVENTION (R5)

The Claim_ID provides a stable, reusable identifier for a semantic claim that may recur across multiple audits, surfaces, and time periods.

### Claim_ID Stability Requirements

- Stable across repeated audits of the same semantic claim
- Unique within its governance/audit context
- Not generated differently merely because auditor/tool changed
- Suitable for reconciliation across surfaces
- Not vendor-specific or implementation-dependent

### Minimal Claim_ID Contract

Use a **namespaced pattern** suitable for your context:

**Recommended Format:**

```
<ARTIFACT>::<CLAIM_CLASS>::<CLAIM_NAME>
```

**Examples:**

- `SAD_AUDIT_SURFACES_AND_PROMOTION_GATES_V1.md::PROTOCOL-STATUS-CLARITY`
- `Architecture_V1.md::RATIFICATION-STATUS-CONSISTENCY`
- `Governance_Core.md::SAD_009_RELATIONSHIP_CLARITY`
- `Repository.md::LINK-RESOLUTION`

### Pattern Explanation

- `<ARTIFACT>` — the versioned artifact/document being audited
- `<CLAIM_CLASS>` — category of claim (STATUS, COMPLETENESS, CONSISTENCY, LINK_VALIDITY, DISCOVERABILITY, etc.)
- `<CLAIM_NAME>` — specific claim within that class

Do NOT attempt to enumerate every possible future claim. Instead, define the syntax and use consistent reasoning.

### Across Different Audits

If the same semantic claim recurs in:
- Different audits (S2 vs S5)
- Different times
- Different auditors
- Different surfaces

Use the same Claim_ID to enable reconciliation and prevent silent averaging of conflicting results.

---

`AUDIT_SCOPE_BREACH` does NOT automatically invalidate every claim in the audit.

When an audit exceeds its declared surface:

1. record the originally authorized `Surface_ID` / scope;
2. record the actual additional surface used;
3. identify every `Claim_ID` affected by the additional evidence;
4. separate findings supported entirely by the authorized surface;
5. classify evidence derived from the undeclared surface separately;
6. do NOT present out-of-scope evidence as if it came from the declared surface;
7. determine whether the extra evidence may have materially influenced conclusions;
8. if material influence cannot be excluded, repeat the affected audit under a clean declared scope.

### Claim-Level Salvage Rule

A scope breach may contaminate the audit record without invalidating every claim.

Example:

```text
Declared audit:
LOCAL_GIT

Actual observation:
LOCAL_GIT + PUBLIC_UNAUTHENTICATED_SURFACE

Claim A:
supported only by LOCAL_GIT
→ CLAIM_EVIDENCE_ADMISSIBLE

Claim B:
supported by public web observation
→ reclassify as S5 evidence or exclude from the S2 audit result

Audit-level result:
AUDIT_SCOPE_BREACH

Gate impact:
reconcile provenance before relying on the audit as a whole
```

---

## SECTION 6 — AUDITOR_INDEPENDENCE ≠ AUDIT_SURFACE_DIVERSITY (R6)

### Core Principle

Changing the AI model, agent, or toolchain does NOT by itself create independent evidence.

**Distinct Concepts:**

- `AUDITOR_INDEPENDENCE` — Different observer, different assumptions, different permission context
- `AUDIT_SURFACE_DIVERSITY` — Observing different audit surfaces (S2 vs S5, not two S2 observations)

These are **independent axes**. They do not imply each other.

### Misconceptions to Avoid

❌ **Different model + Same surface = Independent audit**

Two agents reading the same local working tree (S2) are NOT independent audits, regardless of model differences. They observe the same authoritative surface and will typically converge.

❌ **Different vendor + Same technique = Different evidence**

Claude and Copilot both analyzing your S2 Git repository produce surface-diverse results only if they observe materially different surfaces (e.g., one adds S5 observation), not merely because they are different vendors.

### Valid Independence Requirements

Independence may require differences in:

- **Observation surface** — S2 vs S5, not two S2 observations; S6 vs S7, not two S6 observations
- **Evidence source** — Different tools, different witnesses, different documentation stores
- **Authorization context** — Different permission sets, different viewer roles
- **Prior assumptions** — Different baseline knowledge, different starting hypotheses
- **Auditor context** — Different organizational context, different accountability

### Valid Independence Claims

✓ Local Git auditor (S2) + Unauthenticated public-surface auditor (S5) + Runtime observer (S7)  
✓ Same auditor on different surfaces at different times  
✓ Different authorized observers on S6 private surface  
✓ Internal developer + external public observer (different surfaces, different authorization)

### Language Requirement

- Use generic roles: "internal developer auditor", "independent surface observer", "authorized Labs reviewer"
- Do NOT use vendor/model names as normative governance dependencies
- Vendor names appear only as non-normative examples when necessary for implementation guidance

---

## SECTION 7 — AUDIT_SURFACE_PARITY

### Definition: `AUDIT_SURFACE_PARITY`

Critical claims expected to be observable on multiple surfaces must retain semantically compatible meaning across those surfaces.

### Example — Architecture Status

| Surface | Claim | Status |
|---|---|---|
| S2 Local Git | Architecture ratification | RATIFIED |
| S4 Candidate PR | Architecture ratification | RATIFIED |
| S5 Public candidate | Architecture ratification | RATIFIED |
| S5 Public current main | Architecture status | DRAFT — PENDING RATIFICATION ❌ |

This last S5 claim CONTRADICTS the published S3 state.

**Result:** `SURFACE_PARITY_FAIL`

### Fail Condition: `SURFACE_PARITY_FAIL`

Occurs when incompatible current-state claims coexist on surfaces that should present compatible status.

### Publication Gate Impact

No publication may proceed while a material `SURFACE_PARITY_FAIL` exists on expected surfaces.

---

## SECTION 8 — AUDIT_DIVERGENCE

### Definition: `AUDIT_DIVERGENCE`

Two audits produce materially different findings about the same claim.

### Do NOT Resolve By

- majority vote
- model reputation
- choosing the newest auditor
- silently averaging conclusions
- deferring to "more confident" claim

### Required Reconciliation

1. **Identify** Claim_ID
2. **Identify** Surface_ID of each finding
3. **Identify** evidence type and limitations
4. **Identify** scope of each audit
5. **Determine** which surface has authority for that specific claim
6. **Classify** findings as:
   - **compatible** (different aspects of same truth)
   - **different-surface truths** (each surface-bound result is correct in its domain)
   - **genuinely contradictory** (logical incompatibility)
7. **Separate** any `AUDIT_SCOPE_BREACH` from claim-level divergence

### Example

**Claim:** "SAD_SYSTEM_ARCHITECTURE_V1.md status is current and correct"

**S2 Local Git Audit Result:** E+ (artifact present, ratification date correct, dependencies merged)

**S5 Public Surface Audit Result:** E- (public rendering shows "DRAFT — PENDING" while Git shows "RATIFIED")

**Reconciliation:**
- Findings are NOT contradictory
- They reveal a `SURFACE_PARITY_FAIL`: public rendering is stale
- Correction required before publication

### Scope Breach Relation

`AUDIT_SCOPE_BREACH` is NOT automatically `AUDIT_DIVERGENCE`.

- `AUDIT_SCOPE_BREACH` concerns evidence provenance and audit execution
- `AUDIT_DIVERGENCE` concerns materially different findings about the same claim
- They may coexist

### Publication Gate

No publication gate may close while a material `AUDIT_DIVERGENCE` remains unresolved.

---

## SECTION 9 — AUTHORITY BY CLAIM TYPE

### Primary Evidence Surface by Claim Category

| Claim | Primary Surface(s) | Secondary Check |
|---|---|---|
| Local working tree clean | S1/S2 | — |
| Commit ancestry | S2 | S3 (verify remote matches) |
| Remote branch exists | S3 | S4 (PR confirms intention) |
| Exact candidate diff | S4 | S3 (base/head verification) |
| Public link resolves | S5 | S3 (verify published HEAD) |
| Public reader discovers artifact | S5 | S2 (verify in source) |
| Private Labs implementation exists | S6 | — |
| Runtime execution succeeded | S7 | — |
| Human ratification occurred | S8 | S2/S3 (verify commit record) |
| Institutional adoption authorized | S8 | S7 (verify deployment evidence) |
| Administrative audit complete | S8 | S7 (verify audit trail) |

### Authority Principle

An auditor claiming result for a claim type must cite evidence from the primary surface for that claim.

Secondary checks may confirm but do not substitute for primary authority.

---

## SECTION 10 — PROMOTION STATE MACHINE (R10/R12 - Toolchain-Neutral Core)

### Abstract Governance Promotion State Sequence

```
LOCAL_CANDIDATE
      ↓
INTERNAL_AUDITED_CANDIDATE
      ↓
REMOTE_CANDIDATE
      ↓
CANDIDATE_REVIEW_AUDITED
      ↓
EXTERNAL_SURFACE_AUDITED
      ↓
EVIDENCE_RECONCILED
      ↓
READY_FOR_HUMAN_PUBLICATION_GATE
      ↓
CANONICALLY_PUBLISHED
      ↓
POST_PUBLICATION_VERIFIED
```

### State Descriptions (Toolchain-Neutral)

**LOCAL_CANDIDATE:** Artifact created locally, not yet reviewed or tested

**INTERNAL_AUDITED_CANDIDATE:** Artifact audited on internal surfaces only; ready for collaboration

**REMOTE_CANDIDATE:** Candidate published to shared remote version control; creates candidate review opportunity

**CANDIDATE_REVIEW_AUDITED:** Candidate proposed for review; exact diff frozen; review checks validated

**EXTERNAL_SURFACE_AUDITED:** Independent unauthenticated (for public) or authorized (for private) audit complete

**EVIDENCE_RECONCILED:** All audit findings reviewed; divergences resolved; surface parity confirmed

**READY_FOR_HUMAN_PUBLICATION_GATE:** All required evidence collected; waiting for human authority decision

**CANONICALLY_PUBLISHED:** Promotion to canonical destination completed; candidate is now canonical

**POST_PUBLICATION_VERIFIED:** Integrity check confirms published state matches audited candidate; no escapes detected

### Private Artifact Equivalent

For private canonical destinations, replace EXTERNAL_SURFACE_AUDITED with independent authorized S6 audit appropriate to classification.

Principle: **Auditability does not require violating confidentiality.**

### Current Implementation Example — Git/GitHub Mapping

For projects using Git version control and GitHub collaboration:

| Abstract State | Git/GitHub Implementation |
|---|---|
| LOCAL_CANDIDATE | Local commits in working branch, not yet pushed |
| INTERNAL_AUDITED_CANDIDATE | Local branch audited; ready to push |
| REMOTE_CANDIDATE | Candidate branch pushed to origin |
| CANDIDATE_REVIEW_AUDITED | PR created, exact diff fixed, checks run |
| EXTERNAL_SURFACE_AUDITED | Independent S5 (unauthenticated) or S6 (authorized) audit of PR/branch |
| EVIDENCE_RECONCILED | Findings reviewed and reconciled; divergences resolved |
| READY_FOR_HUMAN_PUBLICATION_GATE | PR approved; waiting for merge authority decision |
| CANONICALLY_PUBLISHED | PR merged to origin/main |
| POST_PUBLICATION_VERIFIED | Verify canonical branch matches audited candidate; no unexpected diffs |

**Important:** This Git/GitHub mapping is a current implementation example, not a normative requirement. Other version control systems, forge platforms, or workflows may implement these states differently while preserving the same governance sequence.

---

## SECTION 11 — PREPUBLICATION_GATE

### Definition: `PREPUBLICATION_GATE`

The formal governance checkpoint before canonical promotion.

### Minimum Evidence Requirements for PUBLIC Canonical Artifact

1. Implementation/source validation (S1/S2)
2. Internal audit (S2)
3. Independent interconsultation where material (S4 or S5)
4. Exact candidate commit frozen (S3)
5. Candidate branch published (S3)
6. Exact PR diff audited (S4)
7. Unauthenticated/external public-surface audit of the candidate (S5)
8. Reconciliation of findings across surfaces
9. Security classification check (no secrets in S5)
10. Human publication decision (S8)

### Critical Requirement

The external audit must inspect the SAME candidate SHA intended for merge.

If candidate HEAD changes after audit:

`AUDIT_INVALIDATED_BY_CHANGE`

Affected audits must be repeated before gate closure.

### Private Artifact Requirements

For private destinations:

1-6. (same as public)
7. **Authorized independent audit** appropriate to classification (S6 instead of S5)
8-10. (same as public)

---

## SECTION 12 — PRIVATE_CANONICAL_ARTIFACTS

### Principle

Private canonical artifacts do NOT require public exposure.

### Governance Coverage

Private → auditable (authorized surface)
NOT: Private → unauthenticated or unreviewed

### Example

Labs implementation (private):

- **NOT published to:** S5 (public GitHub)
- **IS auditable via:** S6 (authorized Labs access)
- **NOT less governed than** public artifact
- **Different authority surface** (S6 instead of S5)

### Public Governance Layer + Private Operational Layer

Governance repositories may remain public while operational integrations stay bounded:

- `Governance` (public, auditable via S5)
- `Runtime Connectors` (private or bounded, auditable via S6)
- `Operational Configuration` (private, auditable via S6)
- `Production Credentials` (private, external to Git)

**Principle:** Public ≠ unrestricted operational disclosure

---

## SECTION 13 — HUMAN_PUBLICATION_GATE

### Definition: `HUMAN_PUBLICATION_GATE`

Sole authority for canonical promotion. Only human governance authority may authorize publication after required evidence is reconciled.

### Gate Decision Must Explicitly Distinguish

- **Promotion:** Movement to governed destination (Git merge)
- **Publication:** Making publicly/officially available
- **Production:** Deployed and running
- **Institutional Adoption:** Authority decides to use institutionally

**None of these implies the others automatically.**

### Gate Output

Human decision must state:

1. Authority identity
2. Artifact version/SHA
3. Decision (approve/reject)
4. Conditions or restrictions
5. Post-publication verification requirements
6. Timeline for institutional adoption (if applicable)

### Fail-Closed Default

If gate decision is unclear, missing, or contradictory:

`PUBLICATION_GATE_FAIL_CLOSED`

No merge. No canonical promotion.

---

## SECTION 14 — POST_PUBLICATION_INTEGRITY_CHECK

### Definition: `POST_PUBLICATION_INTEGRITY_CHECK`

Verification that canonical merge preserved audited candidate integrity.

### Purpose

NOT to discover architecture from scratch.

IS to verify:

- Merged commit ancestry (candidate is reachable from origin/main)
- Expected artifact exists on canonical branch
- Public rendering (if S5 applicable) matches audited candidate
- No unexpected diff entered publication
- Publication metadata correct
- Links/navigation still resolve on canonical surface

### Defect Classification

If a material defect observable on the candidate surface is discovered ONLY AFTER canonical merge:

`PREPUBLICATION_GATE_ESCAPE`

This is a process governance incident requiring:

- Immediate correction
- Evidence collection on defect
- Root cause: why gate failed to catch observable defect
- Process improvement

### Expected Norm

Immediate post-publication patches are NOT normalized expected workflow.

A `GATE_ESCAPE` must be exceptional, not routine.

---

## SECTION 15 — EXTERNAL_SURFACE_AUDIT

### For PUBLIC repositories

Standard external test: Auditor behavior as if it has:

- ❌ no local filesystem
- ❌ no private repository access  
- ❌ no prior conversation history
- ❌ no internal agent report

### Audit Targets

- repository landing page
- README discoverability
- link resolution
- architecture/governance status sections
- visibility declarations
- public/private claims
- production/adoption wording
- navigation across repositories
- contradictions across surfaces
- sensitive information exposure

### Classification of Unavailable Evidence

When information is not available from S5:

**Correct:** `NOT_PUBLICLY_OBSERVABLE`

**Incorrect:** (evidence-negative inference)

Absence from S5 is NOT evidence against S6 existence.

### For PRIVATE repositories

Equivalent authorized S6 external audit with same disciplinary rigor.

---

## SECTION 16 — PUBLIC_DISCOVERABILITY

### Distinction

`PUBLISHED` ≠ `DISCOVERABLE`

A file may exist on public main while remaining difficult for external reader to locate.

### Separate Evidence Claims

- `ARTIFACT_PUBLICLY_PRESENT` — File exists on public branch (S3/S5)
- `ARTIFACT_PUBLICLY_DISCOVERABLE` — Independent reader can locate it (S5 navigation/search)

Do NOT infer one from the other.

### Example

- `README.md` — PUBLISHED_TO_ORIGIN_MAIN ✓
- Root-level navigation mentions `docs/governance-core.md` ✓
- External reader searching "governance" finds reference ✓
- BUT: Reader landing on public site may not discover deep governance documentation without explicit link tree

**Result:** Present but not discoverable = publication-gate finding for improvement.

---

## SECTION 17 — SECURITY

### External Public Audit Must Check

- credentials (API keys, tokens)
- secrets (private keys, passwords)
- real source IDs (Sheet IDs, Drive IDs)
- Script IDs
- private endpoints
- personal data
- reconstructable operational topology
- sensitive mappings

### Do NOT Reproduce

- Do not include sensitive values in audit reports
- Do not expose operational infrastructure in findings
- Do not publish private data discovered

### Resolution

Sensitive findings:

1. Report to governance authority (NOT public)
2. Do NOT merge candidate with security issues
3. Gate closes on security finding
4. Cleanup required before publication

---

## SECTION 18 — OBSERVED_EVIDENCE_BASIS

### Motivation

This protocol was motivated by an observed publication-cycle gap in the SAD-MORON Architecture V1 promotion:

- Internal/local/remote PR validation passed ✓
- Remote PR checks passed ✓
- Authorized reviewers approved ✓
- **After canonical publication to origin/main:**
  - Independent unauthenticated public-surface (S5) review identified:
    - current-state documentation contradiction
    - public navigation/discoverability defects
    - both observable from the public candidate surface BEFORE merge
  
**Lesson:** Different surfaces reveal different evidence.

### Root Cause

Insufficient surface coverage before canonical publication.

Internal audits and PR reviews did not include:
- Independent external (S5) perspective
- Navigation/discoverability testing from public surface
- Explicit surface-parity verification

### Resolution

Formalize prepublication discipline requiring evidence reconciliation across multiple audit surfaces before human publication gate closure.

### Importantly

- Do NOT name private data
- Do NOT expose hidden repository content
- Do NOT blame specific AI agent or vendor
- Acknowledge: Process defect was insufficient surface coverage

---

## SECTION 19 — GATE_ESCAPE_METRIC

### Definition: `PREPUBLICATION_GATE_ESCAPE_COUNT`

Number of material defects detected AFTER canonical publication that were:

- Demonstrably observable on the audited candidate surface
- BEFORE merge
- Not flagged during prepublication gate process

### Desired Value

`0`

### Classification Rules

**IS a gate escape:**
- Security issue visible in S5 public rendering (not caught by S5 audit)
- Documentation contradiction observable on S4/S5 (candidates not audited for consistency)
- Link broken on canonical branch (was correct on candidate, changed during merge)

**NOT a gate escape:**
- Discovery from genuinely new surface (new user feedback post-publication)
- Defect introduced by post-publication change (separate from merge)
- Defect only visible with new tools/permissions not available during audit
- External service change (link breakage due to third-party change)

### Evidence Required

Gate escape claims require:

1. Material defect description
2. Observable surface where detectable (S2/S4/S5/S6/S7)
3. Evidence it was detectable pre-merge
4. Why prepublication audit did not catch it
5. Root cause in gate process

---

## SECTION 20 — MINIMUM_AUDIT_RECORD_COLLECTION (R4 - References Canonical Template)

### Canonical Template Reference

All audit records MUST conform to the **Canonical Audit Record Template** defined in **Section 5.**

Do NOT create alternative or divergent audit record definitions. Use the Section 5 template for every material audit finding.

### Audit Record Checklist

When recording an audit result, verify it includes:

- [ ] Audit_ID (unique identifier)
- [ ] Artifact (what is audited)
- [ ] Artifact_Ref / SHA (version/commit)
- [ ] Claim_ID (per R5 convention)
- [ ] Claim (specific assertion)
- [ ] Claim_Surface_ID (authoritative surface for this claim)
- [ ] Declared_Audit_Surface_ID (declared scope)
- [ ] Actual_Audit_Surface_ID (actual scope)
- [ ] Auditor_Role (role, not vendor)
- [ ] Evidence_Type (documentary/technical/observational)
- [ ] Evidence_Result (E+ / E- / NO_DEMOSTRADO / STALE)
- [ ] Claim_Reconciliation_State (CONTRADICTORY if multiple incompatible findings)
- [ ] Audit_Execution_State (AUDIT_SCOPE_COMPLIANT / AUDIT_SCOPE_BREACH)
- [ ] Evidence_Admissibility (OUT_OF_SCOPE / ADMISSIBLE / REQUIRES_REAUDIT)
- [ ] Timestamp (when audit occurred)
- [ ] Scope (what is included)
- [ ] Limitations (what is not covered)
- [ ] Reconciliation_Notes (conflicts with other audits)
- [ ] Gate_Impact (PASS / CONDITIONAL / FAIL)

### Prepublication Matrix Template

Summarize multiple audit findings for quick reconciliation:

```text
Claim_ID | S2_Result | S4_Result | S5_Result | S6_Result | S8_Decision | Reconciled | Gate
---------|-----------|-----------|-----------|-----------|-------------|------------|------
CLAIM-001| E+        | E+        | E+        | —         | APPROVE     | YES        | PASS
CLAIM-002| E+        | E+        | NO_DEM    | —         | CONDITIONAL | REVIEW     | HOLD
CLAIM-003| E+        | E+        | E-        | —         | ESCALATE    | NO         | FAIL
```

### Archive Requirements

Maintain:
- Complete audit record for each material claim using canonical template
- Divergence reconciliation notes
- Gate decision documentation
- Post-publication verification results
- Any gate escapes discovered and addressed
- Timeline for each state transition

---

---

## SECTION 21 — FAIL_CLOSED_CONDITIONS (R8 - Waiver Governance)

Publication MUST STOP on any of:

1. **AUDIT_INVALIDATED_BY_CHANGE** — Candidate SHA changed after audit
2. **UNRESOLVED_AUDIT_DIVERGENCE** — Material findings contradict; reconciliation incomplete
3. **SENSITIVE_INFORMATION_FINDING** — Secrets/credentials discovered in S5
4. **SURFACE_PARITY_FAIL** — Incompatible current-state claims on expected surfaces
5. **EXTERNAL_CANDIDATE_NOT_OBSERVABLE** — Public artifact not visible where required (S5)
6. **UNCLEAR_HUMAN_AUTHORITY** — Gate decision missing, contradictory, or ambiguous
7. **FAILED_REQUIRED_CHECKS** — CI/CD checks, security scans, automated gates fail
8. **SCOPE_CHANGED_AFTER_APPROVAL** — Candidate diff expands beyond approved scope

### Rule: `PUBLICATION_GATE_FAIL_CLOSED`

Do not silently waive, average, or defer failures.

If any fail condition exists:

- ❌ Do NOT merge
- ❌ Do NOT commit to canonical destination
- ❌ Do NOT declare canonical
- ✓ DO escalate to human authority
- ✓ DO document failure cause
- ✓ DO require explicit waiver (rare) or correction (normal)

### Fail-Closed Waiver Governance (R8)

Certain fail conditions CANNOT be waived by automated agents or casual process waiver.

**Conditions Requiring Mandatory Remediation (NOT waivable):**

1. **SENSITIVE_INFORMATION_FINDING** — Secrets/credentials must be removed from artifact before publication
2. **AUDIT_INVALIDATED_BY_CHANGE** — Changed candidate requires re-audit before proceeding
3. **UNCLEAR_HUMAN_AUTHORITY** — Authority decision must be clarified, recorded, and traceable

For these conditions:

- No agent-level waiver is valid
- Human authority must explicitly decide remediation path
- Record must identify artifact/SHA, condition, human authority, rationale, scope, and any conditions/expiration

**Conditions That MAY Require Waiver (rare circumstances):**

1. **UNRESOLVED_AUDIT_DIVERGENCE** — If surface analysis determines findings are compatible/"different-surface truths"
2. **SURFACE_PARITY_FAIL** — If analysis determines inconsistency is out-of-scope or acceptable in context
3. **EXTERNAL_CANDIDATE_NOT_OBSERVABLE** — If determined to be deployment limitation, not publication defect

For these conditions:

- Explicit human governance authority must approve waiver
- Decision record must include: artifact SHA, condition, rationale, scope, explicit authority identity, timestamp
- Waiver does NOT rewrite evidence; it documents governance decision
- Waiver applies ONLY to the specific artifact SHA; new candidate changes require new authorization

**Conditions That CANNOT Be Waived (absolute):**

1. **SENSITIVE_INFORMATION_FINDING** — Remediation required, waiver not an option
2. **AUDIT_INVALIDATED_BY_CHANGE** — Re-audit required, waiver not an option
3. **UNCLEAR_HUMAN_AUTHORITY** — Authority must be clarified, not waived

### Material Scope Breach Fail-Closed Condition

`UNRESOLVED_MATERIAL_AUDIT_SCOPE_BREACH`

Publication must stop when:

- an audit used undeclared evidence surfaces;
- the affected claims are material to the publication gate;
- and provenance/admissibility has not been reconciled.

Determination of "material" is made by:
- Gate authority's judgment considering the specific claims at risk
- Whether alternative authorized evidence is available for the material claims
- Whether scope breach represents isolated versus systemic audit contamination

Do not make every trivial scope deviation automatically block publication. The condition is material, unresolved, and affects critical claims.

---

---

## SECTION 22 — RELATIONSHIP_TO_EXISTING_GOVERNANCE (R7 - SAD_009 and Surface Validation)

### SAD_009 Surface-First Principle (Governance-Core.md)

SAD_009 establishes: **Superficies declaradas antes que operacion**

(Declared surfaces before operation)

This principle requires:

```
PRECHECK
   ↓
PREPARE
   ↓
VERIFY
   ↓
OPERATE
```

**Why SAD_009 Matters:**

No process should assume a surface satisfies a contract without bounded validation under declared governance scope.

### Surface Validation Protocol (protocols/surface-validation-protocol.md)

The **Surface Validation Protocol** operationalizes SAD_009 for **operational and data surfaces.**

It defines pre-operational validation discipline for governed surfaces before deployment/operation begins.

### How This Audit Protocol Extends SAD_009

This **Audit Surfaces and Prepublication Gates Protocol** EXTENDS the surface-first discipline to **audit and evidence observation surfaces.**

**Relationship:**

| Artifact | Applies To | Principle | Cycle |
|---|---|---|---|
| SAD_009 (Governance-Core) | All surfaces | Surfaces before operation | General |
| Surface Validation Protocol | Operational/data surfaces | Pre-op validation gate | PRECHECK→PREPARE→VERIFY→OPERATE |
| This Audit Surfaces Protocol | Evidence/observation surfaces | Pre-publication validation gate | LOCAL→AUDITED→REMOTE→EXTERNAL→RECONCILED→GATE→CANONICAL |

**Key Point:** These are related but NOT interchangeable.

- SAD_009 provides the foundational principle
- Surface Validation Protocol governs operational surface contracts before deployment
- This Audit Surfaces Protocol governs evidence surface integrity before canonical publication

All three work together in the same governance discipline: **declare surfaces, validate governance, operate only after verification.**

**This Protocol Does NOT:**

- Redefine or replace SAD_009
- Modify Surface Validation Protocol requirements
- Blur the boundary between operational validation and evidence validation

### This Protocol

- **Inherits** Framework governance principles (governance-first, surface-first)
- **Extends** repository-governance-standard promotion discipline
- **Implements** SAD_009 Surface-First Principle for audit/evidence surfaces
- **Relates to** Surface Validation Protocol (complementary, not competing)
- **Does NOT replace** Runtime Governance
- **Does NOT replace** Administrative Audit
- **Does NOT replace** domain-specific evidence requirements
- **Does NOT make** private artifacts public
- **Does NOT redefine** human authority

### Governance Inheritance Chain

```
SAD Framework Principles (Governance-Core, SAD_009)
   ↓
Surface Validation Protocol (Operational/Data Surfaces)
   ↓
Repository Governance Standard (Promotion/Audit Roles)
   ↓
Audit Surfaces and Prepublication Gates Protocol (Evidence Validation)
   ↓
Domain Implementation (Specific Repos, Connectors, Runtime)
```

### Relation to Evidence Principles

Inherits from governance-core.md:

- `E+` / `E-` evidence distinction
- Surface-first principle (SAD_009)
- Bounded omission detection (only where scope defined)
- Institutional continuity requirement

Extends through this protocol:

- Explicit surface-parity verification across multiple audit surfaces
- Audit divergence reconciliation (not majority vote, but claim-level analysis)
- Cross-surface authority mapping (which surface governs which claim)
- Human publication gate formalization (explicit authority required)

---

## INTEGRATION WITH EXISTING FRAMEWORK

This protocol is integrated into the Framework governance discovery path via reference in [repository-governance-standard.md](repository-governance-standard.md), which already governs promotion discipline.

**Discovery Path:**

`governance-core.md` (L1 principles: SAD_009 Surface-First)
→ `protocols/surface-validation-protocol.md` (operational surface validation)
→ `repository-governance-standard.md` (promotion/audit roles)
→ `SAD_AUDIT_SURFACES_AND_PROMOTION_GATES_V1.md` (prepublication gates for evidence surfaces) ← **NEW**

**Evidence Basis:**

The governance necessity and learning underlying this protocol is documented in:

→ `reports/SAD_AUDIT_SURFACES_PROTOCOL_V1_EVIDENCE_BASIS_2026-08-05.md`

---

## PROTOCOL STATUS

**Status:** DRAFT — CANDIDATE FOR HUMAN RATIFICATION

**Candidate Distribution State:** PUBLISHED_CANDIDATE_BRANCH

**Canonical Status:** NOT CANONICAL

**Ratification Status:** NOT RATIFIED

**Candidate SHA:** `cdecbbac658d3cc4c66a04dcd3f3d816a8216b4f` (before reconciliation)

**Next Phase:** Evidence reconciliation addressing pre-ratification findings (R1–R14) before human ratification decision

**First Test Case:** This protocol will govern the remediation of identified SAD-MORON Architecture V1 public-surface defects as the initial real-world application before full institutional adoption.

**Validation State:** EVIDENCE RECONCILIATION IN PROGRESS

This protocol remains a local candidate pending reconciliation completion and human governance authority ratification decision.
The complete discipline defined by this protocol has NOT yet been completed.
Further audit and reconciliation are required before any canonical publication.
