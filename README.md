# SAD-MORON-FRAMEWORK

## Purpose

`SAD-MORON-FRAMEWORK` is a documentation-first repository for a clean institutional governance implementation inspired by selected Janus principles.

Its purpose is to define:
- bounded governance concepts
- declared-source discipline
- expected administrative events
- omission review rules
- normative and operational boundaries

This repository does not implement runtime systems, APIs, Apps Script automation, or agent workflows.
This repository does not execute.

## Protocol-Driven Governance Architecture

`SAD-MORON-FRAMEWORK` defines governance first and implementation later.

The repository exists to stabilize:
- protocol meaning
- declared boundaries
- evidence rules
- normative scope
- repository separation across future SAD Moron layers

The architecture distinction is:
- framework layer: governance, protocols, boundaries, and normative meaning
- runtime layer: future ingestion and normalization execution in separate repos
- connectors layer: future source-specific adapters in separate repos
- operations layer: real institutional use over declared sources and workflows
- audit layer: future append-only review and reconstruction in separate repos

Lower layers may implement processes and tools, but they may not redefine governance, evidence semantics, boundaries, or normative scope established here.

## Scope

This repository is limited to institutional governance documentation for SAD Moron.

Initial in-scope areas:
- normative governance definitions
- conceptual protocol documents
- source and schema planning
- architectural layer definitions

Initial out-of-scope areas:
- runtime code
- executable connectors
- Apps Script code
- API implementation
- generalized AI tooling
- infrastructure orchestration

## Boundaries

SAD Moron governance in this repository is bounded by:
- declared sources
- expected administrative events
- defined review periods
- explicit normative rules
- explicit operational rules

No claim should rely on hidden sources, inferred authority, or undefined review scope.

This repository governs future implementation repositories.
Lower layers may implement ingestion, normalization, integration, and operational workflows, but they may not redefine governance, evidence semantics, boundaries, or normative scope established here.

## Janus Adaptation

This repository uses the adaptation review in `reports/SAD_MORON_JANUS_ADAPTATION_REVIEW_V1.md` as its conceptual source.

The safe Janus-inspired concepts adopted here are:
- `E+` and `E-` evidence distinction
- append-only institutional history
- deterministic reconstruction of review context
- omission detection under declared scope
- explicit human accountability boundaries

The repository does not import Janus architecture, Janus runtime code, or Janus operational complexity.

## Repository Structure

```text
.
├── docs/
├── protocols/
├── reports/
└── .gitignore
```

Structure notes:
- `docs/` holds bounded explanatory and normative-facing documentation
- `protocols/` holds conceptual operational rules only
- `reports/` holds analysis and governance review outputs

## Normative Status

At this stage, this repository is a base scaffold.

Normative intent begins in the documents that explicitly define:
- scope and boundaries
- normative framework
- conceptual protocols

Directories reserved for future growth must remain empty of executable code unless a later governance decision expands scope.

Future implementation work belongs in separate lower-layer repositories, not in this framework repository.

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

## Reference

Conceptual source:
- `reports/SAD_MORON_JANUS_ADAPTATION_REVIEW_V1.md`
