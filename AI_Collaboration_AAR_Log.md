# AI Collaboration --- After-Action Review (AAR) Log

Purpose:

Capture friction, improvements, and calibration signals from sessions.

This document stores raw collaboration observations.

Stable improvements are later extracted into: -
Working_Preferences_Generalized.md - AI_Collaboration_Lifecycle.md -
Command_Glossary.md

------------------------------------------------------------------------

# Entries

## Session: AI Collaboration --- 2026-02-16

Friction Observed: - None significant.

What Worked Well: - Separating global collaboration doctrine into a
dedicated public repository clarified authority boundaries and reduced
cross-project coupling. - The Version Channel model (`stable` tag)
balanced control and maintainability better than strict pinning or
floating `main`.

Calibration Adjustment Suggested: - Test Startup Protocol end-to-end
using LMR before freezing or snapshotting the collaboration kit.

Action Required: - Yes (Operational validation required before lifecycle
snapshot).

------------------------------------------------------------------------

## Session: AI Collaboration --- 2026-02-17 (Lifecycle Iteration Review)

What happened: We spent roughly 12 iterations trying to make startup
behave deterministically using lifecycle and startup document
enforcement. We kept tightening the same mechanism (documents and
flags), but the behavior did not fully comply.

We eventually shifted to a gated, step-by-step model, which is more
stable --- but it took too long to get there.

Friction: We stayed too long inside one approach before stepping back
and rethinking the architecture.

It felt like we were trying to force the model to behave like a
deterministic state machine, when that may not be the right abstraction
layer.

The iteration count was too high for the complexity of the goal.

Insight: When something does not work after a couple of attempts, it is
probably not a wording problem --- it is a structural problem.

The faster move would have been: - Step back earlier - Present 2--3
architectural alternatives - Force a branch decision - Move forward
decisively

Calibration for Future Sessions: Adopt a pivot checkpoint: if two
refinements of the same mechanism do not materially improve behavior,
pause and reassess the abstraction layer before continuing.

Additional Process Improvement Identified: When generating replacement
files for download, preserve the original filename and extension
exactly. Changing file extensions creates unnecessary friction and adds
manual cleanup steps during commit workflows.

Action Required: - Yes --- adopt earlier abstraction review when
convergence stalls. - Yes --- preserve exact filenames and extensions
when generating downloadable replacements.
