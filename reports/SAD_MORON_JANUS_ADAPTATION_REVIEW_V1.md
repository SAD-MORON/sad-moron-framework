# SAD Moron Janus Adaptation Review v1

Date: 2026-05-26
Scope reviewed:
- `/Users/martinsanchezmorales/Janus/janus-governance-core`
- `/Users/martinsanchezmorales/Janus/janus-framework-stack`

## Executive Summary

SAD Moron should adopt only the minimal Janus governance kernel, not the full Janus stack.

The safe adaptation target is:
- explicit evidence classification (`E+` / `E-`)
- append-only institutional records
- deterministic reconstruction of administrative history
- omission detection under declared search scope
- explicit human authority boundary for accountable decisions

SAD Moron should not import Janus as a runtime architecture, agent framework, or generalized operational platform. The recommended path is a clean implementation with documentation-first governance rules and a narrow repository structure oriented to institutional administration.

## Review Basis

### From `janus-governance-core`

The repository consistently defines a small governance kernel centered on:
- three append-only logs: `MANAGEMENT_LOG`, `SCHEMA_LOG`, `AUDIT_LOG`
- evidence model: `E+` as recorded presence, `E-` as verified absence
- deterministic rebuildability from logs, schema context, and evidence references
- omission detection as a formal governance signal
- explicit human accountability through `HUMAN_DECISION`
- audit-writer boundary to prevent unauthorized governance records

This repository is the strongest source for concepts safe to adapt.

### From `janus-framework-stack`

The framework adds operational patterns:
- protocol-driven documentation
- root-level structure discipline
- separation between protocols, docs, runtimes, demos, and dev work
- read-only observability and audit-oriented workflows
- documentation conventions around explicit scope, purpose, constraints, and non-goals

It is useful as a pattern library, but not as a template to copy wholesale.

### Important caution from the review

The stack and demo runtime include signs of operational drift that reinforce a clean implementation recommendation:
- some framework architecture text duplicates core architecture text rather than narrowing to SAD-specific usage
- the demo runtime uses `HUMAN_DECISION_REGISTERED`, while the core RFCs define `HUMAN_DECISION` as canonical
- the framework contains broader protocol and runtime material that exceeds SAD Moron institutional needs

These are not reasons to reject Janus concepts. They are reasons not to fork the repositories as-is.

## Adapted Janus Principles

### 1. Evidence model: `E+` / `E-`

Adapt for SAD Moron as:
- `E+`: an administrative fact is explicitly recorded in an authorized institutional source
- `E-`: an expected administrative record is absent after a deterministic search over declared sources and time boundaries

Safe use in SAD context:
- proving a document was issued, received, signed, published, or approved
- proving an expected record is missing from a bounded administrative process

Constraints:
- `E-` is valid only if the expected record, search scope, source set, and evaluation window are declared
- `E-` should trigger review, not automatic blame

### 2. Append-only institutional logs

Adapt the Janus log idea as institutional records, not software event infrastructure.

Recommended SAD interpretation:
- `MANAGEMENT_LOG`: administrative events and declared actions
- `SCHEMA_LOG`: definitions of event types, record classes, source catalogs, and governance criteria
- `AUDIT_LOG`: review outcomes, omission findings, and accountable decisions

Safe principle:
- never silently rewrite governance history
- corrections should append superseding entries, not erase prior institutional state

### 3. Deterministic reconstruction

SAD Moron should preserve enough record context to reconstruct:
- what administrative event was claimed
- which declared source supported it
- what rule or schema applied at the time
- whether a review found presence, omission, inconsistency, or human resolution

This is one of the most valuable Janus imports because it creates institutional memory without requiring complex runtime machinery.

### 4. Omission detection

Adapt omission detection narrowly:
- expected administrative step not recorded
- expected publication not found in declared official source
- expected authorization missing for a recorded action
- expected response or filing absent within a defined period

Omission detection should remain:
- bounded
- reproducible
- source-declared
- reviewable by humans

### 5. Governance boundaries

This is essential for an institutional adaptation.

SAD Moron should define:
- which sources count as institutional truth
- who can confirm or reject omission findings
- who can append accountable decisions to the audit layer
- which decisions are advisory versus normatively binding

The strongest Janus concept here is not “AI governance” in general. It is the explicit separation between detection and accountable decision.

## Operational Patterns Worth Adapting from the Framework

### Protocols

Adapt as lightweight governance documents, not automation systems.

Recommended protocol families:
- source declaration protocol
- event classification protocol
- omission review protocol
- publication and record verification protocol
- change control protocol for governance definitions

### Folder structure

The framework’s structural discipline is useful, but SAD Moron should use a smaller surface.

Recommended principle:
- keep normative material separate from reports and examples
- avoid adding top-level folders unless governance need is clear

### Runtime separation

The Janus separation between governance rules and runtimes is good and should be preserved conceptually.

For SAD Moron:
- governance repository should define rules, record models, and audit/report structures
- it should not start with executors, bots, bridges, connectors, or SDKs
- any future operational tooling should live outside the normative core

### Audit layer

The framework’s read-only observability stance is worth keeping.

Adaptation:
- audit artifacts should observe and evaluate declared records
- audit artifacts should not mutate administrative truth
- review reports should reference evidence and scope explicitly

### Documentation conventions

The stack’s document style is useful and should be adopted:
- explicit scope
- purpose
- constraints
- non-goals
- versioned protocol names where needed
- clear distinction between normative and non-normative documents

