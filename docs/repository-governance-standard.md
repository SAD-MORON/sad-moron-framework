# Repository Governance Standard

## Purpose

This document defines the canonical repository governance standard for SAD repositories.

It exists to establish a lightweight but formal baseline for repository posture, licensing, attribution, Janus Core wording, institutional neutrality, public/private operational boundaries, governance inheritance, and security posture.

Future SAD repositories should inherit this standard before implementation, integration, or operational specialization begins.

## Canonical Status

This document is the canonical repository governance source for SAD repositories.

Where repository-level governance wording conflicts with another explanatory or local document, this standard takes precedence unless an explicitly governed superseding document is adopted.

## Repository Posture

SAD repositories should declare repository posture explicitly.

Required posture concepts include:
- governance-first
- documentation-first when applicable
- bounded execution
- institutional continuity
- auditability
- interoperability

Interpretation:
- governance-first means governance meaning is declared before implementation expands
- documentation-first when applicable means repositories with governance, workflow, or audit roles should stabilize documentation before runtime behavior
- bounded execution means execution scope must be explicitly declared and limited
- institutional continuity means repository use must remain viable beyond any individual author
- auditability means material decisions, boundaries, and evidence posture should be reconstructable
- interoperability means repository structure and wording should support later domain implementations without silent semantic drift

## Janus Core Wording Standard

Preferred Janus wording:
- "inherits governance principles from Janus Core"
- "selectively applies governance principles derived from Janus Core"

Repositories should avoid implying dependency on the entire Janus runtime ecosystem unless that dependency is explicitly true and documented.

Avoid wording that suggests:
- full Janus runtime inheritance by default
- Janus operational dependency where none exists
- architectural coupling to the entire Janus ecosystem without explicit repository evidence

## Attribution Standard

Preferred attribution wording:

Initial governance architecture:
Martín Nicolás Sánchez Morales

Attribution should remain factual, concise, and institutionally neutral.

Avoid:
- personalistic branding
- founder-centric language
- ownership language
- politically sensitive wording
- hero framing

Repository governance should remain transferable, maintainable, and institutionally usable beyond the original author set.

## Licensing Standard

SAD governance and documentation repositories should use the Apache License 2.0 unless an explicitly governed exception is documented.

This standard applies especially to:
- governance repositories
- documentation repositories
- workflow-definition repositories
- audit-facing documentation repositories

Operational connectors, runtime integrations, deployments, and institution-specific operational adapters may remain external or private where boundary, security, or institutional constraints require it.

Governance layers may remain public while operational integrations stay bounded.

## Public and Private Boundary Declaration Standard

Repositories should declare which layers are intended to remain public and which may remain private or institution-bounded.

Public-by-default governance surfaces may include:
- governance
- workflows
- taxonomy
- synthetic scaffolds
- documentation
- audit posture

Potentially private or bounded surfaces may include:
- connectors
- runtime integrations
- credentials
- operational deployments
- institutional mappings
- production adapters

Public governance publication does not require publication of secrets, live connectors, privileged mappings, or production execution artifacts.

## Institutional Neutrality Standard

SAD repositories must:
- avoid political tone
- avoid self-promotion
- emphasize transferability and continuity
- remain institutionally usable beyond original authors

Repository language should prioritize institutional clarity, role continuity, and bounded governance meaning over personality, authorship prominence, or project mythology.

## Governance Inheritance Chain

The default governance inheritance chain is:

Janus Core
-> SAD Framework
-> domain implementations

Domain implementations may specialize workflow, taxonomy, execution, and operational integration only within the inherited governance boundary.

Lower layers may not silently redefine governance meaning inherited from the framework layer.

## Recommended Repository Structure

Recommended repository areas include:
- `docs/`
- `protocols/`
- `workflows/`
- `audit/`
- `reports/`
- `packages/` when applicable

Not every SAD repository must contain every area.

Structure should remain proportional to repository purpose and should not create runtime sprawl where governance documentation is the actual scope.

## Governance Document Metadata Convention

Canonical and normative governance documents should be able to adopt a lightweight metadata surface when repository maturity requires it.

Recommended minimum metadata fields:
- `version`
- `status`
- `last-reviewed`
- `reviewed-by`

This convention is intended to improve traceability and review continuity without implying runtime behavior or unnecessary process expansion.

## Governance States

Repositories should use simple governance states:
- `PASS`
- `REVIEW`
- `BLOCKED`

Interpretation:
- `PASS` means repository posture and declared governance minimums are satisfied
- `REVIEW` means the repository is usable but has unresolved governance issues that require documented follow-up
- `BLOCKED` means the repository should not proceed with the next governance-sensitive phase until blocking issues are resolved

## Security Posture

Required security posture concepts include:
- no credential persistence
- no hidden authority
- audit-before-execution
- append-only evidence when applicable

Interpretation:
- no credential persistence means credentials, tokens, secrets, or session artifacts must not be committed to repository history
- no hidden authority means repositories must not rely on unstated authority, undeclared sources, or implicit approval chains
- audit-before-execution means governance-sensitive execution should not expand before boundary, evidence, and review posture are documented
- append-only evidence when applicable means review evidence and governance reasoning should preserve traceability rather than silently erase prior context

## Repository README Standard

Repository READMEs should, at minimum, declare:
- repository purpose
- governance posture
- scope
- execution boundary
- public/private boundary
- inheritance position within the SAD chain
- licensing status
- attribution wording where appropriate

READMEs should remain concise and should avoid turning repository purpose statements into personal manifestos or implementation promises beyond declared scope.

## Applicability

This standard applies to SAD repositories that define governance, workflows, audit posture, domain implementation boundaries, or operational documentation.

Purely operational private repositories may implement a narrower local surface, but they should still inherit the relevant boundary, security, and attribution rules defined here.

## Summary

This document provides the canonical repository governance standard for SAD repositories so governance remains portable, institutionally neutral, auditable, and bounded across future layers.
