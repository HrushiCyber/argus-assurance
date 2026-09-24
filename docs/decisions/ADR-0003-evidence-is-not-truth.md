# ADR-0003: Evidence Integrity Does Not Establish Truth

**Status:** Accepted  
**Date:** 2026-09-24  
**Decision Type:** Assurance Semantics / Security  
**Scope:** Evidence, proofs, verification, telemetry, attestations

## Context

ARGUS depends on evidence from heterogeneous sources:

- runtime telemetry
- security controls
- validation executions
- software provenance
- remote attestation
- physical sensors
- policy engines
- external assurance systems

Cryptographic mechanisms can establish properties such as:

- integrity
- authenticity
- provenance
- temporal binding
- identity binding

They cannot, by themselves, establish that the underlying observation is
truthful or complete.

For example, a signed telemetry record can prove that a trusted key signed a
specific record. It does not automatically prove that:

- the sensor observed the correct event
- the sensor was correctly configured
- the telemetry was complete
- the producer was uncompromised
- the observation represents the entire relevant system
- the asserted security property actually holds

ARGUS therefore requires an explicit separation between evidence integrity and
claim truth.

## Decision

ARGUS will treat **evidence integrity as a prerequisite for verification, not
as proof of the underlying security property**.

Verification must evaluate both:

1. whether evidence is authentic, intact, correctly scoped, and sufficiently
   fresh; and
2. whether that evidence satisfies the proof obligations required by the
   claim.

A valid signature does not imply a valid assurance claim.

A valid evidence hash does not imply a valid assurance claim.

A trusted issuer does not imply that every claim issued by that issuer is
true.

## Evidence Layers

ARGUS distinguishes at least four layers:

### Layer 1 — Integrity

Can the verifier establish that the evidence has not been modified relative
to its committed representation?

Examples:

- cryptographic hash
- authenticated message
- signed object

### Layer 2 — Provenance

Can the verifier establish where the evidence came from and under which
identity or authority it was produced?

Examples:

- issuer identity
- workload identity
- device identity
- attestation identity

### Layer 3 — Observation Validity

Does the evidence provide a sufficiently reliable observation for the claim?

This may require:

- sensor validation
- telemetry completeness
- environment validation
- clock assumptions
- schema validation
- source health
- independent observation

### Layer 4 — Property Assurance

Does the validated evidence establish the property claimed by the assertion?

This is the actual assurance question.

The layers must not be collapsed.

## Example

Consider a claim:

> Workload W executed only approved software.

Suppose an attestation object is:

- correctly signed
- issued by an approved authority
- cryptographically intact

That establishes properties about the attestation object.

It does not automatically establish that:

- the workload identity is correctly bound to W
- the measurement represents the relevant execution environment
- the measurement covers all executable components
- the approved software policy was correctly defined
- the runtime environment was not modified outside the measured boundary

Additional proof obligations may therefore be required.

## Verification Semantics

A verifier should conceptually evaluate:

```text
EvidenceIntegrity
        AND
EvidenceProvenance
        AND
ObservationValidity
        AND
ProofObligationsSatisfied
        AND
AssumptionsSatisfied
        AND
DependenciesValid
        AND
FreshnessValid
        AND
PolicySatisfied
