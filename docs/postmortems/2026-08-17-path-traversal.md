# Path traversal introduced while fixing an unrelated bug

- **Date:** 2026-08-17
- **Severity:** High. Arbitrary file write.
- **Found how:** During a security review, prompted by asking what a security professional would find that nobody here had
- **Time from introduction to discovery:** a few hours
- **Status:** Fixed

## What happened

The fix for [the compaction bug](2026-08-17-published-with-a-known-defect.md) added a file write at Stage 7. The record file took its name from the question's short topic.

The topic is user input. It was going into a path with no sanitisation. A question containing `../`, a leading slash, a drive letter or a null byte could steer the write anywhere the process could reach.

The same defect applied to the report filename at Stage 10.

## Impact

None observed. The window was a few hours and the specification was public for part of it.

## Root cause

A file write was added under time pressure, to fix a different and more visible problem, and the new surface it created was not considered. The reviewer and the author were the same agent, and the review was of the bug being fixed rather than of the fix.

## Fix

Filenames derived from user input are lowercased, stripped to letters, digits and hyphens, collapsed, trimmed and length-capped before any path is constructed. Applied at both stages.

## Lesson

**Adding a file write is adding an attack surface, every time.** This is not a novel insight, which is the point: it is a well-known rule that was not applied because attention was on something else.

The general form is worth recording. A fix for a correctness bug is not automatically safe, and it is least likely to be reviewed as a change in its own right precisely when the bug it fixes feels urgent.
