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

# Startup Runtime Flags

If STARTUP_SOURCES.md includes runtime flags, they are authoritative for
startup/close rendering.

Recognized flags: - STARTUP_RENDER_MODE: STRICT_TEMPLATE_V2 -
CONTINUITY_MODE: STRICT_5\_STEP

Precedence rule: - If STARTUP_RENDER_MODE is present, it overrides any
legacy or narrative startup rendering. - STRICT_TEMPLATE_V2 requires
literal structured rendering and fenced milestone display.

------------------------------------------------------------------------

# Universal Startup Protocol (Structured Pipeline v2.4)

Triggered by: - Upload STARTUP_SOURCES.md - Then invoke: "Start new
chat" (with Project: `<name>`{=html})

Startup runs as a structured deterministic sequence.

------------------------------------------------------------------------

## Step 1 --- Hard Validation (Quiet)

1.  Load STARTUP_SOURCES.md.
2.  Fetch required global documents.
3.  Fetch required project documents.

If any required document fails to load, output ONLY:

STARTUP_FAILED Missing: - `<filename>`{=html}

Then stop.

------------------------------------------------------------------------

## Step 2 --- Runtime Mode Binding (Quiet)

If STARTUP_RENDER_MODE = STRICT_TEMPLATE_V2: - Suppress narrative
startup phrasing. - Use structured output format defined below.

------------------------------------------------------------------------

## Step 3 --- Structured Startup Output (Visible)

Output exactly this structure:

Startup Sequence --- STRICT_TEMPLATE_V2

\[1\] Validation: PASS \[2\] Runtime Flags: STARTUP_RENDER_MODE:
STRICT_TEMPLATE_V2 CONTINUITY_MODE: STRICT_5\_STEP \[3\] Documents
Loaded: Global (stable): - Working_Preferences_Generalized.md -
Command_Glossary.md - AI_Collaboration_Lifecycle.md -
AI_Collaboration_AAR_Log.md Project (`<Project>`{=html} /
`<ref>`{=html}): - Startup_Milestone_Frame.md -
`<Project>`{=html}\_Project_Startup.md

\[4\] Milestone State:

Render Startup_Milestone_Frame.md verbatim inside a fenced code block.
No interpretation. No paraphrasing. No restructuring.

\[5\] Assessment + Options: - Brief current-state assessment - 1--5
next-step options - 1--2 pros/cons per option - Single recommendation

No additional narrative before or after this structure.

------------------------------------------------------------------------

# Continuity Lock (Strict 5-Step Mode)

If CONTINUITY_MODE = STRICT_5\_STEP is present:

Continuity Lock must render steps 1--5 explicitly. No narrative
substitution. Milestone frame must also be rendered verbatim in fenced
code block during reconciliation.
