# Declared Sources Protocol

## Purpose

This protocol defines how institutional sources become declared sources within the SAD Moron governance framework.

## Boundary

This protocol governs source declaration as a governance act.

It does not govern:
- source ingestion mechanisms
- API connection methods
- scraping or synchronization
- storage implementation

## Responsibilities

This protocol is responsible for defining:
- what qualifies as a declared source
- how source boundaries are described
- how source authority is distinguished from informal references
- how source scope participates in evidence review

Declared sources should be described by:
- institutional origin
- document or record class
- intended governance use
- temporal relevance
- known limitations

## Exclusions

This protocol excludes:
- unrestricted data capture
- undeclared observational sources
- implicit source authority
- connector behavior details

## Enforcement Rules

### Rule 1: No governance without source declaration

No governance claim should rely on a source that has not been declared or explicitly marked as non-authoritative.

### Rule 2: Bounded source use

Each declared source must have a defined boundary so later review can tell what the source was expected to contain.

### Rule 3: Source class transparency

The framework must distinguish official, derivative, reference, and non-authoritative source classes where relevant.

### Rule 4: Connector alignment

Future connectors may access sources, but they must inherit the declared boundary rather than invent one.

## Summary

Declared sources are the entry condition for trustworthy governance review in SAD Moron.
