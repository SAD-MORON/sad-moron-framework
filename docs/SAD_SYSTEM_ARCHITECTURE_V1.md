# SAD-MORON — System Architecture V1

## Status

**DRAFT — PENDING HUMAN RATIFICATION**

- version: V1
- scope: governance infrastructure and repository roles within SAD-MORON ecosystem
- evidence basis: demonstrated repository posture + ratified human decisions from this alignment initiative
- publication state: LOCAL_ONLY — the architecture draft and supporting alignment commits have not yet been promoted or pushed to their governed origin branches
- ratification: awaiting institutional review

---

## Executive Summary

SAD-MORON is a governance-oriented digital pilot for the Secretaría de Asuntos Docentes de Morón, designed so that its governance contracts may support future evolution or reuse without implying official provincial adoption.

SAD-MORON is NOT a single monolithic application. It is an ecosystem of:

1. **Shared Governance Infrastructure** — reusable contracts and principles that may serve multiple administrative systems
2. **Administrative Bounded Contexts** — separate domain systems consuming governance infrastructure without sharing code or operational state
3. **Private Pilot Laboratory** — experimentation and validation environment before promotion to governed destinations
4. **Operational and Data Infrastructure** — implementation-specific deployments, configurations, and real data (currently private or pending definition)
5. **Institutional Sources** — real administrative sources that populate normalized models
6. **Human Authority Boundaries** — explicit human decision gates where administrative consequences require human oversight

---

## 1. Core Architectural Principle

> Shared governance infrastructure may serve multiple administrative systems, while each administrative system preserves its own domain logic and authority boundaries.

This principle enables:

- reuse of governance contracts across multiple contexts
- evolution of each bounded system without silent redefinition of shared concepts
- auditability of decisions at both governance and administrative levels
- interoperability without forced integration

---

## 2. Governance Infrastructure vs. Operational Infrastructure

### RATIFIED HUMAN DECISION

SAD-MORON separates **governance infrastructure** from **operational and data infrastructure**.

**Governance Infrastructure** comprises reusable and auditable contracts, principles, boundaries, schemas, protocols, authority conditions and evidence requirements. This layer defines the conditions under which systems and processes may be considered governed.

Includes:

- governance principles and primitives
- authority and access contracts
- source and connector contracts
- runtime governance rules
- implementation governance rules
- reusable schemas and data models
- communication protocols
- taxonomies and vocabularies
- evidence and audit requirements
- synthetic examples for guidance
- architectural constraints

Governance infrastructure **may be publicly auditable** when information classification permits it. Public auditability is an optional classification decision independent from the governance layer itself. However, any publicly accessible governance artifacts must not expose information that permits unauthorized reconstruction, access or compromise of operational infrastructure or institutional data.

**Operational and Data Infrastructure** contains the concrete deployments, institutional configurations, real mappings, sensitive integrations, source identifiers, operational data and other restricted implementation material required to operate specific systems under declared governance.

Includes:

- production deployments and runtimes
- real institutional source mappings
- real source identifiers and endpoints
- environment-specific configuration
- real institutional snapshots
- administrative and personal data
- sensitive integrations and adapters
- operational telemetry and logs

Operational infrastructure requires access controls bounded by institutional authorization and information sensitivity. Secrets and credentials must remain outside version control regardless of repository classification.

**RATIFIED PRINCIPLE: Promotion does not imply publication.**

Promotion of a governance or operational artifact means its incorporation into a governed destination. The access classification and public auditability of that destination are independent decisions from the promotion decision itself.

---

## 3. Current Repository Map

### DEMONSTRATED CURRENT STATE

#### SAD-MORON-FRAMEWORK

**Role:**

- canonical governance anchor for all other SAD repositories
- defines bounded governance principles and scope
- establishes governance inheritance chain from Janus Core
- defines repository governance standard for future SAD repositories
- preserves institutional continuity and auditability boundaries

**Executes administrative logic?** NO

**Operational secrets?** NO — explicitly excludes production configuration and credentials

**Current status:** DEMONSTRATED — public repository, governance-first, fully documented

**Evidence:** Repository posture verified in `README.md`, `docs/governance-core.md`, `docs/scope-and-boundaries.md`, `docs/repository-governance-standard.md`

---

#### SAD-MORON-ACCESS-GOVERNANCE

**Role:**

