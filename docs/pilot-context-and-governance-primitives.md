# Pilot Context And Governance Primitives

## Purpose

This document explains the pilot context that gave rise to `SAD-MORON-FRAMEWORK` and defines the minimum governance primitives that give meaning to the repository for future human readers and AI agents.

It exists to clarify why this repository is documentation-first, why governance precedes automation, and which minimum concepts must remain stable if later repositories or tools inherit from this layer.

## Pilot Context

This repository originated as a governance-oriented pilot initiative within administrative workflows associated with the Secretaria de Asuntos Docentes (SAD) of Moron, Provincia de Buenos Aires, Argentina.

It is a pilot governance/documentation layer.

It does not claim official endorsement beyond its documented repository scope.

It is intended to support continuity, auditability, interoperability, and responsible modernization of educational administrative workflows.

## Why This Repository Exists

Documentation matters because institutional systems often depend on implicit process knowledge, fragile handoffs, and partial records.

Governance must precede automation because automation without declared boundaries, declared sources, and declared authority can reproduce confusion faster rather than reduce it.

Structural omission is a risk in institutional systems because important administrative events may fail to appear, fail to propagate, or fail to remain reconstructable across time, media, or system changes.

Uncontrolled automation can create drift by silently changing categories, evidence meaning, review assumptions, or workflow expectations without an accountable governance decision.

Human institutional authority remains central because governance review, omission signals, and documentation support decision-making, but they do not replace responsible human authority.

## Minimum Governance Primitives

### Boundary

A boundary is the declared limit of what a document, review, workflow, source, or repository governs.

Without a boundary, interpretation can expand silently beyond intended scope.

### Declared Source

A declared source is an explicitly identified source that may support governance interpretation within a defined scope.

Undeclared sources may be referenced descriptively, but they should not be treated as authoritative by default.

### Expected Event

An expected event is an institutional action, obligation, or trace that should exist under a defined process and scope.

Expected events are necessary for bounded omission review.

### Temporal Window

A temporal window is the defined period within which an expected event, review, or evidence claim is evaluated.

Absence without a declared temporal window is not enough to support an omission claim.

### Evidence

Evidence is the recorded basis for supporting or constraining a governance interpretation within a declared source, scope, and period.

Evidence supports review; it does not automatically authorize institutional action.

### Omission

An omission is the bounded absence of an expected event or record under declared source scope, expected-event scope, and temporal window.

Omission is not the same as blame, fault, or final institutional judgment.

### Drift

Drift is unintended change in governance meaning, workflow interpretation, source assumptions, or execution scope that occurs without explicit review and approval.

Drift can be semantic, operational, or structural.

### Append-Only Record

An append-only record preserves prior governance context by adding clarification, supersession, or later findings rather than silently erasing earlier reasoning.

Append-only practice supports auditability and reconstruction.

### PASS / REVIEW / BLOCKED

`PASS` means the declared governance minimum is satisfied for the relevant phase.

`REVIEW` means the repository, workflow, or claim is usable only with unresolved governance questions made explicit.

`BLOCKED` means progression should not continue until the blocking governance issue is resolved.

### Human Authority Gate

The human authority gate is the rule that governance findings, evidence signals, or omission findings do not become institutional decisions without accountable human review or authorization.

### Sensitive-Data Boundary

The sensitive-data boundary is the rule that personal, restricted, or operationally sensitive data must remain protected, minimized, and outside inappropriate repository surfaces.

### Public/Private Operational Boundary

The public/private operational boundary distinguishes what may remain public as governance or documentation from what may remain bounded, external, or separately governed for operational or security reasons.

## Janus Core Relation

`SAD-MORON-FRAMEWORK` selectively applies governance principles derived from Janus Core.

It does not depend on the full Janus runtime ecosystem.

It adapts those governance principles to the educational administrative domain through bounded documentation, repository separation, auditability, omission discipline, and human authority preservation.

## Guidance For AI Agents Reading This Repository

AI agents reading this repository should observe the following rules:
- do not infer runtime permissions from governance docs
- do not invent authority
- do not convert pilots into production claims
- do not extract or expose sensitive data
- do not treat old reports as current rules
- current authority lives in `docs/` and `protocols/`
- when uncertain, classify `REVIEW` or `BLOCKED`

Governance documents define meaning and boundaries, not automatic permission to execute, ingest, publish, or operationalize.

If authority, scope, or sensitivity is ambiguous, the safe interpretation is that additional human review is required.

## Institutional Neutrality

This repository should be read as an institutional governance artifact with pilot origins, not as a political statement, personal brand, or claim of official state endorsement.

Its intended value is continuity, bounded modernization, and reconstructable governance meaning.

## Summary

This repository is a pilot governance/documentation layer that originated in a bounded administrative context and preserves a minimum set of governance primitives so future readers, repositories, and AI agents can interpret it safely.
