# ADR-0004: Accessibility outranks thoroughness

- **Status:** Accepted
- **Date:** 2026-08-16

## Context

The first working version ran at one size: 38 sub-agents. That is a substantial spend and it puts the tool out of reach of anyone without a large token allowance.

## Decision

Quorum must be usable by people who are not on a large plan. This is a design constraint that outranks thoroughness at the cheap end, not a nice-to-have. Introduce tiers, and let the user choose.

## Alternatives considered

- **One size, documented as expensive.** Rejected on the grounds that a tool only its author can afford to run is not a tool.
- **The tool picks the tier based on question difficulty.** Rejected: the person paying decides what to spend. The tool recommends, the user chooses.

## Consequences

- Produced the tier system, and with it ADR-0005 and ADR-0006, which were the two hardest design problems in the project.
- Forced the discovery that a cheap tier cannot simply be a smaller expensive tier, because some stages stop working below a minimum size while still costing money.
- The tier and its agent count are stated before any spend, and the run stops for approval. That is cost control as a governance step rather than a warning in the documentation.
