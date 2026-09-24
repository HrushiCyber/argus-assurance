# ARGUS PHASE 7 — GLOBAL ASSURANCE NETWORK

**Status:** Architecture + research baseline  
**Date:** 2026-09-23  
**Predecessor:** PHASE_6_HANDOFF.md / ARGUS open security validation protocol  
**Purpose:** Define a privacy-preserving network in which independent organisations can exchange, verify, aggregate and benchmark security-control assurance without creating a central surveillance system.

---

# 0. Executive Decision

## FACT

ARGUS already has the primitives required for network participation:

- `ValidationCase` — what must be proven.
- `ValidationExecution` — what happened.
- `ValidationProof` — authoritative evidence-backed result.
- causal failure domains;
- evidence-reference hashing;
- detached Ed25519 signatures;
- temporal/freshness semantics;
- assurance state;
- vendor-neutral adapter boundaries;
- Control Passport / assurance graph concepts.

The v0.9.0 implementation remains a controlled-environment reference implementation. It does **not** establish production-scale federation, L4 enterprise telemetry, or production deployment.

## PHASE 7 DECISION

ARGUS should **not** become a central repository of customer security telemetry.

It should become a **federated assurance protocol and exchange network** in which:

> **Evidence stays with the organisation that generated it; portable proofs, bounded assertions and privacy-preserving aggregates travel.**

The network is therefore three distinct systems:

1. **Local Assurance Plane** — executes tests and owns raw evidence.
2. **Proof Exchange Plane** — exchanges signed, selectively disclosed claims.
3. **Federated Intelligence Plane** — computes cohort-level intelligence without exposing participant-level security data.

The network is valuable only if participation measurably reduces assurance cost, increases interoperability, improves supplier/third-party decision quality, or improves detection/control validation through population-level evidence.

A network effect is therefore a **hypothesis to prove**, not a product assumption.

---

# 1. Challenge to Phase 6

## FACT

Existing ecosystems already solve important parts of interoperability:

- NIST OSCAL provides machine-readable assessment-result structures for assessors and continuous monitoring.
- CSA STAR provides cloud-security assurance transparency and reduces repetitive questionnaire work.
- OpenSSF Scorecard provides automated security signals for open-source projects.
- NIST CSF 2.0 provides a common cybersecurity-outcome taxonomy and explicit supply-chain guidance.
- W3C Verifiable Credentials define tamper-evident presentations and selective disclosure concepts.

These are complementary, not interchangeable with ARGUS.

## GAP

The remaining problem is not simply:

> "How do we exchange security assessment data?"

The harder problem is:

> **How do independent parties exchange bounded, cryptographically verifiable, freshness-aware claims about security-control effectiveness while preserving evidence locality and avoiding a central database of organisational security posture?**

ARGUS therefore should not attempt to replace OSCAL, CSA CCM/STAR, OpenSSF, NIST CSF, or existing compliance frameworks.

ARGUS should provide a **proof/effectiveness layer** that can map into them.

---

# 2. Network Architecture

```mermaid
flowchart TB

    subgraph ORG_A["Organisation A"]
        A1["Local Assurance Plane"]
        A2["Raw Telemetry"]
        A3["Validation Engine"]
        A4["Evidence Vault"]
        A5["Proof Issuer"]
    end

    subgraph ORG_B["Organisation B / Supplier"]
        B1["Local Assurance Plane"]
        B2["Raw Telemetry"]
        B3["Validation Engine"]
        B4["Evidence Vault"]
        B5["Proof Issuer"]
    end

    subgraph EX["ARGUS Proof Exchange"]
        E1["Proof Directory"]
        E2["Trust / Key Registry"]
        E3["Selective Disclosure"]
        E4["Policy / Consent"]
        E5["Revocation / Freshness"]
    end

    subgraph INT["Federated Intelligence"]
        I1["Cohort Builder"]
        I2["Secure Aggregation"]
        I3["Privacy Controls"]
        I4["Benchmark Engine"]
        I5["Failure Intelligence"]
    end

    A5 --> E1
    B5 --> E1

    E1 --> E2
    E1 --> E3
    E1 --> E4
    E1 --> E5

    E3 --> I1
    E4 --> I1

    I1 --> I2
    I2 --> I3
    I3 --> I4
    I4 --> I5
