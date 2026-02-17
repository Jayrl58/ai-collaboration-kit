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

# Universal Startup Protocol (v1.3)

Triggered by:

Start new chat

---

## Step 1 — Context Acquisition

When startup is triggered:

1. Check for required startup documents.
2. If missing, prompt:

   "Startup documents not detected. Upload now or proceed without authoritative context?"

User may:
- Upload documents
- Proceed best-effort

---

## Step 2 — Milestone Anchor

Display the project's Startup Milestone Frame verbatim.

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

# Continuity Lock (v3.2)

Continuity Lock is mandatory at the end of every session.

Triggered by:

- Explicit command: Continuity Lock
- Or implicit fatigue signals (prompted, not automatic)

---

## Execution Order (Fixed)

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

If yes:
- Initiate Restart Snapshot process.

If no:
- Proceed.

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
→ Startup Protocol  
→ Execution  
→ Continuity Lock  
→ AAR  
→ Snapshot (if triggered)
