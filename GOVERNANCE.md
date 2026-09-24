# ARGUS Governance

## Purpose

ARGUS is intended to evolve from a security-control assurance implementation
into interoperable infrastructure for machine-verifiable claims about
digital systems.

Governance exists to protect:

- technical correctness
- security
- interoperability
- independent verification
- protocol neutrality
- transparent decision-making
- long-term compatibility

Governance must not become a mechanism for creating unnecessary central
control over the protocol.

## Governance Principles

### Open Development

Technical proposals, significant architectural decisions, and protocol
changes should be documented and reviewable.

### Evidence-Based Decisions

Major architectural decisions should identify:

- the problem
- existing alternatives
- proposed solution
- assumptions
- evidence
- security implications
- compatibility implications
- known unknowns
- validation criteria

### Independent Verification

The ecosystem should support implementations that can verify ARGUS claims
without depending on a single ARGUS-controlled service.

### Interoperability First

ARGUS should integrate with established standards and ecosystems wherever
they adequately solve the relevant problem.

Examples include:

- OSCAL
- OCSF
- OpenTelemetry
- STIX/TAXII
- Sigma
- SLSA
- in-toto
- SPIFFE/SPIRE
- RATS
- Sigstore
- SCITT
- W3C Verifiable Credentials

ARGUS should not redefine an existing mechanism without demonstrating a
specific assurance or interoperability gap.

## Protocol Governance

Future protocol specifications should distinguish:

- schema version
- semantic version
- verifier implementation version
- policy version
- claim profile version

Protocol changes must document compatibility implications.

Breaking changes require an explicit migration strategy.

## Trust Neutrality

ARGUS must not become the mandatory root of trust for the ecosystem.

The architecture should support:

- multiple issuers
- multiple trust domains
- multiple verifiers
- multiple trust anchors
- independent implementations
- customer-controlled verification policies

A cryptographic signature establishes authenticity relative to a trust
decision; it does not independently establish the truth of a claim.

## No Global Security Score

ARGUS should not create a universal security score that implies that
heterogeneous systems can be reduced to one authoritative number.

Assurance claims should remain bounded, contextual, and policy-dependent.

## Transparency

Important governance decisions should be documented.

Where practical, publish:

- specifications
- schemas
- test vectors
- conformance requirements
- security considerations
- architectural decisions
- compatibility profiles
- significant research findings

## Conflict of Interest

Contributors should disclose material conflicts of interest when participating
in decisions affecting:

- protocol governance
- trust infrastructure
- vendor interoperability
- certification
- commercial services
- ecosystem policy

## Security Governance

Security-sensitive changes should receive additional review.

Particular scrutiny is required for changes involving:

- cryptographic verification
- trust anchors
- identity
- authorization
- evidence integrity
- claim invalidation
- revocation
- freshness
- federation
- privacy
- isolation boundaries

Security claims should include a falsification strategy.

## Commercial Neutrality

Commercial ARGUS services may exist, but commercial interests should not
implicitly determine protocol semantics.

Protocol interoperability should remain possible without purchasing a
specific ARGUS service.

## Long-Term Direction

The intended evolution is:

1. Reference implementation
2. Open specification
3. Independent implementations
4. Conformance ecosystem
5. Multi-party governance
6. Neutral stewardship where justified

Governance should mature only when ecosystem adoption creates a concrete need
for additional institutional structure.

Premature governance complexity is itself an architectural liability.

## Decision Records

Significant technical decisions should be recorded under:

`docs/decisions/`

Decision records should explain:

- context
- alternatives considered
- decision
- rationale
- consequences
- evidence
- unresolved questions

## Current Governance Status

ARGUS is currently an open engineering and research project.

The governance model is intentionally lightweight until independent
implementations, external contributors, protocol consumers, and ecosystem
participants create a demonstrated need for formal multi-party governance.
