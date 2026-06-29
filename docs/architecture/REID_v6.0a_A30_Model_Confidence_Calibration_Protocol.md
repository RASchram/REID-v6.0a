 # REID v6.0a — A-30
Model Confidence Calibration Protocol (MCCP)
Document ID: REID-MCCP-0030-v6.0a
Layer: A — Architecture
Build Position: 30 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Model Confidence Calibration Protocol (MCCP) defines how REID evaluates, calibrates, and
reconciles confidence scores across multiple models (GPT, Phi, SLM, Vision, Speech, Enterprise).
MCCP ensures:
- stable multi-model confidence behavior
- drift-free confidence scoring
- governance-safe output selection
- predictable synthesis quality
- unified confidence interpretation across surfaces

MCCP is mandatory for all v6.0a surfaces and workflows.

## 2. Confidence Dimensions (CDM-01 through CDM-10)

### CDM-01 — Semantic Confidence
Accuracy of meaning, interpretation, and semantic grounding.

### CDM-02 — Structural Confidence
Accuracy of tables, slides, schemas, formatting.

### CDM-03 — Visual Confidence
Accuracy of image interpretation, OCR, diagram extraction.

### CDM-04 — Temporal Confidence
Accuracy of past-state, present-state, and future-state reasoning.

### CDM-05 — Behavioral Confidence
Accuracy of OS actions, workflow actions, enterprise operations.

### CDM-06 — Workflow Confidence
Accuracy of enterprise workflow progression.

### CDM-07 — Governance Confidence
Accuracy of compliance, constraints, and safety enforcement.

### CDM-08 — Fusion Confidence
Accuracy of multi-model synthesis and routing.

### CDM-09 — Context Confidence
Accuracy of graph grounding and surface normalization.

### CDM-10 — Synthesis Confidence
Accuracy of final output reconciliation.

## 3. Confidence Score Types (CST-01 through CST-05)

### CST-01 — Raw Confidence
Model-provided confidence score.

### CST-02 — Adjusted Confidence
Confidence after governance and drift adjustments.

### CST-03 — Calibrated Confidence
Confidence after cross-model calibration.

### CST-04 — Composite Confidence
Confidence after fusion and synthesis reconciliation.

### CST-05 — Final Confidence
Confidence used for output selection.

## 4. Confidence Calibration Matrix

| Model Class | Strengths | Weaknesses | Calibration Notes |
|-------------|-----------|------------|-------------------|
| GPT-Class | semantic, analytical, generative | structural, behavioral | high semantic weight |
| Phi-Class | extractive, lightweight | deep reasoning | medium semantic weight |
| SLM-Class | device-local, fast | limited reasoning | low semantic weight |
| Vision Models | visual, structural | semantic | high visual weight |
| Speech Models | audio | semantic | medium semantic weight |
| Enterprise Models | workflow, governance | generative | high governance weight |
| Safety Models | governance | generative | overrides all |
| Fusion Models | synthesis | raw reasoning | composite weight |

## 5. Calibration Rules (CR-01 through CR-12)

### CR-01 — Semantic Supremacy
Semantic confidence dominates interpretive, extractive, and generative tasks.

### CR-02 — Structural Supremacy
Structural confidence dominates formatting, tables, slides, and schemas.

### CR-03 — Visual Supremacy
Visual confidence dominates charts, images, diagrams.

### CR-04 — Governance Override
Governance confidence overrides all other confidence dimensions.

### CR-05 — Behavioral Override
Behavioral confidence overrides non-governance confidence for OS actions.

### CR-06 — Workflow Override
Workflow confidence overrides semantic confidence for enterprise tasks.

### CR-07 — Fusion Override
Fusion confidence overrides raw model confidence.

### CR-08 — Drift Immunity
Confidence calibration MUST NOT introduce drift.

### CR-09 — Surface Alignment
Confidence calibration MUST align with surface normalization (A-23).

### CR-10 — Context Alignment
Confidence calibration MUST align with graph grounding (A-25).

### CR-11 — Temporal Alignment
Confidence calibration MUST align with temporal reasoning (A-19).

### CR-12 — Mode Alignment
Confidence calibration MUST align with cognitive mode mapping (A-28).

## 6. Confidence Packet Structure

    confidence_packet:
        identity: [identity_packet]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        model_class: [MC-01 through MC-08]
        raw_confidence: [float]
        adjusted_confidence: [float]
        calibrated_confidence: [float]
        composite_confidence: [float]
        final_confidence: [float]
        confidence_dimensions: [map]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Confidence packets MUST be validated before synthesis.

## 7. Confidence Calibration Pipeline

Pipeline:
1. Identity Anchor stabilization  
2. Pre-Compute ambiguity reduction (A-26)  
3. Intent pre-classification (A-27)  
4. Mode mapping (A-28)  
5. Capability mapping (A-29)  
6. Raw confidence extraction  
7. Governance adjustment  
8. Drift adjustment  
9. Cross-model calibration  
10. Fusion reconciliation  
11. Synthesis reconciliation  
12. Final confidence selection  

Confidence calibration MUST occur before final output selection.

## 8. Confidence Calibration Examples

### Example 1 — Word
User: “Rewrite this paragraph”
- GPT raw confidence: high  
- Structural confidence: medium  
- Governance confidence: high  
Final: generative + structural + governance → high

### Example 2 — Teams
User: “Summarize what she said earlier”
- Extractive confidence: high  
- Temporal confidence: medium  
- Semantic confidence: high  
Final: extractive + temporal → high

### Example 3 — Excel
User: “Explain this chart”
- Vision confidence: high  
- Analytical confidence: medium  
- Generative confidence: medium  
Final: visual + analytical → high

### Example 4 — Dynamics
User: “Advance this case”
- Workflow confidence: high  
- Governance confidence: high  
Final: workflow + governance → very high

## 9. Drift Immunity in Confidence Calibration
Confidence calibration MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor  
- Structural drift prevented by normalization  
- Behavioral drift prevented by Spine  
- Governance drift prevented by Governance Arbiter  
- Lineage drift prevented by Ledger Integrator  

Confidence calibration MUST NOT proceed if drift is active.

## 10. Confidence Matrix (Detailed)

| Dimension | GPT | Phi | SLM | Vision | Speech | Enterprise | Safety | Fusion |
|-----------|-----|-----|-----|--------|--------|------------|--------|--------|
| Semantic | High | Medium | Medium | Low | Medium | High | High | High |
| Structural | Medium | Low | Low | High | Low | Medium | Medium | High |
| Visual | Low | Low | Low | High | Low | Low | Medium | High |
| Temporal | High | Medium | Low | Low | Low | High | Medium | High |
| Behavioral | Low | Low | Low | Low | Low | High | High | Medium |
| Workflow | Medium | Low | Low | Low | Low | High | Medium | Medium |
| Governance | Medium | Low | Low | Medium | Medium | High | High | Medium |
| Fusion | Medium | Low | Low | Medium | Low | Medium | Medium | High |
| Context | High | Medium | Medium | Medium | Medium | High | High | High |
| Synthesis | High | Medium | Medium | Medium | Medium | High | High | High |

## 11. Invariant Bindings
MCCP is bound to:
- INV-01: Substrate-first grounding  
- INV-02: Identity-Lock supremacy  
- INV-03: Drift-driven evolution  
- INV-04: Spine-mediated behavior  
- INV-05: No silent confidence calibration  
- INV-06: Lineage continuity  

## 12. Publication & Succession
- A-30 is a normative v6.0a artifact  
- Successor versions follow semantic versioning  
- Changes require Change Proposal + Lineage-Ledger entry  
- Retirements require Tombstone Record  
