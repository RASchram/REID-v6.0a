 # REID v6.0a — A-26
Pre-Compute Ambiguity Reduction Specification (PCARS)
Document ID: REID-PCARS-0026-v6.0a
Layer: A — Architecture
Build Position: 26 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Pre-Compute Ambiguity Reduction Specification (PCARS) defines how REID detects, resolves, and
reduces ambiguity before intent classification, mode switching, fusion, temporal reasoning, or
synthesis. PCARS ensures:
- stable pre-inference reasoning
- drift-free ambiguity resolution
- predictable multi-surface behavior
- unified entity interpretation
- safe pre-classification of intent

PCARS is mandatory for all v6.0a surfaces and workflows.

## 2. Ambiguity Types (AT-01 through AT-10)

### AT-01 — Pronoun Ambiguity
Unclear references to “it”, “they”, “this”, “that”.

### AT-02 — Entity Ambiguity
Unclear references to people, files, messages, or records.

### AT-03 — Surface Ambiguity
Unclear references to “here”, “this window”, “this app”.

### AT-04 — Temporal Ambiguity
Unclear references to “earlier”, “later”, “recently”.

### AT-05 — Workflow Ambiguity
Unclear references to “next step”, “previous stage”.

### AT-06 — Structural Ambiguity
Unclear references to “this section”, “this table”, “this slide”.

### AT-07 — Behavioral Ambiguity
Unclear references to OS actions or device operations.

### AT-08 — Context Ambiguity
Unclear references to surface context or device context.

### AT-09 — Intent Ambiguity
Unclear user intent (“fix this”, “improve this”, “help me with this”).

### AT-10 — Governance Ambiguity
Unclear compliance or constraint references.

## 3. Ambiguity Reduction Principles (ARP-01 through ARP-10)

### ARP-01 — Identity Continuity
Ambiguity reduction MUST preserve identity continuity.

### ARP-02 — Substrate Supremacy
Ambiguity reduction MUST follow substrate primitives.

### ARP-03 — Drift Immunity
Ambiguity reduction MUST NOT introduce drift.

### ARP-04 — Context Preservation
Context MUST remain stable during ambiguity reduction.

### ARP-05 — Surface Normalization
Ambiguity reduction MUST adapt to surface-specific constraints.

### ARP-06 — Pre-Compute Priority
Ambiguity reduction MUST occur before intent classification.

### ARP-07 — Mode Alignment
Ambiguity reduction MUST align with cognitive mode switching.

### ARP-08 — Fusion Alignment
Ambiguity reduction MUST support multi-model fusion.

### ARP-09 — Temporal Alignment
Ambiguity reduction MUST support temporal reasoning.

### ARP-10 — Governance Priority
Governance constraints override ambiguity resolution rules.

## 4. Ambiguity Packet Structure

    ambiguity_packet:
        identity: [identity_packet]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        ambiguity_types: [list of AT-01 through AT-10]
        resolved_entities: [map]
        resolved_context: [map]
        resolved_surface: [string]
        resolved_intent: [string]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Ambiguity packets MUST be validated before intent classification.

## 5. Ambiguity Resolution Rules (ARR-01 through ARR-12)

### ARR-01 — Pronoun Resolution
Resolve pronouns using:
- graph entities
- surface context
- workflow context

### ARR-02 — Entity Resolution
Resolve entities using:
- graph grounding (A-25)
- surface normalization (A-23)

### ARR-03 — Surface Resolution
Resolve surface references using:
- continuity metadata (A-22)
- device/OS context (A-24)

### ARR-04 — Temporal Resolution
Normalize ambiguous time references using:
- temporal reasoning (A-19)

### ARR-05 — Workflow Resolution
Resolve workflow references using:
- enterprise workflow metadata
- Dynamics context

### ARR-06 — Structural Resolution
Resolve structural references using:
- surface-specific structural maps

### ARR-07 — Behavioral Resolution
Resolve OS action references using:
- device/OS binding (A-24)

### ARR-08 — Context Resolution
Resolve context references using:
- pre-compute context binding

