# ADR-0002: Assurance Is Not a Security Score

**Status:** Accepted  
**Date:** 2026-09-24  
**Decision Type:** Assurance Semantics  
**Scope:** ARGUS claims, verification, policy evaluation, reporting

## Context

Security systems frequently compress heterogeneous observations into a single
score.

Examples include:

- security posture scores
- maturity scores
- control scores
- risk scores
- vendor ratings
- compliance percentages

These values can be useful for specific operational purposes, but they do not
provide a sufficient semantic representation of whether a bounded security
property was actually demonstrated.

ARGUS requires machine-verifiable assurance that preserves:

- what was claimed
- about which subject
- under which assumptions
- using which evidence
- within which scope
- for what period
- under which verification policy
- with which dependencies
- with which falsification conditions

A scalar score cannot faithfully represent these dimensions.

## Decision

ARGUS will not define a universal global security score.

ARGUS will represent assurance as **bounded, structured, verifiable claims**.

A verification result may contain structured state such as:

- `VERIFIED`
- `INVALID`
- `EXPIRED`
- `REVOKED`
- `INSUFFICIENT_CONTEXT`
- `UNSUPPORTED`

The exact verification result is determined by the applicable verification
policy and the evidence available to the verifier.

A relying party may derive its own risk or decision score from verified ARGUS
claims, but that score is outside the core ARGUS assurance semantics.

## Claim Model

A meaningful assurance statement should identify, as applicable:

```text
Subject
Property
Scope
Assumptions
Evidence
Validation
Proof
Dependencies
Freshness
Invalidation Conditions
Verification Policy
Verifier Identity
