# Phase 2 — Universal Assurance Platform

Phase 2 transforms ARGUS from a security-control validation implementation into a vendor-neutral assurance architecture.

## Fundamental Abstraction

The smallest stable universal abstraction identified in this phase is the:

**Assurance Claim**

An Assurance Claim is a bounded proposition whose truth depends on:

- Subject
- Preconditions
- Stimulus
- Observation obligation
- Oracle
- Evidence obligation
- Freshness boundary

This abstraction allows different security products, telemetry systems, detection systems, cloud environments and execution environments to participate without becoming part of the core assurance semantics.

## Architecture

**Security Intent → Universal Control → Assurance Claim → Stimulus / Observation / Oracle → Adapter → Canonical Event → Evidence → Assurance Verdict**

## Universal Adapter

Products and execution environments participate through capability-based adapters.

The universal adapter model separates:

- Assurance semantics
- Protocol semantics
- Adapter capabilities
- Vendor implementation details

This prevents vendor-specific APIs, query languages and schemas from becoming part of the core ARGUS model.

## Important Principle

Unsupported capability must not silently produce PASS or FAIL.

Capability negotiation is therefore part of assurance correctness.

## Telemetry

ARGUS uses a thin canonical telemetry envelope rather than attempting to replace established telemetry standards.

Source-native data can be preserved while being normalised into the assurance model.

## Detection

Detection semantics are represented independently from vendor-specific query languages.

Unsupported correlation or semantic behaviour must be explicitly reported rather than approximated.

## Authentication and Authorization

Authentication and authorization are treated as separate concerns.

Production deployments may use mechanisms such as:

- OAuth2 / OIDC
- mTLS
- Short-lived workload identity
- SPIFFE / SPIRE

## Phase 2 Result

ARGUS now has a vendor-neutral assurance core capable of integrating heterogeneous security and execution environments without embedding individual vendors into the core model.

## Known Limitations

Phase 2 does not by itself solve:

- Enterprise deployment
- Full multi-tenancy
- Independent trust infrastructure
- Federated assurance
- Global interoperability
- Machine-verifiable trust across arbitrary digital systems

Those problems are addressed in later phases.
