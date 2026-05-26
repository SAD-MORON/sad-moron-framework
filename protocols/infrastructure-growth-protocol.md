# Infrastructure Growth Protocol

## Purpose

This protocol defines how `SAD-MORON-FRAMEWORK` should control structural growth.

It is intended to prevent the repository from expanding into unnecessary runtime or platform complexity.

## Scope

This protocol applies to:
- new top-level directories
- new subsystem categories
- changes that alter repository scope

It is conceptual only.
It does not authorize implementation by itself.

## Core Principle

Growth must follow institutional need, not technical convenience.

## Default Rule

No new infrastructure area should be introduced unless there is:
- a written justification
- a clear relation to SAD Moron governance scope
- a statement of boundaries
- confirmation that the change does not silently introduce runtime obligations

## Growth Tests

Before adding a new structural area, the proposal should answer:
- What institutional problem does this solve?
- Why can the problem not be handled within current documentation scope?
- Does the change rely on undeclared sources or undefined events?
- Does it introduce execution, integration, or automation scope?
- Does it expand beyond declared periods or governance boundaries?

## Restricted Growth Areas

The following growth directions should be treated as restricted by default:
- runtime services
- automation scripts
- API implementations
- connectors with live systems
- agent tooling
- deployment infrastructure

These areas require explicit later justification and should not appear implicitly inside documentation growth.

## Safe Growth Areas

The following growth directions are safer in the current phase:
- clarification documents
- source catalogs
- event taxonomies
- review templates
- schema planning
- audit reporting guidance

## Boundary Preservation Rules

### Rule 1: No hidden runtime

A documentation change must not smuggle in executable scope.

### Rule 2: No architecture copy-forward

The repository must not reproduce full Janus structural complexity unless SAD Moron explicitly needs it.

### Rule 3: No shadow authority

No new subsystem should imply decision authority that is not already defined in the normative framework.

### Rule 4: Keep reconstruction intact

Growth must not make institutional review less traceable or less reconstructable.

## Summary

Controlled growth is part of governance.

The repository should remain small, explicit, and institutionally justified until a later, documented need requires expansion.