- defines identity governance contracts without implementing concrete authentication
- governs access, roles, permissions, and electronic acceptance
- establishes identity model where external institutional identity (Google Workspace, ABC) remains authoritative
- documents authority boundaries for access-related decisions
- preserves auditability and institutional continuity

**Identity model principle:**

- Google Workspace and ABC identity remain the primary identity boundary
- this repository does NOT replace, supersede, or re-register institutional identity
- local roles and permissions map to external identity assertions rather than duplicate them
- identity interpretation must remain institutionally transferable

**Does NOT implement:** concrete authentication, password/token management, credential storage, identity replacement

**Executes administrative logic?** NO — documentation and governance layer only

**Operational secrets?** NO — explicitly excludes credentials and personal data

**Current status:** DEMONSTRATED — PUBLIC governance infrastructure, governance-first, fully documented

**Evidence:** Repository posture verified in `README.md`, `docs/identity-model.md`, `docs/electronic-acceptance-boundary.md`

---

#### SAD-MORON-CONNECTORS

**Role:**

- defines connector contracts and source boundaries before operational implementation
- establishes integration compliance packs and evidence expectations
- governs source-specific adaptation without prescribing connector implementation
- preserves audit and governance requirements for future connector operationalization

**Connector contract principles:**

- every connector must declare source scope, temporal boundary, institutional justification
- every connector must remain bounded by declared governance rules
- every connector must maintain reviewable human authorization points
- connector-layer artifacts cannot redefine inherited governance meaning

**Does NOT contain:** operational connectors, APIs, executable integrations, credential flows, scraping logic

**Does NOT introduce:** runtime services, Apps Script, deployment configuration

**Executes administrative logic?** NO — planning and contract layer only

**Operational secrets?** NO — governance packs and synthetic examples only

**Current status:** DEMONSTRATED — PUBLIC governance infrastructure, governance-first, fully documented

**Evidence:** Repository posture verified in `README.md`, `docs/connector-layer-boundary.md`, `docs/connector-public-private-boundary.md`

---

#### SAD-MORON-APPSCRIPT

**Role:**

- establishes governance and implementation patterns for bounded Google Apps Script implementations
- documents technical boundaries and deployment governance for scripts
- provides scaffolding and reference implementations for governed Apps Script contexts
- preserves audit expectations and execution governance

**Implementation scope:**

- NOT claiming that all Apps Script code for SAD must live here
- NOT claiming to be the sole Apps Script layer
- defines governance-first patterns for any Apps Script implementation within SAD governance
- provides documentation, reference patterns, and boundary mapping

**Does NOT contain:** production credentials, production Sheet IDs, production Script IDs, production deployment configuration

**Does NOT assume:** that scaffold code becomes production runtime automatically

**Executes administrative logic?** PARTIALLY DEMONSTRATED — reference implementations only, with audit boundaries clearly marked

**Operational secrets?** NO — explicitly excludes production identifiers and configuration

**Current status:** DEMONSTRATED — PUBLIC governance infrastructure, governance-first documentation with reference patterns, full audit boundaries documented

**Evidence:** Repository posture verified in `README.md`, `docs/deployment-boundaries.md`, `docs/script-id-governance.md`, `docs/governance-boundary-map.md`

---

#### SAD-MORON-RUNTIMES

**Role (from Step 1 alignment):**

Runtime Governance establishes the contracts, boundaries, technical identity, execution conditions and observable evidence that a system must satisfy to be considered a governed execution within the SAD-MORON ecosystem.

**Runtime Governance defines:** technical execution contracts, authority and surface boundaries, execution limits, observable evidence requirements, verifiable results

**Runtime Governance does NOT:**
- implement the business engine
- define administrative processes
- implement the connector layer
- implement data normalization pipelines
- replace technology selection (Apps Script, Python, Java, etc.)
- replace administrative audit

**Distinguishes explicitly:**

| Concept | Question answered | Responsibility |
|---------|-------------------|-----------------|
| **Runtime Evidence** | What did the software execute, under what conditions, with what observable result? | System behavior documentation |
| **Administrative Audit** | What happened administratively, who acted, under what authority, with what evidence? | Institutional review and accountability |

**Current status:** RATIFIED DECISION / LOCAL_ONLY — definition established in Step 1 alignment, awaiting external ratification

**Evidence:** Documented in SAD-MORON-RUNTIMES `docs/runtime-scope.md` and cross-referenced governance documents

---

### UNRESOLVED: Operational Implementation Layer

