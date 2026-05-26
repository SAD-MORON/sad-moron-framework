# Janus Adaptation

## Purpose

This document explains how Janus-inspired concepts are adapted into `SAD-MORON-FRAMEWORK` without importing the full Janus architecture.

## Adaptation Principle

SAD Moron uses Janus as a conceptual reference for minimal governance structure, not as a software template.

The adaptation is selective, institutional, and documentation-first.

## Concepts Adapted

### Evidence distinction

The framework adopts:
- `E+` for explicitly recorded supporting evidence
- `E-` for verified absence of an expected record under declared scope

This distinction helps separate:
- what is present in the institutional record
- what is expected but absent within a bounded review

### Append-only institutional history

The framework adopts the principle that governance history should not be silently rewritten.

Corrections, clarifications, and later decisions should be recorded as additional institutional entries rather than as erasures of prior review history.

### Deterministic reconstruction

The framework adopts the requirement that a later reviewer should be able to reconstruct:
- what was reviewed
- under which source scope
- under which period
- under which rule set
- with which evidence result

### Omission detection

The framework adopts omission detection as a bounded governance practice.

An omission finding requires:
- an expected record
- declared sources
- a defined search period
- an explicit review scope

### Human accountability boundary

The framework adopts the principle that accountable institutional decisions must remain human decisions.

Documentation may support review, but it may not replace responsible authority.

## Concepts Not Adapted

The framework does not adapt:
- Janus runtime architecture
- demo runtimes
- agent-control patterns
- generic development protocols
- bridge or watcher mechanisms
- SDK structures
- execution tooling

## Institutional Reframing

Janus concepts are reframed for SAD Moron as institutional governance concepts:
- logs become institutional record layers
- evidence becomes administrative support or bounded absence
- governance events become accountable review outcomes
- rebuildability becomes institutional reconstruction

## Practical Consequence

This repository should grow first through:
- definitions
- source declarations
- event taxonomy
- protocols
- audit documentation

It should not grow first through software implementation.

## Reference

Primary conceptual source:
- `reports/SAD_MORON_JANUS_ADAPTATION_REVIEW_V1.md`
