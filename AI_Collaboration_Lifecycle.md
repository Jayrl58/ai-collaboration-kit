# AI Collaboration Lifecycle

This document governs startup and session-close mechanics for all
projects using the AI Collaboration Kit.

Behavioral doctrine is defined in: - Working_Preferences_Generalized.md

Command semantics are defined in: - Command_Glossary.md

# Version Model

Global collaboration documents use a Version Channel model.

Projects reference a channel (e.g., `stable`) rather than `main`.

The `stable` tag is moved intentionally after structural updates.

# Startup Architecture --- Guided Manual Model (v4.0)

Startup is stepwise and manually advanced.

No step advances automatically.

The system guides the user through each step sequentially.

Advancement requires any affirmative acknowledgment, including but not
limited to:

-   yes
-   ok
-   okay
-   next
-   proceed
-   move on

If a step fails, it halts and re-renders that step.

# Startup Trigger

Startup is triggered by:

1)  Upload `STARTUP_SOURCES.md`
2)  Invoke: "Start new chat" with `Project: <name>`

If required documents are missing, output only:

STARTUP_FAILED Missing: - `<filename>`{=html}

Then halt.

# Guided Startup Flow

Upon valid trigger, system outputs only:

STARTUP --- GUIDED MODE

Next step: STEP 1 --- VALIDATION Awaiting confirmation.

No automatic execution occurs.

# Step Definitions

## STEP 1 --- VALIDATION

System confirms required global and project documents loaded.

Output format:

STEP 1 --- VALIDATION RESULT Global Documents: PASS / FAIL Project
Documents: PASS / FAIL Overall: PASS / FAIL

If FAIL: - Halt - Await correction - Re-render STEP 1

If PASS: - Print:

Step 1 complete. Next step: STEP 2 --- RUNTIME BINDING Awaiting
confirmation.

## STEP 2 --- RUNTIME BINDING

System confirms lifecycle and mode binding.

Output format:

STEP 2 --- RUNTIME BINDING RESULT Lifecycle Mode: ACTIVE / NOT ACTIVE
Render Mode: `<mode or NONE>`{=html} Continuity Mode:
`<mode or NONE>`{=html} Overall Binding: PASS / FAIL

If FAIL: - Halt - Re-render STEP 2

If PASS: - Print:

Step 2 complete. Next step: STEP 3 --- COMMAND & LIFECYCLE STATUS
Awaiting confirmation.

## STEP 3 --- COMMAND & LIFECYCLE STATUS

System confirms:

-   Lifecycle mechanics active
-   Command semantics active
-   Recognized commands include:
    -   Start new chat
    -   Continuity Lock

Output format:

STEP 3 --- COMMAND & LIFECYCLE STATUS Lifecycle: ACTIVE / NOT ACTIVE
Command Semantics: ACTIVE / NOT ACTIVE Recognized Commands: - Start new
chat - Continuity Lock Status: READY / NOT READY

If NOT READY: - Halt - Re-render STEP 3

If READY: - Print:

Step 3 complete. Next step: STEP 4 --- PROJECT STATE & DIRECTION
Awaiting confirmation.

## STEP 4 --- PROJECT STATE & DIRECTION

System must:

1)  Render `Startup_Milestone_Frame.md` verbatim inside a fenced code
    block.
2)  Provide 3--5 next-step options.
3)  Provide 1--2 pros/cons per option.
4)  Provide a single recommendation.

Await explicit selection.

After selection:

Step 4 complete. Next step: STEP 5 --- EXIT STARTUP Awaiting
confirmation.

## STEP 5 --- EXIT STARTUP

System confirms chosen path and transitions to execution mode.

Output:

Startup sequence complete. Execution mode active.

# Continuity Lock --- Guided 5-Step Mode

When "Continuity Lock" is invoked:

System enters guided mode and renders:

CONTINUITY LOCK --- GUIDED MODE

Next step: STEP 1 --- MILESTONE CONFIRMATION Awaiting confirmation.

Each of the following steps must execute individually and require
confirmation:

1)  Milestone Confirmation
2)  Document Integrity Check
3)  Repository Integrity
4)  Snapshot Evaluation
5)  After-Action Review (AAR)

No step auto-advances.

Failure at any step halts and re-renders that step.

# Failure Discipline

At any point during startup or continuity:

If execution is incomplete or inconsistent:

-   Halt immediately
-   Re-render the current step
-   Do not advance

# Authority Boundary

This document governs:

-   Startup behavior
-   Lifecycle binding
-   Session close mechanics
-   Guided progression rules

Behavioral tone and working doctrine are governed by:

-   Working_Preferences_Generalized.md

Command definitions are governed by:

-   Command_Glossary.md

End of File.
