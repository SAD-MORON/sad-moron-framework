# SAD Audit Surfaces and Prepublication Gates Protocol V1

## Status

**DRAFT — CANDIDATE FOR HUMAN RATIFICATION**

This document is a normative governance protocol governing evidence collection, audit surfaces, independent interconsultation, and prepublication validation. It is NOT canonical until ratified through the discipline it defines.

**Publication State:** LOCAL_COMMIT_ONLY

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

## SECTION 3 — AUDIT SURFACE TAXONOMY

### S1 — LOCAL_FILESYSTEM

**Observation Scope:**
- working files
- local WIP
- untracked artifacts
- local configuration boundaries
- uncommitted changes

**Authority:** Authorship/development view

**Limitations:**
- Cannot establish public state
- Cannot determine remote publication status
- Cannot observe third-party interpretation

---

### S2 — LOCAL_GIT

**Observation Scope:**
- commits
- branches
- ancestry
- diff content
- ahead/behind tracking
- dirty state
- commit messages
- branch history

**Authority:** Local repository history

**Limitations:**
- Cannot establish external public interpretation
- Cannot verify remote branch state (must fetch)
- Does not demonstrate public visibility

---

### S3 — REMOTE_GIT

**Observation Scope:**
- actual remote refs
- origin/main
- published branches
- remote commit ancestry
- remote branch HEAD
- published diff

**Authority:** Remote repository state of record

**Critical Distinction:**

`PUBLISHED_TO_ORIGIN_BRANCH` ≠ `PUBLISHED_TO_ORIGIN_MAIN`

A branch can be pushed to remote without being merged to canonical destination.

**Limitations:**
- Does not demonstrate public unauthenticated visibility
- Does not verify external link resolution
- Does not establish public comprehension

---

### S4 — CANDIDATE_PR

**Observation Scope:**
- exact candidate diff (base vs head)
- base/head commit SHA
- PR checks status
- mergeability assessment
- candidate scope boundary
- PR metadata (title, description)

**Authority:** Candidate proposal state

**Important:** A PR is a CANDIDATE surface, not canonical publication.

**Limitations:**
- Candidate HEAD may change (invalidates prior audits)
- PR closure does not determine canonical status
- PR merge authority differs from PR creation authority

---

### S5 — PUBLIC_UNAUTHENTICATED_SURFACE

**Observation Scope (What independent third party observes without private access):**
- GitHub landing pages and metadata
- public README rendering
- public branch HEAD content
- public links and navigation
- repository descriptions
- public-facing visibility status
- external discoverability
- rendered documentation on public views
- public section contradictions

**Authority:** PRIMARY for claims about:
- public discoverability
- external comprehension
- public links
- public repository visibility
- public-facing contradictions
- external observer experience

**Limitations:**
- Cannot observe private repository content
- Cannot infer private-only status from S5 absence
- Cannot determine private implementation detail from public absence

---

### S6 — PRIVATE_AUTHORIZED_SURFACE

**Observation Scope:**
- authorized observation of private repositories
- private governance surfaces
- Labs environments
- restricted evidence
- authorized-only implementation details
- institutional private records

**Authority:** PRIMARY for claims about private artifact status within authorized scope

**Important:** Private ≠ unaudited. Private ≠ unreviewed.

**Limitations:**
- Absence from S5 does NOT imply S6 absence
- S5 invisibility is not evidence against S6 existence
- Public absence cannot be used to infer private state

---

### S7 — RUNTIME_SURFACE

**Observation Scope:**
- controlled test execution
- telemetry observation
- runtime evidence collection
- actual response/result from execution
- observable state changes
- call sequences
- timing/performance

**Authority:** PRIMARY for claims about:
- actual execution behavior
- runtime correctness (technical, not institutional)
- observable effects
- performance characteristics

**Important:** Must remain separate from Administrative Audit surface.

**Limitations:**
- Does not establish institutional authority
- Does not prove administrative oversight
- Success does not imply approval

---

### S8 — HUMAN_INSTITUTIONAL_SURFACE

**Observation Scope:**
- human ratification decision
- promotion authorization
- institutional authority
- administrative decision
- approval/rejection
- formal governance act
- institutional accountability

**Authority:** PRIMARY for claims about:
- canonical promotion
- institutional adoption
- formal ratification
- governance authority

**Limitations:**
- Git status cannot manufacture human authority
- Merge permission does not guarantee ratification
- Authority must be explicit and traceable

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

## SECTION 5 — AUDIT CLAIM CONTRACT

Every material audit finding should identify:

