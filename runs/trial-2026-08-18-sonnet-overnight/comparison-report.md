# Comparison: discipline-framework line vs Clerk, isolated and combined

Two Quick-tier Quorum runs, same question (colleague's expense rounding), same three
departments, same tier. Run A carried both trial additions. Run B carried neither. Full
records in `q2-record.md` (Run A) and `q2b-record.md` (Run B). Nothing in
`skills/research/quorum/` or `projects/quorum/spec/` was touched, these are trial runs only.

## The one-line answer

**The framework line changed what departments produced, for better in one case and for no
clear gain in the others. The Clerk changed nothing worth its cost and quietly did one thing
it shouldn't have.** Neither result should be read as settled, this is one comparison, not a
study, see Limits at the end.

## 1. The discipline-framework line, isolated

Compare Run A's departments (told to name and cite the actual professional framework their
discipline applies) against Run B's departments (plain prompt, no such instruction).

**What it changed:** Run A's Ethics & Culture department named Mary Gentile's *Giving Voice
to Values*, the standard workplace-ethics teaching framework for exactly this kind of
low-stakes peer conflict, and reached a different conclusion from Run B's Ethics department:
raise it directly with the colleague first, rather than report to the manager. Run B's Ethics
department reasoned instead from an intuitive pattern-over-time argument (months, one
direction, looks intentional) with no named framework, and landed on report-to-manager.
Same discipline, same question, genuinely different output, traceable to the instruction.

**What it didn't change:** audit quality. Run A had two of three departments marked PASS
WITH QUALIFICATION, one for a false self-attack claim (HR claimed ACAS guidance was
unverifiable when it was sitting in a source HR itself had labelled PRIMARY), one for a
mismatched citation (Personal Risk's PNAS study, on inspection, measures an unrelated
scenario). Run B had one PASS WITH QUALIFICATION out of three, for a citation applied outside
its stated scope. **Run B's audit record was cleaner**, having a named framework to cite did
not stop citation errors, and on this trial, the vanilla departments made fewer of them.

**Net:** the framework line produced one genuinely sharper, better-grounded department
report (Ethics, Run A) and no measurable improvement, possibly a slight cost, in the other
two. It changes reasoning quality unevenly rather than uniformly.

## 2. The Clerk, isolated

Compare the Speaker's original verdict in Run A against the Clerk's rewrite of the same
verdict, both in `q2-record.md`.

**What it changed:** almost nothing. Word-for-word, the rewrite matches the original except
for a handful of punctuation substitutions and one added word. No claim, sentence, or section
was reordered, shortened, or rephrased.

**What it did that it shouldn't have:** stripped five instances of bold emphasis, including
the bold on the Ruling sentence itself, the single most load-bearing line in the document.
Nothing in the Clerk's brief authorised removing emphasis, and the Comptroller flagged this
as a real, if minor, fidelity issue, not a stylistic judgement call.

**The genuinely useful result, and it isn't about the Clerk:** the first Comptroller pass on
this run was handed a written description claiming the rewrite was "near-identical", not the
rewrite itself, and correctly refused to certify that as verified fidelity. It scored the
claim unverifiable rather than rubber-stamping it. That is the audit design working exactly
as intended, an unaudited-sounding step got checked rather than trusted, but it was checking
my own recordkeeping error, not a Clerk failure. Once the actual text was supplied, the
second pass found the Clerk's error (the stripped bold) that the first pass, working from a
summary, could not have caught either.

**Net: the Comptroller judged plainly that the Clerk did not earn its cost on this run.** One
full agent call bought four punctuation tweaks and a small, unauthorised formatting change,
against a Speaker draft that was already clean, because the Speaker's own prompt already
carries hard readability rules (bold the load-bearing sentence, decision in the first line,
short sentences, no section over four paragraphs). The Clerk is doing a job the Speaker was
already required to do. The Comptroller itself noted this calculus would plausibly flip for a
Speaker verdict written under worse time or context pressure, with a genuinely buried
decision or run-on structure, this trial didn't produce that condition, so it couldn't test
it.

## 3. Combined, across the whole run

Run A converged: Ethics's audited, framework-grounded position survived scrutiny, the
Speaker reconciled to one clear ruling, Comptroller returned SOUND WITH QUALIFICATION.

Run B did not converge in the same way. The three departments answered three different
questions (what the pattern deserves, what channel is correct, what protects the junior) that
happened to collide on one recommended act. Nothing in the Quick-tier structure forced that
collision to be resolved before all three passed audit individually. The Judiciary branch
caught it and ruled the run NOT SOUND as it stood; the Speaker honestly reported that finding
rather than smoothing it into a false convergence, and proposed a genuine resolution
(establish whether a non-manager reporting channel exists, before choosing). The Comptroller
then caught that the Speaker's own "what can be concluded" section quietly repeated the exact
foreclosure of "let it go" that the Legislature branch had just flagged as unfair, one level
up.

**Caution on causation:** it would be tempting to credit the framework line for Run A's
clean convergence and blame its absence for Run B's non-convergence. The record doesn't
support that. Run B's non-convergence traces to a structural gap in the Quick tier itself,
nothing forces a collision between departments to be resolved before they all exit as PASS,
not to any absence of named frameworks. Run A could plausibly have hit the same structural
gap on a different question, or Run B could have converged cleanly on a different one. With
one run each, this is not separable from ordinary run-to-run variance.

## What both runs actually confirmed

In both runs, independent of either trial addition, the departments that did real work
(cited primary sources, attacked their own positions, produced falsifiable "what would
change my mind" statements) still made real, catchable errors, a false self-attack, a
mismatched citation, an overstated inference in a final verdict. In both runs, it was the
Audit Office and the Comptroller, not the departments or the Speaker, that caught them. That
matches what `NOTES.md` in the Quorum project already recorded from earlier testing: the
research layer adds relatively little on its own, the checking layers are where the value
sits. Tonight's trial of two new additions reinforces that finding rather than overturning
it. Neither addition moved the needle on where the real value came from.

## Limits of this comparison

- **n = 1 per condition.** One question, one tier, one run each. Nothing here generalises
  without repeating on different questions and tiers.
- **The framework line and the Clerk were only tested together (Run A) and absent together
  (Run B).** There is no arm that tests the framework line alone without the Clerk, or the
  Clerk alone without the framework line, at the department level. The Clerk's isolated
  effect could be assessed cleanly regardless, because it sits after the Speaker and provably
  didn't touch content; the framework line's isolated effect rests on the Run A vs Run B
  department comparison, which is clean by design (same question, same tier, only the
  instruction differs).
- **Run B's NOT SOUND finding might not be about either addition at all.** See the causation
  caution above.
- **Neither addition has been added to the published skill.** `skills/research/quorum/` and
  `projects/quorum/spec/` are unchanged. This document is a trial finding, not a design
  decision.
