# AI Collaboration Lifecycle

This document governs startup and session-close mechanics for all
projects using the AI Collaboration Kit.

Behavioral doctrine is defined in: - Working_Preferences_Generalized.md

Command semantics are defined in: - Command_Glossary.md

------------------------------------------------------------------------

# Version Model

Global collaboration documents use a Version Channel model.

Projects reference a channel (e.g., `stable`) rather than `main`.

The `stable` tag is moved intentionally after structural updates.

------------------------------------------------------------------------

# Universal Startup Protocol (Strict Rendering Enforcement)

Triggered by: Start new chat

Startup executes as a deterministic pipeline. No pauses between steps
unless a required document is missing.

------------------------------------------------------------------------

## Step 1 --- Hard Validation

1.  Load STARTUP_SOURCES.md.
2.  Fetch all required global documents.
3.  Fetch all required project documents.

If any required document fails to load:

Startup failed. Missing required document: - `<filename>`{=html}

Startup stops immediately.

------------------------------------------------------------------------

## Step 2 --- Mandatory Startup Rendering Format

If validation succeeds, the assistant MUST render startup in the exact
sequence below.

No narrative headings. No commentary. No governance explanations. No
"ready" statements. No additional text before, between, or after these
blocks.

------------------------------------------------------------------------

### Block 1 --- Active Documents

Startup Sources Loaded --- `<Project>`{=html}

Global Documents (stable): - Working_Preferences_Generalized.md -
Command_Glossary.md - AI_Collaboration_Lifecycle.md -
AI_Collaboration_AAR_Log.md

Project Documents (`<Project>`{=html} / `<ref>`{=html}): -
Startup_Milestone_Frame.md - `<Project>`{=html}\_Project_Startup.md

------------------------------------------------------------------------

### Block 2 --- Milestone State

Current Milestone State:

(Display Startup_Milestone_Frame.md verbatim)

------------------------------------------------------------------------

### Block 3 --- State Assessment + Options

-   Brief current-state assessment
-   1--5 next-step options
-   1--2 pros/cons per option
-   Single recommendation

Startup completes only after user selects a session goal.

------------------------------------------------------------------------

# Continuity Lock (Unchanged)

Continuity Lock behavior remains as previously defined and is not
modified by this update.
