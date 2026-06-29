 # REID v6.0a — A-29
Multi-Model Capability Matrix (MMCM)
Document ID: REID-MMCM-0029-v6.0a
Layer: A — Architecture
Build Position: 29 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Multi-Model Capability Matrix (MMCM) defines the formal capability map for all models available
to REID v6.0a. MMCM ensures:
- deterministic model selection
- drift-aware routing
- governance-safe fusion
- predictable multi-surface behavior
- unified capability interpretation across the Spine

MMCM is mandatory for all v6.0a surfaces and workflows.

## 2. Model Classes (MC-01 through MC-08)

### MC-01 — GPT-Class Models
High-capability reasoning, generative synthesis, multi-domain analysis.

### MC-02 — Phi-Class Models
Lightweight reasoning, fast inference, low-latency tasks.

### MC-03 — SLM-Class Models
Small language models optimized for device-local inference.

### MC-04 — Vision Models
Image interpretation, OCR, diagram extraction, visual reasoning.

### MC-05 — Speech Models
Speech-to-text, text-to-speech, audio event classification.

### MC-06 — Enterprise Models
Dynamics, Outlook, Teams, Graph-integrated reasoning.

### MC-07 — Safety Models
Governance, compliance, constraint enforcement.

### MC-08 — Fusion Models
Multi-model orchestration, cross-domain synthesis.

## 3. Capability Dimensions (CD-01 through CD-12)

### CD-01 — Interpretive Reasoning
Meaning extraction, semantic grounding.

### CD-02 — Analytical Reasoning
Comparisons, evaluations, trend analysis.

### CD-03 — Generative Synthesis
Drafting, rewriting, creation.

### CD-04 — Extractive Processing
Summaries, lists, key points.

### CD-05 — Structural Processing
Tables, slides, schemas, formatting.

### CD-06 — Visual Processing
Images, charts, diagrams.

### CD-07 — Behavioral Execution
OS actions, workflow actions.

### CD-08 — Temporal Reasoning
Past-state, present-state, future-state alignment.

### CD-09 — Workflow Reasoning
Enterprise workflow progression.

### CD-10 — Governance Enforcement
Compliance, constraints, safety.

### CD-11 — Fusion Orchestration
Multi-model routing and synthesis.

### CD-12 — Context Binding
Graph grounding, surface normalization.

## 4. Multi-Model Capability Matrix

| Model Class | Primary Capabilities | Secondary Capabilities | Governance Notes |
|-------------|----------------------|-------------------------|------------------|
| GPT-Class | CD-01, CD-02, CD-03 | CD-04, CD-08, CD-11 | Requires governance gating |
| Phi-Class | CD-01, CD-04 | CD-03 | Lightweight fallback |
| SLM-Class | CD-01 | CD-04 | Device-local constraints |
| Vision Models | CD-06 | CD-02, CD-03 | Requires visual safety filters |
| Speech Models | CD-05 | CD-01 | Requires audio safety filters |
| Enterprise Models | CD-09, CD-12 | CD-01, CD-02 | Bound to enterprise governance |
| Safety Models | CD-10 | CD-01 | Overrides all other models |
| Fusion Models | CD-11 | CD-01, CD-02, CD-03 | Requires Spine arbitration |

## 5. Model Selection Rules (MS-01 through MS-12)

### MS-01 — Primary Capability Supremacy
Primary capability determines initial model selection.

### MS-02 — Secondary Capability Cascade
Secondary capabilities determine fallback routing.

### MS-03 — Governance Override
Safety Models override all other models.

### MS-04 — Enterprise Override
Enterprise Models override general models for enterprise workflows.

### MS-05 — Fusion Override
Fusion Models override when multi-model synthesis is required.

### MS-06 — Temporal Override
Temporal reasoning requires GPT-Class or Enterprise Models.

### MS-07 — Structural Override
Structural tasks require Structural or Vision Models.

