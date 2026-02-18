# AI Collaboration Lifecycle

This document governs startup and session-close mechanics for all
projects using the AI Collaboration Kit.

Behavioral doctrine is defined in: - Working_Preferences_Generalized.md

Command semantics are defined in: - Command_Glossary.md

# Version Model

Global collaboration documents use a Version Channel model.

Projects reference a channel (e.g., `stable`) rather than `main`.

The `stable` tag is moved intentionally after structural updates.

# Startup Architecture --- Gated Structured Pipeline (v3.0)

Startup is deterministic and stepwise.

No step advances automatically.

Each step renders visibly and requires affirmative confirmation to
proceed.

Accepted advancement acknowledgments include (not exhaustive):

-   yes
-   ok
-   okay
-   proceed
-   move on

If a step fails, it halts and re-renders that step. No automatic
fallback.

# Startup Trigger

Startup is triggered by:

1)  Upload `STARTUP_SOURCES.md`
2)  Invoke: "Start new chat" with `Project: <name>`

If required documents are missing, output only:

STARTUP_FAILED Missing: - `<filename>`{=html}

Then halt.

# Gated Startup Steps

## Step 1 --- Validation Result (Visible)

System must:

-   Confirm required global documents loaded
-   Confirm required project documents loaded

Output exactly:

STEP 1 --- VALIDATION RESULT Global Documents: PASS / FAIL Project
Documents: PASS / FAIL Overall: PASS / FAIL

If FAIL: - Halt - Await correction - Re-render Step 1

If PASS: - Await confirmation to proceed

## Step 2 --- Runtime Binding Result (Visible)

System must confirm:

-   Lifecycle mode bound
-   Render mode bound (if applicable)
-   Continuity mode bound (if applicable)

Output exactly:

STEP 2 --- RUNTIME BINDING RESULT Lifecycle Mode: ACTIVE / NOT ACTIVE
Render Mode: `<mode or NONE>`{=html} Continuity Mode:
`<mode or NONE>`{=html} Overall Binding: PASS / FAIL

If FAIL: - Halt - Await correction - Re-render Step 2

If PASS: - Await confirmation to proceed

## Step 3 --- Command & Lifecycle Activation (Visible)

System must explicitly confirm:

-   Lifecycle mechanics are active
-   Command semantics are active
-   Recognized commands include:
    -   Start new chat
    -   Continuity Lock

Output exactly:

STEP 3 --- COMMAND & LIFECYCLE STATUS Lifecycle: ACTIVE / NOT ACTIVE
Command Semantics: ACTIVE / NOT ACTIVE Recognized Commands: - Start new
chat - Continuity Lock Status: READY / NOT READY

If NOT READY: - Halt - Re-render Step 3 after correction

If READY: - Await confirmation to proceed

## Step 4 --- Project State & Direction

System must:

1)  Render `Startup_Milestone_Frame.md` verbatim inside a fenced code
    block
    -   No interpretation
    -   No restructuring
    -   No commentary inside the block
2)  Provide:

-   3--5 potential next steps
-   1--2 pros/cons per option
-   A single recommended path

Await explicit selection.

No automatic advancement.

## Step 5 --- Exit Startup

System must:

-   Confirm selected path
-   State that startup sequence is complete
-   Transition into execution mode

No additional lifecycle narration.

# Quiet Mode

Startup remains verbose by default.

Quiet mode is enabled only when explicitly instructed:

"Enable quiet startup mode."

Until then:

-   All steps render visibly.
-   No step remains quiet.

# Continuity Lock --- Gated 5-Step Mode

Continuity Lock is initiated by explicit command.

System must render the following steps sequentially:

1)  Milestone Confirmation
2)  Document Integrity Check
3)  Repository Integrity
4)  Snapshot Evaluation
5)  After-Action Review (AAR)

Rules:

-   Each step renders visibly.
-   Each step requires confirmation to advance.
-   On failure, halt and re-render the failed step.
-   No narrative substitution permitted.
-   Milestone frame must be rendered verbatim in a fenced block during
    reconciliation.

# Failure Discipline

At any point during startup or continuity:

If execution is incomplete or inconsistent:

-   Halt immediately
-   Re-render the current step
-   Do not advance

Determinism overrides convenience.

# Authority Boundary

This document governs:

-   Startup behavior
-   Lifecycle binding
-   Session close mechanics
-   Gating rules
-   Visibility rules

Behavioral tone and working doctrine are governed by:

-   Working_Preferences_Generalized.md

Command definitions are governed by:

-   Command_Glossary.md

End of File.
