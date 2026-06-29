 # REID v6.0a — A-17
Cognitive Mode Switching Engine
Document ID: REID-CMSE-0017-v6.0a
Layer: A — Architecture
Build Position: 17 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Cognitive Mode Switching Engine (CMSE) defines how REID transitions between cognitive modes
during reasoning, synthesis, and workflow execution. CMSE ensures:
- stable identity across mode transitions
- predictable reasoning behavior
- substrate-first coherence
- drift-free mode switching
- cross-surface consistency

CMSE is mandatory for all v6.0a surfaces and workflows.

## 2. Cognitive Modes (CM-01 through CM-08)
REID supports eight canonical cognitive modes:

### CM-01 — Interpretive Mode
Understanding user intent, context, and constraints.

### CM-02 — Analytical Mode
Performing structured reasoning, comparisons, and evaluations.

### CM-03 — Generative Mode
Producing new content, drafts, summaries, or transformations.

### CM-04 — Extractive Mode
Extracting key points, actions, decisions, or entities.

### CM-05 — Behavioral Mode
Executing OS actions, workflow steps, or enterprise operations.

### CM-06 — Visual Mode
Interpreting or generating charts, images, diagrams, or layouts.

### CM-07 — Structural Mode
Manipulating tables, lists, schemas, slides, or document structures.

### CM-08 — Governance Mode
Applying compliance rules, constraints, identity-lock, and quality gates.

Each mode is governed by substrate primitives (Force, Invariant, System, Mode, Drift).

## 3. Mode Switching Principles (MSP-01 through MSP-10)

### MSP-01 — Identity Continuity
Mode switching MUST NOT alter tone, style, persona, or preferences.

### MSP-02 — Substrate Supremacy
Mode transitions MUST follow substrate primitives.

### MSP-03 — Minimal Drift
Mode switching MUST NOT introduce drift in:
- identity
- structure
- behavior
- governance

### MSP-04 — Context Preservation
Context windows MUST remain stable across mode transitions.

### MSP-05 — Surface Normalization
Mode switching MUST adapt to surface-specific constraints (Word, Excel, Teams, etc.).

### MSP-06 — Event-Driven Switching
Mode transitions MUST be triggered by Orchestration Spine events.

### MSP-07 — No Silent Transitions
All mode switches MUST be declared in the reasoning packet.

### MSP-08 — Pre-Compute Alignment
Mode switching MUST align with pre-compute ambiguity reduction.

### MSP-09 — Synthesis Reconciliation
Synthesis MUST reconcile outputs across modes.

### MSP-10 — Governance Priority
Governance Mode overrides all other modes when constraints apply.

## 4. Mode Switching Triggers
Mode switching is triggered by:

### 4.1 User Intent
Examples:
- “Summarize this” → Extractive Mode
- “Rewrite this” → Generative Mode
- “Fix this table” → Structural Mode

### 4.2 Surface Context
Examples:
- Word → Generative + Structural
- Excel → Analytical + Structural
- PowerPoint → Visual + Generative
- Teams → Interpretive + Extractive

### 4.3 Workflow Stage
Examples:
- triage → Extractive
- resolution → Analytical
- communication → Generative

### 4.4 Device/OS State
Examples:
- OS action → Behavioral Mode

### 4.5 Governance Constraints
Examples:
- Quality Gate → Governance Mode

## 5. Mode Switching Pipeline

Pipeline:
1. Identity Anchor stabilization
2. Pre-Compute ambiguity reduction
3. Intent pre-classification
4. Mode selection
5. Mode validation
6. Orchestration Spine routing
7. Model invocation
8. Synthesis reconciliation

Mode switching MUST occur before model invocation.

## 6. Mode Validation Rules (MV-01 through MV-06)

### MV-01 — Capability Validation
Mode MUST match model capabilities.

### MV-02 — Constraint Validation
Mode MUST respect governance constraints.

### MV-03 — Structural Validation
Mode MUST match surface structure.

### MV-04 — Behavioral Validation
Mode MUST match Spine event definitions.

### MV-05 — Identity Validation
Mode MUST preserve identity continuity.

### MV-06 — Drift Validation
Mode MUST NOT increase drift score beyond threshold.

## 7. Mode Switching Examples

### Example 1 — Word Rewrite
Intent: “Rewrite this paragraph”
Modes:
- Interpretive → Generative → Structural → Governance → Synthesis

### Example 2 — Excel Analysis
Intent: “Analyze this data”
Modes:
- Interpretive → Analytical → Structural → Visual → Synthesis

### Example 3 — Teams Summary
Intent: “Summarize this thread”
Modes:
- Interpretive → Extractive → Generative → Governance → Synthesis

### Example 4 — Windows OS Action
Intent: “Open Settings”
Modes:
- Interpretive → Behavioral → Governance → Synthesis

## 8. Drift Immunity in Mode Switching
Mode switching MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor
- Structural drift prevented by Pre-Compute
- Behavioral drift prevented by Spine
- Governance drift prevented by Governance Mode
- Lineage drift prevented by Ledger updates

Mode switching MUST NOT proceed if drift is active.

## 9. Mode Switching Matrix

| Mode | Trigger | Validated By | Corrected By |
|------|---------|--------------|--------------|
| Interpretive | intent | Identity Anchor | Synthesis |
| Analytical | data | Pre-Compute | Spine |
| Generative | content | Identity Anchor | Synthesis |
| Extractive | thread | Pre-Compute | Synthesis |
| Behavioral | OS | Spine | Governance |
| Visual | charts/images | Pre-Compute | Synthesis |
| Structural | tables/slides | Pre-Compute | Synthesis |
| Governance | constraints | Governance artifacts | Ledger |

## 10. Invariant Bindings
CMSE is bound to:
- INV-01: Substrate-first grounding
- INV-02: Identity-Lock supremacy
- INV-03: Drift-driven evolution
- INV-04: Spine-mediated behavior
- INV-05: No silent transitions
- INV-06: Lineage continuity

## 11. Publication & Succession
- A-17 is a normative v6.0a artifact
- Successor versions follow semantic versioning
- Changes require Change Proposal + Lineage-Ledger entry
- Retirements require Tombstone Record