The following remain **FUTURE / UNDEFINED**:

- destination and governance model for operational runtime implementations
- physical deployment architecture (servers, containers, cloud services)
- real authentication integration with ABC or institutional identity provider
- complete operational data pipeline
- repository or repositories for operational connectors

These are intentionally deferred pending:
- stakeholder alignment
- resource allocation
- institutional authorization
- security review

---

## 4. Private Pilot Laboratory

### RATIFIED HUMAN DECISION

**SAD-MORON-LABS** is a private repository for pilot laboratory.

**Purpose:** experimentation → integration → validation → evidence production → human promotion decision → governed destination

**Current status:** RATIFIED DECISION / LOCAL_ONLY — role established in Step 2 alignment

**Key principles:**

- A pilot remains a pilot until explicitly promoted by human decision
- presence of executable code does NOT contradict the pilot character
- multiple pilots can coexist without sharing domain logic, runtime state, or administrative authority
- pilot maturity is independent from promotion authority

**Promotion gate:**

Human review and decision determine:
- whether pilot evidence is sufficient
- whether pilot is ready for promotion
- what destination the pilot moves to (public governance, private operational, or other)
- what classification and access model applies to the promoted artifact

> Promotion does not imply publication.

Promotion means incorporation to a governed destination. The public/private classification of that destination is a separate decision from the promotion decision.

**Current evidence:** pilot laboratory contains bounded administrative contexts under development, including functional pilotos that remain operationally exercised pilots until explicit promotion

**NO claim:** that any pilot in Labs constitutes production or achieves official adoption

---

## 5. Administrative Bounded Contexts

Administrative processes consuming the shared governance infrastructure remain separate bounded contexts that preserve:

- distinct domain logic
- separate operational state
- independent authority models
- specialized administrative workflows
- distinct audit trails

### DEMONSTRATED CURRENT STATE

#### 5650 — Educational Administrative Process

**Status:** pilot, under development and validation within Labs

**Evidence base:** operational code and workflow scaffolding in Labs demonstrate bounded context for 5650-related administration

**Administrative authority:** separate from other SAD-MORON processes

**Relationship to other contexts:** intentionally separate; no shared domain logic or runtime state with Art.109 or other processes

**Production claim?** NO — explicitly maintained as pilot until promotion decision

**Integration claim?** NO — no designed integration with Art.109 or other bounded contexts at this stage

---

#### Art.109 — Separate Administrative Domain

**Status:** separate bounded administrative context, may eventually align with shared SAD-MORON governance infrastructure

**Current evidence:** distinct process rules and authority model

**Relationship to other contexts:** intentionally separate from 5650 and other contexts at this stage

**NO current contract:** shared domain logic or runtime state with 5650 or other bounded contexts

**Integration claim?** NO — explicitly NOT designed for integration in current architecture

**Future alignment:** Art.109 may eventually consume the same governance infrastructure as other SAD-MORON processes WITHOUT necessarily sharing operational state, code, or administrative authority

**Evidence for future coexistence:** both 5650 and Art.109 can separately inherit governance infrastructure while preserving distinct administrative identities

---

#### Future Administrative Processes

The same pattern applies to any future bounded administrative context:

- consumes shared governance infrastructure
- preserves distinct domain logic
- maintains separate administrative authority
- remains independent unless explicit integration is justified and ratified

---

## 6. Governance Layers vs. Administrative Systems

```
                        SHARED GOVERNANCE LAYERS
                               │
                    ┌──────────┼──────────┐
                    ▼          ▼          ▼
                  5650      Art.109    Future
                    │          │         │
                    └── separate bounded contexts ───┘

                      (each consuming governance
                       layers without sharing
                       operational state)
```

Governance infrastructure includes:

- Governance principles and primitives (Framework)
- Access and identity contracts (Access Governance)
- Source and connector contracts (Connectors)
- Runtime execution contracts (Runtimes)
- Technology implementation governance (AppScript, future implementations)
- Evidence and audit contracts (across all layers)

Administrative systems are the bounded contexts (5650, Art.109, future processes) that consume these layers while preserving their own:

- domain-specific logic
- process-specific state
- authority boundaries
- administrative evidence

---

## 7. Institutional Sources and Snapshots

### Architectural Pattern

