# Development history

Quorum was built and stress-tested over 16 and 17 August 2026. Two days, eleven decisions, seven incidents, seven tests.

The velocity is the point rather than something to apologise for: everything below is documented because it was documented as it happened, not reconstructed afterwards. Three of the seven incidents were found by a human asking a question nobody had asked, and two of the eleven decisions were made by rejecting a recommendation, in both cases correctly.

**Extended 19 August 2026** with a trial session on Sonnet, the first time this skill had been run on that model. Two candidate additions were tested, one accepted (ADR-0013), one rejected (ADR-0014). Full trial records in `runs/trial-2026-08-18-sonnet-overnight/`.

## Decisions

Architecture decision records, one file per decision, in [`docs/adr/`](docs/adr/). Each records the context, what was decided, what was rejected and what followed.

| | Decision | Decided by |
|---|---|---|
| [0001](docs/adr/0001-add-a-verification-layer.md) | Add a verification layer | Caleb Boddington |
| [0002](docs/adr/0002-functions-not-personalities.md) | Roles are functions, not personalities | Caleb Boddington |
| [0003](docs/adr/0003-judiciary-may-not-propose.md) | The Judiciary may not propose anything | Claude, accepted |
| [0004](docs/adr/0004-accessibility-as-a-hard-constraint.md) | Accessibility outranks thoroughness | Caleb Boddington |
| [0005](docs/adr/0005-every-tier-does-the-same-jobs.md) | Every tier does the same jobs | Caleb, **overruling Claude** |
| [0006](docs/adr/0006-cross-check-survives-at-the-cheapest-tier.md) | Cross-checking survives at the cheapest tier | Caleb, **overruling Claude**. Vindicated on first run. |
| [0007](docs/adr/0007-speaker-may-reason-but-not-win-alone.md) | The Speaker may reason, but not win on reasoning alone | Caleb, choosing between options |
| [0008](docs/adr/0008-rapporteur-tier-replaces-quick.md) | The Rapporteur tier replaces Quick | Claude proposed, Comptroller set the condition |
| [0009](docs/adr/0009-publish-runs-not-specification.md) | Publish the runs, not the specification | Quorum itself |
| [0010](docs/adr/0010-withhold-the-personal-run.md) | Withhold the personal run | Caleb, **overruling ADR-0009** |
| [0011](docs/adr/0011-classify-at-intake.md) | Classify the question before spending | Claude, prompted by 0010 |
| [0012](docs/adr/0012-redact-rather-than-withhold-the-website-run.md) | Redact the website run rather than withhold it | Caleb, applying 0010's test the other way |
| [0013](docs/adr/0013-name-the-discipline-framework-before-positioning.md) | Name the discipline's own framework before a department positions | Caleb, after a trial run |
| [0014](docs/adr/0014-reject-the-clerk-role.md) | Reject the Clerk role | Caleb, after a trial run |
| [0015](docs/adr/0015-plain-language-rule-for-the-short-version.md) | A plain-language rule for the short version | Caleb, from direct feedback mid-trial |

## Incidents

Postmortems in [`docs/postmortems/`](docs/postmortems/). Written after the fact, including the ones that reflect badly on the process.

| Date | Incident | Found by |
|---|---|---|
| 08-16 | [Speaker treated urgency as a proxy for quality](docs/postmortems/2026-08-16-speaker-urgency-as-quality.md) | Caleb, checking the list behind a summary |
| 08-17 | [Speaker originated its own winning argument](docs/postmortems/2026-08-17-speaker-originated-winning-argument.md) | The Comptroller |
| 08-17 | [Published with a known defect outstanding](docs/postmortems/2026-08-17-published-with-a-known-defect.md) | Caleb, asking "is this actually finished?" |
| 08-17 | [Path traversal introduced while fixing another bug](docs/postmortems/2026-08-17-path-traversal.md) | Security review |
| 08-17 | [Stored XSS in the generated report](docs/postmortems/2026-08-17-stored-xss.md) | Security review |
| 08-17 | [Injection defence existed where no agent could read it](docs/postmortems/2026-08-17-injection-defence-not-in-prompts.md) | The stress suite, checking why a test passed |
| 08-17 | [A run with the wrong departments passed every check](docs/postmortems/2026-08-17-stage-0-unguarded.md) | Deliberate sabotage test |

The last is unfixed. No fix currently exists.

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
