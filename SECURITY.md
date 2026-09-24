# Security Policy

## Scope

ARGUS is an assurance and verification research project intended to make
bounded claims about digital-system properties independently verifiable.

Security is a core architectural requirement.

ARGUS does not assume that evidence producers, telemetry sources, validators,
verifiers, trust anchors, environments, or dependent systems are inherently
trustworthy.

## Security Principles

ARGUS follows these principles:

1. Fail closed when required assurance evidence is absent or invalid.
2. Separate execution status from assurance verdicts.
3. Bind claims to subjects, evidence, provenance, scope, freshness, and policy.
4. Detect and represent dependency changes and claim invalidation.
5. Make verification independently reproducible where practical.
6. Never treat a cryptographic signature as proof that the underlying claim is true.
7. Never treat telemetry presence as evidence of telemetry correctness.
8. Avoid implicit trust transitivity.
9. Minimize exchange of raw sensitive evidence.
10. Preserve explicit assumptions, limitations, and falsification conditions.

## Threat Model

Relevant threat classes include:

- forged evidence
- modified evidence
- replayed evidence
- stale claims
- revoked credentials
- compromised issuers
- compromised evidence producers
- malicious or compromised verifiers
- telemetry manipulation
- telemetry omission
- schema drift
- dependency substitution
- invalid trust anchors
- clock manipulation
- unauthorized validation execution
- cross-tenant data access
- policy bypass
- contradictory claims
- incomplete observations
- detector or validator defects
- common-mode failures
- malicious adapters
- supply-chain compromise

## Reporting a Vulnerability

Security vulnerabilities should not be disclosed publicly before the project
maintainers have had an opportunity to assess and address them.

Please report vulnerabilities privately through the repository's configured
security reporting mechanism.

Include, where possible:

- affected component
- affected version or commit
- vulnerability description
- security impact
- reproduction steps
- proof of concept
- relevant logs or artifacts
- suggested mitigation

Do not include real credentials, secrets, customer data, or other sensitive
information in the report.

## Responsible Disclosure

The project aims to acknowledge valid reports, investigate them, develop an
appropriate remediation, and coordinate disclosure when practical.

Researchers should avoid:

- accessing data belonging to other users or organisations
- modifying or deleting production data
- disrupting availability
- performing destructive testing against systems without authorization
- retaining sensitive data obtained unintentionally

## Security Claims

ARGUS security claims must be supported by explicit evidence and must have a
defined falsification strategy.

A passing verification result means that the stated verification policy was
satisfied for the bounded claim and evidence available to the verifier.

It does not establish that the underlying system is universally secure.

## Research Status

ARGUS is an evolving research and engineering project.

Reference implementations, schemas, adapters, and verification mechanisms may
contain limitations that are explicitly documented in their respective
security considerations and release documentation.
