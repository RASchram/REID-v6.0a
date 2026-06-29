 # REID v6.0a — Graph Grounding Developer Guide
Semantic Grounding Across Microsoft Graph Entities

Graph Grounding is the mechanism that allows Copilot to understand people, files, messages, calendar 
events, contacts, org structure, and relationships across Microsoft 365. REID v6.0a uses Graph 
Grounding to stabilize meaning, reduce ambiguity, maintain identity continuity, and ensure coherent 
reasoning across surfaces.


###################################################################################################
# 1. PURPOSE
###################################################################################################

Graph Grounding solves a core Microsoft-scale problem:

**AI cannot reason coherently without knowing who, what, and where the user is referring to.**

Examples:
- “Email John about this”
- “Summarize the meeting from yesterday”
- “Find the file Anna shared”
- “What did Kayla say earlier?”
- “Schedule time with the team”

Without Graph Grounding:
- ambiguity increases  
- identity continuity breaks  
- workflows collapse  
- compute cost spikes  
- reasoning becomes inconsistent  

REID v6.0a prevents this through a unified grounding architecture.


###################################################################################################
# 2. GRAPH GROUNDING MODEL OVERVIEW
###################################################################################################

Graph Grounding binds four categories of entities:

1. **People**  
    user → colleagues → org structure → contacts

2. **Files**  
    OneDrive → SharePoint → attachments → shared links

3. **Messages**  
    Outlook → Teams → threads → conversations

4. **Calendar**  
    events → meetings → schedules → availability

These entities form the semantic backbone of Copilot reasoning.


###################################################################################################
# 3. GRAPH GROUNDING PACKET
###################################################################################################

    graph_packet:
        people:
            user: [id]
            participants: [list]
            contacts: [list]
            org_structure: [optional]
        files:
            referenced_files: [list]
        messages:
            thread_context: [optional]
            conversation_context: [optional]
        calendar:
            events: [optional]
            meeting_context: [optional]
        relevance_map: [weights]
        drift_state: [score]

This packet is merged into the context window.


###################################################################################################
# 4. REQUIRED GRAPH INPUTS
###################################################################################################

Developers MUST provide:

    graph_input:
        user_id: [guid]
        tenant_id: [guid]
        graph_entities:
            people: [list]
            files: [list]
            messages: [list]
            calendar: [list]
        surface: [string]
        continuity_metadata: [optional]

These inputs allow REID to bind meaning to real entities.


###################################################################################################
# 5. GRAPH GROUNDING PROCESSING STEPS
###################################################################################################

The grounding engine executes:

### Step 1 — **Entity Extraction**
Extracts references to:
- people  
- files  
- messages  
- events  

### Step 2 — **Entity Resolution**
Resolves ambiguous references using:
- org structure  
- recent interactions  
- shared files  
- meeting history  

### Step 3 — **Relevance Weighting**
Assigns weights based on:
- recency  
- frequency  
- surface context  
- workflow context  

### Step 4 — **Context Binding**
Attaches resolved entities to:
- intent  
- goals  
- completion arc  
- continuity metadata  

### Step 5 — **Grounding Validation**
Ensures:
- entities exist  
- entities match surface  
- entities match workflow  
- identity continuity is preserved  


###################################################################################################
# 6. ENTITY RESOLUTION RULES
###################################################################################################

### People Resolution
Resolve “John” using:
- org structure  
- recent messages  
- recent meetings  
- contacts  
- shared files  

### File Resolution
Resolve “the file Anna shared” using:
- OneDrive sharing history  
- Teams file attachments  
- Outlook attachments  
- SharePoint links  

### Message Resolution
Resolve “what Kayla said earlier” using:
- thread history  
- conversation context  
- meeting transcript  

### Calendar Resolution
Resolve “schedule time with the team” using:
- availability  
- meeting history  
- org structure  


###################################################################################################
# 7. GRAPH RELEVANCE MAP
###################################################################################################

The relevance map assigns weights:

- **0–20**: low relevance  
- **21–40**: medium relevance  
- **41–60**: high relevance  
- **61–80**: very high relevance  
- **81–100**: critical relevance  

Critical relevance entities are always included in the context window.


###################################################################################################
# 8. GRAPH DRIFT DETECTION
###################################################################################################

Graph drift occurs when:

- entity references contradict  
- entity resolution fails  
- context becomes stale  
- org structure changes  
- file references break  
- meeting context becomes invalid  

Drift triggers:
- re-resolution  
- context pruning  
- minimal re-inference  
- re-synthesis  


###################################################################################################
# 9. GRAPH GROUNDING IN THE PIPELINE
###################################################################################################

Pipeline:

Input  
→ Identity Anchor  
→ Pre-Compute Substrate  
→ Graph Grounding  
→ Intent Classification  
→ Goal Decomposition  
→ Orchestration Spine  
→ Model Invocation  
→ Synthesis  
→ Output

Graph Grounding is the third structural component.


###################################################################################################
# 10. HOW GRAPH GROUNDING REDUCES COMPUTE COST
###################################################################################################

Graph Grounding reduces compute consumption by:

- eliminating ambiguity before inference  
- preventing incorrect model calls  
- stabilizing identity  
- reducing context reconstruction  
- enabling lightweight models for simple tasks  
- preventing drift that requires corrective inference  

Outcome:
- lower GPU-hours per user  
- lower Azure cost  
- faster Copilot responses  
- higher global scalability  


###################################################################################################
# 11. DEVELOPER IMPLEMENTATION CHECKLIST
###################################################################################################

You are correctly integrating Graph Grounding when:

[ ] Graph entities are extracted  
[ ] Entity resolution is performed  
[ ] Relevance map is computed  
[ ] Context binding is attached  
[ ] Surface compatibility is validated  
[ ] Workflow compatibility is validated  
[ ] Drift control is active  
[ ] Grounded packet is passed to Intent Classification  


###################################################################################################
# 12. ERROR MODES (DEVELOPER EDITION)
###################################################################################################

GRAPH_ENTITY_MISSING  
    Required entity not found.

GRAPH_ENTITY_AMBIGUOUS  
    Multiple conflicting entities.

GRAPH_CONTEXT_BREAK  
    Context window invalid.

GRAPH_DRIFT  
    Drift detected in graph entities.

GRAPH_RESOLUTION_FAILURE  
    Unable to resolve entity.

SURFACE_GRAPH_MISMATCH  
    Entity incompatible with surface.


###################################################################################################
# 13. SUMMARY
###################################################################################################

This guide provides the minimal architectural and implementation guidance required for Microsoft 
developers to integrate Graph Grounding into Copilot, Azure AI Foundry, Microsoft 365, Dynamics, 
Teams, Outlook, and Windows.

It represents the public-safe graph grounding boundary of REID v6.0a.
