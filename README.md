
# SAD-MORON-FRAMEWORK

	extbf{Piloto de Modernización y Gobernanza:} 
docs/pilot-modernizacion-y-gobernanza.md

## Purpose

`SAD-MORON-FRAMEWORK` is a governance-first, documentation-first repository for a bounded institutional pilot related to the Secretaria de Asuntos Docentes (SAD) of Morón District, Provincia de Buenos Aires, Argentina, within the broader institutional context of the Dirección General de Cultura y Educación (DGCyE). It defines governance assumptions, declared sources, workflows, and control boundaries before any separate implementation layer is considered.

This repository selectively applies governance principles derived from Janus Core and serves as a stable framework repository for future SAD governance and documentation work under a bounded pilot posture.

Its purpose is to define:
- bounded governance concepts
- declared-source discipline
- expected administrative events
- omission review rules
- normative and operational boundaries
- normative sources
- operational workflows
- declared institutional sources
- repository governance standards for future SAD repositories

This repository does not implement runtime systems, APIs, Apps Script automation, or agent workflows. Future runtime implementations must reference the normative, workflow, and declared-source layers defined here.

Repository governance for future SAD repositories is canonically defined in:
- `docs/repository-governance-standard.md`
- `docs/governance-inheritance.md`
- `docs/pilot-context-and-governance-primitives.md`
- `docs/AI_AGENT_GUIDE.md`

## Protocol-Driven Governance Architecture

`SAD-MORON-FRAMEWORK` defines governance first and implementation later. The repository stabilizes protocol meaning, declared boundaries, evidence rules, normative scope, repository separation across future SAD Morón layers, and sensitive data protection boundaries.

The architecture distinction is:
- framework layer: governance, protocols, boundaries, and normative meaning
- normative layer: legal and institutional authority documents that constrain SAD action
- workflow layer: operational institutional processes derived from bounded normative scope
- declared sources layer: operational Google Sheets, Drive documents, Forms, and instructivos used within approved workflows
- runtime layer: future ingestion and normalization execution in separate repos
- connectors layer: future source-specific adapters in separate repos
- operations layer: real institutional use over declared sources and workflows
- audit layer: future append-only review and reconstruction in separate repos

Lower layers may implement processes and tools, but they may not redefine governance, evidence semantics, boundaries, or normative scope established here. Operational Google Sheets and Drive artifacts may support workflows, but they do not carry the same authority as legal or normative source documents.

## Governance Anchors

The current minimum governance anchors are:
- Governance Core: `docs/governance-core.md`
- Repository Governance Standard: `docs/repository-governance-standard.md`
- Governance Inheritance: `docs/governance-inheritance.md`
- Declared Sources Catalog: `docs/declared-sources-catalog.md`
- Change Control Protocol: `protocols/change-control-protocol.md`
- Normative Document Registry: `docs/normative-document-registry.md`
- Sensitive Data Protection Protocol: `protocols/sensitive-data-protection-protocol.md`

Governance evidence, adaptation reviews, audit artifacts, and remediation tracking are maintained in the `reports/` directory.

## Scope

This repository is limited to institutional governance documentation for SAD Morón.

Initial in-scope areas:
- normative governance definitions
- conceptual protocol documents
- source and schema planning
- architectural layer definitions
- normative source registration
- workflow registration
- declared source registration

Initial out-of-scope areas:
- runtime code
- executable connectors
- Apps Script code
- API implementation
- generalized AI tooling
- infrastructure orchestration
- real sensitive operational data in Git
- credentials, tokens, or secrets in Git

Governance and documentation layers may remain public.
Operational connectors, runtime integrations, credentials, institutional mappings, and production adapters may remain bounded, external, or private when institutional security or operational constraints require it.

## Boundaries

SAD Morón governance in this repository is bounded by:
- declared sources
- expected administrative events
- defined review periods
- explicit normative rules
- explicit operational rules

No claim should rely on hidden sources, inferred authority, or undefined review scope. Sensitive operational data must remain outside Git, and workflow planning in this repository must use metadata-first reasoning, minimum necessary fields, and explicit authorization boundaries before any real spreadsheet source is touched.

This repository governs future implementation repositories. Lower layers may implement ingestion, normalization, integration, and operational workflows, but they may not redefine governance, evidence semantics, boundaries, or normative scope established here.
Lower layers must also preserve the distinction between omission detection on existence, status, or timestamps and the prohibited copying of unnecessary personal data.

## Janus Adaptation

The governance principles selectively applied here include:
- `E+` and `E-` evidence distinction
- append-only institutional history
- deterministic reconstruction of review context
- omission detection under declared scope
- explicit human accountability boundaries

The repository does not import the full Janus runtime architecture, Janus runtime code, or Janus operational complexity.

## Repository Governance Posture

This repository adopts the following posture:
- governance-first
- documentation-first
- bounded execution
- institutional continuity
- auditability
- interoperability

These standards are intended to remain institutionally usable beyond the original author set and applicable across future SAD repositories.

## Licensing and Boundary Posture

The repository governance standard declares Apache License 2.0 as the default license for SAD governance and documentation repositories.

This repository separates:
- public governance, workflows, taxonomy, synthetic scaffolds, documentation, and audit posture
- bounded or potentially private connectors, runtime integrations, credentials, operational deployments, institutional mappings, and production adapters

### Institutional Boundary Notice

This repository documents a bounded institutional pilot context and governance framework. It does not by itself claim official endorsement, publication, or representational authority from SAD Morón, the Provincia de Buenos Aires, or the Dirección General de Cultura y Educación.

## Repository Structure

```text
.
├── declared-sources/
├── docs/
├── normative/
├── protocols/
├── reports/
├── workflows/
└── .gitignore
```

Structure notes:
- `normative/` holds structured records for legal, regulatory, and institutional authority sources
- `workflows/` holds structured records for bounded SAD operational workflows
- `declared-sources/` holds structured records for operational Google Sheets, Drive, Forms, and instructive sources
- `docs/` holds bounded explanatory and normative-facing documentation
- `protocols/` holds conceptual operational rules, including sensitive data protection requirements
- `reports/` holds analysis and governance review outputs

At the current pilot stage, `reports/` is the active repository surface for governance evidence, adaptation reviews, audit artifacts, and remediation tracking.

Recommended SAD repository areas may also include:
- `audit/`
- `packages/` when applicable

Where a future dedicated `audit/` area is added, it should complement `reports/` rather than silently redefine current governance review history.

## Normative Status

Normative intent begins in the documents that explicitly define:
- governance core
- scope and boundaries
- normative framework
- declared source catalog
- normative document registry
- conceptual protocols

Directories reserved for future growth must remain empty of executable code unless a later governance decision expands scope. Future implementation work belongs in separate lower-layer repositories, not in this framework repository.

## Non-Goals

This repository does not:
- automate municipal workflows
- replace official systems of record
- create software services
- expose APIs
- host Apps Script implementations
- host connector implementations
- execute omission detection automatically
- make accountable decisions without human authority
- store real personal administrative data in Git
- store credentials, tokens, or secrets in Git

## Reference

Governance evidence, adaptation reviews, audit artifacts, and remediation tracking are maintained in the `reports/` directory.

Canonical repository governance source:
- `docs/repository-governance-standard.md`

## Licensing

Licensing and attribution references:
- `LICENSE`
- `NOTICE`
- `docs/repository-governance-standard.md`
