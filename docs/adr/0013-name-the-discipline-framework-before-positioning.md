# ADR-0013: Name the discipline's own framework before a department positions

- **Status:** Accepted
- **Date:** 2026-08-19
- **Note:** Reached after a trial run on Sonnet.

## Context

Departmental reports state a position backed by researched claims, but nothing in the
prompt asked a department to ground itself in how its own discipline actually reasons. A
"Minister for Workplace Ethics" could write a competent, sourced position without ever
touching the professional literature workplace ethicists actually use to think about a case
like this.

The original framing was broader: have each department research how to be the best
practitioner in its field before starting. Rejected in discussion before the trial ran,
because that is generic self-improvement content, context rather than evidence, and it
directly contradicts what `docs/testing.md`'s Baseline test already found: the research
layer adds little on its own, the checking layers are where a run earns its cost. Refined to
a narrower, falsifiable version: name and cite the actual professional framework, test or
standard the discipline applies to this specific question, before stating a position.

## Decision

Every departmental report prompt, Stage 4 (Standard/Full) and Stage 4 Quick tier, now opens
with a required step: name and cite the real framework a practitioner in that discipline
would apply, then use it. The department's output gains a `## Framework applied` section,
first in the structure, before `## Position`.

## Cost of the fix

None. No new agent. One instruction added to a prompt each department already runs.

## Consequences, measured

Trial run, 19 August 2026, two Quick-tier runs on the same question with and without the
line, full records in `runs/trial-2026-08-18-sonnet-overnight/`.

**What it changed:** the Workplace Ethics & Culture department, given the line, named Mary
Gentile's *Giving Voice to Values*, the standard teaching framework for exactly this kind of
low-stakes peer conflict, and reached a materially different, better-grounded conclusion
than the same department run without it.

**What it didn't change:** audit cleanliness. The run carrying the framework line had two of
three departments marked PASS WITH QUALIFICATION by the Audit Office, for a false
self-attack claim and a mismatched citation respectively. The run without it had one
qualification out of three. Having a named framework to cite did not stop citation errors on
this trial, and the vanilla run's audit record was, if anything, cleaner.

## Note

Kept despite the mixed audit result because the cost is zero and the one clear win (Ethics's
sharper, framework-grounded position) is real. This is not evidence the line prevents
error, it doesn't, only that it sometimes sharpens reasoning at no cost. One trial, one
question, one tier. Worth re-testing on a different question before trusting the pattern.
