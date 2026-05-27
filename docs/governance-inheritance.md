# Governance Inheritance

## Purpose

This document defines how governance inheritance flows from Janus Core through `SAD-MORON-FRAMEWORK` into future SAD repositories.

Its purpose is to ensure that lower-layer repositories inherit governance meaning, repository posture, and boundary discipline without inheriting unnecessary runtime assumptions.

## Canonical Source

The canonical repository governance source for SAD repositories is:
- `docs/repository-governance-standard.md`

The canonical Layer 1 governance anchor for this repository is:
- `docs/governance-core.md`

## Inheritance Chain

The default governance inheritance chain is:

Janus Core
-> SAD Framework
-> domain implementations

## Inheritance Rule

Future SAD repositories should inherit governance principles from Janus Core through the SAD framework layer rather than claiming direct inheritance from the full Janus runtime ecosystem by default.

Preferred wording:
- "inherits governance principles from Janus Core"
- "selectively applies governance principles derived from Janus Core"

Avoid wording that implies:
- full Janus runtime dependency where none exists
- wholesale Janus ecosystem inheritance where only governance principles are inherited
- architectural coupling beyond declared repository scope

## SAD Framework Role

`SAD-MORON-FRAMEWORK` is the inheritance bridge that translates Janus Core governance principles into SAD repository standards, institutional boundaries, documentation posture, and domain-safe governance language.

This repository establishes:
- repository governance posture
- institutional neutrality expectations
- public/private boundary declarations
- security posture expectations
- workflow and documentation boundary discipline

## Lower-Layer Rule

Domain implementations may extend workflow logic, connectors, runtime behavior, operational adapters, or private deployments only within the governance boundaries inherited from this framework.

Lower layers may not silently redefine:
- governance meaning
- declared boundary conditions
- attribution rules
- institutional neutrality posture
- public/private security boundaries

## Summary

Governance inheritance for SAD repositories flows from Janus Core through `SAD-MORON-FRAMEWORK` into domain implementations, with this framework serving as the bounded institutional translation layer.