```
Institutional Source
          │
          ▼
   Authorized Source Registry
          │
          ▼
   Read-only Acquisition
          │
          ▼
   Raw Versioned Snapshot
          │
          ▼
Sanitization / Minimization
          │
          ▼
    Usable Snapshot
          │
          ▼
Adapter / Normalization
          │
          ▼
Reconciliation / Validation
          │
          ▼
Human or Governed Promotion
          │
          ▼
Operational Normalized Model
```

### DEMONSTRATED / FUTURE

- Current evidence: Framework defines declared-sources discipline
- Connectors establish source boundaries and adaptation contracts
- Operational pipeline (data normalization, validation) remains FUTURE / NOT DEMONSTRATED

### Key Principle

> A newer snapshot does not automatically acquire operational authority merely because it is newer.

Distinguish:

- **latest observed** — most recent snapshot acquired from source
- **latest valid** — most recent snapshot passing reconciliation/validation
- **latest promoted** — most recent snapshot approved for operational use by human authority

Each has different evidentiary standing. A newer observation does not supersede an older validation or promotion unless explicitly reviewed.

---

## 8. Explicit Uncertainty

### Architectural Principle

> Absence of evidence is not evidence of absence.

The system must NOT convert:

- missing information
- contradictory data
- stale observations
- unresolved questions

into artificial certainty.

### Classification Framework

When evidence is absent or conflicting, classify as:

- **unknown** — no data available
- **negative** — evidence demonstrates absence of something
- **contradictory** — multiple sources present incompatible claims
- **stale** — evidence is old or conditions may have changed

Do NOT coerce these into false certainty.

Preserve ambiguity when appropriate; escalate to human authority when administrative consequences would follow.

---

## 9. Identity Architecture

### Conceptual Flow

```
External Institutional Identity Provider (ABC, Google Workspace)
          │
          ▼
   Verified Identity Assertion
          │
          ▼
SAD-MORON Bounded Session / Authority Context
          │
          ▼
Authorized Administrative Action
```

### Principles

- SAD-MORON does NOT duplicate institutional authentication unnecessarily
- External institutional credentials remain external and must NOT be stored in SAD systems
- A verified identity does NOT automatically imply administrative authority
- **Authorization is separate from authentication**
- Browser/client software is NOT an authority source; authority remains institutional or human
- Identity verification must remain transferable across future technology changes

### Current State

- Identity model defined and documented in Access Governance
- Concrete ABC integration NOT YET DEMONSTRATED
- Status: GOVERNANCE CONTRACT DEFINED / IMPLEMENTATION FUTURE

---

## 10. Authority Boundaries

### Core Principle

> Human authority remains explicit.

The system may:

- observe source data
- organize evidence
- validate governance contracts
- detect inconsistencies
- prepare proposals
- record decisions

The system must NOT:

- convert evidence automatically into administrative decision
- bypass human authority when administrative consequences require it
- hide authority behind technical defaults or algorithmic choices

### Human Authority Gates

Processes with administrative consequences must preserve explicit human decision gates according to their specific governance contracts.

Examples:

- source snapshot promotion requires human review when operational data depends on it
- access permission changes require authorized human acknowledgment
- integration of bounded contexts requires institutional decision
- changes to evidence interpretation or classification rules require governance review

---

## 11. Evidence Architecture

### Distinct Evidence Categories

| Evidence Type | Question | Responsibility | Future location |
|---------------|----------|-----------------|-----------------|
| **Source Evidence** | What was observed in an institutional source? | Declared sources layer | Operational data layer / audit |
| **Runtime Evidence** | What did the software execute, under what conditions, with what result? | Runtime governance layer | Append-only runtime audit |
| **Administrative Evidence** | What decision was made, by whom, under what authority, with what justification? | Institutional authority | Administrative audit layer |
| **Promotion Evidence** | What justifies promotion from pilot to governed destination? | Review and governance gates | Archive of promotion decisions |

These evidence categories serve different purposes and may NOT use a single unified schema.

---

## 12. Deterministic Reconstruction

### Objective

When deterministic reconstruction is required, identify sufficient information to recreate interpretation consistently:

- Snapshot version or ID (which acquisition moment)
- Adapter version (which transformation rules)
- Contract version (what governance was in effect)
- Rules version (what interpretation logic was applied)

### Current State

- Versioning requirements established in governance framework
- Versioning implementation details FUTURE / NOT DEMONSTRATED

### Principle

> same governed inputs + same governed transformation versions → reproducible interpretation

Distinguish from:

