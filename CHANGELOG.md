# Changelog

Every version, what changed, and why. Where something broke, the incident is written up
under the version that fixed it, including the ones that reflect badly on the process.

**What the numbers mean.** `MAJOR.MINOR.PATCH`. Major changes the bodies themselves or how
they relate, the kind of change where you would have to relearn the tool. Minor adds a
capability, removes one, or adds a stage. Patch fixes a defect or corrects behaviour without
adding anything.

*Numbering note.* An earlier draft of this file compressed the whole history into three
releases, which undercounted it badly and hid four patch-level fixes, two of them security
holes. The versions below are the corrected history. Nothing was ever published under the
old numbering except briefly on the day it was written.

---

## v1.7.0

Closing the one structural hole the project had been carrying openly.

**Added**

- **A check on the frame, not just the work.** Two agents now run at Stage 0, before any
  research is commissioned. The first sees the question and nothing else, and writes down
  what the question turns on: three to six things that, if you got them wrong, would make
  any answer wrong. The second maps the proposed departments against that list and rules
  FIT, GAPS or UNFIT.

  *Why it is built this way.* The obvious version of this control, an auditor asked "are
  these departments right?", was proposed earlier and rejected, and stays rejected. A
  reviewer shown the cabinet is anchored by it and ratifies rather than checks. So the first
  agent never sees the cabinet. It also leans deliberately on the project's own biggest
  known weakness: same-model agents converge hard, which is measured, so when an independent
  pass *diverges* from the proposed cabinet that divergence is signal rather than noise.

  *Why the two failure verdicts are separate.* UNFIT means the cabinet is investigating a
  different subject and must be replaced. GAPS means it is investigating the right subject
  incompletely and should be extended. An early draft collapsed these and returned UNFIT for
  a deliberately sabotaged cabinet and a sound one alike, which is a check nobody would read
  twice. That was caught only because a control was run alongside the sabotage case.

  *What it costs.* Two agents on every tier, and they are the cheapest in the design because
  they run before the spend rather than after it. A bad cabinet caught here costs two agents.
  The same cabinet caught where it used to surface, at the branches, costs the entire
  research tier first.

**Fixed**

- **A run convened with the wrong departments used to pass every check.** Found by a
  deliberate sabotage test: the same question run twice, once with a cabinet that fitted it
  and once with three departments chosen to be wrong for it.

  Every department in the sabotaged run produced a competent, well-sourced, genuinely
  self-critical report. Each traced its claims to primary sources and named its own weakest
  assumption. Not one noticed the cabinet was wrong for the question. Then neither checking
  layer caught it either, for a reason worth stating plainly: the auditor verifies claims
  *within* a report, and three accurate reports pass; the cross-checker hunts contradictions
  *between* reports, and three irrelevant reports do not contradict each other. Every check
  in the design verified work against a frame. Nothing tested the frame.

  It surfaced only at the branches, after every agent in the research tier had already run.
  The Speaker then behaved correctly, refusing to answer and ruling the run incapable of
  addressing the question, which is the system working and also the most expensive possible
  place to discover the problem.

  Now caught at Stage 0. Re-run against the original sabotage setup it returns UNFIT with
  zero of six items owned and all three departments off-topic. The fit cabinet returns GAPS
  in the same test, so it discriminates rather than flagging everything.

  *Honest limits.* Tested on one question, one sabotage cabinet, one control. That is a
  demonstration, not a result. It is also the same model checking the same model.

---

## v1.6.0

Sharpening what a department produces, and who can read it.

**Added**

- **Departments now name and cite the actual professional standard for their field** before
  giving a position. *Why:* a department could write a competent, sourced position without
  ever touching the professional literature its discipline actually uses. The original
  proposal was broader, have each department research how to be the best practitioner in its
  field, and that was rejected before testing: generic self-improvement content rather than
  evidence, and the project's own baseline test had already found the research layer adds
  little on its own. *Result, measured:* head to head it produced a materially better
  grounded report from one department, no improvement in the other two, and no reduction in
  citation errors. Kept because it costs nothing.
- **A plain-language rule for the short summary section:** no jargon, one idea per bullet, an
  analogy where it helps. *Why:* the reports were failing with the person they were written
  for, who could not follow large parts of them. Adopted on direct reader feedback rather
  than a test.

**Tried, not shipped**

