# Omission Detection Protocol

## Purpose

This protocol defines the conceptual rules for omission review in `SAD-MORON-FRAMEWORK`.

It is documentation only.
It does not implement detection logic.

## Scope

This protocol applies to bounded institutional review of expected administrative records.

It does not apply to:
- automated enforcement
- runtime monitoring
- external system execution

## Core Principle

An omission is not merely a missing item.

Within this repository, omission review is valid only when the absence concerns an expected administrative record under declared scope.

## Required Inputs

Any omission review must define:
- the expected administrative event
- the declared sources to be checked
- the relevant period
- the applicable rule or requirement
- the reviewing authority context

If one of these inputs is missing, the result should be treated as incomplete review, not as a confirmed omission.

## Evidence Model

This protocol uses:
- `E+` when the expected record is found in a declared source
- `E-` when the expected record is not found after bounded review of declared sources and period

`E-` indicates verified absence within scope.
It does not by itself assign blame or institutional fault.

## Review Rules

### Rule 1: Declared-source rule

Only declared sources may be used to support or reject the omission review.

### Rule 2: Defined-period rule

The review must specify the period within which the expected record should exist.

### Rule 3: Deterministic-scope rule

The review should make clear:
- where the search occurred
- what was considered
- which source classes were in scope

### Rule 4: Separation of detection and decision

Detection of `E-` is not the same as an accountable institutional decision.

Human review remains necessary for:
- confirmation
- rejection
- clarification
- escalation

### Rule 5: Reconstruction rule

The review output should preserve enough detail so a later reviewer can understand:
- what was expected
- where it was sought
- during what period
- with what result

## Non-Goals

This protocol does not:
- define sanctions
- automate conclusions
- implement search tools
- create legal determinations

## Summary

This protocol establishes omission review as a bounded, declared, and reconstructable institutional practice.
