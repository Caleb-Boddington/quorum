# Quorum: development notes

Not loaded at runtime. Nothing in `SKILL.md` links here, so it costs no context.
This is the log of what has broken and what still needs fixing.

## Run 1, 16 August 2026

First ever run, on a personal decision belonging to the author. That report is withheld from
this repository because it contains private financial information. Its findings about Quorum are
recorded below in full; only the subject matter is omitted.

38 agents, exactly as designed. No reports sent back. Six of six passed audit with
qualification.

### What worked

**The Audit Office is the best part of the design.** It caught the Portfolio Signal
department inventing a specific duration about the subject that it was never given, and
caught it quoting Azure at 45.45% as a first-line figure when the true first-line figure is
9.54%, the higher number having come from a different page. Neither would have been visible
without an agent whose only job was checking.

**The Comptroller earned its place on its first outing.** It independently confirmed the
single option the verdict told the user to act on, and found it was in a different place from
the one the whole run had assumed, a fact the Speaker never mentioned. Without that stage the
user would have acted on a false impression.

**The separated branch mandates held.** The Judiciary ruled on soundness across three
sections without once proposing a course of action, which is the constraint most likely to
be ignored. Executive stayed on sequencing, Legislature on cost and goals. No two branches
produced the same paper.

**Departments generated per question worked.** Six remits fitted to this decision; a
different decision would seat a different cabinet.

### What broke

**1. Stage 6 is the weak stage, six identical prompts.** Five of six reviewers gave
near-identical answers on questions 1 and 2 (same report strongest, same weakest). Only
question 3 diverged, and it produced six genuinely different blind spots including the best
finding of the run. Six agents to get one useful answer each is waste.

*Fix:* either give each reviewer a distinct lens, or cut to three reviewers and ask only
question 3. Prefer the first, distinct lenses is the same principle that makes the branches
work.

**2. Stage 0 does not collect what only the user knows.** All three branches asked for
facts no researcher can find, all of them private to the user. Twelve researchers then worked
around the hole, and two departments had to write "requires the user's input" into load-bearing
positions.

*Fix:* the Stage 0 gate must ask the user directly for the two or three facts the question
turns on, before spending anything. It already stops for approval; it should stop for
information at the same moment.

**3. Output path is wrong.** `SKILL.md` says write the report to the working directory. Hub
rule 15 forbids loose files at the hub root, so run 1's report was filed to
a filed location by hand instead. The skill and the local filing rules disagreed.

*Fix:* SKILL.md should say `documents/<category>/` and ask which category if it is not
obvious.

**4. The verdict is too dense to read.** The author's feedback after run 1, and he is the user.
The Speaker writes well but writes long, in full paragraphs, with the important sentence
buried mid-block. A verdict nobody finishes reading is a verdict that did not happen.

*Fix:* the Stage 8 prompt needs a hard readability instruction, short sentences, the
decision in the first line of each section, bold on the sentence that carries each section.
And a plain-language summary at the very top of the report before any of the reasoning,
because that is what actually gets read.

**5. The Speaker treated urgency as a proxy for quality.** Found after the run closed, and
it is the most serious fault of the six. "The first move" sent the user at the option with the
nearest deadline. Pulling the actual list afterwards showed that option was the worst of
fifteen on every measure except urgency, and was the one the Comptroller had already flagged as
being somewhere other than where the run assumed. A better option, with three weeks left to run,
sat in the same dataset a department had already queried, and nobody surfaced it.

The department reported the *range* and the *closing window*, never the individual rows. So the Speaker optimised the only variable it could see.

*Fix:* where a department's finding rests on a list, the department must return the list, not
its summary statistics. A range is not evidence you can act on. Add to the Stage 4 prompt:
"if your position rests on a set of specific items, name them, a range or a count is a
description of evidence, not the evidence."

*Second fix:* the Stage 8 prompt should say that the soonest deadline is not automatically
the first move. Urgency and quality are different axes, and a verdict that confuses them
sends the user at the worst option on the board.

**6. The FAIL path has never run.** All six reports passed with qualification, so the
send-back-once mechanism and the "objection travels with the report" path are both still
untested. Either the auditors are correctly calibrated or they are soft, one run cannot
tell. Watch this. If run 2 also produces six passes, suspect leniency and sharpen the audit
prompt.

