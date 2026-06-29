  # REID v6.0a — A-15
Cross-Layer Binding Rules
Document ID: REID-CLBR-0015-v6.0a
Layer: A — Architecture
Build Position: 15 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
Cross-Layer Binding Rules (CLBR) define how artifacts across Layers 1–4 may reference, depend on, or
govern one another. CLBR ensures:
- substrate-first grounding
- explicit dependency declaration
- acyclic structural relationships
- governance-safe behavioral coupling
- drift-aware evolution

All v6.0a artifacts MUST declare bindings using the CLBR taxonomy.

## 2. Binding Types (CL-1 through CL-4)

### CL-1 — Normative Reference
A document’s normative content depends on another artifact.
- MUST be declared
- MUST NOT form cycles
- MUST reference exact AID + version

### CL-2 — Structural Dependency
A document imports schemas, data models, or structural definitions.
- MUST be declared
- Cycles prohibited
- MUST match Dependency Graph (I-25) edge types STR or INF

### CL-3 — Behavioral Dependency
A document depends on runtime behavior, events, or state transitions.
- Cycles allowed only when annotated as:
  (circular-CL-3, operationally justified)
- MUST map to Orchestration Spine events (A-14)

### CL-4 — Governance Constraint
A document’s lifecycle or compliance obligations are governed by another artifact.
- MUST be declared
- MUST reference governance artifacts (F-04, F-05, R-22, O-29, L-41, L-43)

## 3. Mandatory Foundation-Layer Bindings
Every artifact in Layers 2–4 MUST declare:

| Foundation Artifact | Binding | Meaning |
|--------------------|---------|---------|
| F-01 Master Specification | CL-1 | Apex normative reference |
| F-02 Vocabulary Register | CL-1 | Normative term definitions |
| F-03 Primitive Specification | CL-2 | Force, Invariant, System, Mode, Drift |
| F-04 Identity-Lock Protocol | CL-4 | Identity governance |
| F-05 Invariant-Persistence Rules | CL-4 | Version-transition constraints |
| F-08 Build Manifest | CL-1 | Build position + registry seed |

## 4. Layer-Specific Binding Requirements

### Layer 1 — Meta-Substrate
- No upward dependencies
- MAY declare CL-3 bindings to A-14 (Spine)
- MUST declare CL-4 bindings to F-04 and F-05

### Layer 2 — Cognitive Architecture & Identity
- MUST declare CL-2 bindings to A-11
- MUST declare CL-3 bindings to A-14 (ISL events, Closure events)
- MUST declare CL-4 bindings to F-04 and C-layer artifacts

### Layer 3 — Requirements Architecture
- MUST declare CL-1 bindings to A-12
- MUST declare CL-2 bindings to I-25 (Dependency Graph)
- MUST declare CL-3 bindings to A-14 (requirements drift propagation)
- MUST declare CL-4 bindings to R-22 (Quality Gates)

### Layer 4 — Enterprise Intelligence
- MUST declare CL-1 bindings to A-13
- MUST declare CL-3 bindings to A-14 (governance events)
- MUST declare CL-4 bindings to O-29 and L-41

## 5. Declaration Format
Every artifact MUST include:

Cross-Layer Bindings:
CL-1: [AID list]
CL-2: [AID list]
CL-3: [AID list]
CL-4: [AID list]


Rules:
- MUST list AIDs + versions
- MUST match Dependency Graph edges
- MUST annotate circular CL-3 relationships

## 6. Prohibited Patterns (PRB-01 through PRB-05)

### PRB-01 — Circular CL-1 Normative References
Forbidden.

### PRB-02 — Circular CL-2 Structural Dependencies
Forbidden.

### PRB-03 — Undeclared Event Consumption
Critical violation.

### PRB-04 — Apex Reference Omission
Missing F-01, F-04, or F-08 is registry-blocking.

### PRB-05 — Governance Downgrade
Declaring governance constraints as CL-1 or CL-2 is prohibited.

## 7. Validation & Enforcement

### Automated Registry Checks (L-41)
Registry SHALL:
- verify mandatory F-layer declarations
- validate AID existence + version
- detect prohibited CL-1/CL-2 cycles
- confirm CL-3 bindings match Spine event catalog

### CMB Manual Audits
CMB SHALL:
- validate CL-3 behavioral correctness
- validate CL-4 governance completeness
- cross-check bindings against I-25
- record violations as Layer-1 Drift events

## 8. Drift & Evolution Rules
Binding inconsistency triggers:
1. DRIFT_REGISTERED (Layer 1)
2. Evolve Engine evaluation
3. Change Proposal (O-29)
4. Registry update (L-41)
5. Lineage-Ledger entry (L-43)

## 9. Canonical Binding Examples

### Example — R-18 Requirements Analysis
CL-1: F-01, F-02, A-12
CL-2: I-25
CL-3: A-14
CL-4: F-04, R-22, O-29


### Example — A-11 Cognitive Identity Module
CL-1: F-01, F-02
CL-2: F-03, A-11
CL-3: A-14
CL-4: F-04, C-layer artifacts


## 10. Invariant Bindings
CLBR is bound to:
- INV-01: Structural/Behavioral acyclicity
- INV-02: Substrate-first grounding
- INV-03: Identity-Lock supremacy
- INV-04: Drift-driven evolution
- INV-05: Lineage continuity
- INV-06: Spine-mediated behavior
- INV-07: Explicit interface declaration
- INV-08: No silent dependencies

## 11. Publication & Succession
- A-15 is a normative v6.0a artifact
- Successor versions follow semantic versioning
- Changes require Change Proposal + Lineage-Ledger entry
- Retirements require Tombstone Record


