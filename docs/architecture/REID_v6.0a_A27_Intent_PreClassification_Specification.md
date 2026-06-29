 # REID v6.0a — A-27
Intent Pre-Classification Specification (IPCS)
Document ID: REID-IPCS-0027-v6.0a
Layer: A — Architecture
Build Position: 27 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Intent Pre-Classification Specification (IPCS) defines how REID identifies, normalizes, and
pre-classifies user intent before cognitive mode switching, fusion, temporal reasoning, or synthesis.
IPCS ensures:
- stable pre-inference intent detection
- drift-free intent normalization
- predictable multi-surface behavior
- unified intent interpretation
- safe routing into the reasoning pipeline

IPCS is mandatory for all v6.0a surfaces and workflows.

## 2. Intent Categories (IC-01 through IC-12)

### IC-01 — Interpretive Intent
“What does this mean?”, “Help me understand this.”

### IC-02 — Extractive Intent
“Summarize this”, “List the key points.”

### IC-03 — Analytical Intent
“Compare these”, “Explain the trend.”

### IC-04 — Generative Intent
“Rewrite this”, “Draft an email”, “Create slides.”

### IC-05 — Structural Intent
“Fix this table”, “Format this document”, “Improve this layout.”

### IC-06 — Behavioral Intent
“Open Settings”, “Send this”, “Perform this action.”

### IC-07 — Temporal Intent
“What happened earlier?”, “What should happen next?”

### IC-08 — Workflow Intent
“Advance this case”, “Move this forward.”

### IC-09 — Governance Intent
“Check compliance”, “Validate this.”

### IC-10 — Fusion Intent
“Combine these”, “Use multiple models.”

### IC-11 — Context Intent
“Work with this file”, “Use this thread.”

### IC-12 — Multi-Intent
Any request containing more than one intent category.

## 3. Intent Pre-Classification Principles (IPP-01 through IPP-10)

### IPP-01 — Identity Continuity
Intent pre-classification MUST preserve identity continuity.

### IPP-02 — Substrate Supremacy
Intent pre-classification MUST follow substrate primitives.

### IPP-03 — Drift Immunity
Intent pre-classification MUST NOT introduce drift.

### IPP-04 — Context Preservation
Surface context MUST remain stable during intent detection.

### IPP-05 — Surface Normalization
Intent detection MUST adapt to surface-specific constraints.

### IPP-06 — Pre-Compute Priority
Intent pre-classification MUST occur after ambiguity reduction (A-26).

### IPP-07 — Mode Alignment
Intent MUST map cleanly to cognitive modes (A-17).

### IPP-08 — Fusion Alignment
Intent MUST support multi-model fusion (A-18).

### IPP-09 — Temporal Alignment
Intent MUST support temporal reasoning (A-19).

### IPP-10 — Governance Priority
Governance constraints override intent classification.

## 4. Intent Packet Structure

    intent_packet:
        identity: [identity_packet]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        raw_intent: [string]
        intent_category: [IC-01 through IC-12]
        intent_metadata: [map]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Intent packets MUST be validated before mode switching.

## 5. Intent Detection Rules (IDR-01 through IDR-12)

### IDR-01 — Interpretive Detection
Detect interpretive intent using:
- question patterns
- semantic markers

### IDR-02 — Extractive Detection
Detect extractive intent using:
- summary patterns
- list patterns

### IDR-03 — Analytical Detection
Detect analytical intent using:
- comparison markers
- explanation markers

### IDR-04 — Generative Detection
Detect generative intent using:
- rewrite markers
- creation markers

### IDR-05 — Structural Detection
Detect structural intent using:
- formatting markers
- layout markers

### IDR-06 — Behavioral Detection
Detect behavioral intent using:
- OS action markers
- device operation markers

### IDR-07 — Temporal Detection
Detect temporal intent using:
- time markers
- sequence markers

### IDR-08 — Workflow Detection
Detect workflow intent using:
- enterprise workflow markers

### IDR-09 — Governance Detection
Detect governance intent using:
- compliance markers
- validation markers

