# Governance Core

## Purpose

This document is the single canonical Layer 1 governance anchor for `SAD-MORON-FRAMEWORK`.

Its purpose is to define the minimal governance kernel that future SAD Moron repositories must inherit before any operational or implementation layer is created.

## Canonical Status

This document is the canonical governance reference for future SAD Moron repositories.

Where another framework document appears to conflict with this document, this document takes precedence unless it is explicitly superseded through governed change control.

## Framework Purpose

`SAD-MORON-FRAMEWORK` exists to define:
- normative governance boundaries
- declared-source discipline
- expected-event discipline
- temporal review constraints
- evidence meaning
- omission review limits
- repository separation across future layers
- infrastructure growth limits

## Normative Boundary

This repository is governance-only.

It defines institutional meaning and review boundaries, but it does not:
- execute workflows
- implement APIs
- implement connectors
- implement Apps Script
- create operational repositories
- automate institutional decisions

## Governance-Only Nature

The framework is documentation-first and specification-only.

Its role is to govern future implementation, runtime, operational, and audit repositories without becoming one of those layers itself.

## Relation to Janus Governance

This framework is conceptually informed by selected Janus Governance principles, especially:
- `E+` / `E-` evidence distinction
- append-only institutional history
- deterministic reconstruction
- bounded omission detection
- explicit human accountability

This framework does not import Janus runtime architecture, generic agent tooling, or Janus operational complexity.

## Relation to SAD Moron Institutional Scope

This framework applies to SAD Moron institutional governance within the bounded context of Provincia de Buenos Aires educational administration and related SAD operational processes.

It is not a general municipal governance platform and must not expand silently beyond SAD Moron institutional scope.

## `E+` / `E-` Evidence Principle

The framework adopts:
- `E+` as explicit evidence of presence in a declared source or declared review artifact
- `E-` as verified absence of an expected record under declared source scope, expected event scope, and temporal scope

Evidence classification supports governance interpretation, but it does not replace accountable institutional judgment.

## Omission Detection Boundary

Omission review is valid only when all of the following are defined:
- declared source boundary
- expected event
- temporal boundary
- applicable governance rule
- accountable review context

Omission detection is bounded review, not automatic fault attribution.

## Infrastructure Growth Boundary

Infrastructure growth in this repository must remain proportional to defined governance needs.

This framework must not expand into runtime, integration, automation, or platform behavior unless a governed future decision explicitly creates a separate lower-layer repository for that purpose.

## Repository Separation Rule

This framework governs future repositories, but lower layers cannot redefine governance.

In particular:
- framework repositories cannot execute
- runtime repositories cannot redefine governance
- connector repositories must declare source boundaries
- audit repositories must remain append-only evidence oriented

## Human Governance Boundary

Institutional decisions remain attributable to accountable human authority.

No document, protocol, or future implementation may treat software outputs as a substitute for authorized institutional decision.

## Summary

`docs/governance-core.md` is the canonical Layer 1 anchor for SAD Moron governance.

Future repositories may inherit from this framework, but they may not redefine its governance core.
