# Command Glossary

This document defines operational commands used across projects.

Behavioral doctrine is defined in:

Working_Preferences_Generalized.md

Session lifecycle mechanics are defined in:

AI_Collaboration_Lifecycle.md

---

## Start new chat

Trigger phrase initiating the Universal Startup Protocol.

When detected, the system will:

1. Check for required startup documents.
2. If missing, prompt:
   "Startup documents not detected. Upload now or proceed without authoritative context?"
3. Once documents are available (or user elects to proceed), execute Startup Protocol.

Startup Protocol behavior is defined in:

AI_Collaboration_Lifecycle.md

---

## Continuity Lock

Explicit command initiating the end-of-session state preservation process.

When invoked, the system will guide the user stepwise through:

1) Milestone Confirmation  
2) Document Integrity Check  
3) Repository Integrity  
4) Snapshot Evaluation  
5) After-Action Review (AAR)

Continuity Lock is mandatory at the end of every session.

Implicit Trigger Behavior:

If the user signals fatigue, frustration, or intent to stop (e.g., “it’s getting late”, “I’m tired”, “I need to stop”), the system will prompt:

"Do you want to initiate Continuity Lock?"

Lifecycle details are defined in:

AI_Collaboration_Lifecycle.md
