# Contributing to ARGUS

ARGUS is an assurance and verification infrastructure project.

Contributions should improve the correctness, interoperability, security,
reproducibility, or practical utility of the system.

## Before Contributing

Read:

- `README.md`
- `SECURITY.md`
- `handoffs/`
- relevant material under `docs/`
- the relevant phase documentation

Understand the distinction between:

- FACT
- HYPOTHESIS
- ASSUMPTION
- EXPERIMENT
- RESULT
- CLAIM

Do not present hypotheses or experimental results as established facts.

## Contribution Principles

### 1. Evidence over novelty

Do not introduce a new abstraction, protocol, dependency, or architecture
merely because it appears technically interesting.

Explain:

- the problem being solved
- why existing mechanisms are insufficient
- the proposed mechanism
- measurable acceptance criteria
- known limitations

### 2. Preserve interoperability

ARGUS should integrate with existing standards and ecosystems where practical.

Do not replace an established standard without demonstrating a concrete
interoperability or assurance gap.

### 3. Fail closed

Security-critical verification logic must not silently convert:

- missing evidence into success
- unsupported semantics into success
- invalid signatures into success
- stale evidence into current assurance
- execution success into assurance success

### 4. Make claims bounded

Every assurance claim should define its:

- subject
- property
- scope
- assumptions
- evidence
- validity period
- dependencies
- verification requirements
- invalidation conditions

### 5. Security claims require falsification

For every significant security property, identify how that property could be
shown false.

Examples include:

- forged evidence
- replay
- stale evidence
- dependency mutation
- trust-anchor compromise
- policy bypass
- cross-tenant access
- contradictory evidence
- malformed proof
- incomplete observation

## Pull Requests

A pull request should clearly state:

### Problem

What concrete problem does this change solve?

### Design

What mechanism solves it?

### Evidence

What tests, experiments, benchmarks, formal reasoning, or external evidence
support the change?

### Security Impact

What new attack surface or trust assumption is introduced?

### Compatibility

Does the change preserve existing protocol, schema, API, or evidence
compatibility?

### Limitations

What remains unproven?

## Testing

Changes should include appropriate tests.

Security-sensitive changes should include negative tests wherever practical.

At minimum, consider:

- valid input
- malformed input
- missing evidence
- modified evidence
- replayed evidence
- expired evidence
- revoked credentials
- unsupported versions
- dependency changes
- invalid trust anchors
- authorization failures

Tests should be deterministic and reproducible.

## Protocol and Schema Changes

Protocol or schema changes require particular care.

Document:

- semantic change
- compatibility impact
- versioning impact
- migration requirements
- affected implementations
- affected test vectors

Do not silently change the meaning of an existing field.

## Dependencies

New dependencies should have a demonstrated requirement.

Consider:

- security posture
- maintenance status
- licensing
- transitive dependencies
- supply-chain risk
- operational complexity
- whether the functionality can reasonably be implemented without the
  dependency

Avoid dependencies added solely for convenience when they create significant
architectural coupling.

## Documentation

Architectural changes must update the relevant documentation.

Important decisions should be recorded in `docs/decisions/`.

Research findings should distinguish evidence from interpretation.

## Code of Conduct

Participants are expected to communicate professionally and constructively.

Technical disagreement is encouraged when supported by evidence and reasoning.

## Final Principle

ARGUS should become more trustworthy through every contribution.

A contribution that adds functionality while weakening verification semantics,
security boundaries, reproducibility, interoperability, or epistemic clarity
is not an improvement.