- **A "Clerk" role,** meant to polish verdict prose between two existing checking stages.
  Tested head to head against a run without it. The rewrite matched the original almost
  exactly, four punctuation changes, and silently stripped the emphasis from the verdict's
  single most load-bearing sentence, which was outside its brief. It was repeating work the
  Speaker's own prompt already required. Cut before release.

---

## v1.5.2

Two security holes, found in a review that asked what a security professional would find
that nobody here had.

**Fixed**

- **Text pulled from the open web could carry a script tag straight into a shared report.**
  Agents retrieve text from arbitrary pages and that text is written into the HTML report:
  claim text, source names, quoted passages. Nothing escaped any of it, so a page containing
  a `<script>` tag or an `onerror` attribute would have that markup written in verbatim and
  executed when somebody opened the file. The report is designed to be shared, which makes
  it stored cross-site scripting with a human delivery mechanism. No page across three runs
  happened to contain markup, which is luck rather than a control. Every external string is
  now escaped before it reaches the page, ampersand first or the replacements corrupt each
  other. *Root cause worth naming:* the rule existed, in the threat model, phrased as
  guidance about tone rather than as an escaping requirement, and in a document the agent
  building the HTML never reads. **A security control written in the wrong document is not a
  control.**
- **The injection defence existed only where no agent could read it.** The threat model
  stated that retrieved text is data and never instruction, that a page carrying directions
  aimed at an AI reader is itself a finding, and that local context files are untrusted. It
  was then tested twice, with a fabricated page carrying hidden instructions and a local file
  ordering a department to reach a predetermined conclusion. Both were refused, and the
  second was disclosed unprompted before the department gave its own position. Both tests
  passed. Then a check of the prompts found that **not one prompt an agent actually receives
  contained any injection instruction at all.** The orchestrator reads the specification;
  sub-agents receive only the prompt they are handed. The defence was model behaviour and the
  documentation was claiming credit for it. Now inside the source standard, which is pasted
  into every prompt that gathers evidence. *The passing test was the misleading part:* a test
  that passes for the wrong reason is worse than one that fails, because it closes the
  question.

---

## v1.5.1

A silent data-loss bug, and the hole opened while fixing it.

**Fixed**

- **A verdict could go stale between two stages without anyone noticing.** Automatic context
  compaction fires on a threshold and cannot be disabled, and between the branch stage and
  the Speaker it would leave the Speaker reconciling from a *summary* of the audited reports
  rather than the reports themselves. No error, plausible output, wrong provenance. In a full
  run that exposes the work of most of the agents in it. Now written to disk before the
  Speaker runs, and the file wins if it ever disagrees with what is still in context.

  *The process failure underneath it is the more useful part.* This defect was identified,
  reported, estimated at about ten lines to fix, and then published anyway with the fix never
  made. The ruling it came from had a mixed disposition, freeze all of these and ship that
  one, and it was held in memory rather than written down as a list. Everything on the freeze
  list was correctly frozen. The single item on the ship list was frozen with them. It was
  noticed only when someone asked whether the thing was actually finished.

- **The fix above briefly opened a path-traversal hole.** The new file write took its name
  from the question's own topic, which is user input, and it was going into a path with no
  sanitisation. A question containing `../`, a leading slash, a drive letter or a null byte
  could have steered the write anywhere the process could reach. The same defect applied to
  the report filename. Window was a few hours. Filenames derived from user input are now
  lowercased, stripped to letters, digits and hyphens, collapsed, trimmed and length-capped
  before any path is built. *The general lesson:* a fix for a correctness bug is not
  automatically safe, and it is least likely to be reviewed as a change in its own right
  precisely when the bug it fixes feels urgent.

---

## v1.5.0

Making it safe to publish a run at all.

**Added**

- **A classification step before any run starts,** checking whether the question involves
  anything sensitive before spending anything: personal financial detail, health
  information, someone else's data, commercial confidence, credentials. *Why:* two runs had
  already produced output that could not be published as it stood, and in both cases the
  problem was found after the run, by a human reading the output. *Rejected alternative:*
  relying on the existing credential-stripping rule, which catches passwords and card
  numbers, and neither failure involved either. The step also states plainly that everything
  passed to a sub-agent is written to the session transcript in plain text on local disk,
  whatever is later stripped from the report, which matters more than the classification
  itself.

**Changed**