### ARR-09 — Intent Resolution
Resolve ambiguous intent using:
- pre-classification heuristics
- surface-specific patterns

### ARR-10 — Governance Resolution
Resolve governance ambiguity using:
- governance protocol (A-21)
- quality gates

### ARR-11 — Multi-Model Resolution
Resolve ambiguity using:
- fusion metadata (A-18)

### ARR-12 — Synthesis Resolution
Resolve ambiguity using:
- synthesis reconciliation rules

## 6. Ambiguity Validation Rules (AV-01 through AV-08)

### AV-01 — Identity Validation
Ambiguity resolution MUST preserve identity continuity.

### AV-02 — Structural Validation
Resolved entities MUST match surface structure.

### AV-03 — Behavioral Validation
Resolved actions MUST match Spine event definitions.

### AV-04 — Temporal Validation
Resolved timestamps MUST be normalized.

### AV-05 — Drift Validation
Ambiguity resolution MUST NOT increase drift score beyond threshold.

### AV-06 — Governance Validation
Resolved intent MUST respect governance constraints.

### AV-07 — Workflow Validation
Resolved workflow references MUST match workflow stage.

### AV-08 — Synthesis Validation
Resolved entities MUST support synthesis reconciliation.

## 7. Ambiguity Reduction Execution Pipeline

Pipeline:
1. Identity Anchor stabilization
2. Pre-Compute substrate alignment
3. Ambiguity packet creation
4. Ambiguity detection
5. Entity resolution
6. Context resolution
7. Surface resolution
8. Intent resolution
9. Priority routing through Spine
10. Governance arbitration
11. Mode switching (if required)
12. Fusion orchestration (if required)
13. Temporal alignment
14. Synthesis reconciliation

Ambiguity reduction MUST occur before reasoning, fusion, or synthesis.

## 8. Ambiguity Reduction Examples

### Example 1 — Word
User: “Fix this”
Resolution:
- resolve “this” → paragraph
- resolve intent → correction
- Analytical → Generative → Synthesis

### Example 2 — Teams
User: “Summarize what she said earlier”
Resolution:
- resolve “she” → participant
- resolve “earlier” → timestamp
- Extractive → Generative → Synthesis

### Example 3 — Excel
User: “Explain this”
Resolution:
- resolve “this” → chart
- resolve intent → analysis
- Analytical → Generative → Synthesis

### Example 4 — Dynamics
User: “Move this forward”
Resolution:
- resolve “this” → case
- resolve “forward” → next workflow stage
- Governance → Behavioral → Synthesis

## 9. Drift Immunity in Ambiguity Reduction
Ambiguity reduction MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor
- Structural drift prevented by normalization
- Behavioral drift prevented by Spine
- Governance drift prevented by Governance Arbiter
- Lineage drift prevented by Ledger Integrator

Ambiguity reduction MUST NOT proceed if drift is active.

## 10. Ambiguity Matrix

| Ambiguity Type | Prevents | Corrects | Escalates |
|----------------|----------|----------|-----------|
| Pronoun | identity drift | reference mismatch | Governance |
| Entity | structural drift | entity mismatch | Synthesis |
| Surface | continuity drift | surface mismatch | Spine |
| Temporal | temporal drift | timestamp mismatch | Governance |
| Workflow | workflow drift | stage mismatch | Ledger |
| Structural | structural drift | layout mismatch | Synthesis |
| Behavioral | OS drift | action mismatch | Governance |
| Context | reasoning drift | context mismatch | Spine |
| Intent | reasoning drift | intent mismatch | Governance |
| Governance | governance drift | constraint mismatch | Ledger |

## 11. Invariant Bindings
PCARS is bound to:
- INV-01: Substrate-first grounding
- INV-02: Identity-Lock supremacy
- INV-03: Drift-driven evolution
- INV-04: Spine-mediated behavior
- INV-05: No silent ambiguity resolution
- INV-06: Lineage continuity

## 12. Publication & Succession
- A-26 is a normative v6.0a artifact
- Successor versions follow semantic versioning
- Changes require Change Proposal + Lineage-Ledger entry
- Retirements require Tombstone Record
