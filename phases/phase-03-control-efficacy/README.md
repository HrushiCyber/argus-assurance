# Phase 3 — Control Efficacy and Causal Assurance

Phase 3 extends ARGUS from validating whether a control executed toward determining whether the control actually produced the intended security effect.

## Fundamental Question

A control can:

- exist,
- execute successfully,
- generate telemetry,
- trigger a detection,

and still fail to provide the intended security outcome.

Therefore:

**Control Execution ≠ Control Effectiveness**

## Core Model

Phase 3 introduces a stronger assurance chain:

**Security Objective → Control Mechanism → Stimulus → System State Change → Observation → Detection → Outcome → Evidence → Assurance Claim**

The critical addition is the relationship between the security control and the security outcome it is intended to produce.

## Causal Assurance

ARGUS investigates whether observed outcomes can be reasonably attributed to the control under test.

This requires explicit modelling of:

- Preconditions
- Control intervention
- Expected system behaviour
- Observable effects
- Alternative explanations
- Confounding conditions
- Counterfactual behaviour
- Failure conditions
- Evidence requirements

## Counterfactual Principle

Where appropriate, validation should ask:

> What would have happened if the control had not been present or effective?

A detection event alone is therefore insufficient evidence of control efficacy.

## Assurance States

Phase 3 strengthens the distinction between:

- PASS
- FAIL
- INCONCLUSIVE
- NOT OBSERVABLE
- NOT APPLICABLE

An inability to establish the required causal relationship must not be silently converted into PASS.

## Evidence Model

Evidence must support the specific assurance claim being evaluated.

Evidence quality depends on factors including:

- Integrity
- Completeness
- Provenance
- Temporal alignment
- Observation coverage
- Independence
- Reproducibility
- Semantic relevance

## Falsification

Every significant assurance claim should define conditions that would invalidate it.

Examples include:

- Missing expected control effect
- Unexpected system state
- Conflicting telemetry
- Evidence substitution
- Temporal mismatch
- Control bypass
- Environmental change
- Unmodelled dependency

## Result

Phase 3 establishes a more rigorous concept of security assurance:

**A security control should not be considered effective merely because it exists or executed successfully.**

The evidence must support the intended security property under defined conditions.

## Known Limitations

Causal assurance remains difficult in complex distributed systems.

Potential limitations include:

- Hidden dependencies
- Partial observability
- Correlated controls
- Incomplete telemetry
- Non-deterministic systems
- Confounding environmental conditions
- Difficulty constructing reliable counterfactuals

These limitations must remain explicit rather than being hidden behind a binary assurance result.
