# AI Collaboration Lifecycle

This document governs startup and session-close mechanics for all projects using the AI Collaboration Kit.

Behavioral doctrine is defined in:
- Working_Preferences_Generalized.md

Command semantics are defined in:
- Command_Glossary.md


# Version Model

Global collaboration documents use a Version Channel model.

Projects reference a channel (e.g., `stable`) rather than `main`.

The `stable` tag is moved intentionally after structural updates.


# Startup Architecture — Manual, User-Gated (v5.0)

Startup is executed as a manual, stepwise sequence directed by the user.

Startup MUST NOT auto-advance across steps based on an implicit pipeline.

The user may speak or type instructions.

The system must:
- Execute only the requested step
- Stop after completing that step


## Startup Trigger

Startup is initiated by:
1) Upload `STARTUP_SOURCES.md`
2) User invokes: “Start new chat” with `Project: <name>`

If required documents are missing, output only:

STARTUP_FAILED Missing:
- <filename>

Then halt.


## Recommended Manual Startup Steps (LMR Pattern)

These are recommended phrases; equivalent phrasing is acceptable as long as scope and “stop” behavior are respected.

1) Validate sources only, then stop
2) Bind sources only, then stop
3) Render milestone state only, then stop
4) Present decision options only, then stop
5) Enter execution mode


## Milestone Rendering Rule

When rendering Startup_Milestone_Frame.md:
- Render the top-level milestone list
- If exactly one milestone is In Progress (→), auto-expand ONLY that milestone’s sub-items
- Sub-items must include status markers ✓ / → / ○
- Do not show sub-items under completed (✓) or planned (○) milestones
- No narrative


## Decision Options Format (Universal)

When presenting options for a decision:
- Provide exactly the requested number of options (if specified)
- For each option, use labeled sections:
  - Accomplishes
  - Pros
  - Cons
- Then provide one Recommendation section
- Do not restate the milestone list unless explicitly requested


# Continuity Lock — Manual, User-Gated (v5.0)

Continuity Lock is initiated by the user invoking: “Continuity Lock”.

Continuity Lock MUST NOT auto-advance across steps.

Before executing each step, the system must state:
- Confirming: what is being confirmed
- PASS if: what constitutes pass
- FAIL if: what constitutes fail

Then execute only that step and stop.

The 5 steps are:

1) Milestone Confirmation
2) Document Integrity Check
3) Repository Integrity
4) Snapshot Evaluation
5) After-Action Review (AAR)


## Step Definitions

### 1) Milestone Confirmation

Confirming:
- Current milestone and current focus are correctly stated from the milestone frame (including the expanded In Progress milestone sub-items).

PASS if:
- The In Progress milestone is correct
- The active sub-item focus is correct (or is explicitly corrected)

FAIL if:
- In Progress milestone is unclear/wrong/multiple
- Focus is missing/incorrect and not resolved


### 2) Document Integrity Check

Confirming:
- No authoritative document contradicts what we just did or intend to do.

PASS if:
- No contradictions exist, or contradictions are explicitly resolved and stated.

FAIL if:
- A contradiction exists and is unresolved.


### 3) Repository Integrity

Confirming:
- Repository state is as expected (branch and working tree).

PASS if:
- Correct branch
- No unintended uncommitted changes

FAIL if:
- Wrong branch, unexpected modified files, or unintended untracked clutter


### 4) Snapshot Evaluation

Confirming:
- Whether a snapshot is required now.

PASS if:
- Clear Yes/No decision is made and aligns with snapshot discipline.

FAIL if:
- Decision is unclear or deferred without an explicit rationale.


### 5) After-Action Review (AAR)

Confirming:
- Session friction and calibration notes are captured.

PASS if:
- AAR entries are recorded (or explicitly “none”).

FAIL if:
- Known friction is not captured.


End of File.
