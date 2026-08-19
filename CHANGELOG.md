# Changelog

Version history, patch-notes style. Full reasoning for every entry lives in its own file
under [`docs/adr/`](docs/adr/), linked below each one.

## v1.2.0, 19 August 2026

**Added**
- Every department now names and cites the actual professional standard for its field
  before giving a position, not just researched claims.
  [ADR-0013](docs/adr/0013-name-the-discipline-framework-before-positioning.md)
- A plain-language rule for the short summary section: no jargon, one idea per bullet, an
  analogy where it actually helps.
  [ADR-0015](docs/adr/0015-plain-language-rule-for-the-short-version.md)

**Tried, not shipped**
- An experimental "Clerk" role meant to polish verdict prose between two existing checking
  stages. Tested head to head, didn't earn its cost, cut before release.
  [ADR-0014](docs/adr/0014-reject-the-clerk-role.md)

## v1.1.0, 17 August 2026

**Added**
- The Rapporteur tier, a leaner cheap-tier build that replaces Quick as the recommended
  starting point. [ADR-0008](docs/adr/0008-rapporteur-tier-replaces-quick.md)
- A classification step before any run starts, checking whether the question involves
  anything sensitive before spending anything.
  [ADR-0011](docs/adr/0011-classify-at-intake.md)

**Changed**
- The project now leads with its own recorded runs instead of its specification.
  [ADR-0009](docs/adr/0009-publish-runs-not-specification.md)
- A run on a public website gets redacted in place rather than pulled entirely when it
  contains sensitive material.
  [ADR-0012](docs/adr/0012-redact-rather-than-withhold-the-website-run.md)

**Fixed**
- A run built around a personal decision got withheld rather than published, once it was
  clear the tool had no concept of personal data.
  [ADR-0010](docs/adr/0010-withhold-the-personal-run.md)

## v1.0.0, 16 August 2026

First working build.

**Added**
- An independent Audit Office that verifies claims before they reach a verdict.
  [ADR-0001](docs/adr/0001-add-a-verification-layer.md)
- Three branches with separate mandates, not personalities, so each one answers a different
  question. [ADR-0002](docs/adr/0002-functions-not-personalities.md)
- A tier system, so the tool doesn't only work for someone with a large token budget.
  [ADR-0004](docs/adr/0004-accessibility-as-a-hard-constraint.md)

**Changed**
- The Judiciary branch can test reasoning but can't propose an answer of its own.
  [ADR-0003](docs/adr/0003-judiciary-may-not-propose.md)
- Every tier does the same six jobs. Cheaper tiers do them at a smaller size, they don't
  skip whole checks. [ADR-0005](docs/adr/0005-every-tier-does-the-same-jobs.md)
- Cross-checking, departments reading each other's work, survives even at the cheapest
  tier. [ADR-0006](docs/adr/0006-cross-check-survives-at-the-cheapest-tier.md)
- The Speaker can reason on its own once the evidence runs out, but can't win a verdict on
  that reasoning alone.
  [ADR-0007](docs/adr/0007-speaker-may-reason-but-not-win-alone.md)