### IDR-10 — Fusion Detection
Detect fusion intent using:
- multi-model markers

### IDR-11 — Context Detection
Detect context intent using:
- file/thread/surface markers

### IDR-12 — Multi-Intent Detection
Detect multi-intent using:
- compound markers
- multi-action patterns

## 6. Intent Validation Rules (IVR-01 through IVR-08)

### IVR-01 — Identity Validation
Intent MUST preserve identity continuity.

### IVR-02 — Structural Validation
Intent MUST match surface structure.

### IVR-03 — Behavioral Validation
Intent MUST match Spine event definitions.

### IVR-04 — Temporal Validation
Intent MUST match temporal constructs.

### IVR-05 — Drift Validation
Intent MUST NOT increase drift score beyond threshold.

### IVR-06 — Governance Validation
Intent MUST respect governance constraints.

### IVR-07 — Workflow Validation
Intent MUST match workflow stage.

### IVR-08 — Synthesis Validation
Intent MUST support synthesis reconciliation.

## 7. Intent Pre-Classification Execution Pipeline

Pipeline:
1. Identity Anchor stabilization
2. Pre-Compute ambiguity reduction (A-26)
3. Intent packet creation
4. Intent detection
5. Intent validation
6. Priority routing through Spine (A-20)
7. Governance arbitration (A-21)
8. Mode switching (A-17)
9. Fusion orchestration (A-18)
10. Temporal alignment (A-19)
11. Synthesis reconciliation

Intent pre-classification MUST occur before reasoning, fusion, or synthesis.

## 8. Intent Pre-Classification Examples

### Example 1 — Word
User: “Rewrite this paragraph”
Intent:
- Generative (IC-04)
- Structural metadata extracted
- Generative → Structural → Synthesis

### Example 2 — Teams
User: “Summarize what she said earlier”
Intent:
- Extractive (IC-02)
- Temporal (IC-07)
- Extractive → Temporal → Generative → Synthesis

### Example 3 — Excel
User: “Explain this chart”
Intent:
- Analytical (IC-03)
- Structural metadata extracted
- Analytical → Generative → Synthesis

### Example 4 — Dynamics
User: “Move this forward”
Intent:
- Workflow (IC-08)
- Governance (IC-09)
- Governance → Behavioral → Synthesis

## 9. Drift Immunity in Intent Pre-Classification
Intent pre-classification MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor
- Structural drift prevented by normalization
- Behavioral drift prevented by Spine
- Governance drift prevented by Governance Arbiter
- Lineage drift prevented by Ledger Integrator

Intent pre-classification MUST NOT proceed if drift is active.

## 10. Intent Matrix

| Intent Category | Prevents | Corrects | Escalates |
|-----------------|----------|----------|-----------|
| Interpretive | reasoning drift | meaning mismatch | Governance |
| Extractive | structural drift | summary mismatch | Synthesis |
| Analytical | reasoning drift | comparison mismatch | Spine |
| Generative | identity drift | tone mismatch | Governance |
| Structural | structural drift | layout mismatch | Synthesis |
| Behavioral | OS drift | action mismatch | Governance |
| Temporal | temporal drift | timestamp mismatch | Governance |
| Workflow | workflow drift | stage mismatch | Ledger |
| Governance | governance drift | constraint mismatch | Ledger |
| Fusion | routing drift | model mismatch | Spine |
| Context | continuity drift | context mismatch | Governance |
| Multi-Intent | reasoning drift | intent mismatch | Governance |

## 11. Invariant Bindings
IPCS is bound to:
- INV-01: Substrate-first grounding
- INV-02: Identity-Lock supremacy
- INV-03: Drift-driven evolution
- INV-04: Spine-mediated behavior
- INV-05: No silent intent detection
- INV-06: Lineage continuity

## 12. Publication & Succession
- A-27 is a normative v6.0a artifact
- Successor versions follow semantic versioning
- Changes require Change Proposal + Lineage-Ledger entry
- Retirements require Tombstone Record