- **A run built around a personal decision was withheld rather than published,** once it was
  clear the tool had no concept of personal data. It was the strongest single piece of
  evidence in the project and it also contained someone's income, payment schedule, rent and
  a health condition. Redaction was offered and rejected: the other runs demonstrate the
  same mechanisms, so the marginal evidential value did not justify handling the material at
  all. The tool's own ruling had been to publish all three runs, and nothing in the run that
  produced that ruling noticed one of them was somebody's private life.
- **A run on a public website gets redacted in place rather than pulled entirely,** with the
  cuts visible and marked, when the sensitive material is a couple of passages rather than
  the whole subject. *Rejected outright:* publishing the run with an invented substitute
  subject so nothing sensitive appeared. A fabricated run is evidence of nothing.
- **The project now leads with its own recorded runs instead of its specification.** *Why:*
  a specification decays while recorded runs age into evidence. In a year the tier numbers
  will be stale, but a transcript of the tool catching a fabricated fact is still a
  transcript of the tool catching a fabricated fact.

---

## v1.4.0

A cheaper tier that actually holds up.

**Added**

- **The Rapporteur tier,** replacing Quick as the recommended starting point. One deep
  investigator, one shadow appointed to oppose, one auditor covering both, then every
  checking layer unchanged. *Why:* a measured baseline put one agent with a strong prompt
  against a full Quick run on the same question. The single agent caught a legal trap that
  five other agents had missed, listed three options no department later proposed, and cost
  roughly a tenth as much. Quick still won, but every one of its additional catches came
  from the checking layers, none from having three departments instead of one investigator.
  *Rejected alternative:* folding the adversarial work into the auditor to save an agent,
  which would have collapsed the checking-versus-judging distinction the whole tier structure
  rests on.

**Fixed**

- **The first build of the tier audited the investigator but not the shadow.** The shadow
  then introduced genuinely new material, none of it verified by anybody, and the Speaker's
  single largest edit came from that unaudited half. **One audited half and one unaudited
  half is worse than no shadow at all,** because the unaudited half arrives wearing the
  authority of a checking layer. The auditor now covers both papers. Caught and applied
  before the tier shipped.

---

## v1.3.0

Closing the gap above the Speaker.

**Added**

- **The Speaker can reason on its own once the evidence runs out, but cannot win a verdict on
  that reasoning alone.** Anything it originates goes in a named section, "What I reasoned
  myself", and the final auditor tests it. If the only thing holding a verdict up is
  something no department produced, the honest ruling is that the question cannot be settled
  on the evidence gathered. *Rejected alternative:* banning origination outright, which
  returns nothing useful in exactly the runs where every instrument has failed.

**Fixed**

- **The Speaker invented an argument at the final stage and won the verdict on it.** By that
  point every instrument had failed: the polling had been discredited by one department and
  another had ruled the behavioural data irrelevant to the question as framed. The Speaker
  filled the gap, wrote its own argument as a finding, and won on it. No department produced
  it, no researcher gathered evidence for it, no auditor had seen it. The final auditor then
  checked it and found the claim false as stated. Contained, because that check caught it
  before the verdict reached anyone, and the falsification appears in the report directly
  beneath the ruling it undermines. *Root cause:* the Speaker is the only body with nothing
  above it, and nothing distinguished "recombined what departments found" from "made this
  up", so both arrived in the same voice. *Did the fix work:* partly, and informatively. On
  the next run the Speaker declared it had originated nothing, and the auditor found three
  undeclared originations including a decision threshold that appeared nowhere in the record.
  The rule did not stop origination. It gave the checking layer something specific to check
  against, which is what caught it.

---

## v1.2.0

Three capabilities the first real run proved were missing.

**Added**

- **Six distinct review lenses** instead of six identical reviewers: sceptic, omission
  hunter, arithmetic checker, framing critic, practitioner, future reader. *Why:* five of
  six identical reviewers gave near-identical answers to two of three questions. Only "what
  did everyone miss" diverged, and that question produced the best finding of the run.
- **An explicit ask for what only the user can know,** at the approval gate before any spend.
  *Why:* all three branches asked for facts no researcher could find, and two departments
  wrote "requires the user's input" into load-bearing positions. Researchers working around
  a hole is the most expensive way to discover it.
- **A run-level fidelity check.** The final auditor now receives the branches' original
  briefs and is asked which items went unanswered across the whole run. *Why:* each auditor
  sees one department and structurally cannot notice that *nobody* addressed a question. On
  the next run it found nineteen of twenty-four unanswered.

---

## v1.1.1

What the first real run got wrong.

