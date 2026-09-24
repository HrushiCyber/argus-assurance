# ARGUS Verifiable System Claims — Falsification

**Status:** Draft v1.0  
**Scope:** Counterexample generation, falsification experiments, and claim challenge semantics

## 1. Purpose

Validation asks whether available evidence satisfies the proof obligations of
a claim.

Falsification asks whether a plausible counterexample can demonstrate that the
claim does not hold.

ARGUS treats falsification as a first-class assurance mechanism.

The objective is not to prove that a system has no possible failure.

The objective is to systematically search for evidence that would invalidate
a bounded claim.

## 2. Core Principle

A claim is stronger when it survives relevant attempts to falsify it.

A claim MUST NOT be considered universally true merely because a finite set of
falsification experiments did not find a counterexample.

Therefore:

```text
No counterexample found
        ≠
No counterexample exists
