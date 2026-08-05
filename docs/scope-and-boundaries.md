# Scope and Boundaries

## Purpose

This document defines the initial governance scope of `SAD-MORON-FRAMEWORK` and the boundaries that constrain its growth.

## In Scope

The repository currently governs documentation about:
- declared institutional sources
- expected administrative events
- bounded omission review
- normative and operational governance rules
- audit-facing review conventions

## Out of Scope

The repository does not currently govern:
- production systems
- workflow execution
- live integrations
- data synchronization
- user interfaces
- automation runtimes
- AI agent execution

## Governance Infrastructure vs. Operational Infrastructure

SAD-MORON separates **governance infrastructure** from **operational and data infrastructure**.

**Governance infrastructure** comprises reusable and auditable contracts, principles, boundaries, schemas, protocols, authority conditions and evidence requirements. This layer defines the conditions under which systems and processes may be considered governed.

Examples of governance infrastructure scope:
- governance principles and primitives
- authority and access contracts
- connector contracts
- runtime governance rules
- implementation governance rules
- reusable schemas and data models
- communication protocols
- taxonomies and vocabularies
- evidence and audit requirements
- synthetic examples for guidance
- architectural constraints

Governance infrastructure **may be publicly auditable** when its information classification permits it. This is a decision independent of the governance layer itself. However, any publicly accessible governance artifacts must not expose information that permits unauthorized reconstruction, access or compromise of operational infrastructure or institutional data.

**Operational and data infrastructure** contains the concrete deployments, institutional configurations, real mappings, sensitive integrations, source identifiers, operational data and other restricted implementation material required to operate specific systems under declared governance.

Examples of operational infrastructure scope:
- production deployments and runtimes
- real institutional source mappings
- real source identifiers and endpoints
- configuration for specific environments
- real institutional snapshots
- administrative and personal data
- sensitive integrations and adapters

Operational infrastructure requires access controls bounded by institutional authorization and information sensitivity. Secrets and credentials must remain outside version control regardless of repository classification.

**Promotion does not imply publication.** Promotion of a governance or operational artifact means its incorporation into a governed destination. The access classification and public auditability of that destination are independent decisions from the promotion decision itself.

## Boundary Conditions

Any governance analysis in this repository must declare:
- source scope
- event scope
- time or period scope
- applicable rule set
- human authority boundary

If any of these conditions is undefined, the analysis is incomplete and should not be treated as institutionally reliable.

## Declared Sources Boundary

Only declared institutional sources may support an evidence claim.

Examples of source classes expected in the SAD Moron context:
- resolutions
- decrees
- ordinances
- administrative registries
- publication records
- notifications
- archive records

Undeclared or informal sources may be noted, but they must not be treated as normative evidence by default.

## Administrative Events Boundary

The framework is limited to a bounded set of expected administrative events.

Illustrative event family:
- receipt
- registration
- assignment
- drafting
- authorization
- publication
- notification
- archival closure

This list is intentionally narrow at the scaffold stage.

## Temporal Boundary

All omission review must operate within a defined period.

A defined period should state:
- start condition or date
- end condition or date
- applicable deadline or expected interval

Absence outside a declared period is not sufficient to establish omission.

## Normative and Operational Boundary

The repository distinguishes between:
- normative rules: what counts as institutional governance truth in this framework
- operational rules: how reviews are conducted and documented

Operational documents must not silently alter normative meaning.

## Growth Boundary

No new subsystem should be added unless it is justified by:
- a documented institutional need
- compatibility with declared boundaries
- explicit confirmation that the addition does not introduce runtime scope by default

## Summary

The core boundary principle is simple:

Only bounded, declared, reviewable institutional governance belongs in this repository.
