# Normative Document Registry

## Purpose

This document classifies framework documents by authority level so future repositories can distinguish governing rules from explanatory material and audit evidence.

## Authority Classes

### Canonical

Canonical documents provide the highest governance reference within the framework layer.

They define the authoritative anchor future repositories should cite when a single governing document is required.

### Normative

Normative documents define institutional meaning, boundary, and governance interpretation that other framework artifacts must respect.

### Protocol

Protocol documents define governance procedures, responsibilities, exclusions, and enforcement rules within the framework layer.

These are protocol-level normative documents.

### Explanatory

Explanatory documents clarify structure, rationale, or adaptation context but do not override canonical or normative meaning.

### Audit / Report Evidence

Audit and report documents provide review evidence, analysis, or append-only governance artifacts.

They are not governing rules unless explicitly promoted through governed change control.

## Registry

### Canonical

- `docs/governance-core.md`

Explicit identification:
- `docs/governance-core.md` is the canonical governance reference for `SAD-MORON-FRAMEWORK`

### Normative

- `docs/normative-framework.md`
- `docs/scope-and-boundaries.md`
- `docs/declared-sources-catalog.md`
- `docs/architecture-layers.md`

### Protocol

Protocol-level normative documents include:
- `protocols/*.md`

This includes current protocol documents such as:
- framework contracts
- declared sources
- expected events
- temporal boundaries
- evidence classification
- institutional governance
- connector compliance
- audit reconstruction
- normative scope
- repository separation
- pipeline planner
- omission detection
- infrastructure growth
- change control

### Explanatory

- `docs/janus-adaptation.md`

### Audit / Report Evidence

- `reports/*.md`

Explicit identification:
- `reports/*.md` are evidence and audit artifacts, not governing rules unless later promoted through governed change control

## Interpretation Rule

If a document conflict occurs:
1. canonical documents take precedence
2. normative documents take precedence over explanatory and report artifacts
3. protocol documents govern procedural interpretation within the framework layer
4. reports and audits inform governance evidence but do not govern by default

## Summary

This registry exists so future SAD Moron repositories can distinguish governance authority from explanation and evidence.