- **Technical reproducibility** — same code, same inputs → same outputs
- **Administrative reproducibility** — same facts, same rules → same decision

These are different assurances.

---

## 13. Security and Sensitive Information Boundary

### Core Principle

> Public governance documentation must not enable unauthorized reconstruction or compromise of private operational infrastructure.

### DEMONSTRATION / VERIFICATION

All governance documents must NOT expose:

- Sheet IDs (Google Sheets identifiers)
- Script IDs (Google Apps Script project identifiers)
- authentication tokens or secrets
- restricted endpoints or URLs
- private institutional mappings
- personal or administrative data
- physical infrastructure topology enabling access

### Credential Storage

Secrets and credentials must remain outside Git repositories regardless of whether the repository is public or private. External secret management (environment variables, encrypted vaults, institutional secret stores) is required.

---

## 14. Promotion Model

### Decision Flow

```
Pilot Artifact (in Labs or private context)
          │
          ▼
     Evidence Collection
          │
          ▼
    Human Review Gate
          │
          ▼
 Sensitivity Classification
     (public / private)
          │
          ▼
  Destination Selection
  (governance / operational)
          │
          ▼
  Explicit Promotion Decision
     (human or delegated)
          │
          ▼
   Governed Artifact
          │
          └─── Publication (separate decision)
```

### Principles

- **Maturity ≠ automatic promotion** — reaching a functional level does NOT automatically move an artifact to production or publication
- **Newer ≠ authoritative** — recent changes do NOT automatically supersede older validated versions
- **Promotion ≠ publication** — moving an artifact to a governed destination is separate from deciding whether to publish it
- **Classification is independent** — the public/private designation of a destination is decided separately from the promotion decision
- **Nothing becomes canonical merely because it exists** — presence in Labs or any repository does NOT confer governance authority without explicit promotion

---

## 15. Current State vs. Future State

### STATUS MATRIX

| Architectural Element | Current Status | Evidence Class | Notes |
|---|---|---|---|
| Governance infrastructure separation | RATIFIED_HUMAN_DECISION / LOCAL_ONLY | evidence from Step 3 alignment | documented in Framework, Connectors, AppScript, Access Governance; commit c264afc; not published |
| Runtime Governance definition | RATIFIED_HUMAN_DECISION / LOCAL_ONLY | evidence from Step 1 alignment | documented in SAD-MORON-RUNTIMES; commit 49b0956; not published |
| Labs private pilot role | RATIFIED_HUMAN_DECISION / LOCAL_ONLY | evidence from Step 2 alignment | private repository (DEMONSTRATED), role decision in commit 4adc013; not published |
| Framework governance anchor | DEMONSTRATED | observed repository posture | public repository, governance-first |
| AppScript governance patterns | DEMONSTRATED | observed repository posture | PUBLIC governance infrastructure, reference implementations with audit boundaries |
| Connectors contract layer | DEMONSTRATED | observed repository posture | PUBLIC governance infrastructure, contract definitions and compliance packs |
| Access Governance layer | DEMONSTRATED | observed repository posture | PUBLIC governance infrastructure, identity and access governance |
| 5650 pilot system | PARTIALLY_DEMONSTRATED | code and workflows in Labs | pilot character maintained, no production claim |
| Art.109 bounded context | DEMONSTRATED_LOCAL_ONLY | separate administrative processes | local unpublished branch; intentionally separate from 5650, no integration contract; not on origin/main |
| Institutional source acquisition | RATIFIED_DECISION | governance framework defined | implementation FUTURE |
| Data normalization pipeline | NOT_DEMONSTRATED | planning pattern documented | implementation awaiting resource allocation |
| Operational runtime layer | NOT_DEMONSTRATED | none | destination and architecture FUTURE |
| ABC identity integration | NOT_DEMONSTRATED | governance contract defined | implementation future |
| Provincial adoption | NOT_DEMONSTRATED | none | explicitly NOT claimed |
| Production deployment | NOT_DEMONSTRATED | none | all current systems are pilots or labs |

---

## 16. Open Architectural Decisions

The following decisions remain **OPEN — HUMAN DECISION REQUIRED** and are NOT resolved by this document:

1. **Destination for promoted operational artifacts** — where do pilot implementations go after promotion? Options include private governed repository, institutionally controlled infrastructure, district-managed systems, or hybrid models.

2. **Physical deployment architecture** — servers, containers, cloud services, on-premises infrastructure, hybrid?

