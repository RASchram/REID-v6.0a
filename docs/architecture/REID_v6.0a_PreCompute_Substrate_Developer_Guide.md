 # REID v6.0a — Pre-Compute Substrate Developer Guide
Meaning Stabilization and Compute Reduction for Microsoft Developers

This guide explains how REID v6.0a’s Pre-Compute Substrate stabilizes meaning, filters ambiguity, 
normalizes intent, and reduces Azure inference cost before any model is invoked. It is the first 
active component in the REID cognitive spine and one of the most important mechanisms for 
Microsoft-scale efficiency.


###################################################################################################
# 1. PURPOSE
###################################################################################################

The Pre-Compute Substrate solves a core problem:

AI models are expensive when used as the *first* step.

Most Copilot requests contain:
- ambiguity  
- missing context  
- unstable intent  
- inconsistent phrasing  
- unnecessary complexity  

If sent directly to a model:
- GPU-hours spike  
- latency increases  
- reasoning becomes inconsistent  
- identity continuity breaks  

REID v6.0a prevents this by stabilizing meaning *before* inference.


###################################################################################################
# 2. WHAT THE PRE-COMPUTE SUBSTRATE DOES
###################################################################################################

The substrate performs five critical functions:

1. **Meaning Stabilization**  
    Converts raw user input into a stable semantic representation.

2. **Ambiguity Filtering**  
    Removes uncertainty that would force the model to guess.

3. **Intent Normalization**  
    Converts user phrasing into a canonical intent form.

4. **Goal Pre-Classification**  
    Identifies likely goals before full decomposition.

5. **Context Binding**  
    Attaches Entra + Graph + device + surface context.

These steps reduce the number of model calls required.


###################################################################################################
# 3. INPUTS REQUIRED BY THE SUBSTRATE
###################################################################################################

Developers MUST provide:

    precompute_input:
        raw_text: [string]
        entra_token: [token]
        user_id: [guid]
        tenant_id: [guid]
        device_id: [guid]
        session_id: [guid]
        graph_context: [optional]
        surface: [word | excel | teams | outlook | windows | dynamics]
        continuity_metadata: [optional]

These inputs allow the substrate to stabilize meaning and identity.


###################################################################################################
# 4. SUBSTRATE PROCESSING STEPS
###################################################################################################

The substrate executes the following pipeline:

### Step 1 — **Semantic Parsing**
Extracts meaning from raw text.

### Step 2 — **Ambiguity Detection**
Identifies unclear or underspecified elements.

### Step 3 — **Ambiguity Filtering**
Removes ambiguity using:
- Graph context  
- Entra identity  
- device context  
- surface metadata  

### Step 4 — **Intent Normalization**
Converts user phrasing into canonical intent.

Example:
- “Can you maybe help me with this?”  
    → intent: “assist_with_task”

### Step 5 — **Goal Pre-Classification**
Predicts likely goals before full decomposition.

### Step 6 — **Context Binding**
Attaches identity and context metadata.

### Step 7 — **Substrate Output Packaging**
Produces a stable intent package.


###################################################################################################
# 5. SUBSTRATE OUTPUT FORMAT
###################################################################################################

Developers MUST consume:

    precompute_output:
        canonical_intent: [string]
        stabilized_meaning: [string]
        ambiguity_score: [0–100]
        preclassified_goals: [list]
        context_binding:
            entra: [ids]
            graph: [entities]
            device: [metadata]
            surface: [string]
        continuity_metadata: [optional]

This output is passed to Intent Classification.


###################################################################################################
# 6. AMBIGUITY SCORE
###################################################################################################

Ambiguity Score ranges:

- **0–20**: Clear  
- **21–40**: Mild ambiguity  
- **41–60**: Moderate ambiguity  
- **61–80**: Severe ambiguity  
- **81–100**: Unusable  

Scores ≥ 61 trigger:
- additional filtering  
- context expansion  
- minimal re-inference  


###################################################################################################
# 7. HOW THE SUBSTRATE REDUCES COMPUTE COST
###################################################################################################

The substrate reduces compute consumption by:

- eliminating unnecessary model calls  
- reducing model input complexity  
- preventing drift before inference  
- stabilizing identity before inference  
- reducing ambiguity that forces larger models to work harder  
- enabling lightweight models for simple tasks  

Outcome:
- lower GPU-hours per user  
- lower Azure cost  
- faster Copilot responses  
- higher global scalability  


###################################################################################################
# 8. HOW THE SUBSTRATE FITS INTO THE PIPELINE
###################################################################################################

Pipeline:

Input  
→ Identity Anchor  
→ Pre-Compute Substrate  
→ Intent Classification  
→ Goal Decomposition  
→ Orchestration Spine  
→ Model Invocation  
→ Synthesis  
→ Output

The substrate is the first active reasoning component.


###################################################################################################
# 9. DEVELOPER IMPLEMENTATION CHECKLIST
###################################################################################################

You are correctly integrating the substrate when:

[ ] Raw text is provided  
[ ] Entra identity is bound  
[ ] Graph context is provided when available  
[ ] Device context is provided  
[ ] Surface metadata is provided  
[ ] Ambiguity Score is computed  
[ ] Canonical intent is produced  
[ ] Preclassified goals are produced  
[ ] Context binding is attached  
[ ] Output is passed to Intent Classification  


###################################################################################################
# 10. ERROR MODES (DEVELOPER EDITION)
###################################################################################################

Developers MUST handle:

AMBIGUITY_OVERFLOW  
    Ambiguity Score ≥ 81.

CONTEXT_MISSING  
    Required context unavailable.

IDENTITY_ANCHOR_LOSS  
    Entra identity missing or corrupted.

SURFACE_MISMATCH  
    Surface metadata inconsistent.

PRECOMPUTE_FAILURE  
    Substrate unable to stabilize meaning.


###################################################################################################
# 11. SUMMARY
###################################################################################################

This guide provides the minimal architectural and implementation guidance required for Microsoft 
developers to integrate the Pre-Compute Substrate into Copilot, Azure AI Foundry, Microsoft 365, 
Dynamics, Teams, Outlook, and Windows.

It represents the public-safe substrate boundary of REID v6.0a.
