# Framework Contracts

## Purpose

This protocol defines the contract surface of `SAD-MORON-FRAMEWORK` as a governance-only repository.

It establishes what the framework must define, what lower layers may consume, and what this repository must never become.

## Boundary

This protocol applies only to the governance and specification layer.

It does not apply to:
- runtime execution
- integration code
- connector code
- operational dashboards
- audit tooling implementation

## Responsibilities

The framework layer is responsible for defining:
- normative boundaries
- governance concepts
- evidence rules
- declared source discipline
- expected event discipline
- temporal review rules
- repository separation rules

The framework layer is also responsible for constraining how future repos interpret these concepts.

## Exclusions

The framework layer must not:
- execute workflows
- ingest records
- normalize data
- automate omission checks
- issue institutional decisions through software

## Enforcement Rules

### Rule 1: Contract-first governance

Every lower-layer implementation must be interpretable against a framework contract defined here.

### Rule 2: No implicit expansion

If an implementation concern is introduced without a framework contract, it is out of scope for this repository.

### Rule 3: Lower-layer compliance

Future runtime, connector, operations, and audit repos must treat framework protocols as governing inputs rather than optional guidance.

### Rule 4: Stable meaning

Framework contracts must prefer semantic stability over convenience so lower layers do not drift into competing interpretations.

## Summary

`SAD-MORON-FRAMEWORK` is the contract layer for governance meaning, not the place where SAD Moron executes implementation logic.
