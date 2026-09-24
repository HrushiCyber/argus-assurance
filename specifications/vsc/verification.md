# ARGUS Verifiable System Claims — Verification

**Status:** Draft v1.0  
**Scope:** Normative verification semantics for VSC objects

## 1. Purpose

This document defines the verification process for a Verifiable System Claim
(VSC).

The verifier determines whether a bounded claim satisfies a specified
verification policy using the available claim, evidence, dependencies, trust
configuration, and verification context.

Verification MUST NOT silently infer facts that are absent from the claim or
its evidence.

## 2. Verification Principle

The core operation is:

```text
verify(claim, policy, context) -> VerificationResult
