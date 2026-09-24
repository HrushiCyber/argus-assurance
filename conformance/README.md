# ARGUS VSC Conformance

## Purpose

This directory defines the conformance model for implementations of the ARGUS Verifiable System Claim (VSC) protocol.

Conformance exists to establish interoperability between independent implementations without requiring trust in the ARGUS reference implementation.

## Conformance Principle

An implementation is conformant only when it produces the required semantic result for the defined test vectors and protocol behaviors.

Passing schema validation alone does not establish VSC conformance.

Conformance MUST cover:

1. Schema validity
2. Canonicalization
3. Signature verification
4. Subject binding
5. Scope validation
6. Evidence integrity
7. Temporal validity
8. Assumption evaluation
9. Dependency validity
10. Proof-obligation evaluation
11. Falsification status
12. Revocation handling
13. Invalidation handling
14. Unsupported-version handling
15. Malformed-input handling

## Implementation Independence

A conformant verifier MUST be capable of validating a VSC produced by an independent issuer implementation.

A conformant issuer MUST NOT require the ARGUS verifier implementation to generate or validate its claims.

Interoperability MUST be demonstrated across independently implemented components.

## Conformance Levels

### Level 0 — Schema

Validates:

- JSON structure
- Required fields
- Data types
- Enumerations
- Structural constraints
- Schema version

Level 0 does not establish cryptographic or semantic conformance.

### Level 1 — Semantic Verification

Validates:

- Claim semantics
- Subject binding
- Scope
- Assumptions
- Evidence references
- Proof obligations
- Freshness
- Dependencies
- Claim lifecycle

### Level 2 — Cryptographic Verification

Validates:

- Canonicalization
- Content digests
- Signature coverage
- Signature verification
- Trust-anchor processing
- Key identification
- Algorithm handling

### Level 3 — Adversarial Conformance

Validates rejection of:

- Tampered evidence
- Invalid signatures
- Replayed claims
- Expired claims
- Revoked claims
- Modified dependencies
- Subject substitution
- Scope expansion
- Missing proof obligations
- Malformed claims
- Unsupported versions
- Invalid trust anchors
- Contradictory evidence

### Level 4 — Independent Interoperability

Demonstrates:

- Independent issuer → verifier interoperability
- Independent verifier → verifier agreement
- Cross-language canonicalization
- Cross-platform cryptographic verification
- Stable verification results
- Reproducible failure classification

Level 4 is the minimum target for production-grade protocol interoperability.

## Required Test Result

Each conformance test MUST produce:

```json
{
  "vector_id": "string",
  "implementation": "string",
  "implementation_version": "string",
  "protocol_version": "string",
  "expected_result": "string",
  "actual_result": "string",
  "passed": true,
  "evaluated_at": "timestamp",
  "trace_digest": "sha256"
}