3. **Real authentication strategy** — how is ABC identity actually integrated? OAuth2? SAML? Direct integration? Federated?

4. **Operational data storage** — where does versioned snapshot history live? How is backup and availability managed?

5. **Synchronization and concurrency** — if multiple users/processes interact with sources concurrently, what conflict resolution applies?

6. **Audit trail storage** — append-only audit implementation details, retention, compliance requirements?

7. **Multi-district or multi-context scaling** — can the architecture serve multiple districts, or is it SAD-Morón-specific?

8. **Definitive institutional schemas** — what data models are authoritative for educational administration?

9. **Art.109 scope and relationship** — if Art.109 later aligns with SAD-MORON governance, what domain contracts are shared and what remain separate?

10. **Future bounded contexts** — what governance process applies when new administrative processes want to consume SAD-MORON governance?

11. **Integration vs. federation** — should future bounded contexts share operational databases or remain federated with APIs?

12. **Credential management system** — what technology stack for managing secrets, rotation, audit?

13. **Operational private repository classification** — should operational implementation remain private Git, separate artifact store, or other?

14. **Institutional records management** — how does SAD-MORON architecture interact with official records retention requirements?

15. **Regulatory compliance mapping** — what compliance frameworks (privacy, educational, administrative) constrain future implementations?

These questions require institutional stakeholder involvement, not technical architectural decision.

---

## 17. Non-Goals

This document does **NOT**:

- serve as a deployment or operations manual
- define technology stack requirements in detail
- provide runbook or operational procedures
- define physical infrastructure topology
- integrate administrative processes that today remain separate
- claim production readiness
- claim official provincial adoption
- expose sensitive information
- design a monolithic application
- prescribe implementation language or frameworks
- resolve open architectural decisions

This document **DOES**:

- explain the governance-first architectural approach
- map current repository roles and boundaries
- preserve separation of concerns across governance and operational layers
- document ratified human decisions from this alignment initiative
- clarify what remains unresolved and requires future decision

---

## 18. Architectural Overview Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                    INSTITUTIONAL SOURCES                         │
│         (Google Sheets, Drive docs, Forms, registries)          │
└──────────────────────────┬──────────────────────────────────────┘
                           │
         ┌─────────────────────────────────────┐
         │  SOURCE / CONNECTOR GOVERNANCE      │
         │  (SAD-MORON-CONNECTORS)            │
         │  - source boundaries               │
         │  - connector contracts             │
         │  - integration compliance          │
         └──────────────────┬──────────────────┘
                           │
        ┌──────────────────────────────────────┐
        │  OPERATIONAL DATA PIPELINES          │
        │  (private / bounded)                │
        │  - acquisition                     │
        │  - sanitization                    │
        │  - normalization                   │
        │  - reconciliation                  │
        └──────────────────┬───────────────────┘
                           │
        ┌──────────────────────────────────────┐
        │  NORMALIZED OPERATIONAL MODELS       │
        │  (governed by contracts)             │
        └──────────────────┬───────────────────┘
                           │
        ┌──────────────────┴────────────────────┐
        ▼                                       ▼
    ┌─────────┐  ┌──────────┐  ┌──────────────┐
    │  5650   │  │ Art.109  │  │ Future       │
    │ BOUNDED │  │ BOUNDED  │  │ BOUNDED      │
    │ CONTEXT │  │ CONTEXT  │  │ CONTEXTS     │
    └────┬────┘  └────┬─────┘  └────┬─────────┘
         │            │            │
         └────────────┼────────────┘
                      │
         ┌────────────────────────────┐
         │   HUMAN AUTHORITY GATE     │
         │  (administrative decisions)│
         └────────────────┬───────────┘
                          │
         ┌────────────────────────────────┐
         │  ADMINISTRATIVE EVIDENCE AUDIT  │
         │  (decisions, actors, authority)│
         └────────────────────────────────┘

SURROUNDING SHARED GOVERNANCE INFRASTRUCTURE:
├─ SAD-MORON-FRAMEWORK (governance principles, inheritance)
├─ SAD-MORON-ACCESS-GOVERNANCE (identity, roles, authority)
├─ SAD-MORON-CONNECTORS (source boundaries, contracts)
├─ SAD-MORON-APPSCRIPT (governance patterns, audit boundaries)
├─ SAD-MORON-RUNTIMES (execution contracts, evidence)
└─ Evidence and audit contracts (across all layers)

