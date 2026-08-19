# Changelog

## Known issues, still open

- **A run convened with the wrong departments passes every check.** Found by a deliberate
  sabotage test. Every department in a mis-convened run can still produce a competent,
  well-sourced report, and neither the auditor nor the cross-checker catches that the whole
  cabinet was wrong for the question. Only the branches do, after every agent has already
  run. No fix exists yet.

---

## v1.2.0

Sharpening what a department produces, and who can read it.

Departments were already researching and sourcing well, but nothing made them ground a
position in how their own field reasons, and the finished reports were dense enough that
their intended reader was bouncing off them. Both addressed here. A third idea was tested
in the same pass and cut.

**Added**
- Every department now names and cites the actual professional standard for its field
  before giving a position, not just researched claims.
- A plain-language rule for the short summary section: no jargon, one idea per bullet, an
  analogy where it actually helps.

**Tried, not shipped**
- A "Clerk" role, meant to polish verdict prose between two existing checking stages.
  Tested head to head against a run without it, didn't earn its cost, cut before release.

---

## v1.1.0

Making it affordable, making it safe to publish, and fixing what the stress testing found.

The founding build worked, but only at full size. Putting it under real scrutiny turned up
a cluster of problems: a cheaper tier that actually held up, questions about what a run is
even safe to publish, and four genuine defects including two security holes.

**Added**
- The Rapporteur tier, a leaner cheap-tier build that replaces Quick as the recommended
  starting point.
- A classification step before any run starts, checking whether the question involves
  anything sensitive before spending anything.

**Changed**
- The project now leads with its own recorded runs instead of its specification.
- A run on a public website gets redacted in place rather than pulled entirely when it
  contains sensitive material.
- The Speaker can reason on its own once the evidence runs out, but can't win a verdict on
  that reasoning alone, after a run where it invented an unchecked argument and won on it.

**Fixed**
- A run built around a personal decision was withheld rather than published, once it was
  clear the tool had no concept of personal data.
- A verdict could go stale between two stages without anyone noticing, because automatic
  context compaction can silently swap an audited report for a summary of it. Now written
  to disk before the Speaker runs, and the file wins if it ever disagrees with what is
  still in context.
- The fix above briefly opened a path-traversal hole: a run's own topic, unsanitised, was
  going straight into a filename. Closed the same day.
- Text pulled from the open web could carry a script tag straight into a shared report and
  run when someone opened it. Every external string is now escaped before it reaches the
  page.
- A written rule said retrieved text must never be treated as an instruction, but no
  sub-agent actually received that rule, only the orchestrator did. Moved into the block
  every evidence-gathering prompt actually gets.

---

## v1.0.0

The founding build: a deliberation structure that verifies its own claims.

The starting point was an existing idea, a panel of models peer-reviewing each other, with
one gap: nobody ever checks whether the underlying claims are true. Everything in this
version follows from closing that gap, then working out what the bodies around it have to
be for the checking to mean anything.

**Added**
- An independent Audit Office that verifies claims before they reach a verdict.
- Three branches with separate mandates, not personalities, so each one answers a different
  question.
- A tier system, so the tool doesn't only work for someone with a large token budget.

**Changed**
- The Judiciary branch can test reasoning but can't propose an answer of its own.
- Every tier does the same six jobs. Cheaper tiers do them at a smaller size, they don't
  skip whole checks.
- Cross-checking, departments reading each other's work, survives even at the cheapest
  tier.

**Fixed**
- A verdict sent the reader at the worst option on the board because it optimised for the
  nearest deadline instead of quality. Departments must now name individual items rather
  than summarise them as a range, and urgency is no longer allowed to stand in for quality.
