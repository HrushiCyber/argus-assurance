# ARGUS Verifiable System Claims — Semantics

**Status:** Draft v1.0  
**Scope:** Normative semantic model for VSC objects

## 1. Purpose

A Verifiable System Claim (VSC) is a bounded machine-readable assertion that
a subject satisfies a defined property under explicit assumptions, evidence,
validation methods, dependencies, and validity conditions.

A VSC does not represent universal system security.

It represents a claim that can be independently evaluated according to a
defined verification policy.

## 2. Core Model

The semantic relationship is:

```text
Subject
   ↓
Property
   ↓
Scope + Assumptions
   ↓
Evidence
   ↓
Validation
   ↓
Proof Obligations
   ↓
Claim
   ↓
Verification Result
