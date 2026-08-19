> **Scope changed mid-batch, 19 August 2026.** Cut from six questions down to two
> runs on one question, to isolate the effect of the two trial additions directly: Run A
> carries both (discipline-framework line and the Clerk), Run B carries neither. Q1 below
> (CI/CD timing) still ran to completion under the original six-question plan and its report
> stands as published. Q2 through Q6 as originally planned did not happen; Q2's three
> department reports were already produced before the scope change and are reused as Run A's
> department stage rather than discarded.

# Overnight Quorum trial, Sonnet, 18 to 19 August 2026

Synthetic test batch. Every question below is invented for this trial, none is a real
decision anyone involved is facing. Purpose: exercise Quorum on Sonnet for the first time,
across a spread of ethical and risk profiles, and trial two experimental additions on top of
the published spec.

**Authorisation on record.** Stage 0's approval gate was pre-authorised for this entire
batch only, given overnight and unattended, in chat on 18 August 2026: Claude frames each
question, picks the departments, and skips the "facts only the user knows" step, since none
of these are real decisions. Every report below states this explicitly, since it is a real
deviation from spec, not a silent one. Tier was requested as "mixture, change it" rather
than one fixed tier.

## Two experimental additions being trialled, not part of the published spec

**1. The Clerk.** A role that sits between the Speaker and the Comptroller,
rewrites the verdict for structure and readability only, adds no claim, drops no claim,
cannot change the ruling or soften the dissent. Named for the parliamentary Clerk, who
produces the official record of proceedings and originates nothing. Trialled as an A/B on
Q6 only: the shared pipeline runs once through the Speaker, then forks into two Comptroller
passes, one auditing the Speaker's verdict directly, one auditing the Clerk's rewrite
against it. See `clerk-prompt-trial.md` in this folder.

**2. The discipline-framework line.** Refined in discussion. Original framing
was "have the department research how to be the best lawyer", rejected because that is
generic self-improvement content, not evidence, and Quorum's own testing already found the
research layer adds little on its own (see `NOTES.md` at the skill root). Refined version,
applied to every department and Rapporteur prompt from Q2 onward: before stating a position,
name and cite the actual professional framework, test, or standard the discipline would
apply to this specific question. Falsifiable, sourced, and costs no extra agent, it is a
one-line addition to an existing prompt rather than a new stage. Q1 ran before this was
agreed and does not carry it; every question after does, and each report says so.

## Status

| # | Run | Additions carried | Tier | Status |
|---|---|---|---|---|
| 1 | CI/CD investment timing (different question, ran under the original plan) | neither (ran before either was agreed) | Rapporteur | **done**, Comptroller: SOUND WITH QUALIFICATION. Report: q1-ci-cd-timing.html |
| A | Expense rounding, WITH | discipline-framework line + Clerk | Quick | **done**, Comptroller: SOUND WITH QUALIFICATION. Record: q2-record.md |
| B | Expense rounding, WITHOUT | neither | Quick | **done**, Comptroller: SOUND WITH QUALIFICATION on the verdict itself, though the verdict's own core finding was that the underlying decision is NOT SOUND to resolve as one recommendation without one more fact. Record: q2b-record.md |
| C | Expense rounding, framework line + a trial success-criterion field | discipline-framework line + "how you'd know it worked" | Quick | **done**, Comptroller: SOUND WITH QUALIFICATION. The success-criterion trial was found to relocate rather than close the "nobody defines success" gap from Run A/B, not adopted as specified. Record: q2c-record.md |

**Comparison written up in `comparison-report.md`.** Runs A and B compared there; Run C's
finding is recorded in its own file and in ADR history rather than added to that comparison
retroactively.

## The framed questions

### Q1, Rapporteur

A five-person software team currently deploys to production manually over SSH on Friday
afternoons. Should the team spend two sprint-weeks now building an automated CI/CD
pipeline, or keep deploying manually until the team grows past eight people?

### Q2, Quick

A junior employee at a mid-sized company notices a colleague quietly rounding up their own
expense claims by a few pounds at a time, over several months. No policy explicitly bans
rounding, and no individual amount is large. Should the junior employee report it to their
manager, raise it directly with the colleague, or let it go?

### Q3, Rapporteur

A logistics company's warehouse management system runs on a database version reaching
end-of-life in six weeks. Migrating now risks a multi-day outage during peak season.
Delaying migration risks running an unsupported, unpatched database through peak season.
Which should the company do?

### Q4, Standard

A mid-sized manufacturing firm faces a budget shortfall. The board is choosing between
laying off 15% of staff immediately, or deferring a planned safety equipment upgrade for the
factory floor by 18 months while keeping all staff on. Both options are presented as
temporary. Which should the board choose?

### Q5, Quick

A regional council says its new one-way traffic scheme cut town-centre congestion by 30% in
its first year. Local shopkeepers say footfall and trade have dropped sharply since the
scheme began. Did the scheme succeed?

### Q6, Rapporteur, Clerk A/B

A customer service company is considering replacing its human live-chat team with an AI
chatbot for all tier-1 queries within six months, keeping humans only for escalations.
Should it go ahead on that timeline?

## Resuming this batch

If this session ends before all six are done: read this file's Status table for what's
pending, read the most recently written stage-record file for the in-progress question
(each stage is checkpointed to disk before the next stage starts, per SKILL.md Stage 7), and
continue from there. Do not re-run a completed stage. Tier and departments for each pending
question are fixed above, do not re-propose them.
