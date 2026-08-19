# ADR-0011: Classify the question before spending anything

- **Status:** Accepted
- **Date:** 2026-08-17
- **Prompted by:** ADR-0010, and the instruction to remove personal data from the repository

## Context

Two runs produced output that could not be published as it stood. One had to be withheld entirely. The second required an hour of manual redaction, including finding a worked example inside the specification itself that quietly disclosed where the author was job-hunting.

In both cases the problem was discovered after the run, by a human reading the output. Nothing in the design had ever asked what sensitivity the question carried.

## Decision

Add a classification step at Stage 0, before any agent spawns. One question: does this question, or the context gathered while framing it, contain anything that should not leave this machine. Personal financial detail, health information, someone else's data, commercial confidence, credentials.

If it does, agree before the run what happens to the output: which parts get written to disk, whether the report is safe to share, and whether the run should proceed at all.

The step also states plainly that everything passed to a sub-agent is written to the session transcript in plain text on local disk, whatever is later stripped from the report.

## Alternatives considered

- **Rely on the existing credential-stripping rule.** Rejected: it catches passwords and card numbers, and neither failure involved either. Income, rent and a health condition are not credentials.
- **Classify at output rather than intake.** Rejected: by then the material is already in a dozen transcripts.

## Consequences

- Costs one question and prevents an entire class of failure.
- The transcript disclosure matters more than the classification itself. A user who strips their financial details from a published report may reasonably believe they have removed them. They have not.
