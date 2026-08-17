# ADR-0005: Every tier does the same jobs

- **Status:** Accepted
- **Date:** 2026-08-16
- **Decided by:** Caleb Boddington, overruling Claude

## Context

Two ways to build tiers were on the table.

**Shrink the same process.** Every stage runs at every tier, just smaller. Simple to explain, one thing to maintain.

**Different jobs per tier.** Each tier built to do a smaller job properly. Quick answers "what am I missing", Full answers "I cannot afford to be wrong".

Claude costed both and recommended different-jobs, on the grounds that a uniformly shrunk process is cheaper at the low end and avoids stages that quietly stop working below a minimum size.

## Decision

Caleb rejected the recommendation. Every tier does the same jobs. Going down a tier costs coverage and tokens, never a kind of check.

His reasoning, recorded because it is the better argument: **a tier that drops a whole job is a different tool wearing the same name.** A user who runs Quick and reads a verdict has no way of knowing that a class of check simply did not happen, and the format carries authority the process did not earn.

## Alternatives considered

- **Different jobs per tier**, as recommended. Rejected for the reason above.
- **Two tiers instead of three.** Considered and dropped: the middle option is the one most people would actually want.

## Consequences

- Forced the checking-versus-judging distinction in ADR-0006, because some stages genuinely do break at small sizes and the constraint made that a problem to solve rather than avoid.
- Every tier's output must state which tier ran and what it therefore did not check.
- The landing point took the useful half of both approaches: same six jobs everywhere, and each stage rebuilt at a size that still works rather than shrunk until it does not.

## Note

This is the first of two decisions where the recommendation was rejected and the rejection was correct. See also ADR-0006.
