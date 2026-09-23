# Phase 5 — Independent Trust Infrastructure

Phase 5 strengthens ARGUS by separating evidence production from evidence verification.

The fundamental question becomes:

> Who verifies the verifier?

## The Trust Problem

A security system can produce:

- telemetry,
- validation results,
- evidence,
- assertions,
- compliance reports,
- assurance claims.

However, the producer of evidence should not automatically be treated as the independent authority on whether that evidence proves the claim.

Therefore:

**Evidence Production ≠ Evidence Verification**

## Independent Verification

ARGUS introduces explicit separation between:

1. Claim definition
2. Validation execution
3. Evidence production
4. Evidence custody
5. Proof generation
6. Independent verification
7. Relying-party decision

Different trust domains may perform these functions.

## Trust Architecture

The conceptual flow becomes:

**Subject → Control → Validation → Evidence → Proof → Independent Verification → Trust Decision**

The verifier evaluates whether the supplied proof satisfies the declared assurance requirements.

The verifier does not simply accept the producer's conclusion.

## Cryptographic Provenance

Evidence and proofs should be bound to:

- Subject
- Scope
- Validation execution
- Evidence identifiers
- Evidence digests
- Validation procedure
- Validator identity
- Timestamps
- Freshness requirements
- Assumptions
- Verification policy

Cryptographic integrity does not automatically establish truth.

It establishes that the verified object has not been altered relative to the trust boundary.

## Trust Anchors

Production deployments may use existing trust infrastructure such as:

- Enterprise PKI
- Workload identity
- SPIFFE / SPIRE
- Verifiable Credentials
- Transparency systems
- Signed provenance
- Hardware-backed attestation

ARGUS should not invent a new root of trust when an established trust mechanism is sufficient.

## Independence

Independence must be represented explicitly.

Examples of verification relationships include:

- Same system verification
- Separate service verification
- Separate security domain
- Independent security team
- Independent assessor
- Customer-observed verification
- Third-party verification

Independence is a property of the dependency graph and trust relationships.

It should not be reduced to an arbitrary numerical score.

## Evidence Custody

Evidence may remain with the organisation that generated it.

A verifier may instead receive:

- Evidence digests
- Signed assertions
- Selectively disclosed evidence
- Cryptographic commitments
- Verification receipts
- Proof packages

This allows assurance without requiring unrestricted transfer of sensitive telemetry.

## Verification Result

A verifier should be able to return states such as:

- VALID
- INVALID
- INCONCLUSIVE
- STALE
- EXPIRED
- REVOKED
- UNVERIFIED

A cryptographically valid signature does not necessarily mean the underlying security claim is true.

## Falsification

Trust infrastructure must define how claims can be challenged.

Potential falsification conditions include:

- Evidence substitution
- Signature compromise
- Invalid provenance
- Stale evidence
- Changed validation semantics
- Changed subject
- Changed environment
- Missing evidence
- Unsupported verification method
- Compromised verifier
- Trust-anchor failure

## Result

Phase 5 establishes independent verification as a first-class architectural concern.

ARGUS moves from:

**"A system says its control passed."**

toward:

**"A defined verifier can independently determine whether a bounded assurance claim is supported by the supplied proof."**

## Known Limitations

Independence is difficult to guarantee in real systems.

Potential problems include:

- Shared infrastructure
- Shared administrators
- Common software dependencies
- Correlated evidence sources
- Compromised trust anchors
- Insider influence
- Supply-chain dependencies
- Collusion
- Verifier compromise

Therefore, ARGUS treats independence as an explicit property to be modelled and verified rather than assumed.
