# ARGUS Verifiable System Claims — Security Considerations

**Status:** Draft v1.0  
**Scope:** Security properties, threats, trust boundaries, and failure modes of the VSC protocol

## 1. Purpose

This document defines the security considerations for Verifiable System Claims
(VSC).

ARGUS assumes that evidence producers, validators, issuers, verifiers,
telemetry systems, dependencies, and execution environments can fail or be
compromised.

The protocol therefore treats security claims as bounded and conditional.

## 2. Security Objective

The primary security objective is:

> Prevent a relying party from accepting a VSC as verified when the claim's
> required verification conditions have not been satisfied.

Secondary objectives include:

- preserving evidence integrity
- binding claims to the correct subject
- preventing replay
- enforcing freshness
- detecting dependency changes
- preventing unauthorized verification or execution
- preserving verifier independence
- preventing cross-tenant information disclosure
- making security failures observable
- preserving cryptographic agility
- limiting trust concentration

## 3. Security Boundary

The conceptual boundary is:

```text
Digital Subject
      |
      v
Evidence Producer
      |
      v
Evidence
      |
      v
VSC Issuer
      |
      v
VSC
      |
      v
Independent Verifier
      |
      v
Verification Policy
      |
      v
Relying Party Decision
