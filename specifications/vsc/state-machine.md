# VSC Claim State Machine

## Purpose

This document defines the normative lifecycle of a Verifiable System Claim (VSC).

A claim lifecycle MUST distinguish issuance, verification, validity, expiration, revocation, supersession, and dependency invalidation.

A claim being successfully verified at one point in time MUST NOT imply that it remains valid indefinitely.

## States

A VSC MAY transition through the following states:

```text
DRAFT
  |
  v
ISSUED
  |
  v
VERIFIED
  |
  v
ACTIVE
  |
  +--> STALE
  |
  +--> REVALIDATION_REQUIRED
  |
  +--> SUPERSEDED
  |
  +--> EXPIRED
  |
  +--> REVOKED
  |
  +--> INVALIDATED
  |
  +--> INVALID
