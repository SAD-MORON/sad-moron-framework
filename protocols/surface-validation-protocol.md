# Surface Validation Protocol

## Purpose

This protocol defines the minimum governance requirements for validating declared surfaces before operation.

It operationalizes SAD_009 (Superficies declaradas antes que operacion) as a pre-operational governance gate.

## Scope

This protocol applies to governance interpretation and pre-operational validation planning in SAD repositories.

It does not define runtime tooling, deployment scripts, or implementation-specific checks.

## Required Sequence

PRECHECK
↓
PREPARE
↓
VERIFY
↓
OPERATE

Sequence intent:
- PRECHECK: identify declared surface, declared boundary, and contract assumptions.
- PREPARE: define verification context, inputs, and evidence expectations.
- VERIFY: confirm that declared surface assumptions are valid within scope.
- OPERATE: proceed only after verification is satisfied.

## Prohibited Behavior

The following behaviors are prohibited:
- assuming surface contracts without declared validation
- mutating surfaces before PRECHECK
- operating on unverified surfaces

## Promotion Note

This protocol is generalized from SAD-MORON-LABS/5650 governance evidence and adaptation lessons, without importing implementation details.

## Summary

No governed operation should begin on a surface that has not passed declared pre-operational validation.