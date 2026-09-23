# Phase 7 — Global Assurance Network

Phase 7 explores how assurance could operate across organisational boundaries.

The fundamental question becomes:

> How can organisations exchange trustworthy assurance information without sharing their underlying sensitive evidence?

## Core Principle

Raw evidence should generally remain with the organisation that owns it.

What travels across organisational boundaries should be the minimum information required to establish a bounded assurance claim.

The architecture therefore separates:

1. Local Assurance Plane
2. Proof Exchange Plane
3. Federated Intelligence Plane

## Local Assurance Plane

Each organisation maintains its own:

- Security controls
- Telemetry
- Validation systems
- Evidence
- Internal policies
- Trust anchors
- Assurance state

The network does not require organisations to centralise their raw security data.

## Proof Exchange Plane

Organisations can exchange bounded proof objects containing information such as:

- Proof identifier
- Issuer
- Subject
- Claim
- Scope
- Proof method
- Evidence commitment
- Freshness
- Provenance
- Integrity information
- Disclosure policy

The objective is to exchange proof without unnecessarily exchanging raw evidence.

## Federated Intelligence Plane

Aggregated information can provide insight into broad assurance patterns while attempting to preserve organisational privacy.

Potential techniques include:

- Coarse cohorts
- Secure aggregation
- Differential privacy
- Selective disclosure
- Cryptographic commitments
- Privacy-preserving computation

These mechanisms should only be used where they provide measurable value.

## Privacy Principle

ARGUS follows:

**MINIMISE → LOCALISE → COMMIT → DISCLOSE SELECTIVELY → AGGREGATE → PRIVATISE**

The network should not require:

- Raw endpoint telemetry
- Usernames
- IP addresses
- Customer records
- Secrets
- Full security inventories
- Raw attack payloads

## Proof Classes

A possible proof hierarchy includes:

- P0 — No proof
- P1 — Signed assertion metadata
- P2 — Selective proof or commitment
- P3 — Cohort-level statistical proof
- P4 — Secure computation result

These are proof mechanisms, not security scores.

## Assurance Metrics

The network should exchange measurable assurance outcomes rather than simplistic organisational security ratings.

Possible metrics include:

- Validation pass rate
- Revalidation latency
- Stale proof proportion
- Evidence completeness
- Missing telemetry rate
- Detection miss rate
- Resilience failures
- Assurance debt age
- Supplier proof coverage
- Control equivalence

Metrics must retain their population, time period, methodology and limitations.

## Control Equivalence

Two controls should not be considered equivalent merely because they have similar names.

Equivalence should consider:

- Security intent
- Threat model
- Protected asset
- Enforcement mechanism
- Enforcement boundary
- Telemetry
- Validation procedure
- Failure semantics
- Assurance level

A proposed equivalence classification may range from:

**E0 — No demonstrated equivalence**

to:

**E4 — Strong demonstrated equivalence**

Equivalence must remain evidence-based.

## Supplier Assurance

The network could support a supplier assurance workflow:

**Buyer Requirement → Proof Request → Supplier Disclosure Policy → Proof → Verification → Freshness Check → Gap Analysis**

The purpose is to reduce repeated manual evidence collection while retaining explicit uncertainty.

## Independent Issuers

Potential proof issuers include:

- Organisation security teams
- Internal audit
- MSSPs
- Independent assessors
- External auditors
- Customer-observed verifiers
- Cloud providers
- Industry consortium authorities

Issuer identity, validation method, scope and freshness must remain visible.

## Cyber Insurance

ARGUS should provide evidence rather than attempt to become a universal cyber-risk scoring authority.

Insurance or underwriting decisions remain decisions made by the relevant organisation.

## M&A and Third-Party Assurance

Federated proofs could help identify:

- Missing evidence
- Stale assurance
- Control gaps
- Unknown dependencies
- Supplier assurance gaps
- Incompatible control assumptions

The objective is to expose uncertainty rather than conceal it behind a single score.

## Network Effect Hypothesis

A global assurance network could become more useful as more independent participants exchange compatible proofs.

However:

**Network effect is a hypothesis, not an architectural assumption.**

The project must establish whether participation actually creates measurable value.

## Threats

Important threats include:

- False attestations
- Compromised issuers
- Correlated verification
- Privacy leakage
- Re-identification
- Statistical manipulation
- Proof replay
- Stale assurance
- Control-equivalence abuse
- Collusion
- Governance capture

## Falsification

The network architecture should be tested by attempting to:

- Link supposedly private proofs to organisations
- Re-identify participants from aggregates
- Replay expired proofs
- Substitute evidence
- Manipulate cohort statistics
- Exploit control-equivalence mappings
- Use compromised issuers
- Infer sensitive organisational information

## Result

Phase 7 extends ARGUS from enterprise assurance toward federated assurance.

The network model allows organisations to exchange bounded, cryptographically verifiable assurance information while keeping sensitive evidence local.

## Known Unknowns

Important unresolved questions include:

- Whether organisations will share assurance proofs
- Whether privacy requirements reduce practical utility
- Whether independent verification is economically valuable
- Whether network effects materialise
- What governance model can remain neutral
- How proof liability should be allocated
- How different regulatory jurisdictions affect evidence exchange
