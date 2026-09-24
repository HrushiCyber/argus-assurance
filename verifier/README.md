# ARGUS VSC Reference Verifier

## Purpose

The reference verifier is the first executable implementation of the ARGUS Verifiable System Claim (VSC) protocol.

Its purpose is to demonstrate that VSC claims can be independently parsed, validated, cryptographically checked, and evaluated without trusting the issuer or ARGUS itself.

## Verification Pipeline

The verifier MUST evaluate claims in this order:

1. Parse input.
2. Validate schema and version.
3. Validate semantic structure.
4. Resolve subject identity.
5. Validate scope.
6. Resolve canonicalization.
7. Verify signature.
8. Verify evidence integrity.
9. Resolve trust context.
10. Check temporal validity.
11. Evaluate assumptions.
12. Resolve dependencies.
13. Detect invalidation.
14. Evaluate proof obligations.
15. Evaluate falsification status.
16. Apply verifier policy.
17. Produce a deterministic verification result.
18. Produce an auditable verification trace.

## Core Rule

A successful signature MUST NOT imply a valid security claim.

A claim is VERIFIED only when all mandatory verification conditions required by the active policy are satisfied.

## Result States

The reference verifier supports:

- `VERIFIED`
- `INVALID`
- `EXPIRED`
- `REVOKED`
- `INSUFFICIENT_CONTEXT`
- `UNSUPPORTED`

The verifier MUST NOT silently convert uncertainty or missing context into `VERIFIED`.

## Verification Result

The implementation MUST produce a result structurally equivalent to:

```json
{
  "status": "VERIFIED",
  "claim_id": "claim-031",
  "verifier_id": "argus-reference-verifier",
  "policy_id": "default-vsc-policy",
  "evaluated_at": "2026-09-24T10:00:00Z",
  "assumptions": {
    "satisfied": [],
    "unsatisfied": [],
    "unknown": []
  },
  "dependencies": {
    "valid": [],
    "invalid": [],
    "unknown": []
  },
  "evidence": {
    "valid": [],
    "invalid": [],
    "missing": []
  },
  "falsification": {
    "passed": [],
    "failed": [],
    "not_run": []
  },
  "trace": []
}
