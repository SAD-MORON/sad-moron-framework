# Repository Separation Protocol

## Purpose

This protocol defines the separation rules between framework, runtime, connector, operations, and audit repositories in the SAD Moron architecture.

## Boundary

This protocol governs repository role separation only.

It does not define:
- git workflows
- deployment processes
- source control permissions
- CI/CD behavior

## Responsibilities

This protocol is responsible for defining:
- what belongs in framework repositories
- what belongs in runtime repositories
- what belongs in connector repositories
- what belongs in audit repositories
- how lower layers remain subordinate to governance

## Exclusions

This protocol excludes:
- cross-repo execution orchestration
- implementation code placement details
- build system design

## Enforcement Rules

### Rule 1: Framework repos cannot execute

Framework repositories define governance, protocols, and normative boundaries only. They must not execute runtime logic.

### Rule 2: Runtime repos cannot redefine governance

Runtime repositories may implement ingestion, normalization, validation, and operational logic, but they may not redefine governance semantics, evidence classes, declared boundaries, or normative scope.

### Rule 3: Connectors must declare source boundaries

Connector repositories must explicitly declare which source boundaries they operate within and must inherit governance definitions rather than invent new ones.

### Rule 4: Audit repos are append-only evidence oriented

Audit repositories must prioritize append-only evidence history, reconstruction, and temporal comparison rather than mutable operational control.

### Rule 5: Operations remain institution-bound

Operational repositories or workspaces must remain tied to real institutional use and declared source scope, not drift into unrestricted collection or undefined governance use.

## Summary

Repository separation keeps governance stable, implementation bounded, operations contextual, and audit reconstructable.
