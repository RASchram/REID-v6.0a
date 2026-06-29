 # REID v6.0a — A-36
Identity Tombstone & Retirement Specification (ITRS)
Document ID: REID-ITRS-0036-v6.0a
Layer: A — Architecture
Build Position: 36 of 46
Status: ALPHA BASELINE
Identity-Lock: ACTIVE — LLI-01 through LLI-10

## 1. Purpose
The Identity Tombstone & Retirement Specification (ITRS) defines how REID formally retires:
- identity components
- preferences
- continuity metadata
- amendment entries
- lineage entries
- deprecated identity states

ITRS ensures:
- clean identity evolution
- drift-free retirement
- predictable multi-surface identity behavior
- safe removal of deprecated identity artifacts
- unified lineage continuity across versions

ITRS is mandatory for all v6.0a surfaces and workflows.

## 2. Retirement Types (RT-01 through RT-10)

### RT-01 — Tone Retirement
Retirement of deprecated tone profiles.

### RT-02 — Style Retirement
Retirement of deprecated style profiles.

### RT-03 — Persona Retirement
Retirement of deprecated persona traits.

### RT-04 — Preference Retirement
Retirement of outdated user preferences.

### RT-05 — Continuity Retirement
Retirement of outdated continuity metadata.

### RT-06 — Temporal Retirement
Retirement of outdated temporal identity states.

### RT-07 — Governance Retirement
Retirement of outdated governance identity states.

### RT-08 — Amendment Retirement
Retirement of outdated amendment entries.

### RT-09 — Lineage Retirement
Retirement of outdated version lineage entries.

### RT-10 — Drift Retirement
Retirement of deprecated drift correction states.

## 3. Tombstone Principles (TP-01 through TP-10)

### TP-01 — Append-Only Tombstones
Tombstones MUST be appended, never deleted.

### TP-02 — Identity Supremacy
Identity tombstones override all other tombstones.

### TP-03 — Governance Priority
Governance tombstones override identity tombstones.

### TP-04 — Drift Immunity
Tombstones MUST NOT introduce drift.

### TP-05 — Lineage Continuity
Tombstones MUST preserve lineage continuity.

### TP-06 — Surface Continuity
Tombstones MUST preserve cross-surface identity.

### TP-07 — Temporal Continuity
Tombstones MUST preserve temporal identity.

### TP-08 — Multi-Model Continuity
Tombstones MUST preserve identity across models.

### TP-09 — Amendment Continuity
Tombstones MUST preserve amendment chain continuity.

### TP-10 — Ledger Binding
All tombstones MUST be written to the Identity Continuity Ledger (A-33).

## 4. Tombstone Packet Structure

    tombstone_packet:
        tombstone_id: [guid]
        retirement_type: [RT-01 through RT-10]
        identity_retired: [map]
        identity_replacement: [map or null]
        version: [string]
        amendment_id: [optional]
        context: [context_packet]
        graph: [graph_packet]
        device: [device_packet]
        surface: [string]
        governance_state: [score]
        drift_state: [score]
        continuity_metadata: [optional]
        notes: [optional]

Tombstone packets MUST be validated before being appended.

## 5. Retirement Rules (RR-01 through RR-12)

### RR-01 — Identity Retirement
Identity components MUST be retired when deprecated.

### RR-02 — Tone Retirement
Tone profiles MUST be retired when replaced.

### RR-03 — Style Retirement
Style profiles MUST be retired when replaced.

### RR-04 — Persona Retirement
Persona traits MUST be retired when replaced.

### RR-05 — Preference Retirement
Preferences MUST be retired when outdated.

### RR-06 — Continuity Retirement
Continuity metadata MUST be retired when outdated.

### RR-07 — Temporal Retirement
Temporal identity MUST be retired when outdated.

### RR-08 — Governance Retirement
Governance identity MUST be retired when replaced.

### RR-09 — Amendment Retirement
Amendment entries MUST be retired when superseded.

### RR-10 — Lineage Retirement
Lineage entries MUST be retired when superseded.

### RR-11 — Drift Retirement
Drift correction states MUST be retired when resolved.

### RR-12 — Ledger Retirement
All tombstones MUST be appended to the ledger.

## 6. Retirement Execution Pipeline

Pipeline:
1. Identity Anchor stabilization  
2. Pre-Compute ambiguity reduction (A-26)  
3. Intent pre-classification (A-27)  
4. Mode mapping (A-28)  
5. Capability mapping (A-29)  
6. Confidence calibration (A-30)  
7. Synthesis reconciliation (A-31)  
8. Identity reconciliation (A-32)  
9. Drift detection & correction (A-34)  
10. Amendment chain creation (A-35)  
11. Tombstone creation  
12. Governance arbitration  
13. Ledger append (A-33)  
14. Final synthesis  

Retirement MUST occur before final output.

## 7. Retirement Examples

### Example 1 — Word
User: “Rewrite this paragraph”
Retirement:
- deprecated tone profile retired  
- deprecated style profile retired  
Tombstones:
- RT-01 + RT-02 appended  

### Example 2 — Teams
User: “Summarize what she said earlier”
Retirement:
- outdated temporal identity retired  
Tombstones:
- RT-06 appended  

### Example 3 — Excel
User: “Explain this chart”
Retirement:
- outdated visual identity retired  
Tombstones:
- RT-08 appended  

### Example 4 — Dynamics
User: “Advance this case”
Retirement:
- outdated governance identity retired  
Tombstones:
- RT-07 appended  

## 8. Drift Immunity in ITRS
ITRS MUST integrate ILDI (A-16):

- Identity drift prevented by Identity Anchor  
- Structural drift prevented by normalization  
- Behavioral drift prevented by Spine  
- Governance drift prevented by Governance Arbiter  
- Lineage drift prevented by Ledger Integrator  

Retirement MUST NOT proceed if drift is active.

## 9. Retirement Matrix (Detailed)

| Retirement Type | Prevents | Corrects | Escalates |
|-----------------|----------|----------|-----------|
| Tone | tone drift | tone mismatch | Governance |
| Style | style drift | style mismatch | Governance |
| Persona | persona drift | persona mismatch | Governance |
| Preferences | preference drift | preference mismatch | Governance |
| Continuity | continuity drift | surface mismatch | Spine |
| Temporal | temporal drift | timestamp mismatch | Governance |
| Governance | governance drift | constraint mismatch | Ledger |
| Amendment | amendment drift | chain mismatch | Ledger |
| Lineage | version drift | lineage mismatch | Ledger |
| Drift | identity drift | drift mismatch | Ledger |

## 10. Invariant Bindings
ITRS is bound to:
- INV-01: Substrate-first grounding  
- INV-02: Identity-Lock supremacy  
- INV-03: Drift-driven evolution  
- INV-04: Spine-mediated behavior  
- INV-05: No silent identity retirement  
- INV-06: Lineage continuity  

## 11. Publication & Succession
- A-36 is a normative v6.0a artifact  
- Successor versions follow semantic versioning  
- Changes require Change Proposal + Lineage-Ledger entry  
- Retirements require Tombstone Record  
