 # REID v6.0a — Goal Decomposition Developer Guide
Structured Multi-Step Reasoning for Microsoft Developers

This guide explains how REID v6.0a decomposes canonical intent into structured goals. Goal 
Decomposition is the third major reasoning step in the REID cognitive spine and is essential for 
multi-model orchestration, identity continuity, and compute efficiency.


###################################################################################################
# 1. PURPOSE
###################################################################################################

Goal Decomposition solves a core problem:

Intent alone is not actionable.

Examples:
- “Summarize this”
- “Fix this”
- “Analyze this”
- “Make this better”
- “Draft a reply”
- “Explain this”

These intents require multiple steps, often across multiple models.

Without decomposition:
- models guess incorrectly  
- workflows collapse  
- compute cost spikes  
- identity continuity breaks  
- multi-step tasks become inconsistent  

REID v6.0a prevents this by converting intent into structured goals.


###################################################################################################
# 2. GOAL DECOMPOSITION PIPELINE
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

Goal Decomposition is the third active reasoning component.


###################################################################################################
# 3. INPUTS REQUIRED FOR GOAL DECOMPOSITION
###################################################################################################

Developers MUST provide:

    goal_input:
        canonical_intent: [string]
        intent_confidence: [0–100]
        ambiguity_score: [0–100]
        context_binding:
            entra: [ids]
            graph: [entities]
            device: [metadata]
            surface: [string]
        continuity_metadata: [optional]
        completion_arc: [optional]

These inputs come directly from Intent Classification.


###################################################################################################
# 4. GOAL DECOMPOSITION STEPS
###################################################################################################

The Goal Decomposer executes:

### Step 1 — **Goal Pattern Selection**
Selects a decomposition pattern based on canonical intent.

### Step 2 — **Contextual Goal Adjustment**
Uses:
- Graph context  
- Entra identity  
- device context  
- surface metadata  
- continuity metadata  
- completion arc  

to refine goals.

### Step 3 — **Goal Structuring**
Creates:
- atomic goals  
- composite goals  
- parallelizable goals  
- sequential goals  
- conditional goals  

### Step 4 — **Goal Validation**
Checks for:
- context availability  
- identity continuity  
- workflow alignment  
- surface compatibility  

### Step 5 — **Goal Packaging**
Produces a structured goal package for the Orchestration Spine.


###################################################################################################
# 5. CANONICAL GOAL PATTERNS
###################################################################################################

REID v6.0a uses canonical goal patterns across all Microsoft surfaces:

### Pattern: **Summarize Content**
- extract_key_points  
- extract_actions  
- extract_decisions  
- produce_summary

### Pattern: **Rewrite Content**
- identify_meaning  
- identify_tone  
- identify_constraints  
- produce_rewrite

### Pattern: **Explain Content**
- identify_topic  
- identify_confusion_points  
- produce_explanation

### Pattern: **Analyze Data**
- identify_columns  
- identify_patterns  
- identify_anomalies  
- produce_analysis

### Pattern: **Visualize Data**
- identify_chart_type  
- extract_data  
- generate_visual  
- produce_caption

### Pattern: **Draft Response**
- identify_sender_intent  
- identify_required_response  
- generate_draft  
- maintain_tone

### Pattern: **Improve Formatting**
- identify_formatting_issues  
- identify_structure  
- apply_formatting_rules  
- produce_improved_output

### Pattern: **Execute OS Action**
- identify_action  
- validate_permissions  
- execute_action  
- verify_result

### Pattern: **Continue Workflow**
- identify_stage  
- identify_next_steps  
- execute_step  
- update_workflow_state


###################################################################################################
# 6. GOAL STRUCTURE TYPES
###################################################################################################

Goals are structured into:

### **Atomic Goals**
Single-step tasks.

### **Composite Goals**
Multi-step tasks.

### **Parallelizable Goals**
Tasks with no dependencies.

### **Sequential Goals**
Tasks requiring ordering.

### **Conditional Goals**
Tasks requiring branching logic.


###################################################################################################
# 7. GOAL PACKAGE FORMAT
###################################################################################################

Developers MUST consume:

    goal_package:
        goals: [list of structured goals]
        goal_graph: [dependency map]
        parallelizable_groups: [list]
        sequential_groups: [list]
        conditional_branches: [list]
        context_binding:
            entra: [ids]
            graph: [entities]
            device: [metadata]
            surface: [string]
        continuity_metadata: [optional]
        completion_arc: [optional]

This package is passed to the Orchestration Spine.


###################################################################################################
# 8. GOAL GRAPH
###################################################################################################

The Goal Graph defines:

- dependencies  
- ordering  
- parallelization  
- conditional branches  

It is used by the Orchestration Spine to schedule model calls.


###################################################################################################
# 9. HOW GOAL DECOMPOSITION REDUCES COMPUTE COST
###################################################################################################

Goal Decomposition reduces compute consumption by:

- preventing incorrect model calls  
- enabling parallel execution  
- reducing model input complexity  
- eliminating unnecessary inference cycles  
- stabilizing identity before inference  
- enabling lightweight models for simple goals  

Outcome:
- lower GPU-hours per workflow  
- lower Azure cost  
- faster Copilot responses  
- higher global scalability  


###################################################################################################
# 10. DEVELOPER IMPLEMENTATION CHECKLIST
###################################################################################################

You are correctly integrating Goal Decomposition when:

[ ] Canonical intent is provided  
[ ] Goal pattern is selected  
[ ] Goals are structured  
[ ] Goal Graph is generated  
[ ] Parallelizable groups are identified  
[ ] Sequential groups are identified  
[ ] Conditional branches are identified  
[ ] Context binding is attached  
[ ] Output is passed to the Orchestration Spine  


###################################################################################################
# 11. ERROR MODES (DEVELOPER EDITION)
###################################################################################################

Developers MUST handle:

GOAL_AMBIGUOUS  
    Goals unclear or underspecified.

GOAL_INVALID  
    Goals incompatible with surface.

GOAL_CONTEXT_MISSING  
    Required context unavailable.

GOAL_DEPENDENCY_ERROR  
    Invalid dependency graph.

GOAL_COLLISION  
    Conflicting goals detected.


###################################################################################################
# 12. SUMMARY
###################################################################################################

This guide provides the minimal architectural and implementation guidance required for Microsoft 
developers to integrate Goal Decomposition into Copilot, Azure AI Foundry, Microsoft 365, Dynamics, 
Teams, Outlook, and Windows.

It represents the public-safe goal decomposition boundary of REID v6.0a.
