# Change Control Protocol

## Purpose

This protocol governs how normative framework changes are proposed, evaluated, approved, and recorded within `SAD-MORON-FRAMEWORK`.

## Boundary

This protocol governs governance change control only.

It does not define:
- software release processes
- CI/CD approvals
- deployment gates
- implementation roadmaps

## Responsibilities

This protocol is responsible for defining:
- what counts as a governance change
- who may propose changes
- what justification and evidence are required
- what review gate applies
- how approval is recorded
- how the append-only decision trail is preserved

## What Counts as a Governance Change

A governance change includes any change that modifies:
- canonical framework meaning
- normative boundary
- declared source authority or scope
- expected-event interpretation
- evidence classification meaning
- omission review boundary
- repository separation rules
- infrastructure growth limits
- document authority classification

## Who May Propose Changes

Governance changes may be proposed by:
- authorized framework maintainers
- authorized institutional reviewers
- designated governance contributors acting within declared scope

Proposal authority does not equal approval authority.

## Required Justification

Every governance change proposal must include:
- the specific governance problem being addressed
- the reason current framework language is insufficient
- the expected effect on future repositories
- the affected documents
- the boundary impact, if any

## Required Evidence

Every governance change proposal must include evidence appropriate to the change, such as:
- institutional rationale
- regulatory or procedural reference
- conflict or ambiguity observed in the framework
- audit finding
- reconstruction need

Where the change responds to external review, the relevant audit artifact should be cited explicitly.

## Review Gate

No governance change should be treated as valid until it passes a review gate that checks:
- scope clarity
- compatibility with canonical governance core
- compatibility with normative scope
- consistency with repository separation
- absence of silent runtime expansion

## Approval Rule

A governance change requires explicit approval by the responsible human governance authority for the framework.

Approval must be:
- explicit
- documented
- attributable
- traceable to the affected governance artifacts

## Append-Only Decision Trail

Governance change history must remain append-only in meaning.

Corrections, refinements, or superseding decisions should add to the decision trail rather than silently erase prior governance reasoning.

Git history helps preserve this trail, but the governance intent must also remain explicit in the document set and associated decision artifacts.

## Repository History Integrity

Where repository platform controls are available, governance repositories should preserve history integrity through controls such as:
- branch protection on the primary branch
- anti-force-push governance
- append-only operational controls for governance history

These controls strengthen repository history preservation, but they do not replace accountable human review or the documented governance decision trail.

## Prohibition on Silent Governance Changes

Silent governance changes are prohibited.

No contributor may:
- change normative meaning without explicit documentation
- alter canonical or protocol authority by implication
- widen governance scope without stated justification
- convert evidence or audit artifacts into governing rules without explicit promotion

## Exclusions

This protocol excludes:
- feature planning for future runtime repos
- connector implementation changes
- operational spreadsheet changes
- audit tooling mechanics

## Enforcement Rules

### Rule 1: Explicit proposal required

No governance change begins implicitly. It must be proposed as a governance change.

### Rule 2: Evidence before approval

No governance change should be approved without declared justification and supporting evidence.

### Rule 3: Human review required

Governance change approval must remain attributable to accountable human authority.

### Rule 4: Append-only reasoning

Governance change records should preserve prior reasoning rather than conceal it.

## Summary

Governance changes in `SAD-MORON-FRAMEWORK` must be explicit, evidenced, reviewed, approved, and traceable.
