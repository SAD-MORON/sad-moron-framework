# AI Agent Guide

## Purpose

This document provides guidance for AI agents reading or operating around `SAD-MORON-FRAMEWORK`.

It exists to clarify which documents are authoritative, which repository boundaries must be preserved, and which safety rules apply before any interpretation, planning, or implementation work proceeds.

## Authoritative Documents

Current repository authority lives primarily in:
- `docs/`
- `protocols/`

Key authoritative documents include:
- `docs/governance-core.md`
- `docs/repository-governance-standard.md`
- `docs/governance-inheritance.md`
- `docs/pilot-context-and-governance-primitives.md`
- `docs/normative-document-registry.md`
- `protocols/change-control-protocol.md`
- `protocols/sensitive-data-protection-protocol.md`
- `protocols/repository-separation-protocol.md`

These documents define governance meaning, repository posture, boundaries, and procedural constraints.

## Reports And Historical Evidence

`reports/` is evidence and history, not the default source of current governance rules.

AI agents must not treat reports, audits, or older review artifacts as current authority when more recent `docs/` or `protocols/` documents define the active rule set.

Reports may inform interpretation, provide background, or explain why a governance artifact exists, but they should not silently override current authoritative documents.

## Runtime And Permission Boundaries

AI agents must not infer runtime permissions from governance documents.

Governance documentation defines meaning, constraints, and repository posture. It does not grant permission to execute connectors, touch live systems, access operational data, or assume deployment authority.

No AI agent should infer:
- runtime permission
- deployment approval
- credential access
- connector authorization
- operational write authority

## Institutional Authority Boundary

AI agents must not invent institutional authority.

No governance interpretation, classification, omission finding, or documentation summary should be presented as an institutional decision unless accountable human authority has explicitly made that decision through the appropriate governed process.

## Sensitive Data Rule

AI agents must never expose sensitive data.

This includes:
- personal identifiers
- administrative records containing protected details
- credentials
- tokens
- secrets
- privileged operational mappings

If a task would require revealing or copying sensitive information, the safe result is `REVIEW` or `BLOCKED` unless explicit authority and safe handling boundaries are already documented.

## Connector And Operational Boundary

AI agents must never create operational connectors without a declared source and declared boundary.

Before any connector, runtime adapter, Apps Script package, ingestion process, or operational integration is proposed as valid, the following minimum conditions must already be satisfied:
- declared source
- boundary definition
- relevant governance context
- sensitive-data handling rule
- human review path

Absent those conditions, the correct classification is `REVIEW` or `BLOCKED`.

## Pilot Boundary

AI agents must never promote a pilot repository into a production claim.

`SAD-MORON-FRAMEWORK` is a governance/documentation layer with pilot context. Its existence does not by itself prove production approval, official endorsement, institutional deployment, or live operational adoption beyond the documented repository scope.

## Uncertainty Classification

When uncertainty exists, AI agents should classify the situation as:
- `REVIEW`
- `BLOCKED`

Use `REVIEW` when:
- meaning is mostly clear but an unresolved governance question remains
- documentation exists but scope, timing, or authority needs confirmation

Use `BLOCKED` when:
- authority is missing
- source boundary is missing
- sensitive-data handling is undefined
- execution would exceed declared repository scope

## Governance Change Rule

AI agents must never modify governance meaning without the change-control protocol.

If a task would alter repository posture, authority hierarchy, source meaning, omission interpretation, public/private boundary, or governance wording, the agent should treat the task as a governed change and reference:
- `protocols/change-control-protocol.md`

## Janus Core Wording Rule

AI agents must preserve the repository's approved Janus Core wording.

Preferred wording:
- "inherits governance principles from Janus Core"
- "selectively applies governance principles derived from Janus Core"

AI agents must not reintroduce wording that implies dependency on the full Janus runtime ecosystem unless that dependency is explicitly documented and true.

## Institutional Neutrality Rule

AI agents must preserve institutional neutrality.

They should:
- avoid self-promotion
- avoid political claims
- avoid founder-centric framing
- avoid overstating endorsement or authority
- keep language sober, bounded, and transferable

## Summary

AI agents should treat `docs/` and `protocols/` as current authority, `reports/` as evidence and history, uncertainty as `REVIEW` or `BLOCKED`, and any operational, sensitive, or governance-changing action as requiring explicit declared boundaries and accountable human review.