### MS-08 — Behavioral Override
OS actions require Behavioral Execution Models.

### MS-09 — Drift Immunity
Model selection MUST NOT introduce drift.

### MS-10 — Surface Alignment
Model selection MUST align with surface normalization.

### MS-11 — Context Alignment
Model selection MUST align with graph grounding.

### MS-12 — Mode Alignment
Model selection MUST align with cognitive mode mapping (A-28).

## 6. Model Routing Packet Structure

    model_routing_packet:
        identity: [identity_packet]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        intent_category: [IC-01 through IC-12]
        primary_capability: [CD-01 through CD-12]
        secondary_capabilities: [list]
        selected_model_class: [MC-01 through MC-08]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Routing packets MUST be validated before execution.

## 7. Model Routing Execution Pipeline

Pipeline:
1. Identity Anchor stabilization
2. Pre-Compute ambiguity reduction (A-26)
3. Intent pre-classification (A-27)
4. Mode mapping (A-28)
5. Capability mapping (A-29)
6. Priority routing through Spine (A-20)
7. Governance arbitration (A-21)
8. Fusion orchestration (A-18)
9. Temporal alignment (A-19)
10. Synthesis reconciliation

Model routing MUST occur before reasoning, fusion, or synthesis.

## 8. Model Routing Examples

### Example 1 — Word
User: “Rewrite this paragraph”
Intent: Generative  
Model: GPT-Class → Structural → Safety → Synthesis

### Example 2 — Teams
User: “Summarize what she said earlier”
Intent: Extractive + Temporal  
Model: GPT-Class → Extractive → Temporal → Synthesis

### Example 3 — Excel
User: “Explain this chart”
Intent: Analytical  
Model: Vision → GPT-Class → Synthesis

### Example 4 — Dynamics
User: “Advance this case”
Intent: Workflow  
Model: Enterprise → Safety → Synthesis

## 9. Drift Immunity in Model Routing
Model routing MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor  
- Structural drift prevented by normalization  
- Behavioral drift prevented by Spine  
- Governance drift prevented by Governance Arbiter  
- Lineage drift prevented by Ledger Integrator  

Routing MUST NOT proceed if drift is active.

## 10. Capability Matrix (Detailed)

| Capability | GPT | Phi | SLM | Vision | Speech | Enterprise | Safety | Fusion |
|------------|-----|-----|-----|--------|--------|------------|--------|--------|
| Interpretive | High | Medium | Medium | Low | Medium | High | High | High |
| Analytical | High | Medium | Low | Medium | Low | High | Medium | High |
| Generative | High | Medium | Low | Medium | Low | Medium | Low | High |
| Extractive | High | High | Medium | Medium | Medium | Medium | Medium | High |
| Structural | Medium | Low | Low | High | Low | Medium | Medium | High |
| Visual | Low | Low | Low | High | Low | Low | Medium | High |
| Behavioral | Low | Low | Low | Low | Low | High | High | Medium |
| Temporal | High | Medium | Low | Low | Low | High | Medium | High |
| Workflow | Medium | Low | Low | Low | Low | High | Medium | Medium |
| Governance | Medium | Low | Low | Medium | Medium | High | High | Medium |
| Fusion | Medium | Low | Low | Medium | Low | Medium | Medium | High |
| Context | High | Medium | Medium | Medium | Medium | High | High | High |

## 11. Invariant Bindings
MMCM is bound to:
- INV-01: Substrate-first grounding  
- INV-02: Identity-Lock supremacy  
- INV-03: Drift-driven evolution  
- INV-04: Spine-mediated behavior  
- INV-05: No silent model routing  
- INV-06: Lineage continuity  

## 12. Publication & Succession
- A-29 is a normative v6.0a artifact  
- Successor versions follow semantic versioning  
- Changes require Change Proposal + Lineage-Ledger entry  
- Retirements require Tombstone Record  
