# Phase 8 — Moonshot

## Machine-Verifiable Trust for Digital Systems

Phase 8 generalises ARGUS beyond conventional cybersecurity controls.

The long-term question becomes:

> Can important claims about digital systems become machine-readable, cryptographically bound, continuously verifiable and independently checkable?

## The Core Primitive

The proposed primitive is the:

**Verifiable System Claim (VSC)**

A VSC is a machine-readable, cryptographically bound statement that a defined property held for a defined subject, scope and time interval, supported by specified evidence and validation procedures, under explicit assumptions and provenance.

A VSC must also describe how the claim could be falsified.

## Formal Model

A VSC can be represented conceptually as:

**C = ⟨S, P, O, V, E, A, T, D, I⟩**

Where:

- **S** — Subject and scope
- **P** — Property being claimed
- **O** — Obligations and observations
- **V** — Validation procedure
- **E** — Evidence
- **A** — Assumptions
- **T** — Temporal validity
- **D** — Dependency and change graph
- **I** — Integrity and provenance

## Verification

The conceptual verification function is:

**Verify(C, E, A, Policy) → VALID | INVALID | INCONCLUSIVE**

A verification process should also produce a verification trace explaining how the result was established.

## Assurance Is Not Binary

A system should not reduce all assurance into a single PASS or FAIL value.

Relevant dimensions may include:

- Authenticity
- Evidence integrity
- Execution integrity
- Observation completeness
- Validation strength
- Independence
- Freshness
- Reproducibility
- Environmental coverage
- Assumption health
- Causal confidence

Possible states include:

- VALID
- VALID_BUT_STALE
- VALID_WITH_UNMET_ASSUMPTION
- PARTIAL
- INCONCLUSIVE
- INVALID
- EXPIRED
- REVOKED
- SUPERSEDED
- NOT_VERIFIABLE

## Proof Stack

The broader trust architecture can be represented as:

**Trust Anchor → Subject → Observation → Validation → Proof → Verification → Decision**

ARGUS provides verifiable claims and verification mechanisms.

The relying party ultimately decides whether the resulting assurance is sufficient for its purpose.

ARGUS is therefore not a universal trust authority.

## Evidence Classes

Possible evidence mechanisms include:

- E0 — Assertion
- E1 — Signed Evidence
- E2 — Observable Evidence
- E3 — Runtime Validation
- E4 — Independent Validation
- E5 — Hardware / TEE Anchored Evidence
- E6 — Formal Proof
- E7 — Composed Proof

These describe evidence mechanisms and provenance strength.

They are not universal security scores.

## Falsification as a First-Class Concept

Every VSC should expose:

**Claim → Preconditions → Expected Observations → Counterexample Conditions → Falsification Procedure → Revocation Triggers**

This prevents assurance from becoming an unchallengeable assertion.

## Change-Aware Assurance

Trust decays when the system that produced the evidence changes.

Potential invalidating changes include:

- Code
- Configuration
- Dependencies
- Infrastructure
- Security controls
- Policies
- Models
- Identity
- Keys
- Environment
- Threat conditions
- Telemetry
- Validation procedures

The conceptual dependency graph becomes:

**Artifact → Build → Workload → Control → Observation → Validation → Proof → VSC**

A change should therefore produce:

**Impact(Change) → Affected Claims → Required Revalidation**

The long-term objective is continuous assurance with the minimum necessary re-validation.

## AI Agent Assurance

The VSC model can also be applied to AI agents.

Relevant properties include:

- Agent identity
- Model identity and version
- System policy
- Tools
- Permissions
- Memory
- Context sources
- Execution environment
- Actions
- Outcomes

Potential proof obligations include:

- Identity verification
- Authority verification
- Tool authorization
- Data-access constraints
- Prompt and context provenance
- Memory integrity
- Action constraints
- Human approval requirements
- Model integrity
- Runtime isolation
- Auditability
- Rollback capability
- Kill capability
- Cross-agent delegation
- Secret handling
- Policy-change invalidation

## Autonomous Systems

The same architecture can extend to systems interacting with the physical world.

A conceptual chain becomes:

**Physical System → Sensors → Observed State → Digital Representation → Invariant Model → Runtime Monitor → Counterexample → VSC**

Assurance must explicitly account for:

- Sensor coverage
- Sensor trust
- Model fidelity
- Synchronisation
- Unobservable state
- Environmental boundaries
- Model drift

## Formal Methods and Runtime Evidence

No single verification method is sufficient for every system.

ARGUS can combine:

- Testing
- Runtime validation
- Formal verification
- Signed provenance
- Hardware attestation
- Independent validation
- Policy evaluation
- Cryptographic proof

The verification method must remain visible.

## Theoretical Limits

ARGUS does not claim universal verification is possible.

Important limits include:

- Universal software security verification is impossible in general.
- Formal proofs are relative to their specifications.
- Hardware attestation is relative to what the hardware actually measures.
- Testing samples behaviour rather than proving all behaviour.
- Evidence can be authentic yet irrelevant.
- Independent validators can share hidden dependencies.
- Time can invalidate previously correct evidence.

These limitations are fundamental parts of the architecture.

## Privacy-Preserving Assurance

Potential mechanisms include:

- Hash commitments
- Selective disclosure
- Verifiable Credentials
- Zero-knowledge proofs
- Secure enclaves
- Local verification
- Secure aggregation
- Private set intersection

These mechanisms should be introduced only when their privacy benefit justifies their complexity.

## Federated Trust

Trust should be interoperable rather than dependent on one central authority.

Different organisations may use different trust anchors while exchanging machine-verifiable claims through common protocols.

## Machine-Readable Regulation

A possible future architecture is:

**Regulation → Requirement → Control Objective → Evidence Obligation → Validation Procedure → VSC → Independent Verification → Audit Interface**

ARGUS does not automatically determine legal compliance.

It provides machine-verifiable evidence and assurance primitives that can support compliance processes.

## What ARGUS Becomes

ARGUS is no longer simply:

- A security-control testing platform
- A BAS platform
- A SIEM
- A GRC platform
- A cyber-risk score
- A central telemetry repository
- A universal certification authority

Instead, the architectural direction is:

> **An interoperability and assurance layer for continuously verified properties of digital systems.**

## Fundamental Principle

The central principle of the entire ARGUS project is:

> **Do not merely state that a system is trustworthy. Define the claim, show the evidence, expose the assumptions, describe how it was validated, make it falsifiable, and allow another party or machine to verify it.**

## Known Unknowns

The Moonshot remains a research direction.

Important unresolved questions include:

- Whether organisations will adopt portable machine-verifiable claims
- Whether VSC can become a broadly useful abstraction
- How trust liability should be allocated
- How independent verification should operate economically
- How privacy and verification should be balanced
- How regulatory systems could consume machine-verifiable claims
- How rapidly changing systems can maintain valid assurance
- How to prevent protocol fragmentation
- How to establish neutral governance
- Which parts of the architecture should become open standards

## Final Objective

The long-term objective of ARGUS is:

**Machine-Verifiable Trust for Digital Systems.**

Not trust because someone says:

> "This system is secure."

But trust supported by:

**A defined claim + defined evidence + defined validation + explicit assumptions + cryptographic integrity + freshness + falsification + independent verification.**
