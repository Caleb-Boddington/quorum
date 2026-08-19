# ADR-0007: The Speaker may reason, but may not win on reasoning alone

- **Status:** Accepted
- **Date:** 2026-08-17
- **Prompted by:** [Speaker originated its own winning argument](../postmortems/2026-08-17-speaker-originated-winning-argument.md)

## Context

In run 2 the Speaker invented an argument at the final stage, wrote it as a finding, and won the verdict on it. No department produced it, no researcher gathered evidence for it, and no auditor checked it. The Audit Office then partly falsified it after the fact.

The Speaker is the only body in the design with nothing above it, which is why this can happen at all.

## Decision

Originating an argument is allowed, under two conditions:

1. It must be declared in a named section, "What I reasoned myself".
2. It may not be the sole basis of the ruling. If the only thing holding a verdict up is something no department produced, the honest ruling is that the question cannot be settled on the evidence gathered, and here is the hypothesis worth testing first.

The Comptroller then tests whatever was declared.

## Alternatives considered

- **Ban origination entirely.** Rejected. In the run that prompted this, every instrument had failed and a Speaker confined to recombining department output would have returned nothing. Returning nothing when reasoning is the only way out is its own failure.
- **Spend an agent testing any originated argument before the verdict finalises.** Considered, and kept in reserve. The Comptroller already performs this function at no extra cost.

## Consequences

- On the next run the Comptroller caught the Speaker declaring "none" when it had in fact originated a decision threshold, an unconditional governance step, and an inversion of another agent's argument. The declaration requirement gave it something specific to check against.
- The rule does not stop origination. It stops origination from being invisible, which is the part that matters.
