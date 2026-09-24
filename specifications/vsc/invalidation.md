# ARGUS Verifiable System Claims — Invalidation

**Status:** Draft v1.0  
**Scope:** Claim dependency, change detection, invalidation, and revalidation

## 1. Purpose

A VSC is valid only within the assumptions, evidence, dependencies, scope,
and validity conditions under which it was established.

When a material dependency changes, the claim may no longer represent the
current state of the subject.

ARGUS therefore treats assurance as **conditional and invalidatable**, rather
than permanent.

## 2. Core Principle

A previously verified claim MUST NOT be assumed to remain valid after a
material change to a dependency that affects the claim.

The fundamental relationship is:

```text
Claim
 └── Proof
      ├── Validation
      ├── Evidence
      ├── Schema
      ├── Policy
      ├── Telemetry
      ├── Control
      ├── Artifact
      └── Environment
