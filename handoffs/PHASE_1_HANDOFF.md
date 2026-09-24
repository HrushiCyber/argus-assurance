# ARGUS PHASE 1 HANDOFF

**Release candidate:** 1.0.0rc1  
**Implementation commit:** `95912a8e0897dfc74a3bcd3d5e1343518b1182a4`  
**Phase:** Foundation / v1.0  
**Date:** 2026-09-23

## 1. Current architecture

```text
Scenario + Control Contract
        ↓
ValidationCase
        ↓
Execution Orchestrator
        ├── Safety policy
        ├── Telemetry contract
        ├── Detection engine
        └── Runtime/resilience adapters
        ↓
ValidationExecution
        ↓
Evidence package
  ├── telemetry
  ├── detection result
  ├── provenance
  ├── environment
  ├── metrics
  └── manifest + Ed25519 signature
        ↓
ValidationProof
        ↓
Control Passport
        ↓
Assurance Debt / Assurance Graph
