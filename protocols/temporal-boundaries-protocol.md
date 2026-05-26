# Temporal Boundaries Protocol

## Purpose

This protocol defines how time and period boundaries constrain governance review in SAD Moron.

## Boundary

This protocol governs conceptual temporal scope only.

It does not define:
- scheduling systems
- job timing
- cron behavior
- implementation clocks

## Responsibilities

This protocol is responsible for defining:
- when a review period starts
- when a review period ends
- how deadlines or expected intervals are stated
- how temporal boundaries affect omission interpretation

## Exclusions

This protocol excludes:
- automatic reminders
- runtime timers
- polling strategies
- operational calendar implementation

## Enforcement Rules

### Rule 1: Defined period required

No omission finding should be treated as valid unless the relevant review period is defined.

### Rule 2: Temporal proportionality

The time boundary must be appropriate to the administrative obligation being reviewed.

### Rule 3: Boundary visibility

Every governance review should make explicit the period used to interpret presence or absence.

### Rule 4: No timeless omission

An expected record cannot be treated as omitted in the abstract. It must be evaluated against a concrete period.

## Summary

Temporal boundaries prevent governance review from turning undefined lateness or uncertainty into false omission claims.
