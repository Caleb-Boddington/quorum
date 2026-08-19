# ADR-0001: Add a verification layer

- **Status:** Accepted
- **Date:** 2026-08-16
- **Context:** Founding decision. Everything else follows from it.

## Context

Andrej Karpathy's LLM Council asks a panel of models one question, has them peer-review each other anonymously, then a chairman synthesises. Used over a period, one gap kept recurring: the panel reviews each other for quality of argument, and nobody at any point checks whether the underlying claims are true.

The failure mode is specific. Five well-argued answers can all rest on a figure one advisor invented, and peer review will not surface it, because reviewers are assessing reasoning rather than facts.

## Decision

Keep the anonymous peer review. Add an independent Audit Office whose only job is verifying claims, reporting to none of the deliberating bodies and holding no opinion on the answer.

## Alternatives considered

- **Ask advisors to check each other's facts.** Rejected: it makes verification a side task for an agent with a stake in the outcome, which is the same structural problem as self-review.
- **Verify only the final answer.** Rejected: by then a bad figure has already shaped every position built on it.

## Consequences

- Adds one agent per report, plus one final auditor.
- Produced the design's highest-value results. In three runs the Audit Office caught a fabricated fact about a real person, an invented citation, a job located in the wrong city, an arithmetic error, and a Speaker inventing its own winning argument.
- Created a second problem, solved in ADR-0007: the Audit Office can catch a wrong answer but nothing was checking the body that writes the verdict.
