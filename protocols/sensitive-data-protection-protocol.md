# Sensitive Data Protection Protocol

## Purpose

This protocol defines the documentation-first protection rules for sensitive institutional data in `SAD-MORON-FRAMEWORK`.

It exists to ensure that workflow registration, declared source registration, and future omission review planning do not normalize unsafe handling of personal or restricted administrative data.

## Sensitive Data Definition

Within this repository, sensitive data includes:
- names
- DNI
- CUIL
- contact data
- employment status
- health or license data
- disciplinary data
- salary or liquidation data
- any personally identifiable administrative record

If a source can identify a person directly or indirectly in administrative context, it must be treated as sensitive unless a documented institutional rule states otherwise.

## Rule 1: Documentation first

No real spreadsheet workflow should be registered for operational use until its governing workflow, declared source, and applicable normative context have been documented.

Sensitive-source handling requirements must be declared before runtime implementation, connector work, or Apps Script planning proceeds.

## Rule 2: Metadata-first testing

All early analysis, validation design, and workflow planning must begin with metadata-first testing.

Preferred early inputs include:
- sheet existence
- tab names
- column names
- row counts
- timestamps
- record presence indicators
- workflow status markers

Real personal data must not be used when metadata is sufficient to validate workflow structure, timing, or source existence.

## Rule 3: No real data in Git

Real sensitive data must not be committed to Git in this repository.

This prohibition includes:
- exported spreadsheet rows
- copied form responses
- pasted personnel records
- screenshots containing personal data
- attachments containing sensitive administrative content

This repository is for governance documentation only, not for storing operational personal data.

## Rule 4: No credentials or tokens in Git

Credentials, tokens, secrets, session artifacts, or access keys must not be committed to Git in this repository.

Future implementation repositories must preserve the same prohibition.

## Rule 5: Minimum necessary fields

Any declared workflow or source that may involve sensitive data must define the minimum necessary fields required for its institutional purpose.

If a field is not required for the declared workflow purpose, it should not be copied, exported, cached, or included in evidence planning.

## Rule 6: Anonymization or hashing for evidence

When evidence must reference sensitive operational records, evidence should use anonymization or hashing rather than copying personal data whenever institutional purpose allows it.

Evidence design should prefer:
- hashed identifiers
- redacted excerpts
- aggregate counts
- non-identifying status indicators
- temporal markers without copied personal content

## Rule 7: Institutional authorization required

Sensitive sources may not be accessed without documented institutional authorization appropriate to the source and workflow.

Declared source registration should record the authorization basis, ownership boundary, and intended use before access proceeds.

## Rule 8: Read-only first access

Any new sensitive source must begin with read-only first access.

Before any write-capable or modifying interaction is considered, the source must first be reviewed for:
- institutional purpose
- declared workflow relevance
- sensitive data risk
- minimum necessary fields
- audit expectations

## Rule 9: Sensitive risk classification in declared sources

Every declared source that may contain personal or administrative records must include an explicit sensitive data risk classification.

At minimum, the declaration should clarify:
- whether the source contains sensitive data
- what categories are present
- whether metadata-first review is possible
- whether authorization is required
- whether read-only first access applies

## Rule 10: Excluded fields in workflows

Every workflow that may touch sensitive data must define excluded fields.

Excluded fields are fields that are present in an operational source but are not necessary for the declared workflow purpose and therefore must not be copied into evidence, extracts, or implementation planning.

## Rule 11: Omission detection without personal data copying

Omission detection may operate on existence, status, timestamps, expected-event presence, and comparable metadata without copying personal data.

Where omission review can be performed using non-identifying administrative indicators, that method should be preferred over any approach that reproduces personally identifiable records.

## Compliance Effect

This protocol applies before real spreadsheet workflows are registered for operational use.

No future Apps Script, connector, or runtime implementation should proceed unless the relevant workflow and declared source documentation are compatible with this protocol.
