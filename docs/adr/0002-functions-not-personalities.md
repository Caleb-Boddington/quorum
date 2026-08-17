# ADR-0002: Roles are functions, not personalities

- **Status:** Accepted
- **Date:** 2026-08-16
- **Decided by:** Caleb Boddington

## Context

The LLM Council's five advisors are thinking styles: a contrarian, an expansionist, an outsider. They all answer the same question from different attitudes.

Five personalities answering one question is still one question asked five times. The tension between them is stylistic rather than structural, so their disagreements are about tone as often as about substance.

## Decision

Replace personalities with functions. Each body answers a *different* question, drawn from the separation of powers:

- Executive: what follows from this in practice
- Legislature: is this the right question, and what does answering it cost
- Judiciary: does the reasoning hold

## Alternatives considered

- **Keep personalities, add more of them.** Rejected: more of the same axis.
- **Domain experts rather than functions.** Rejected: domain coverage is what the departments below the branches are for. Making the top layer domain-based would duplicate them and leave nobody ruling on process.

## Consequences

- Disagreements between branches became informative rather than decorative. In every run to date, no two branches produced the same paper.
- Required ADR-0003, because a body ruling on soundness must be prevented from authoring what it rules on.
- Made the design legible: a reader who knows how a government works can predict what each body will say.
