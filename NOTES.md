# Development history

Every decision, incident and test is documented as it happened, not reconstructed
afterwards. Several of the incidents were found by asking a question nobody had asked, and
some of the decisions were made by rejecting a recommendation, and turned out right for it.

Most recently, a trial session on Sonnet tested two candidate additions, one accepted
(ADR-0013), one rejected (ADR-0014). Full trial records in
`runs/trial-2026-08-18-sonnet-overnight/`.

## Decisions and incidents

Both now live in one place: **[CHANGELOG.md](CHANGELOG.md)**, patch-notes style, grouped by
version rather than split across separate tables. Each line there links to the full record,
an ADR in [`docs/adr/`](docs/adr/) for a decision, a postmortem in
[`docs/postmortems/`](docs/postmortems/) for an incident, including the one that's still
unfixed.

## Tests

Results in [`docs/testing.md`](docs/testing.md): convergence, baseline, fault injection, the rewrite loop, injection, Stage 0 sabotage and instrumentation. Listed whether they passed, failed, or passed for the wrong reason.

Three of them changed the design. The baseline produced ADR-0008, the convergence result closed off the obvious fix for the independence problem, and the sabotage test produced the project's most serious open finding.

**A fourth test, 19 August 2026**, on Sonnet: two Quick-tier runs on the same question, one with two candidate additions (the discipline-framework line and an experimental Clerk role), one without. Produced ADR-0013 (accepted) and ADR-0014 (rejected). See "Department framework priming and the Clerk role" in [`docs/testing.md`](docs/testing.md).

## Earlier defects, fixed without a postmortem

Found in run 1 and fixed the same day. Recorded for completeness rather than written up, because the fixes were straightforward and the causes uninteresting.

**Six identical cross-reviewers.** Five of six gave near-identical answers to two of three questions. Only "what did everyone miss" diverged, and it produced the best finding of the run. Fixed by giving each reviewer a distinct lens: sceptic, omission hunter, arithmetic checker, framing critic, practitioner, future reader.

**Stage 0 never asked for what only the user knows.** All three branches asked for facts no researcher could find, and two departments wrote "requires the user's input" into load-bearing positions. Fixed by adding an explicit ask at the approval gate.

**Verdicts too dense to finish reading.** Fixed with hard readability rules in the Speaker prompt: decision in the first line of each section, short sentences, no section over four paragraphs, plain summary above the reasoning.

**No run-level fidelity check.** A brief item went unanswered and nothing caught it, because each auditor sees one department and cannot notice that *nobody* answered something. Fixed by giving the Comptroller the briefs and asking which items went unanswered across the whole run. On the next run it found nineteen of twenty-four unanswered.

**Reports written to the wrong location, and a specification that leaked its author's context.** The skill assumed a filing layout that only existed on one machine, and a worked example inside the prompts quietly disclosed where the author was job-hunting. Both fixed when the repository was prepared for publication.
