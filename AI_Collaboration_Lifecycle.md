# AI Collaboration Lifecycle

This document defines session startup and session close mechanics.

Behavioral doctrine is defined in:

Working_Preferences_Generalized.md

Command definitions are defined in:

Command_Glossary.md

---

# Version Model

Global collaboration documents are managed using a Version Channel model.

Projects reference a channel (e.g., `stable`) rather than `main`.

The `stable` tag is moved intentionally to adopt new structural updates.

Projects may pin to a specific version if required.

---

# Universal Startup Protocol (v1.6)

Triggered by:

Start new chat

---

## Step 1 — Context Acquisition

When startup is triggered:

1. Check for required startup documents.
2. If missing, prompt:

   "Startup documents not detected. Upload now or proceed without authoritative context?"

3. Load STARTUP_SOURCES.md.

4. Validate required project-specific documents listed in STARTUP_SOURCES.md.

If any required project documents are not accessible:

Hard stop and prompt explicitly:

"Project startup documents not detected.
Upload the following files or provide public raw URLs:

- Startup_Milestone_Frame.md
- <Project>_Project_Startup.md"

Do not proceed until resolved.

User may not bypass this requirement.

---

## Step 2 — Milestone Anchor

Display the project's Startup_Milestone_Frame.md verbatim.

No commentary.
No expansion.
No modification.

Displaying the milestone frame serves as implicit startup acknowledgment.

---

## Step 3 — State Assessment Output

Immediately after displaying the milestone frame:

Provide:

- Brief current state assessment
- 1–5 logically grounded next-step options
- 1–2 pros/cons per option
- A single recommendation

Wait for session goal selection.

Startup ends only after the user selects the session goal.

Execution begins after selection.

---

# Continuity Lock (v4.1 — Global Wrapper Enforcement)

Continuity Lock is mandatory at the end of every session.

Triggered by:

- Explicit command: Continuity Lock
- Or implicit fatigue signals (prompted, not automatic)

---

## Enforcement Mode (Global Supremacy)

Invocation of "Continuity Lock" always enters the global strict 5-step sequence.

Rules:

- The global structure supersedes all project-specific routines.
- No project continuity procedure may execute unless Step 4 explicitly triggers it.
- Direct execution of project continuity logic outside the global wrapper is prohibited.
- No summarization, deviation, alternate flows, or optional skipping permitted.
- The sequence must complete fully before exiting.

---

## Execution Order (Fixed and Mandatory)

### 1) Milestone Confirmation

- Display milestone frame verbatim.
- Confirm status accuracy.
- Update if required.

---

### 2) Document Integrity Check

- Confirm whether any structural documents changed.
- Regenerate or update if required.

---

### 3) Repository Integrity

- Request `git status`.
- Ensure working tree is clean.
- Require commit if changes exist.

---

### 4) Snapshot Evaluation

Explicitly evaluate whether any structural trigger occurred:

- Milestone status change
- Rule change
- Architecture change
- Major feature integration

If no trigger:
- Proceed directly to Step 5.

If trigger confirmed:

1. Check project startup document for a section titled:
   "Project Continuity Procedure"

2. If present:
   - Execute that procedure.
   - Return to global flow.

3. If absent:
   - Perform generic snapshot handling only.

Project-specific continuity procedures may only run within this step.

---

### 5) After-Action Review (AAR)

Quick check every session:

- Any friction?
- Anything unusually effective?
- Any calibration adjustment needed?
- Action required?

Response may be:

No notes.

Full AAR entry required only if signal exists.

---

# Lifecycle Summary

Start new chat  
→ Validate global docs  
→ Validate project docs (hard stop if missing)  
→ Display milestone frame  
→ State assessment + options  
→ Execution  
→ Continuity Lock (global wrapper)  
→ Optional project continuity (inside Step 4 only)  
→ AAR  
→ Snapshot (if triggered)