## What SAD Moron Should Adapt

### Normative boundary

SAD Moron needs an explicit normative boundary that answers:
- what this repository governs
- what it does not govern
- which documents are normative
- which actors can issue accountable review outcomes

Recommended rule:
- only governance definitions, source declarations, event definitions, and audit decision formats are normative
- operational notes, examples, and exploratory material are non-normative unless explicitly promoted

### Declared sources

This is the most important institutional specialization.

SAD Moron should define a declared source catalog for:
- official municipal resolutions
- decrees
- ordinances
- administrative records
- publication surfaces
- inbound/outbound registry artifacts
- any recognized external institutional dependencies

Every evidence claim should reference one of these declared sources or explicitly state that no declared source supports the claim.

### Expected administrative events

SAD Moron should define a first small set of expected events, for example:
- document received
- document registered
- review assigned
- resolution drafted
- authorization recorded
- publication completed
- notification issued
- archival closure recorded

These should be modeled as administrative expectations first, not runtime events.

### Controlled infrastructure growth

Growth should be controlled through governance, not convenience.

Recommended rule:
- no new top-level subsystem without written justification
- no runtime/tooling directory in v1 unless a concrete institutional need is proven
- no generalized “agent” or “automation” layer in the initial repository

## What Should Not Be Imported

### Unnecessary runtime complexity

Do not import:
- demo runtimes
- watcher/bridge patterns
- SDK assumptions
- execution pipelines designed for development environments

These solve Janus operational problems, not SAD Moron’s initial governance problem.

### Generic agent tooling

Do not import:
- prompt governance as a central repository concern
- bot scheduling abstractions
- agent interaction controls
- generic AI-assisted development workflow machinery

These are orthogonal unless SAD Moron later defines a real institutional AI operation boundary.

### Experimental modules

Do not import:
- demos as structural requirements
- archive content
- milestone experiments
- partially evolved operational protocols without SAD-specific need

### Infrastructure outside SAD scope

Do not import:
- frontend product layer protocols
- web governance modules unless municipal publication control is explicitly in scope
- developer tooling layers
- broad observability surfaces meant for software runtimes

## Recommended Repo Structure for `sad-moron-framework`

Minimal recommended structure:

```text
sad-moron-framework/
├── README.md
├── reports/
├── core/
│   └── SAD_MORON_GOVERNANCE_CORE_V1.md
├── docs/
│   ├── glossary.md
│   ├── governance-scope.md
│   ├── declared-sources.md
│   ├── event-model.md
│   ├── omission-detection.md
│   └── reconstruction-model.md
├── protocol/
│   ├── source-declaration.md
│   ├── record-verification.md
│   ├── omission-review.md
│   └── change-control.md
├── rfcs/
│   └── 0001-sad-moron-governance-core.md
└── examples/
    └── sample-audit-cases.md
```

Notes:
- `core/` holds the minimal normative kernel
- `docs/` explains and stabilizes semantics
- `protocol/` holds operational governance rules without runtime code
- `reports/` stores audit and analysis outputs like this review
- `examples/` is optional and non-normative

Not recommended for v1:
- `runtimes/`
- `dev/`
- `demos/`
- `observability/`
- `sdk/`
- `adapters/`

Those can be introduced later only if a real institutional need appears.

## Initial Scope and Boundaries

### Initial scope

The first SAD Moron repository should cover only:
- institutional governance definitions for records and reviews
- declared source catalog
- administrative event taxonomy
- omission detection rules
- accountable audit decision format
- reconstruction requirements for later review

### Explicit boundaries

The first repository should not cover:
- workflow automation
- municipal service execution
- integrations with live systems
- agent execution
- publishing engines
- user interfaces
- deployment infrastructure

## Risks of Over-Expansion

Primary risks:
- importing software-governance machinery where institutional record discipline is enough
- confusing evidence review with system execution
- creating a pseudo-platform before stabilizing the normative model
- allowing undeclared sources to become shadow truth
- introducing event names or workflows that drift from the declared core
- expanding repository structure faster than the institutional scope justifies

The main failure mode would be building a Janus-shaped software stack instead of a SAD Moron governance repository.

## Recommendation: Fork vs Clean Implementation

Recommendation: clean implementation.

Reasoning:
- SAD Moron needs selective conceptual adaptation, not repository inheritance
- `janus-governance-core` is valuable as a governance reference, but it is broader than the initial SAD need
- `janus-framework-stack` contains useful patterns but also runtime, protocol, and organizational layers outside scope
- a fork would import naming drift, structural overhead, and pressure to preserve Janus-specific concerns that are not institutionally necessary

Best approach:
- write a SAD-specific governance core from scratch
- cite Janus internally as conceptual inspiration if desired
- preserve only the minimal kernel concepts and documentation discipline
- add tooling only after the normative boundary and source model are stable

## Final Conclusion

The safest adaptation is a documentation-first institutional governance repository that imports Janus as a set of principles, not as an architecture.

SAD Moron should adopt:
- evidence as presence and bounded absence
- append-only governance history
- deterministic reconstruction
- omission review under declared scope
- explicit accountable decision boundaries

SAD Moron should reject:
- full stack inheritance
- runtime-first design
- generic agent governance machinery
- non-essential infrastructure expansion

This supports a disciplined, auditable, and institutionally appropriate `sad-moron-framework` without reproducing the full Janus ecosystem.
