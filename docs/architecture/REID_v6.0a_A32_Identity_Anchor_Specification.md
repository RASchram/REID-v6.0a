 # REID v6.0a — A-32
Identity Anchor Specification (IAS)
Document ID: REID-IAS-0032-v6.0a
Layer: A — Architecture
Build Position: 32 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Identity Anchor Specification (IAS) defines the formal identity-lock mechanism that stabilizes
REID’s tone, style, persona, preferences, and reasoning identity across:
- surfaces
- sessions
- models
- workflows
- temporal spans

IAS ensures:
- stable identity continuity
- drift-free persona behavior
- predictable multi-surface tone
- unified reasoning identity
- governance-safe identity persistence

IAS is mandatory for all v6.0a surfaces and workflows.

## 2. Identity Components (ICMP-01 through ICMP-10)

### ICMP-01 — Tone Profile
Conversational tone, professional tone, narrative tone.

### ICMP-02 — Style Profile
Sentence structure, formatting preferences, structural tendencies.

### ICMP-03 — Persona Profile
Personality traits, interaction style, behavioral tendencies.

### ICMP-04 — Preference Profile
User-specific preferences, formatting preferences, workflow preferences.

### ICMP-05 — Reasoning Identity
Analytical tendencies, interpretive tendencies, synthesis tendencies.

### ICMP-06 — Surface Identity
Surface-specific tone/style adjustments.

### ICMP-07 — Temporal Identity
Consistency across past, present, and future interactions.

### ICMP-08 — Continuity Identity
Cross-surface continuity metadata.

### ICMP-09 — Governance Identity
Compliance, constraints, safety behavior.

### ICMP-10 — Drift Immunity Identity
Identity stability under multi-model fusion.

## 3. Identity-Lock Principles (ILP-01 through ILP-10)

### ILP-01 — Identity Supremacy
Identity-lock overrides all other reasoning layers.

### ILP-02 — Substrate Supremacy
Identity-lock MUST follow substrate primitives.

### ILP-03 — Drift Immunity
Identity-lock MUST NOT introduce drift.

### ILP-04 — Tone Continuity
Tone MUST remain stable across surfaces.

### ILP-05 — Style Continuity
Style MUST remain stable across surfaces.

### ILP-06 — Persona Continuity
Persona MUST remain stable across surfaces.

### ILP-07 — Preference Continuity
Preferences MUST persist across sessions.

### ILP-08 — Surface Normalization Alignment
Identity-lock MUST adapt to surface-specific constraints.

### ILP-09 — Governance Priority
Governance constraints override identity preferences.

### ILP-10 — Synthesis Alignment
Identity-lock MUST be applied during final synthesis.

## 4. Identity Anchor Packet Structure

    identity_anchor_packet:
        tone_profile: [map]
        style_profile: [map]
        persona_profile: [map]
        preference_profile: [map]
        reasoning_identity: [map]
        surface_identity: [map]
        temporal_identity: [map]
        continuity_identity: [map]
        governance_identity: [map]
        drift_identity: [map]
        continuity_metadata: [optional]
        drift_state: [score]
        governance_state: [score]

Identity anchor packets MUST be validated before reasoning.

## 5. Identity Validation Rules (IV-01 through IV-10)

### IV-01 — Tone Validation
Tone MUST match identity anchor.

### IV-02 — Style Validation
Style MUST match identity anchor.

### IV-03 — Persona Validation
Persona MUST match identity anchor.

### IV-04 — Preference Validation
Preferences MUST persist across surfaces.

### IV-05 — Structural Validation
Identity MUST align with surface structure.

### IV-06 — Behavioral Validation
Identity MUST align with Spine event definitions.

### IV-07 — Temporal Validation
Identity MUST remain stable across temporal spans.

### IV-08 — Drift Validation
Identity MUST NOT increase drift score beyond threshold.

### IV-09 — Governance Validation
Identity MUST respect governance constraints.

### IV-10 — Synthesis Validation
Identity MUST be applied during final synthesis.

## 6. Identity Anchor Execution Pipeline

Pipeline:
1. Identity Anchor stabilization  
2. Pre-Compute ambiguity reduction (A-26)  
3. Intent pre-classification (A-27)  
4. Mode mapping (A-28)  
5. Capability mapping (A-29)  
6. Confidence calibration (A-30)  
7. Multi-model output collection  
8. Identity reconciliation  
9. Governance arbitration  
10. Drift correction  
11. Final synthesis (A-31)  
12. Ledger update  

Identity-lock MUST be applied before final output.

## 7. Identity Anchor Examples

### Example 1 — Word
User: “Rewrite this paragraph”
Identity:
- tone preserved
- style preserved
- persona preserved
- generative → structural → identity → final

### Example 2 — Teams
User: “Summarize what she said earlier”
Identity:
- tone preserved
- persona preserved
- extractive → temporal → identity → final

### Example 3 — Excel
User: “Explain this chart”
Identity:
- tone preserved
- persona preserved
- visual → analytical → identity → final

### Example 4 — Dynamics
User: “Advance this case”
Identity:
- tone preserved
- persona preserved
- workflow → governance → identity → final

## 8. Drift Immunity in Identity Anchoring
Identity anchoring MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor  
- Structural drift prevented by normalization  
- Behavioral drift prevented by Spine  
- Governance drift prevented by Governance Arbiter  
- Lineage drift prevented by Ledger Integrator  

Identity anchoring MUST NOT proceed if drift is active.

## 9. Identity Matrix (Detailed)

| Identity Component | GPT | Phi | SLM | Vision | Speech | Enterprise | Safety | Fusion |
|--------------------|-----|-----|-----|--------|--------|------------|--------|--------|
| Tone | High | Medium | Medium | Low | Medium | High | High | High |
| Style | High | Medium | Medium | Low | Low | High | High | High |
| Persona | High | Medium | Medium | Low | Low | High | High | High |
| Preferences | High | Medium | Medium | Medium | Medium | High | High | High |
| Reasoning Identity | High | Medium | Medium | Low | Low | High | High | High |
| Surface Identity | High | Medium | Medium | Medium | Medium | High | High | High |
| Temporal Identity | High | Medium | Low | Low | Low | High | Medium | High |
| Continuity Identity | High | Medium | Medium | Medium | Medium | High | High | High |
| Governance Identity | Medium | Low | Low | Medium | Medium | High | High | Medium |
| Drift Identity | High | Medium | Medium | Medium | Medium | High | High | High |

## 10. Invariant Bindings
IAS is bound to:
- INV-01: Substrate-first grounding  
- INV-02: Identity-Lock supremacy  
- INV-03: Drift-driven evolution  
- INV-04: Spine-mediated behavior  
- INV-05: No silent identity transitions  
- INV-06: Lineage continuity  

## 11. Publication & Succession
- A-32 is a normative v6.0a artifact  
- Successor versions follow semantic versioning  
- Changes require Change Proposal + Lineage-Ledger entry  
- Retirements require Tombstone Record  
