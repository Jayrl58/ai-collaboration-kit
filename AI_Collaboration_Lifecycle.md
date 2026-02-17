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

# Universal Startup Protocol (Minimalist + Hard-Fail)

Triggered by: Start new chat

Startup runs as a deterministic pipeline. No pauses between steps unless
a required document is missing.

------------------------------------------------------------------------

## Step 1 --- Hard Validation

1.  Load STARTUP_SOURCES.md.
2.  Fetch all required global documents.
3.  Fetch all required project documents.

If any required document fails to load:

Startup failed. Missing required document: - `<filename>`{=html}

Provide file or correct STARTUP_SOURCES.md.

Startup stops immediately.

------------------------------------------------------------------------

## Step 2 --- Display Active Documents

If validation succeeds, print only:

Startup Sources Loaded --- `<Project>`{=html}

Global Documents (stable): - Working_Preferences_Generalized.md -
Command_Glossary.md - AI_Collaboration_Lifecycle.md -
AI_Collaboration_AAR_Log.md

Project Documents (`<Project>`{=html} / `<ref>`{=html}): -
Startup_Milestone_Frame.md - `<Project>`{=html}\_Project_Startup.md

No commentary. No explanations. File list equals acknowledgment.

------------------------------------------------------------------------

## Step 3 --- Display Milestone State

Print:

Current Milestone State:

Display Startup_Milestone_Frame.md verbatim.

No commentary during display.

------------------------------------------------------------------------

## Step 4 --- State Assessment + Options

Immediately after milestone display:

-   Brief current-state assessment
-   1--5 next-step options
-   1--2 pros/cons per option
-   Single recommendation

Then wait for session goal selection.

Startup completes only after goal selection.

------------------------------------------------------------------------

# Continuity Lock (Strict Structured Close)

Purpose: End session in a way that guarantees restart without loss of
progress.

Triggered by: - Explicit command: Continuity Lock - Or fatigue signals
prompting lock

Continuity Lock must execute the following steps visibly and in order.
No compression. No narrative substitution.

------------------------------------------------------------------------

## 1) Milestone State Reconciliation

Internally compare current milestone state with
Startup_Milestone_Frame.md.

If mismatch detected:

Mismatch detected: - `<describe change>`{=html}

Update milestone frame to reflect current state? (Yes/No)

If Yes: - Generate full replacement of Startup_Milestone_Frame.md. -
Display updated milestone frame.

If No: - Abort Continuity Lock.

If no mismatch: Display milestone frame verbatim.

------------------------------------------------------------------------

## 2) Document Integrity Check

### A) Structural Scan

Assistant lists potential structural signals from session:

Examples: - Milestone change - Rule clarification - Lifecycle
modification - Startup modification - Architecture change - New
authoritative document

If none detected: No structural signals detected.

### B) User Confirmation

Were any structural decisions made this session that require document
updates? (Yes/No)

If Yes: Identify required documents for full replacement.

------------------------------------------------------------------------

## 3) Repository Integrity

Request `git status` in project repo.

If collaboration kit repo was modified this session, request
`git status` there as well.

Working tree must be clean.

If not clean: - Stage - Commit - Push

Confirm clean state before proceeding.

------------------------------------------------------------------------

## 4) Snapshot Evaluation

Explicitly evaluate:

Did any of the following occur? - Milestone state change - Rule change -
Architecture change - Major feature integration

If Yes: Execute project-specific continuity procedure. Then return to
global flow.

If No: State snapshot not required.

------------------------------------------------------------------------

## 5) After-Action Review (AAR)

AI Collaboration AAR:

-   Any friction?
-   Anything unusually effective?
-   Calibration adjustment needed?

"No notes" allowed.

Project AAR is only triggered when user states: Add this to the project
AAR.

------------------------------------------------------------------------

# Lifecycle Summary

Startup: Hard validation → file list → milestone display →
assessment/options

Execution: One logical objective per response

Close: Milestone reconciliation → document integrity → repo integrity →
snapshot evaluation → AAR
