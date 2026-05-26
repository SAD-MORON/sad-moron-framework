# Connector Compliance Protocol

## Purpose

This protocol defines how future connector repositories must comply with the governance framework defined here.

## Boundary

This protocol applies to future connector implementations as governed artifacts.

It does not define:
- connector code
- connector APIs
- transport methods
- credential handling mechanisms

## Responsibilities

This protocol is responsible for defining that future connectors must:
- declare source boundaries
- respect declared-source authority classes
- avoid capturing undeclared data
- preserve traceability between source access and governance meaning

## Exclusions

This protocol excludes:
- connector implementation details
- source synchronization behavior
- secret management design
- platform-specific integration logic

## Enforcement Rules

### Rule 1: Source boundary declaration

Connectors must declare which sources they are allowed to access and the boundaries of that access.

### Rule 2: No undeclared capture

Connectors must not expand source scope beyond what governance has declared.

### Rule 3: Governance inheritance

Connectors may carry data across systems, but they may not redefine evidence meaning, expected events, or normative scope.

### Rule 4: Auditability support

Connector behavior should remain interpretable in later audit and reconstruction layers, even though those layers are defined elsewhere.

## Summary

Future connectors are subordinate to governance boundaries and must operate within declared source limits.
