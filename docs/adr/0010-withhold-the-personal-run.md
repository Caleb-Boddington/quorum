# ADR-0010: Withhold the personal run

- **Status:** Accepted
- **Date:** 2026-08-17
- **Decided by:** Caleb Boddington, overruling ADR-0009

## Context

ADR-0009, decided by Quorum itself, instructed that all three run transcripts become the repository's primary content.

The first run Quorum ever performed was on a personal decision. Its report contained the author's income, course payment schedule, an estimate of his rent, and a health condition. It was also the strongest single piece of evidence in the project: the run where the Audit Office caught a department inventing a fact about a real person, and where the Comptroller caught a recommended option being in a different city from the one the whole run had assumed.

Nothing in the run that produced ADR-0009 noticed that one of the three transcripts was somebody's private life.

## Decision

Withhold it entirely. No redaction attempt.

Redaction was offered and considered: keep the reasoning and both catches, replace the figures. It was rejected on the grounds that the other two runs already demonstrate the same mechanisms, so the marginal evidential value did not justify handling the material at all.

## Consequences

- The repository has two published runs instead of three, and says plainly that a third exists and why it is withheld.
- The findings from that run survive in the development history with the subject matter stripped and the author anonymised.
- Prompted ADR-0011, since the underlying failure was that nothing had classified the question's sensitivity before the run started.

## Note

This is the clearest case in the project of the tool's own ruling being wrong and a human catching it. Quorum optimised for evidential value and had no concept of personal data. The instruction to publish all three was not a slip in reasoning; it was a whole consideration the design did not contain.
