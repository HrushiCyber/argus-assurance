# ARGUS VSC Test Vectors

**Status:** Initial test-vector specification  
**Scope:** Interoperability and negative-testing requirements for Verifiable System Claims

## Purpose

VSC test vectors provide deterministic inputs and expected verification
outcomes for independent implementations.

A conforming verifier should be able to consume the same test vector and
produce the expected semantic result without relying on the ARGUS reference
implementation.

## Test-Vector Structure

Each test vector SHOULD contain:

```text
vector_id
description
claim
verification_policy
verification_context
expected_result
expected_failures
