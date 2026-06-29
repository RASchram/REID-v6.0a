 # REID v6.0a — Intent Classification Developer Guide
Canonical Intent Stabilization Across All Microsoft Surfaces

This guide explains how REID v6.0a classifies user intent across devices, sessions, products, threads, 
workflows, and multi-model pipelines. Intent Classification is the first major reasoning step after 
the Pre-Compute Substrate and is essential for stable, predictable Copilot behavior.


###################################################################################################
# 1. PURPOSE
###################################################################################################

Intent Classification solves a core Microsoft-scale problem:

Users express intent in inconsistent, ambiguous, informal, or incomplete ways.

Examples:
- “Can you help with this?”
- “Fix this”
- “Make this better”
- “What’s going on here?”
- “Do the thing we talked about earlier”
- “You know what I mean”

Without intent classification:
- models guess incorrectly  
- GPU-hours spike  
- reasoning becomes inconsistent  
- identity continuity breaks  
- multi-step workflows collapse  

REID v6.0a prevents this by converting raw user phrasing into canonical intent.


###################################################################################################
# 2. INTENT CLASSIFICATION PIPELINE
###################################################################################################

Pipeline:

Input  
→ Pre-Compute Substrate  
→ Intent Classification  
→ Goal Decomposition  
→ Orchestration Spine  
→ Model Invocation  
→ Synthesis  
→ Output

Intent Classification is the second active reasoning component.


###################################################################################################
# 3. INPUTS REQUIRED FOR INTENT CLASSIFICATION
###################################################################################################

Developers MUST provide:

    intent_input:
        stabilized_meaning: [string]
        canonical_intent: [optional]
        ambiguity_score: [0–100]
        preclassified_goals: [optional]
        context_binding:
            entra: [ids]
            graph: [entities]
            device: [metadata]
            surface: [string]
        continuity_metadata: [optional]

These inputs come directly from the Pre-Compute Substrate.


###################################################################################################
# 4. INTENT CLASSIFICATION STEPS
###################################################################################################

The Intent Classifier executes:

### Step 1 — **Semantic Intent Extraction**
Extracts intent from stabilized meaning.

### Step 2 — **Contextual Intent Adjustment**
Uses:
- Graph context  
- Entra identity  
- device context  
- surface metadata  
- continuity metadata  

to refine intent.

### Step 3 — **Canonical Intent Mapping**
Maps user phrasing to canonical intent.

Examples:
- “Can you help me understand this?”  
    → intent: “explain_content”

- “Make this look better”  
    → intent: “improve_formatting”

- “What should I do next?”  
    → intent: “recommend_next_steps”

### Step 4 — **Intent Validation**
Checks for:
- ambiguity  
- missing context  
- identity mismatch  
- surface mismatch  

### Step 5 — **Intent Packaging**
Produces a stable intent package for Goal Decomposition.


###################################################################################################
# 5. CANONICAL INTENT CATEGORIES
###################################################################################################

REID v6.0a uses canonical intent categories across all Microsoft surfaces:

- **summarize_content**  
- **rewrite_content**  
- **explain_content**  
- **improve_formatting**  
- **analyze_data**  
- **visualize_data**  
- **draft_response**  
- **recommend_next_steps**  
- **execute_os_action**  
- **prepare_presentation**  
- **triage_case**  
- **resolve_case**  
- **continue_workflow**  
- **search_information**  
- **generate_content**  
- **correct_errors**  
- **classify_information**  
- **extract_information**  
- **plan_actions**  

These categories ensure consistent reasoning across products.


###################################################################################################
# 6. INTENT NORMALIZATION RULES
###################################################################################################

Intent normalization rules:

1. **Remove ambiguity**  
2. **Remove informal phrasing**  
3. **Remove surface-specific noise**  
4. **Bind identity and context**  
5. **Map to canonical intent**  
6. **Validate against surface**  

Example:

Raw: “Can you fix this thing for me real quick?”  
Normalized: “correct_errors”


###################################################################################################
# 7. INTENT VALIDATION
###################################################################################################

Intent validation checks:

- **Surface compatibility**  
- **Context availability**  
- **Identity continuity**  
- **Ambiguity threshold**  
- **Workflow stage alignment**  

If validation fails:
- substrate re-runs  
- context expands  
- minimal re-inference occurs  


###################################################################################################
# 8. INTENT PACKAGE FORMAT
###################################################################################################

Developers MUST consume:

    intent_package:
        canonical_intent: [string]
        intent_confidence: [0–100]
        ambiguity_score: [0–100]
        context_binding:
            entra: [ids]
            graph: [entities]
            device: [metadata]
            surface: [string]
        continuity_metadata: [optional]

This package is passed to Goal Decomposition.


###################################################################################################
# 9. INTENT CONFIDENCE SCORE
###################################################################################################

Confidence Score ranges:

- **0–20**: Unusable  
- **21–40**: Low confidence  
- **41–60**: Moderate confidence  
- **61–80**: High confidence  
- **81–100**: Very high confidence  

Scores < 41 trigger:
- substrate re-run  
- context expansion  
- minimal re-inference  


###################################################################################################
# 10. HOW INTENT CLASSIFICATION REDUCES COMPUTE COST
###################################################################################################

Intent Classification reduces compute consumption by:

- preventing incorrect model calls  
- reducing model input complexity  
- eliminating unnecessary inference cycles  
- stabilizing identity before inference  
- reducing ambiguity that forces larger models to work harder  
- enabling lightweight models for simple tasks  

Outcome:
- lower GPU-hours per user  
- lower Azure cost  
- faster Copilot responses  
- higher global scalability  


###################################################################################################
# 11. DEVELOPER IMPLEMENTATION CHECKLIST
###################################################################################################

You are correctly integrating Intent Classification when:

[ ] Stabilized meaning is provided  
[ ] Canonical intent is produced  
[ ] Intent confidence is computed  
[ ] Ambiguity Score is validated  
[ ] Context binding is attached  
[ ] Surface compatibility is checked  
[ ] Identity continuity is validated  
[ ] Output is passed to Goal Decomposition  


###################################################################################################
# 12. ERROR MODES (DEVELOPER EDITION)
###################################################################################################

Developers MUST handle:

INTENT_AMBIGUOUS  
    Ambiguity Score ≥ threshold.

INTENT_INVALID  
    Intent incompatible with surface.

INTENT_CONTEXT_MISSING  
    Required context unavailable.

IDENTITY_ANCHOR_LOSS  
    Entra identity missing or corrupted.

INTENT_COLLISION  
    Multiple conflicting intents detected.


###################################################################################################
# 13. SUMMARY
###################################################################################################

This guide provides the minimal architectural and implementation guidance required for Microsoft 
developers to integrate Intent Classification into Copilot, Azure AI Foundry, Microsoft 365, Dynamics, 
Teams, Outlook, and Windows.

It represents the public-safe intent classification boundary of REID v6.0a.