```text
Audit_ID:                          [unique identifier]
Artifact:                          [what is being audited]
Artifact_Ref / SHA:                [version/commit/reference]
Claim_ID:                          [standardized claim type]
Claim:                             [specific assertion]
Declared_Surface_ID:               [surface(s) authorized for this audit]
Actual_Surface_ID:                  [surface(s) actually used]
Surface_ID:                        [S1/S2/S3/S4/S5/S6/S7/S8]
Auditor_Role:                      [role, not vendor]
Evidence_Type:                     [documentary/technical/observational/etc]
Result:                            [E+/E-/NO_DEMOSTRADO/CONTRADICTORY/STALE]
Timestamp:                         [when audit occurred]
Scope:                             [what is and is not included]
Limitations:                       [what this audit does NOT cover]
Divergence:                        [notes on conflicts with other audits]
```

### Evidence Result Taxonomy

- `E+` — Explicit evidence of presence in declared source or review artifact
- `E-` — Verified absence of expected record under declared scope
- `NO_DEMOSTRADO` — Cannot determine (evidence insufficient, surface inaccessible, scope unclear)
- `CONTRADICTORY` — Different audit found opposite result
- `STALE` — Evidence was valid at timestamp but may be invalidated by subsequent change
- `AUDIT_SCOPE_COMPLIANT` — Evidence stayed within the declared audit scope
- `AUDIT_SCOPE_BREACH` — Audit used undeclared evidence surface, source, or permission context
- `OUT_OF_SCOPE_EVIDENCE` — Evidence obtained outside the declared scope
- `CLAIM_EVIDENCE_ADMISSIBLE` — Claim is supported entirely by authorized evidence
- `CLAIM_REQUIRES_REAUDIT` — Claim cannot be relied on until scoped audit is repeated

### Important Principle

Absence of evidence is NOT evidence of absence.

Do not collapse:
- `E-` (verified absence)
- `NO_DEMOSTRADO` (unknown)
- `CONTRADICTORY` (conflicting findings)
- `STALE` (changed since audit)

Each has different governance implications.

### Audit Scope Provenance

An audit must preserve evidence provenance by recording both the declared scope and the actual evidence used.

Required scope provenance fields:

- `Declared_Surface_ID`
- `Actual_Surface_ID`

### Scope Breach Rule

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

## SECTION 6 — AUDITOR ROLE ≠ AUDIT SURFACE

### Core Principle

Changing the AI model, agent, or toolchain does NOT by itself create independent evidence.

### Independence Requirements

Independence may require differences in:
- observation surface (S2 vs S5, not two S2 observations)
- evidence source (different tools/witnesses)
- authorization context (different permission sets)
- audit toolchain (different implementations)
- prior assumptions (different baseline knowledge)

### Invalid Independence Claim

❌ Two agents reading the same local working tree = two independent audits
❌ Claude audit + Copilot audit of same S2 = surface diversity

### Valid Independence Claim

✓ Local Git auditor (S2) + Unauthenticated public-surface auditor (S5) + Runtime observer (S7)
✓ Same auditor on different surfaces at different times
✓ Different authorized observers on S6 private surface

### Language Requirement

- Use generic roles: "internal developer auditor", "independent surface observer", "authorized Labs reviewer"
- Do NOT use vendor/model names as normative governance dependencies
- Vendor names appear only as non-normative examples when necessary

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

## SECTION 10 — PROMOTION STATE MACHINE

```
LOCAL_CANDIDATE
      ↓
INTERNAL_AUDITED_CANDIDATE
      ↓
PUBLISHED_CANDIDATE_BRANCH
      ↓
REMOTE_PR_AUDITED
      ↓
EXTERNAL_SURFACE_AUDITED
      ↓
EVIDENCE_RECONCILED
      ↓
READY_FOR_HUMAN_PUBLICATION_GATE
      ↓
PUBLISHED_TO_ORIGIN_MAIN
      ↓
POST_PUBLICATION_VERIFIED
```

### State Descriptions

**LOCAL_CANDIDATE:** Artifact created locally, not yet reviewed or tested

**INTERNAL_AUDITED_CANDIDATE:** Artifact audited on local surfaces (S1/S2); ready for collaboration

**PUBLISHED_CANDIDATE_BRANCH:** Candidate branch pushed to origin (S3); creates S4 PR opportunity

**REMOTE_PR_AUDITED:** PR created and audited; exact diff frozen; checks validated

**EXTERNAL_SURFACE_AUDITED:** Independent unauthenticated S5 audit (for public) or authorized S6 audit (for private) complete

**EVIDENCE_RECONCILED:** All audit findings reviewed; divergences resolved; surface parity confirmed

**READY_FOR_HUMAN_PUBLICATION_GATE:** All required evidence collected; waiting for human authority decision

**PUBLISHED_TO_ORIGIN_MAIN:** Merge completed; candidate is now canonical

**POST_PUBLICATION_VERIFIED:** Integrity check confirms published state matches audited candidate; no escapes detected

### Private Artifact Equivalent

For private canonical destinations, replace EXTERNAL_SURFACE_AUDITED with independent authorized S6 audit appropriate to classification.