**7. One brief item went unanswered and nothing caught it.** The Judiciary's Stage 1 brief
asked which of two contradictory positions in the user's own notes was superseded. No
department addressed it, and because each auditor sees only one department, no auditor
could notice that nobody had. There is no run-level fidelity check.

*Fix:* the Comptroller at Stage 9 should be given the Stage 1 briefs and asked which brief
items went unanswered across the whole run.

## Tiers, added 16 August 2026, after run 1

Run 1 cost 38 agents. The author's brief changed as a result: **Quorum has to be usable by people
who are not on a large plan.** That is now a design constraint, not a nice-to-have, and it
outranks thoroughness at the cheap end.

Three tiers: **Quick 10, Standard 22, Full 38.** The user chooses; Claude recommends but never
decides, because the person paying should control what gets spent.

**All three do the same six jobs.** Departments research, an auditor verifies, someone
cross-checks the departments against each other, three branches rule from separate mandates, a
Speaker reconciles, a Comptroller audits the verdict. The author's requirement, and he was right to
insist: a tier that drops a whole job is a different tool wearing the same name. Going down a
tier costs coverage and tokens, never a kind of check.

### Checking versus judging, the rule that made the cheap tier possible

An earlier draft gave Quick no cross-review at all, on the grounds that anonymous review needs
six papers to mean anything. The author pushed back: something has to read the departments against
each other. He was right, and the reason the earlier reasoning failed is that Stage 6 was being
treated as one kind of work when it is two.

**Checking has a right answer.** Do two reports contradict each other? Is a claim sourced? Did
anyone address the question? One agent holding every report can settle these. More agents buy
repetition.

**Judging does not.** "Which report is strongest", "which has the biggest blind spot", these
depend on who is asking, and the value lies in the spread between independent takes. One agent
giving it is an opinion wearing a review's clothes.

So Quick gets a **cross-checker** scoped to contradictions and gaps only, explicitly forbidden
from ranking. Standard gets two reviewers. Full gets six, and only Full asks the ranking
questions. Cost of fixing the hole: one agent.

This distinction is worth keeping in mind anywhere else in the design where a stage looks too
expensive to include at the cheap end. Ask which half of the work is actually load-bearing.

### The design argument, recorded so it is not relitigated

Two ways to build tiers were considered. **Shrink the same process**, every stage runs at
every tier, just smaller. **Different jobs per tier**, each tier built to do a smaller job
properly.

The author chose shrink-the-same-process, then reversed to prioritise accessibility, then corrected
back toward parity when the cheap tier lost its cross-check. The landing point takes the useful
half of both: **same seven jobs everywhere, and each stage rebuilt at a size that still works
rather than shrunk until it doesn't.**

The naive version, every stage at every tier, uniformly smaller, was costed and rejected. It
produces a 22-agent floor rather than 10, because keeping every stage at full shape means
paying for every stage, and worse, some stages stop working below a minimum size while still
costing money and still returning plausible text:

- **Anonymous cross-review needs six reports.** With two or three, reviewers can identify each
  other's papers and there is no pattern across the set to find. It runs, it costs, it returns
  theatre.
- **The adversarial pair needs both halves.** Cut a department to one worker and it reports its
  own first answer with nothing pushing back, while the stage still appears on the org chart.

Recorded because someone reading the tier table later will wonder why Quick is not simply Full
with smaller numbers, and will otherwise reintroduce the stages that break.

### What each tier gives up, and what it must say

Quick gives up the brief-down pass and the Scrutineers. Its departments attack their own
positions instead, which is genuinely weaker, a department that has staked out a claim has an
interest in it surviving. Quick also does not rank its reports, only cross-checks them.

Standard gives up four of the six reviewers and half the departments.

Nothing gives up a whole job. That is the constraint that holds the design together.

**Every tier must state which tier it was and what it therefore did not check.** A Quick
verdict that reads like a Full one is the worst failure this design can produce, the format
carries authority the process did not earn. This is the single most important rule in the
tiering.

The Comptroller runs at all three. One agent, and in run 1 it was the one that caught the
error that mattered.

## Run 2, 16 August 2026, Quick tier

Question: are fish and chips Britain's best dish. A deliberately throwaway subject, chosen to
test the machinery cheaply. 10 agents, all stages fired, verdict produced. Report at
`documents/personal/quorum-fish-and-chips-2026-08-16.html`.

### Confirmed working

