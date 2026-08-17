# ADR-0006: Cross-checking survives at the cheapest tier

- **Status:** Accepted
- **Date:** 2026-08-16
- **Decided by:** Caleb Boddington, overruling Claude. Vindicated on first run.

## Context

An earlier draft of the cheap tier had no cross-review at all. Claude's reasoning: anonymous review needs around six reports to mean anything. With three, reviewers can identify each other's papers, anonymity is fiction, and there is no pattern across the set to find. It costs agents and returns theatre.

Caleb rejected this. His objection: something has to read the departments against each other, or nothing ever will.

## Decision

The cheapest tier gets a cross-checker.

The reason the original reasoning failed is that Stage 6 was being treated as one kind of work when it is two.

**Checking has a right answer.** Do two reports contradict each other? Is a claim sourced? Did anyone address the question? One agent holding every report can settle these. More agents buy repetition.

**Judging does not.** "Which report is strongest" depends on who is asking, and the value lies in the spread between independent takes. One agent giving it is an opinion wearing a review's clothes.

So the cheap tier gets a **cross-checker** scoped to contradictions and gaps only, explicitly forbidden from ranking. Higher tiers add reviewers, and only the fullest tier asks the ranking questions.

## Cost of the fix

One agent.

## Consequences, measured

On its first run the cross-checker caught a department resting its entire position on superseded polling data that sat, current, in a sister department's report. It also caught two departments giving figures nearly 4,000 apart for the same object with neither noticing the other.

Neither finding was visible from any single report. The tier would have shipped without them.

## Note

The general principle, worth reusing: when a stage looks too expensive to include at the cheap end, check whether it is doing two kinds of work and whether only one of them is load-bearing.
