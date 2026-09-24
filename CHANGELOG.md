# Changelog

All notable changes to ARGUS are documented in this file.

ARGUS follows a phase-based architecture. Major architectural changes,
protocol changes, security changes, and externally relevant implementation
milestones should be recorded here.

## [Unreleased]

### Architecture

- Transitioning ARGUS from a security-control validation platform toward
  machine-verifiable assurance infrastructure.
- Phase 8 establishes the Verifiable System Claim (VSC) architecture.
- Future implementation work will focus on protocol schemas, independent
  verification, conformance, evidence binding, invalidation, and
  falsification.

### Planned

- VSC protocol schema
- Canonical serialization rules
- Reference verifier
- Reference issuer
- Test vectors
- Conformance suite
- Independent verification implementation
- Claim invalidation model
- Falsification engine
- Standards interoperability adapters

---

## Phase 8 — Moonshot

### Added

- Verifiable System Claim architecture.
- Machine-verifiable claim model.
- Subject, property, assumption, observation, validation, proof, claim, and
  verification-result primitives.
- Independent verifier architecture.
- Dependency and invalidation graph.
- Falsification engine architecture.
- Trust-domain federation model.
- Transparency and revocation architecture.
- AI-agent assurance model.
- Cyber-physical-system assurance model.
- Privacy-preserving evidence model.
- Standards alignment model for SPIFFE, SLSA, in-toto, RATS, Sigstore,
  SCITT, and related ecosystems.

### Security

- Explicit treatment of compromised evidence producers.
- Explicit treatment of compromised verifiers and trust anchors.
- Replay, expiry, revocation, dependency mutation, provenance manipulation,
  telemetry incompleteness, and schema-drift considerations.
- Fail-closed verification semantics for invalid or insufficient evidence.

### Architectural Decision

ARGUS is not a global root of trust.

ARGUS provides assurance semantics and verification infrastructure that allows
bounded claims to be independently verified by relying parties.

---

## Phase 7 — Global Assurance Network

### Added

- Federated assurance exchange architecture.
- Proof exchange model.
- Selective disclosure model.
- Privacy-preserving benchmark architecture.
- Supplier assurance exchange model.
- Control-equivalence model.
- Federated intelligence architecture.
- Multi-party trust and governance requirements.

### Security

- Raw telemetry exchange prohibited by default.
- Raw evidence exchange prohibited by default.
- Independent verification required.
- Revocation and freshness required.
- Stable public organisation identifiers prohibited for privacy-sensitive
  benchmark participation.

---

## Phase 6 — Open Security Validation Protocol

### Added

- Open protocol boundary for assurance transactions.
- Protocol objects for controls, scenarios, executions, assertions,
  evidence, proofs, verification results, freshness, revocation, and
  capability negotiation.
- Independent verification model.
- Canonical serialization requirements.
- Conformance and negative test-vector requirements.

### Architectural Decision

ARGUS does not attempt to replace established ecosystems such as OSCAL,
ATT&CK/STIX/TAXII, Sigma, OpenTelemetry, OCSF, SPIFFE, SLSA, or related
standards.

The protocol provides an assurance and verification layer across existing
ecosystems.

---

## Phase 5 — Independent Trust

### Added

- Independent trust architecture.
- Cryptographically bound assurance concepts.
- Verification-oriented trust model.
- Evidence commitment and issuer concepts.
- Freshness and revocation considerations.

---

## Phase 4 — Enterprise Assurance Plane

### Added

- Enterprise assurance control-plane architecture.
- Tenant isolation model.
- RBAC/ABAC authorization model.
- OIDC claim validation model.
- Secret non-persistence principle.
- Connector capability contracts.
- Durable idempotent validation jobs.
- Worker leases and retry semantics.
- Rate limiting.
- Hash-chained audit records.
- Security-control digital twins.
- Business-service assurance graph.
- Control SLO model.

### Security

- Explicit trust boundaries between tenants, runners, connectors, telemetry,
  evidence, and secret providers.
- Cross-tenant access, replay, lease hijacking, secret exposure, audit
  forgery, and authorization bypass identified as security test areas.

---

## Phase 3 — Control Efficacy

### Added

- Causal assurance model.
- Necessary and sufficient evidence analysis.
- Event-removal experiments.
- Telemetry mutation testing.
- Benign-neighbour testing.
- Detector mutation testing.
- Autonomous falsification concepts.
- Semantic input fingerprinting.
- Proof-strength vector.

### Architectural Decision

Detection success alone is insufficient to establish control assurance.

ARGUS distinguishes detector execution from causal evidence supporting the
security claim.

---

## Phase 2 — Universal Assurance

### Added

- Universal Assurance Core.
- Assurance Claim abstraction.
- Universal Control model.
- Universal Adapter capability contract.
- Canonical event envelope.
- Detection semantic representation.
- Capability negotiation.
- Adapter isolation from assurance semantics.

### Architectural Decision

Products, vendors, telemetry systems, detection systems, cloud environments,
and execution environments participate through capability providers rather
than becoming part of the assurance model itself.

---

## Phase 1 — Foundation

### Added

- ValidationCase.
- ValidationExecution.
- ValidationProof.
- Evidence package model.
- Cryptographic evidence manifests.
- Control Passport.
- Assurance Debt model.
- Assurance Graph.
- Safety-policy enforcement.
- Evidence freshness.
- Idempotent execution ledger.
- Fail-closed assurance semantics.

### Architectural Invariant

Execution status is not assurance verdict.

A successful execution cannot independently establish that a security control
provides the claimed protection.

---

## Versioning Principles

ARGUS distinguishes:

- implementation version
- protocol version
- schema version
- semantic version
- verifier implementation version
- policy version
- claim-profile version

A change that alters the meaning of an existing assurance object must be
explicitly versioned.

Security-sensitive semantic changes require corresponding:

- documentation
- tests
- negative test cases
- compatibility analysis
- migration guidance
- security analysis

## Evidence Discipline

ARGUS documentation distinguishes:

- **FACT** — directly supported by implementation, experiment, specification,
  or authoritative external evidence.
- **HYPOTHESIS** — proposition requiring validation.
- **ASSUMPTION** — condition accepted for a bounded design or experiment.
- **EXPERIMENT** — defined test intended to evaluate a proposition.
- **RESULT** — observed experimental outcome.
- **CLAIM** — bounded statement supported by identified evidence.

Unvalidated architectural hypotheses must not be represented as production
capabilities.