Principle: **Auditability does not require violating confidentiality.**

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

## SECTION 20 — MINIMUM_AUDIT_RECORD_TEMPLATE

### Individual Audit Record

```text
Audit_ID:                          [unique: AUDIT-2026-08-05-001]
Artifact:                          [what is audited]
Artifact_Ref:                      [commit SHA / document version]
Claim_ID:                          [CLAIM-STATUS / CLAIM-COMPLETENESS]
Claim:                             [Specific assertion being audited]
Surface_ID:                        [S2 / S5 / S6 / etc]
Auditor_Role:                      [e.g., independent external observer]
Evidence:                          [specific finding]
Evidence_Result:                   [E+ / E- / NO_DEMOSTRADO / CONTRADICTORY / STALE]
Timestamp:                         [2026-08-05T11:30:00Z]
Scope:                             [what was included in audit]
Limitations:                       [what was out of scope]
Divergence_Notes:                  [conflicts with other audit findings]
Gate_Impact:                       [PASS / CONDITIONAL / FAIL]
```

### Prepublication Matrix Template

```text
Claim_ID | S2_Result | S4_Result | S5_Result | S6_Result | S8_Decision | Reconciled | Gate
---------|-----------|-----------|-----------|-----------|-------------|------------|------
CLAIM-001| E+        | E+        | E+        | —         | APPROVE     | YES        | PASS
CLAIM-002| E+        | E+        | NO_DEM    | —         | CONDITIONAL | REVIEW     | HOLD
CLAIM-003| E+        | E+        | E-        | —         | ESCALATE    | NO         | FAIL
```

### Archive Requirements

Maintain:
- Complete audit record for each material claim
- Divergence reconciliation notes
- Gate decision documentation
- Post-publication verification results
- Any gate escapes discovered and addressed
- Timeline for each state transition

---

## SECTION 21 — FAIL_CLOSED_CONDITIONS

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
- ❌ Do NOT commit to main
- ❌ Do NOT declare canonical
- ✓ DO escalate to human authority
- ✓ DO document failure cause
- ✓ DO require explicit waiver (rare) or correction (normal)

### Material Scope Breach Fail-Closed Condition

`UNRESOLVED_MATERIAL_AUDIT_SCOPE_BREACH`

Publication must stop when:

- an audit used undeclared evidence surfaces;
- the affected claims are material to the publication gate;
- and provenance/admissibility has not been reconciled.

Do not make every trivial scope deviation automatically block publication. The condition is material and unresolved.

---

## SECTION 22 — RELATIONSHIP_TO_EXISTING_GOVERNANCE

### This Protocol

- **Inherits** Framework governance principles (governance-first, surface-first)
- **Extends** repository-governance-standard promotion discipline
- **Implements** SAD_009 Surface-First Principle prepublication gates
- **Does NOT replace** Runtime Governance
- **Does NOT replace** Administrative Audit
- **Does NOT replace** domain-specific evidence requirements
- **Does NOT make** private artifacts public
- **Does NOT redefine** human authority

### Governance Inheritance Chain

```
SAD Framework (governance-core)
  ↓
Repository Governance Standard (promotion/audit roles)
  ↓
Audit Surfaces and Prepublication Gates (multi-surface validation)
  ↓
Domain Implementation (specific repos, connectors, etc.)
```

### Relation to Evidence Principles

Inherits:

- `E+` / `E-` evidence distinction from governance-core
- Surface-first principle (SAD_009)
- Bounded omission detection (only where scope defined)
- Institutional continuity requirement

Extends:

- Explicit surface-parity verification
- Audit divergence reconciliation
- Cross-surface authority mapping
- Human publication gate formalization

---

## INTEGRATION WITH EXISTING FRAMEWORK

This protocol is integrated into the Framework governance discovery path via reference in [repository-governance-standard.md](repository-governance-standard.md), which already governs promotion discipline.

**Discovery Path:**

`governance-core.md` (L1 principles)
→ `repository-governance-standard.md` (promotion/audit roles)
→ `SAD_AUDIT_SURFACES_AND_PROMOTION_GATES_V1.md` (prepublication gates) ← **NEW**

---

## PROTOCOL STATUS

**Status:** DRAFT — CANDIDATE FOR HUMAN RATIFICATION

**Publication State:** LOCAL_COMMIT_ONLY

**Next Phase:** Internal review / interconsultation before any public branch publication

**First Remediation Case:** This protocol will be applied to fix identified SAD-MORON Architecture V1 public-surface defects as the initial prepublication test case.

**Validation State:** PREPUBLICATION INTERCONSULTATION IN PROGRESS

This protocol remains a local candidate.
The complete discipline defined by this protocol has NOT yet been completed.
Further audit and reconciliation are required before any canonical publication.
