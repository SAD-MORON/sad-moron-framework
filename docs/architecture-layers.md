# Architecture Layers

## Purpose

This document defines the architectural layering for SAD Moron and clarifies the boundary of `sad-moron-framework` as a governance-only repository.

## Layer Model

### LAYER 1 — GOVERNANCE / FRAMEWORK

Repo: `sad-moron-framework`

Purpose:
- protocols
- boundaries
- normative scope
- evidence rules
- infrastructure growth limits

This layer defines the meaning of governance objects and the rules lower layers must follow.

This layer does not execute, ingest, normalize, or automate.

### LAYER 2 — IMPLEMENTATION / ADAPTERS

Future repos:
- `sad-moron-connectors`
- `sad-moron-runtime`
- `sad-moron-appscript`

Purpose:
- APIs
- connectors
- Apps Script
- normalization
- ingestion

This layer may implement interfaces and technical adapters, but it may not redefine the governance framework established in Layer 1.

### LAYER 3 — OPERATIONS / INSTITUTIONAL USE

Purpose:
- real spreadsheets
- dashboards
- administrative workflows
- declared sources

This layer is where institutional work happens in practice.

It operates with real administrative artifacts and real declared sources, but it must remain bounded by the governance definitions and evidence rules defined above.

### LAYER 4 — AUDIT / RECONSTRUCTION

Future repo: `sad-moron-audit`

Purpose:
- temporal comparison
- omission detection
- append-only evidence
- `E+` / `E-` reconstruction

This layer focuses on review, reconstruction, and audit interpretation over time.

It should remain able to reconstruct what was expected, what was declared, what was found, and what institutional decision followed.

## Layer Rules

### Rule 1: Governance precedence

Layer 1 governs the lower layers.

### Rule 2: No downward redefinition

Layers 2, 3, and 4 may apply governance rules, but they may not redefine governance semantics, evidence categories, or normative scope.

### Rule 3: Separation of implementation and governance

Implementation concerns belong in future implementation repositories, not in `sad-moron-framework`.

### Rule 4: Audit independence

Audit and reconstruction should remain conceptually separate from implementation so that later review is not controlled by the same layer that performs ingestion or normalization.

## Pipeline / Planner Interpretation

The layers may operate as a governed pipeline:

source declaration -> expected event definition -> ingestion/normalization -> validation -> omission detection -> audit report -> institutional decision

This pipeline should be interpreted as layered governance flow, not as an instruction to collapse all concerns into a single repository.

## Summary

`sad-moron-framework` exists only at Layer 1.

Its role is to govern future implementation, operational use, and audit reconstruction without becoming those things itself.