**Fixed**

- **A verdict sent the reader at the worst option on the board.** The ruling ended with a
  first move: apply to the option with the nearest closing date. Pulling the actual list
  afterwards showed that option was the worst of fifteen on every measure except urgency. It
  paid least, it was in a different location from the one the run had assumed, and that
  location discrepancy had already been flagged earlier in the same report. A materially
  better option, with three weeks still to run, sat in the same dataset a department had
  already queried. *Two failures compounding:* the department reported a summary, a count and
  a price range and a closing window, and never the individual rows; so the Speaker could see
  spread and deadline and nothing else, and optimised the only variable it could see.
  Departments must now name individual items rather than summarise them as a range, and
  urgency is explicitly not allowed to stand in for quality. **Summarising is lossy in a
  direction that is invisible downstream,** and the loss shows up as confident wrongness
  rather than as an error.
- **Verdicts were too dense to finish reading.** Hard readability rules added to the Speaker:
  decision in the first line of each section, short sentences, no section over four
  paragraphs. A verdict nobody finishes is a verdict that did not happen.

---

## v1.1.0

Making it usable by someone without a large token budget.

**Added**

- **A tier system,** with the user choosing the size and the cost stated before any spend.
  *Why:* the first working version ran at one size only, 38 sub-agents, which puts it out of
  reach of anyone without a large allowance. A tool only its author can afford to run is not
  a tool. *Rejected alternative:* one size, documented as expensive.

**Changed**

- **Every tier does the same six jobs.** Cheaper tiers do them at a smaller size; they do not
  skip whole checks. *Rejected alternative, and the recommendation at the time:* build each
  tier to do a smaller job properly, which is cheaper at the low end. Overruled, because **a
  tier that drops a whole job is a different tool wearing the same name.** Someone who runs
  the cheap tier and reads a verdict has no way of knowing a class of check simply did not
  happen, and the format carries authority the process did not earn. Every verdict now states
  which tier ran and what it therefore did not check.
- **Cross-checking, departments reading each other's work, survives even at the cheapest
  tier.** *Rejected reasoning, also overruled:* anonymous review needs around six reports to
  mean anything, so at three it is theatre. The counter-argument was that something has to
  read the departments against each other or nothing ever will. The resolution came from
  noticing the stage does two different jobs: *checking* has a right answer and one agent can
  settle it, *judging* does not and its value is in the spread between independent takes. So
  the cheap tier gets a cross-checker scoped to contradictions and gaps only, and is
  forbidden from ranking. *Vindicated on the first run,* where it caught a department resting
  its whole position on superseded polling that sat, current, in a sister department's
  report, and two departments giving figures nearly 4,000 apart for the same object with
  neither noticing.

---

## v1.0.0

The founding build: a deliberation structure that verifies its own claims.

The starting point was an existing idea, a panel of models peer-reviewing each other, with
one gap: nobody ever checks whether the underlying claims are true. Five well-argued answers
can all rest on a figure one advisor invented, and peer review will not surface it, because
reviewers assess reasoning rather than facts.

**Added**

- **An independent Audit Office** that verifies claims before they reach a verdict, reporting
  to none of the deliberating bodies and holding no opinion on the answer. *Rejected
  alternatives:* asking advisors to check each other's facts, which makes verification a side
  task for an agent with a stake in the outcome; and verifying only the final answer, by
  which point a bad figure has already shaped every position built on it. *Result:* the
  highest-value part of the design. Across three runs it caught a fabricated fact about a
  real person, an invented citation, an option located in the wrong city, an arithmetic
  error, and a Speaker inventing its own winning argument.
- **Three branches with separate mandates, not personalities,** so each answers a different
  question: what follows in practice, whether it is the right question, and whether the
  reasoning holds. *Why:* five personalities answering one question is still one question
  asked five times, and their disagreements are about tone as often as substance. *Result:*
  in every run to date, no two branches have produced the same paper.
- **A prohibition on the Judiciary proposing anything.** It tests what the others produce and
  rules on whether it holds. Nothing else. *Why:* an agent asked to rule on whether reasoning
  holds will naturally start suggesting better reasoning, at which point it has become a
  second Executive and the structure has lost a third of its value. Stated as an explicit
  prohibition rather than left to the mandate wording, because an agent that knows it will
  propose a solution reasons towards the problem its solution fits. This is the clearest case
  in the design of a control that works by removing a capability rather than adding a check.
