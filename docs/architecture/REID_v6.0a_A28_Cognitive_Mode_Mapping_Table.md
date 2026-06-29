 # REID v6.0a — A-28
Cognitive Mode Mapping Table (CMMT)
Document ID: REID-CMMT-0028-v6.0a
Layer: A — Architecture
Build Position: 28 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Cognitive Mode Mapping Table (CMMT) defines the formal mapping between:
- intent categories (A-27)
- cognitive modes (A-17)

CMMT ensures:
- deterministic intent → mode transitions
- drift-free cognitive routing
- predictable multi-surface behavior
- unified reasoning identity
- safe orchestration across the Spine

CMMT is mandatory for all v6.0a surfaces and workflows.

## 2. Cognitive Modes (CM-01 through CM-08)

### CM-01 Interpretive Mode
Understanding meaning, context, and constraints.

### CM-02 Analytical Mode
Comparisons, evaluations, explanations.

### CM-03 Generative Mode
Drafting, rewriting, creating content.

### CM-04 Extractive Mode
Summaries, lists, key points.

### CM-05 Behavioral Mode
OS actions, workflow actions, enterprise operations.

### CM-06 Visual Mode
Charts, images, diagrams, layouts.

### CM-07 Structural Mode
Tables, lists, schemas, slides, formatting.

### CM-08 Governance Mode
Compliance, constraints, quality gates.

## 3. Intent Categories (IC-01 through IC-12)
(From A-27)

### IC-01 Interpretive  
### IC-02 Extractive  
### IC-03 Analytical  
### IC-04 Generative  
### IC-05 Structural  
### IC-06 Behavioral  
### IC-07 Temporal  
### IC-08 Workflow  
### IC-09 Governance  
### IC-10 Fusion  
### IC-11 Context  
### IC-12 Multi-Intent  

## 4. Cognitive Mode Mapping Table (Primary)

| Intent Category | Primary Mode | Secondary Modes | Notes |
|-----------------|--------------|------------------|-------|
| IC-01 Interpretive | CM-01 Interpretive | CM-03, CM-04 | Used for meaning clarification |
| IC-02 Extractive | CM-04 Extractive | CM-03 | Summaries → generative follow-up |
| IC-03 Analytical | CM-02 Analytical | CM-03, CM-07 | Often paired with structural or generative |
| IC-04 Generative | CM-03 Generative | CM-07 | Drafting + formatting |
| IC-05 Structural | CM-07 Structural | CM-03 | Formatting + rewriting |
| IC-06 Behavioral | CM-05 Behavioral | CM-08 | OS actions + governance |
| IC-07 Temporal | CM-01 Interpretive | CM-02, CM-03 | Temporal → interpretive → analytical |
| IC-08 Workflow | CM-05 Behavioral | CM-08 | Workflow actions + governance |
| IC-09 Governance | CM-08 Governance | CM-05 | Compliance → behavioral enforcement |
| IC-10 Fusion | CM-02 Analytical | CM-03, CM-07 | Fusion requires analytical grounding |
| IC-11 Context | CM-01 Interpretive | CM-04, CM-03 | Context → interpretive → extractive |
| IC-12 Multi-Intent | CM-01 Interpretive | CM-02, CM-03, CM-07 | Multi-intent resolves into multiple modes |

## 5. Mode Selection Rules (MSR-01 through MSR-10)

### MSR-01 — Primary Mode Supremacy
Primary mode MUST be selected first.

### MSR-02 — Secondary Mode Cascade
Secondary modes MUST follow primary mode in deterministic order.

### MSR-03 — Governance Override
Governance Mode (CM-08) overrides all other modes when constraints apply.

### MSR-04 — Behavioral Override
Behavioral Mode (CM-05) overrides all non-governance modes for OS actions.

### MSR-05 — Temporal Override
Temporal intent MUST route through Interpretive Mode first.

### MSR-06 — Structural Override
Structural intent MUST route through Structural Mode before Generative Mode.

### MSR-07 — Fusion Override
Fusion intent MUST route through Analytical Mode first.

### MSR-08 — Multi-Intent Expansion
Multi-intent MUST expand into multiple mode selections.

### MSR-09 — Surface Normalization Alignment
Mode selection MUST align with surface normalization (A-23).

### MSR-10 — Drift Immunity
Mode selection MUST NOT introduce drift.

## 6. Mode Mapping Packet Structure

    mode_mapping_packet:
        identity: [identity_packet]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        intent_category: [IC-01 through IC-12]
        primary_mode: [CM-01 through CM-08]
        secondary_modes: [list]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Mode mapping packets MUST be validated before execution.

## 7. Mode Mapping Execution Pipeline

Pipeline:
1. Identity Anchor stabilization
2. Pre-Compute ambiguity reduction (A-26)
3. Intent pre-classification (A-27)
4. Mode mapping (A-28)
5. Priority routing through Spine (A-20)
6. Governance arbitration (A-21)
7. Fusion orchestration (A-18)
8. Temporal alignment (A-19)
9. Synthesis reconciliation

Mode mapping MUST occur before reasoning, fusion, or synthesis.

## 8. Mode Mapping Examples

### Example 1 — Word
User: “Rewrite this paragraph”
Intent: IC-04 Generative  
Modes: CM-03 → CM-07 → CM-08 → Synthesis

### Example 2 — Teams
User: “Summarize what she said earlier”
Intent: IC-02 + IC-07  
Modes: CM-04 → CM-01 → CM-03 → Synthesis

### Example 3 — Excel
User: “Explain this chart”
Intent: IC-03 Analytical  
Modes: CM-02 → CM-06 → CM-03 → Synthesis

### Example 4 — Dynamics
User: “Move this forward”
Intent: IC-08 Workflow  
Modes: CM-05 → CM-08 → Synthesis

## 9. Drift Immunity in Mode Mapping
Mode mapping MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor  
- Structural drift prevented by normalization  
- Behavioral drift prevented by Spine  
- Governance drift prevented by Governance Arbiter  
- Lineage drift prevented by Ledger Integrator  

Mode mapping MUST NOT proceed if drift is active.

## 10. Mode Mapping Matrix

| Intent | Primary Mode | Secondary Modes | Escalates |
|--------|--------------|------------------|-----------|
| Interpretive | CM-01 | CM-03, CM-04 | Governance |
| Extractive | CM-04 | CM-03 | Synthesis |
| Analytical | CM-02 | CM-03, CM-07 | Spine |
| Generative | CM-03 | CM-07 | Governance |
| Structural | CM-07 | CM-03 | Synthesis |
| Behavioral | CM-05 | CM-08 | Governance |
| Temporal | CM-01 | CM-02, CM-03 | Governance |
| Workflow | CM-05 | CM-08 | Ledger |
| Governance | CM-08 | CM-05 | Ledger |
| Fusion | CM-02 | CM-03, CM-07 | Spine |
| Context | CM-01 | CM-04, CM-03 | Governance |
| Multi-Intent | CM-01 | CM-02, CM-03, CM-07 | Governance |

## 11. Invariant Bindings
CMMT is bound to:
- INV-01: Substrate-first grounding  
- INV-02: Identity-Lock supremacy  
- INV-03: Drift-driven evolution  
- INV-04: Spine-mediated behavior  
- INV-05: No silent mode mapping  
- INV-06: Lineage continuity  

## 12. Publication & Succession
- A-28 is a normative v6.0a artifact  
- Successor versions follow semantic versioning  
- Changes require Change Proposal + Lineage-Ledger entry  
- Retirements require Tombstone Record  
