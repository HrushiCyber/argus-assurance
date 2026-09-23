# Phase 6 — Open Security Validation Protocol

Phase 6 investigates whether ARGUS should evolve from a product architecture into an open interoperability protocol.

The fundamental question is:

> How can independently produced security validation results be exchanged and verified across different organisations, products and assurance systems?

## Why a Protocol?

Existing ecosystems already provide important building blocks for security interoperability.

Examples include:

- OSCAL
- MITRE ATT&CK
- STIX / TAXII
- Sigma
- OCSF
- OpenTelemetry
- CACAO
- SPIFFE
- Verifiable Credentials
- in-toto
- SCITT
- OPA / Rego

ARGUS should not replace these systems.

The remaining problem is the binding between:

**Control Intent → Scenario → Execution → Telemetry → Detection → Assertion → Evidence → Proof → Freshness → Assurance State**

## Open Security Validation Protocol

The proposed protocol is:

**OSVP — Open Security Validation Protocol**

OSVP is intended as a thin interoperability layer for exchanging security validation intent and assurance results.

It should complement existing standards rather than become another competing security taxonomy.

## Core Objects

An OSVP package can contain:

- Protocol version
- Package identifier
- Package type
- Subject
- Control reference
- Scenario
- Telemetry contract
- Detection contract
- Assertions
- Evidence references
- Proof metadata
- Freshness information
- Provenance
- Verification requirements

## Three Package Types

### Validation Pack

Defines portable validation intent.

It describes what should be validated without requiring a specific vendor implementation.

### Adapter Pack

Defines how portable validation intent is translated into a particular execution or technology environment.

Vendor-specific implementation details remain at the adapter boundary.

### Proof Pack

Contains the resulting assurance claim, evidence references, cryptographic integrity information and verification metadata.

## Assurance States

OSVP should support explicit states including:

- VERIFIED_PASS
- VERIFIED_FAIL
- INCONCLUSIVE
- STALE
- EXPIRED
- REVOKED
- UNVERIFIED
- INVALID

Missing evidence must not automatically be interpreted as detection failure.

Unsupported semantics must be explicitly represented.

## Freshness

Assurance is time-bounded.

A proof should expose information such as:

- observed_at
- issued_at
- fresh_until
- maximum allowed age

A valid signature does not make indefinitely old evidence trustworthy.

## Capability Discovery

Implementations may expose machine-readable capability information.

A capability declaration can describe:

- Supported protocol version
- Supported operations
- Supported evidence types
- Supported detection semantics
- Supported telemetry schemas
- Supported verification methods

Unsupported capabilities must not silently produce an assurance result.

## Cryptographic Proof

OSVP may carry cryptographic proof metadata.

The protocol should remain compatible with established mechanisms including:

- Enterprise PKI
- Verifiable Credentials
- in-toto
- Transparency systems
- Hardware-backed attestation

OSVP is not intended to become a new universal root of trust.

## Conformance

A conforming implementation must not silently reinterpret unsupported semantics.

Implementations should declare:

- Supported protocol version
- Supported object types
- Supported semantic features
- Verification capabilities
- Security limitations

Conformance claims should remain narrow.

There should be no generic claim such as:

> "OSVP certified secure."

## Security Threats

Important threats include:

- Forged proof
- Modified validation result
- Evidence substitution
- Replay
- Stale telemetry
- Semantic downgrade
- Untrusted issuer
- Missing telemetry misclassification
- Compromised verifier
- Malicious validation package
- Adapter semantic drift

## Falsification Strategy

Protocol security should be tested by deliberately attempting to:

- Modify signed fields
- Replace evidence digests
- Replay old proofs
- Submit stale observations
- Remove required evidence
- Change adapter semantics
- Introduce unsupported critical extensions
- Use an untrusted signing key
- Apply a proof to a different subject

A protocol security claim is incomplete without a defined way to falsify it.

## Governance

OSVP should not become an ARGUS-controlled proprietary standard.

A credible open protocol would require:

- Public specification
- Open change process
- Reproducible test vectors
- Compatibility matrix
- Independent implementations
- Versioning rules
- Clear extension rules
- Vendor-neutral governance

A stable protocol should require multiple independent implementations before claiming interoperability.

## Kill Criteria

OSVP should be reconsidered if:

1. Existing standards can express the complete assurance transaction with lower complexity.
2. Independent implementations cannot interoperate without ARGUS-specific semantics.
3. The protocol creates more complexity than interoperability value.
4. Existing ecosystems provide an equivalent mechanism.

In those circumstances, the correct architectural decision may be to shrink OSVP or contribute the required capability to an existing standard.

## Result

Phase 6 establishes OSVP as a candidate interoperability layer for exchanging security validation intent, evidence and assurance proofs.

Its adoption remains an open hypothesis rather than an established fact.

## Known Unknowns

Important unresolved questions include:

- Whether organisations will adopt another interoperability layer
- Where OSVP should terminate and existing standards should begin
- How much semantic complexity the protocol should contain
- How independent implementations should be certified
- How privacy-preserving evidence exchange should work
- Which governance model would be credible
