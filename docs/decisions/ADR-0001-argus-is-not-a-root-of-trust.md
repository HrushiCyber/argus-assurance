# ADR-0001: ARGUS Is Not a Root of Trust

**Status:** Accepted  
**Date:** 2026-09-24  
**Decision Type:** Architecture  
**Scope:** ARGUS protocol, assurance semantics, verification infrastructure

## Context

ARGUS evolved from security-control validation into infrastructure for
machine-verifiable claims about digital systems.

A critical architectural question is:

> Should ARGUS itself become the authoritative root of trust for the claims
> it verifies?

A central trust authority would simplify some deployment models, but it would
also introduce systemic coupling and create a single entity whose compromise,
failure, policy changes, or commercial incentives could affect the trust
decisions of the ecosystem.

ARGUS therefore requires a trust model that allows relying parties to make
their own trust decisions.

## Decision

ARGUS will **not** be a global root of trust.

ARGUS provides:

- assurance semantics
- claim structures
- evidence binding
- proof construction
- verification algorithms
- dependency and invalidation semantics
- falsification mechanisms
- conformance requirements
- interoperability mechanisms

Trust remains a decision made by the relying party according to its own
policy and trust configuration.

ARGUS may support trust anchors, issuers, verifiers, transparency services,
and federation metadata, but none of these are globally authoritative merely
because they participate in the ARGUS ecosystem.

## Trust Model

The architecture separates four concepts:

### 1. Claim

A bounded statement about a subject.

### 2. Evidence

Material supporting the claim.

### 3. Verification

A deterministic or explicitly bounded process that evaluates the claim,
evidence, dependencies, assumptions, and policy.

### 4. Trust Decision

A relying party's decision about whether the verified result is sufficient
for its purpose.

These concepts must not be collapsed into a single global trust score.

## Consequences

### Positive

- Multiple independent issuers can coexist.
- Multiple independent verifiers can coexist.
- Organisations can operate their own trust domains.
- Relying parties retain policy control.
- ARGUS can interoperate with existing trust ecosystems.
- A compromised ARGUS service does not automatically invalidate every
  ecosystem trust decision.
- Independent implementations can verify claims without depending on one
  central ARGUS service.
- The protocol can remain useful across different regulatory and operational
  environments.

### Negative

- Trust configuration becomes more complex.
- Relying parties must define appropriate trust policies.
- Different organisations may reach different decisions from the same claim.
- Federation requires explicit trust-domain metadata.
- Interoperability requires careful handling of algorithms, schemas,
  identities, freshness, revocation, and policy versions.

These costs are accepted because centralising trust would create a larger
systemic dependency.

## Security Properties

The decision is intended to prevent the following architectural failure:

> "ARGUS verified it, therefore the system is trusted."

That statement is invalid.

A valid ARGUS verification result means that the claim satisfied the
specified verification policy and available evidence at the relevant time.

It does not establish universal security or universal trust.

## Falsification Strategy

This architectural decision should be considered violated if an ARGUS
implementation requires a central ARGUS-controlled authority for independent
verification.

Security testing should attempt to demonstrate:

1. A claim cannot be independently verified without contacting ARGUS.
2. A relying party cannot select its own trust anchors.
3. A relying party cannot apply its own verification policy.
4. A compromised ARGUS service can silently alter previously issued claims.
5. Revocation or freshness decisions require a single ARGUS-controlled
   service.
6. Independent verifier implementations produce materially different results
   for identical valid inputs without a documented policy difference.

Any confirmed result should trigger architectural review.

## Compatibility

This decision preserves compatibility with:

- existing PKI trust models
- SPIFFE/SPIRE trust domains
- software supply-chain provenance systems
- remote attestation ecosystems
- transparency systems
- federated identity systems
- organisation-specific assurance policies

ARGUS should integrate with these mechanisms rather than replace them.

## Rejected Alternatives

### Central ARGUS Root of Trust

Rejected because it creates excessive systemic dependency and conflicts with
independent verification.

### Single Global ARGUS Trust Score

Rejected because heterogeneous claims, evidence, risk models, and relying-party
policies cannot be meaningfully reduced to one universally authoritative score.

### Mandatory ARGUS Registry

Rejected as a protocol requirement.

A registry may be useful in particular deployments, but protocol correctness
must not depend on one central registry.

## Known Unknowns

- Optimal federation metadata model.
- Operational cost of maintaining independent trust domains.
- Revocation distribution at global scale.
- Transparency availability requirements.
- Policy interoperability between independent relying parties.
- Long-term governance model for protocol evolution.

These remain implementation and research questions rather than reasons to
centralise trust.

## Result

ARGUS is defined as **assurance and verification infrastructure**, not as a
global authority that decides what systems should be trusted.

The core invariant is:

> **No system is trusted by ARGUS. ARGUS makes bounded claims independently
> verifiable so another system can decide what trust to place in them.**
