# ADR-0014: Reject the Clerk role

- **Status:** Rejected
- **Date:** 2026-08-19
- **Decided by:** Caleb Boddington, after a trial run on Sonnet

## Context

Caleb proposed a role sitting between the Speaker and the Comptroller: an independent
writer, styled after a parliamentary Clerk, that would take the Speaker's verdict and
present it in a neater, more structured format without adding or changing content. The
worry going in was placement, a rewrite step after the Comptroller would be unaudited, and a
rewrite step before the departments reach the Audit Office would sit between the departments
and the one body checking them. Placing it between the Speaker and the Comptroller, with the
Comptroller given an added question checking the rewrite against the original, was designed
to avoid both.

## Decision

Do not add the Clerk role. It was trialled once, on Sonnet, as an A/B within a single Quick
tier run, full record in `runs/trial-2026-08-18-sonnet-overnight/q2-record.md`, and is not
part of the shipped specification. `clerk-prompt-trial.md` in that folder is kept as a record
of what was tried and why it was rejected, not as a live prompt.

## Cost of the fix not taken

One full agent call per run, avoided.

## Consequences, measured

The rewrite matched the Speaker's original in substance almost exactly, four punctuation
changes and one added word, no claim, sentence or section added, dropped, reordered or
shortened. It also stripped five instances of bold emphasis, including the bold on the
Ruling sentence itself, the single most load-bearing line in the document, something nothing
in its brief authorised.

The Comptroller's own verdict: the Clerk did not earn its cost on this run. The Speaker's
prompt already carries hard readability rules (bold the load-bearing sentence, decision in
the first line, short sentences, no section over four paragraphs), so the Clerk was mostly
repeating work the Speaker was already required to do, and on this trial the one thing it
changed without permission was a formatting rule, not an improvement.

**One genuinely useful result came out of the trial, and it isn't about the Clerk.** The
first Comptroller pass on this run was, by the orchestrator's own process error, handed a
written summary claiming the rewrite was near-identical rather than the rewrite itself, and
it correctly refused to certify that as verified fidelity, scoring it unverifiable instead of
rubber-stamping it. That is the audit design working as intended: an unaudited-sounding step
got checked rather than trusted. It validates the placement decision (between Speaker and
Comptroller, not after), even though the role it was protecting against didn't turn out to
be worth adding.

## Note

The Comptroller flagged that this calculus would plausibly flip for a Speaker verdict
written under worse time or context pressure, with a genuinely buried decision or run-on
structure. This trial's Speaker output was already clean, so that condition was never
tested. If a future run produces a demonstrably poor Speaker draft, the Clerk idea is worth
revisiting against that evidence specifically, not reintroduced on the strength of the
original argument alone.
