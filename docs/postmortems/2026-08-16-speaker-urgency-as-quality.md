# The Speaker treated urgency as a proxy for quality

- **Date:** 2026-08-16
- **Severity:** High. The verdict sent the user at the worst available option.
- **Found how:** After the run closed, by asking for the underlying list the department had summarised
- **Status:** Fixed

## What happened

Run 1's verdict ended with a "first move": apply to the option with the nearest closing date.

Pulling the actual list afterwards showed that option was the worst of fifteen on every measure except urgency. It paid the least, it was in a different location from the one the run had assumed, and the Comptroller had already flagged that location discrepancy earlier in the same report. A materially better option, with three weeks still to run, sat in the same dataset a department had already queried.

## Impact

The user would have acted on it. The verdict was persuasive, internally consistent, and pointed at the wrong thing.

## Root cause

Two failures compounding.

**The department reported a summary instead of the data.** It gave a count and a price range and a closing window. It never returned the individual rows. So the Speaker could see spread and deadline, and nothing else.

**The Speaker optimised the only variable it could see.** Given a deadline and no quality signal, it treated the deadline as the ranking. That is not unreasonable behaviour for an agent holding only one dimension; it is a consequence of what it was handed.

## Fix

Two changes, at different stages.

At Stage 4: if a department's position rests on a set of specific items, it must name them individually. A range, a count or an average is a description of evidence, not the evidence.

At Stage 8: the soonest deadline is not automatically the first move. Urgency and quality are different axes, and a verdict that confuses them sends the user at the worst option on the board.

## Lesson

The failure was not in the reasoning. Every agent behaved sensibly given what it held. **Summarising is lossy in a direction that is invisible downstream**, and the loss shows up as confident wrongness rather than as an error.
