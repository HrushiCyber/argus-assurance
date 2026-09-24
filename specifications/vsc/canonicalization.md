# ARGUS VSC Canonicalization

**Status:** Draft v1.0  
**Scope:** Deterministic representation of VSC objects for hashing and signatures

## 1. Purpose

A VSC may be created, transported, parsed, and verified by independent
implementations written in different languages.

Those implementations must agree on the exact bytes that are:

- hashed
- signed
- verified
- referenced by evidence digests
- referenced by dependency digests

Canonicalization provides that deterministic representation.

## 2. Core Principle

The semantic meaning of a VSC MUST NOT depend on:

- JSON member ordering
- insignificant whitespace
- indentation
- line endings
- serializer implementation
- object construction order

The same semantic VSC MUST produce the same canonical representation.

## 3. Canonical Representation

VSC v1 SHOULD use a deterministic JSON representation based on:

- UTF-8 encoding
- JSON objects
- JSON arrays
- deterministic object-member ordering
- no insignificant whitespace
- deterministic number representation
- deterministic string escaping

The canonicalization mechanism MUST be explicitly identified by the signed
object.

Recommended identifier:

```text
JCS-RFC8785