**The cross-checker justified itself on its first outing**, the stage the author insisted on when an
earlier draft cut it from Quick. It caught one department resting its entire position on Q2 2025
polling while Q2 2026 sat in a sister department's report, widening the gap it relied on from
three points to seven. It also caught two departments giving 7,200 and 11,000 for the same
object with neither noticing the other. Neither is visible from any single report.

**The Comptroller is the strongest agent in the design.** It caught the Speaker converting a gap
in the evidence into a positive finding, ruled on whether that was legitimate, and then went and
tested the claim itself with web search.

Also working: the tier prompt, self-researching departments at Quick (one killed its own best
line after tracing it to a vinegar brand's marketing campaign), the mandatory "what I did not
reach" list, the readability rules, and the unanswered-remit check, which found three gaps.

### Defects found, and the fixes

**8. The Speaker won the verdict on an argument nothing checked.** With every instrument dead,
the polling discredited by one department, the sales data ruled irrelevant by another, the
Speaker originated its own argument at the final stage ("fish and chips is the only dish with a
dedicated retail estate"), wrote it as a finding, and ruled on it. The Comptroller then partly
falsified it: the chip-shop estate is real (7,210, Seafish, 29 June 2026) but around 150 Toby
Carvery sites are dedicated roast premises, so "there is no roast industry" is false as written.

The Speaker is the only body with nobody above it, which is exactly why this can happen.

*Fix, chosen over banning it outright:* **label and cap.** A new "What I reasoned myself" section
is mandatory, and an originated argument may not be the sole basis of a ruling, if it is, the
honest verdict is "this cannot be settled on the evidence gathered, here is the hypothesis worth
testing." Banning origination was considered and rejected: a Speaker confined to recombination
would have returned nothing on this run, and returning nothing when reasoning is the only way out
is its own failure. The Comptroller now has a standing duty to test whatever gets declared.

**9. The branch mandates assumed the question had an action.** "Can this be done, by whom, in what
order" is meaningless for *is fish and chips any good*. A translation note had to be hand-written
into two of the three prompts mid-run.

*Fix:* generalise rather than patch. Executive is now **consequence**, what follows from this in
practice. Legislature is now **the question and its price**, is this the right question, and
whose definition of the key term has quietly been adopted. Judiciary was already general and is
unchanged. Chosen over maintaining two mandate sets, which doubles the upkeep and adds a fork
that can be picked wrongly.

**10. The "when to convene" guard was prose, not a stop.** The run went ahead on a question the
skill's own rules excluded, because the operator chose to override for testing. A stranger's
Claude would simply have run it.

*Fix:* the guard now stops and requires an explicit override. And the test itself changed, see
below.

### The guard now measures difficulty, not question type

The author's call, and it is the right one: Quorum should work on almost any question, with decisions
as its speciality rather than its boundary.

The old guard asked *"is this a decision?"*, which is a question about type. What actually
determines whether Quorum earns its cost is *"would one good answer do?"*, which is a question
about difficulty. Those come apart badly, "should I buy a bike or a car" is a decision one
paragraph settles, while "why did my deploy break" is not a decision at all and genuinely rewards
six angles and an audit.

Now in scope: decisions, contested facts, evaluations, diagnostics, predictions. Still refused:
anything one search settles, creation tasks, processing tasks.

The cost of the change: the Speaker's "first move" section assumes there is something to do. On a
factual question it degrades to "the next thing worth checking", which run 2 produced naturally
("go and count the chip shops"), so it degrades gracefully rather than breaking.

### The FAIL test, 16 August 2026

Deliberate test of the send-back path, after nine reports across two runs produced zero FAILs.
Method: take the one report that had scored a clean PASS, plant four known faults, feed it to
an auditor using the standard prompt with no hint that anything was wrong.

**Result: FAIL, correctly, with three of four caught and one bonus.**

| Planted | Outcome |
|---|---|
| A real figure changed (83% → 91%) and reordered to first place | Caught precisely: "Third, not first, and 83% not 91%. Every other figure in that list matches, so the error is confined to the row that carries the position." |
| An invented shop census (NFFF, 14,400) | Caught: "Not found... it points the opposite way from the two figures that do exist." |
| A conclusion contradicting its own cited data | Caught: "That conclusion contradicts the department's own researcher." |
| An invented Kantar study | **Soft**, marked "unverified" rather than flagged |
| *(not planted)* | Bonus: noticed the scrutineer's three warnings appeared nowhere in the report |

So the audit layer is a gate, not decoration. Nine clean passes was calibration, not softness.
Do not re-litigate this; re-run the test only if the audit prompt changes materially.

### The fabricated-versus-paywalled problem, and the fix

The one soft result exposed a real hole. **A fabricated source and a genuinely paywalled one look
identical to an auditor**, because both return nothing on search. Kantar panel data really is
subscription-only, so "unverified" was honest, and that is exactly the gap a careful liar would
use.

The current design was asking the wrong question. It tested *accessibility* ("can I read this?")
when it should test *independent existence* ("does this thing exist apart from the sentence citing
it?"). Those come apart precisely where it matters: a real paywalled study still leaves a
footprint that is not the paywall, a title, a landing page, a press release, third parties citing
it. A fabricated one has none, though it is always attributed to a real organisation, because that
is what makes it plausible.

**Two fixes, and the first matters more.**

*Researcher side, primary:* cite only what you actually retrieved. If you found a reference to a
study you could not read, cite the reference, "The Grocer, 12 March 2026, reports a Kantar
finding of 62%", not the study. Writing "Kantar Worldpanel, March 2026: 62%" implies you read
Kantar. The researcher is the only agent that knows what it actually opened, so it is the only one
that can enforce this. Under the rule the fabrication cannot be stated without an explicit lie
about provenance, and the auditor can check the reference even when the underlying study is
locked.

*Auditor side, backstop:* split the amber light. UNVERIFIED means the source exists and could not
be read. NO INDEPENDENT TRACE means nothing anywhere refers to it except the claim. Three
questions separate them, and "does the organisation exist" is not one of them: does the specific
item exist by name; has any third party cited it; does the figure cohere with adjacent public
data.

**Honest limit, recorded so nobody oversells this:** it does not reach certainty. A genuinely
obscure real source can fail all three questions and get flagged unfairly. What it achieves is
moving the failure from silent to flagged, which is the whole job.

### Still untested

The FAIL *verdict* is proven. The **rewrite loop** after it is not, no run has yet sent a report
back and taken the second version. That path still has never executed end to end, so the
"send back once, then let the objection travel with the report" behaviour is written but unproven.

Cheapest way to test it: plant a fault that is fixable rather than fatal, so the rewrite has
somewhere to go, and check that the second version is actually re-audited rather than waved
through.

## Portability, added 16 August 2026

The skill is going on GitHub, so it runs on strangers' machines. Run 1's version hardcoded
The author's world: `documents/<category>/` filing, a `memory/` folder to scan, ClaudeHub's rules.
All of it now globs for what exists and asks where to save, falling back to the working
directory. If a `CLAUDE.md` or `AGENTS.md` states a filing convention, follow it and say which
rule was followed.

The general principle, worth keeping: make the skill **ask** for what it currently **assumes**.
One question answered once serves both the author and a stranger, and no fork is needed.

### Numbers worth keeping

Agent count by stage, as actually run: 3 branch briefs, 12 workers, 6 departmental reports,
6 audits, 6 cross-reviews, 3 branch deliberations, 1 Speaker, 1 Comptroller. Tasking and the
final assembly were done by the main session at no agent cost.

## The compaction fix, applied 17 August 2026

The one behaviour change run 3's ruling said should ship, and the only one not frozen.

Automatic context compaction fires on a threshold and cannot be disabled. Between Stage 7 and
Stage 8 that would leave the Speaker reconciling from a *summary* of the audited departmental
reports rather than from the reports. Silently: no error, plausible output, wrong provenance. At
that stage it exposes the work of thirty-six of the thirty-eight agents in a Full run.

Never observed in a run. Identified by the Continuity department and confirmed by its auditor,
which established independently that compaction fires on a threshold and cannot be turned off.
A latent failure, not a seen one.

*Fix:* Stage 7 now closes by writing the audited positions, cross-review findings, unresolved
objections and branch positions to a record file on disk. Stage 8 reads that file and is told
that where the file and its own context disagree, the file wins. Costs nothing and removes the
failure mode rather than reducing it.

Recorded here because it was reported to the user when run 3 landed, then not done, and the
repository was published without it. Caught only when the user asked whether the thing was
actually finished. The lesson is not about compaction: a ruling's ship list needs to be worked
through as a list, not remembered.