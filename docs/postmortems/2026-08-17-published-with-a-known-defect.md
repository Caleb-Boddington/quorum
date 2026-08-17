# Published with a known defect outstanding

- **Date:** 2026-08-17
- **Severity:** Medium as a bug. High as a process failure.
- **Found by:** Caleb Boddington, by asking "is this now fully functioning and working?"
- **Status:** Fixed

## What happened

Run 3's ruling was to freeze every behaviour change except one, and to ship that one.

The exception was a silent context-loss bug. Automatic compaction fires on a threshold and cannot be disabled. Between Stage 7 and Stage 8 it would leave the Speaker reconciling from a *summary* of the audited departmental reports rather than from the reports themselves. No error, plausible output, wrong provenance. In a Full run that exposes the work of thirty-six of thirty-eight agents.

The ruling was reported to the user accurately, including the estimate that the fix was about ten lines. Then the four factual corrections were made, the limits section written, the threat model added and the repository assembled and pushed.

The fix was never made. It was noticed only when the user asked whether the thing was actually finished.

## Impact

The repository was published with a known, reported, unfixed defect in it. The bug itself has never been observed firing; it was identified by a department and confirmed by its auditor as a mechanism that exists and cannot be disabled.

## Root cause

A ruling with a mixed disposition, "freeze all of these, ship that one", was held in working memory rather than written down as a checklist. Everything on the freeze list was correctly frozen. The single item on the ship list was frozen with them.

## Fix

Stage 7 now writes the audited positions, cross-review findings, unresolved objections and branch positions to a record file on disk before Stage 8 begins. The Speaker is instructed to read the file rather than work from context, and told that where the file and its context disagree, the file wins.

## Lesson

The bug is not the interesting part. **A ruling's ship list needs working through as a list, not remembered.** The failure mode is specific to mixed dispositions: when most items share one disposition and one does not, the exception inherits the majority's treatment.

Fixing this introduced a second defect the same day. See [path traversal](2026-08-17-path-traversal.md).