SEPARATE FROM GOVERNANCE: PRIVATE PILOT LABORATORY
├─ Experimentation
├─ Integration testing
├─ Evidence production
└─ Human Promotion Gate → Governed Destination (public governance OR private operational)
```

---

## 19. Repository Map

### GOVERNANCE INFRASTRUCTURE REPOSITORIES

| Repository | Architectural Role | Executes Domain Logic? | Contains Operational Secrets? | Status |
|---|---|---|---|---|
| **SAD-MORON-FRAMEWORK** | Canonical governance anchor, principles, scope, inheritance, governance standards | NO | NO | Public, fully documented |
| **SAD-MORON-ACCESS-GOVERNANCE** | Public governance infrastructure: identity governance, roles, permissions, authority, electronic acceptance contracts | NO | NO | Public governance infrastructure, fully documented |
| **SAD-MORON-CONNECTORS** | Public governance infrastructure: connector contracts, source boundaries, integration compliance, evidence expectations | NO | NO | Public governance infrastructure, fully documented |
| **SAD-MORON-APPSCRIPT** | Public governance infrastructure: Apps Script governance patterns, implementation scaffolding, audit boundaries | REFERENCE PATTERNS ONLY | NO | Public governance infrastructure, fully documented with audit boundaries |
| **SAD-MORON-RUNTIMES** | Runtime execution governance contracts, technical identity, evidence requirements | NO (GOVERNANCE ONLY) | NO | Governance defined, implementation future |

### PILOT LABORATORY

| Repository | Architectural Role | Executes Domain Logic? | Contains Operational Secrets? | Status |
|---|---|---|---|---|
| **SAD-MORON-LABS** | Private pilot laboratory for experimentation, integration, validation, evidence, promotion | YES (PILOTS ONLY) | NO | Private, pilot character maintained |

### OPERATIONAL IMPLEMENTATION (FUTURE)

| Repository | Architectural Role | Executes Domain Logic? | Contains Operational Secrets? | Status |
|---|---|---|---|---|
| **TBD** | Operational runtime, data normalization, connector execution | YES | EXTERNAL (not in Git) | Destination and architecture FUTURE |

---

## 20. Janus Core Relationship

SAD-MORON selectively applies governance principles derived from Janus Core. This relationship is:

- **conceptual inheritance** — governance primitives and bounded decision-making patterns from Janus Core inform SAD-MORON design
- **NOT architectural dependency** — SAD-MORON does not require Janus runtime, infrastructure, or complete ecosystem
- **NOT technology binding** — Janus Core concepts are applied to educational administrative domain without requiring Janus technology stack
- **preserves independence** — SAD-MORON governance may evolve independently from Janus

Reference: Janus Governance Core principles inform but do not constrain SAD-MORON future evolution.

---

## 21. Document Evolution and Ratification

This document version (V1) is:

- **DRAFT** — pending institutional review and ratification
- **BASE FOR ALIGNMENT** — establishes architectural baseline for future SAD-MORON governance
- **NOT CANONICAL** — authority derives from ratification, not from mere publication

Future versions will be numbered sequentially (V2, V3, etc.) and must preserve:

- evidence-based claims (DEMONSTRATED vs. RATIFIED vs. FUTURE)
- explicit uncertainty and open decisions
- governance infrastructure principles
- separation of governance from operational concerns

---

## 22. Appendix: Acronyms and Terminology

- **SAD** = Secretaría de Asuntos Docentes (Educational Administrative Secretary)
- **SAD-MORON** = governance pilot and ecosystem serving Secretaría de Asuntos Docentes de Morón (Morón District)
- **DGCyE** = Dirección General de Cultura y Educación (provincial education authority)
- **ABC** = institutional identity provider (assumed external boundary)
- **5650** = pilot administrative process within Labs
- **Art.109** = separate administrative bounded context
- **RATIFIED_DECISION** = human decision formally adopted during this alignment initiative
- **DEMONSTRATED** = observed in repository documentation, code, or posture
- **FUTURE / UNRESOLVED** = architectural questions requiring future decision
- **Promotion** = moving an artifact from experimental status to a governed destination
- **Bounded context** = administrative system with distinct domain logic and authority
- **Governance infrastructure** = reusable contracts and principles
- **Operational infrastructure** = implementation-specific systems and data

---

**END OF DOCUMENT**
