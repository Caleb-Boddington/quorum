# ADR-0015: A plain-language rule for the short version

- **Status:** Accepted
- **Date:** 2026-08-19
- **Note:** Reached from direct feedback mid-trial, not an A/B test.

## Context

The report specification already had a "short version" section, six or fewer plain-language
bullets, but no concrete rule for what "plain-language" meant, and in practice tonight's
runs weren't producing it that way. Reading the raw verdicts as they came out of Run A, B
and C surfaced a direct comprehension complaint: large parts of the text weren't landing for
the reader they were written for. That's a comprehension failure, not a formatting one,
terms like qualifying disclosure test, materiality, PIDA, load-bearing claim, were landing on
the page unglossed.

Unlike ADR-0013 and ADR-0014, this wasn't run as an A/B. The evidence is one direct report
from the run's actual reader, which is a different and in some ways stronger kind of
evidence than a second agent's opinion of readability, but it means this hasn't been tested
against a second reader or a second run.

## Decision

The short version section gets a concrete, worded rule: zero jargon (not jargon defined in
brackets, the everyday word instead), one finding per bullet, state what a finding means for
the reader rather than what the process found, an analogy is allowed here and nowhere else
in the report, six bullets hard cap. The rest of the report stays exactly as formal as
before, the public-inquiry-paper register is a deliberate choice for the working detail, this
rule only touches the one section built for a reader who won't go further.

## Cost of the fix

None. No new agent. A rule added to an existing, already-specified section.

## Consequences

Not yet measured against a second run. The test is whether the next report actually reads
differently to the same reader, which this ADR cannot claim yet. Recorded now because the
decision and its reasoning are worth keeping regardless of whether the next run confirms it.

## Note

This sits next to, not instead of, a separate obligation: when Claude reports Quorum results
in chat, the reader's own standing instructions already require a `## In plain English`
section under a hard word limit, no jargon, an analogy where it helps. That rule governs the
conversation. This ADR governs the file. Both were being missed for the same reason tonight,
and both needed fixing, but they are enforced by different things: one by Claude's own
standing instructions, one by what this skill's report specification requires of the
sub-agent that writes the report.
