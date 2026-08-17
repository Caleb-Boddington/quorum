# Quorum record, part 2: the three branch positions

Continues `quorum-record-claude4beginners-audit.md`. Same run, 17 August 2026, FULL tier.
This file is authoritative for Stage 7. If anything in a later agent's context disagrees with
it, this file wins.

> **Redacted before publication, 17 August 2026.** Two mechanism names are withheld and both are
> marked in place. No finding, verdict or dissent has been altered. See ADR-0012.

---

## EXECUTIVE (consequence, sequencing, capacity, the first move)

**Position.** Nothing ships until the currently-live file is downloaded and kept as the
rollback zip, and the 124-byte, different-hash gap against local is reconciled. That is the
first move, half an hour, and it is a precondition for every other item, because the file six
departments propose editing is not the file serving readers. Deploy local as-is and you
silently revert production.

Then five slices, each its own zip, each checked live before the next.

1. Text only, zero layout risk: the privacy error, the Part 08 ZIP route, the glossary terms,
   Cowork defined at first use, the injection callout duplicated. Roughly 6 hours. This slice
   is also the rehearsal of the deploy itself.
2. External lead time, so it starts the same week: regenerate og.png, add mailto, LinkedIn and
   GitHub links, register the feedback form. Caches take days to weeks and nothing else waits
   on them.
3. Script behaviour: theme init into head, `js-paged` on `.pager` and `.copy`, reduced motion
   on the two smooth scrolls, modal focus escape, focus target on part change.
4. Layout CSS, all together, measured after: 320px `minmax`, the measure, h4, the two contrast
   tokens.
5. Only then diagrams, then apparatus.

Everything else waits. Department 2's 22.5-hour month list will not ship at two days a week
alongside exams and applications; plan on zero of it. The scale rebuild and the plate colours
wait, because there is no way to view dark mode or print before the zip lands.

Before this URL goes into another application, get the account layer's database permissions
independently confirmed. That is a gate on distribution, not on editing. *(Specifics redacted,
17 August 2026, while the finding is unremediated. See ADR-0012.)*

**What the departments got wrong.** Department 3 prescribed 62ch when its own auditor measured
100-character lines at that setting; do not ship the number it gave. It also placed a
plate-colour system that has never once rendered into the ship-now slice, immediately after
naming untestable dark mode and print as the way a solo author breaks the site. Department 6
was right to sequence the deploy check first and wrong about why: its findings hold on the live
host, so the reconciliation blocks editing, not evidence. Department 4 dropped the reader
apparatus, which was the exact ordering question put to it. Department 1's stamp consolidation
is a 45-minute edit that removes the only per-part audit trail and makes one future edit assert
currency for fifteen parts; defer it. All six stopped the clock at "the edit is made". None
costed the deploy, and six separate "largest effect per hour" claims share no denominator, so
they cannot be ordered against each other.

**The condition.** That the 124-byte gap turns out to be a version stamp or equivalent, meaning
local is ahead of live and nothing unique lives only in production. If live carries edits that
exist nowhere else, slice 1 stops being a rehearsal and becomes a recovery job, and the whole
sequence reorders behind it.

---

## LEGISLATURE (the question and its price)

**Position.** The question was right. The instrument was not, and the price is unpayable as
written.

"Covers all aspects" was never defined by the author. Department 2 filled the gap with its own
standard, then produced a month list at 22.5 hours by treating Anthropic's shipping surface as
the yardstick. That yardstick had 37 dated shipping days in 100. It expires monthly and has no
end. Nobody voted for it, and the department admits its completeness standard is unsourced
judgement, its exclusions never stated, and the author's changelog never read, so it cannot tell
an omission from a decision.

The parallel capture: "top tier design" became measurable properties of the stylesheet.
Department 3 answers "not generated" by counting 53 spacing literals and an feTurbulence grain,
things no reader sees. Available evidence chose the definition.

The bill is 51.8 to 58.3 hours, against a man with four certification exams due by 06/08/2027, a
90% four-times practice gate, a job search, and course instalments falling on 7 September, 7
October and 7 November 2026. (Those dates come from the author's standing instructions, not from
this run's research.) The ship-now 13.35 to 15.85 hours is itself a month of evenings, and the
deploy is uncosted.

What he asked for was assurance, not a programme. The defensible spend is the wrong-class items
only: the privacy error, the ZIP route, the glossary, the og.png. Under four hours. Everything
else is optional.

**What the departments got wrong.** Department 2 priced 22.5 hours of additions without asking
whether a beginner reaches Part 11, and never priced the consequence of shipping none of it.
Department 3 answered the reader question with stylesheet evidence, then prescribed 62ch, which
its own auditor measured at 100 characters against the 80 it cites. Department 6 called the
privacy claim "TRUE as written" while its own confidence block says signed-in is untested. All
six proposed additions and none proposed a cut: six incentives, one direction.

**The condition.** That his time is genuinely the binding constraint. If he has slack evenings
he wants to spend here, the arithmetic changes and the deferred work becomes affordable.

---

## JUDICIARY (soundness)

**Position.** Six reports pass audit, and passing audit establishes only that quoted lines exist
as quoted. That is a narrow thing, and most of the record is narrower than it reads.

1. **The measure.** ESTABLISHED: `--measure: 72ch` computes to 774.97px against a 768px
   paragraph box, so the cap never binds, and lines exceed 80 characters. Three independent
   instrument readings agree (the department's, the auditor's re-walk, the auditor's Range walk).
   The sceptic reasoned from an assumed glyph advance without measuring, and arithmetic from a
   guessed constant does not defeat three direct measurements, so that objection FAILS. But the
   PRESCRIPTION falls: 62ch was measured at up to 100 characters by the department's own auditor
   and independently computed short by the arithmetic reviewer. The defect is established. The
   remedy is not.
2. **SC 2.4.11.** The citation FAILS, the defect SURVIVES. A centre hit-test proves partial
   obscuring only. SC 2.4.3 carries it independently, and the accounts.js evidence (zero `inert`,
   zero Tab handler, Escape only) is direct. Rely on the finding, not the criterion.
3. **Department 6's privacy claim.** NOT ESTABLISHED as written. "TRUE as written" is asserted
   over an untested signed-in path, and the Position contradicts the report's own Confidence
   block. Established: true for the signed-out load, unverified signed in.
4. **The 320px scoping.** The resolution HOLDS. Department 5 measured eighteen part routes;
   Departments 3 and 4 measured the landing contents grid, which is not among them. Different
   referents cannot contradict. Department 5's "every route" wording overstates its own scope.
5. **Authentication.** The omission STANDS UNREBUTTED. The project's own security notes are
   self-authored, unaudited and unchecked this session. They can defeat "nothing was ever done".
   They cannot establish "the protection is correctly configured now". A portfolio piece for
   cyber security roles carries the burden of proof, not the presumption. *(Mechanism name
   redacted, 17 August 2026. See ADR-0012.)*

**What the departments got wrong.** Department 3 prescribed a value its own standard refutes.
Department 5 reached for a criterion its evidence could not support, and dropped a Level A item
while ranking Level AA. Department 6 asserted in its Position what it hedged in its Confidence,
and conflated a stale deploy with unreliable measurement when its auditor reproduced everything
against the live host. Department 1 converted an unnamed uncertainty into a specific direct-read
claim about an article that does not contain the figure. Department 2 listed an MCP glossary
omission for a word the guide never uses, and dropped two scrutineer findings silently.
Department 4 dropped its own researcher's apparatus finding, which was the exact subject of the
ordering question.

THE DROPPED LABELS COST THIS. Every department except partly 1 and 2 abandoned the verifiable
defect versus aesthetic preference marking. The consequence is precise: where an auditor
independently confirmed a quoted line, the item is established regardless of labelling.
Everywhere else, and that covers Department 2's fourteen-item month list, Department 5's
lower-ranked items and every "largest reader effect per hour" claim, the reader cannot
distinguish a breach of a cited standard from a designer's taste, because the writer declined to
say which it was. Those items are NOT established facts. Treating them as such is the error the
labelling requirement existed to prevent.

**The condition.** That the auditors fetched the same artefact the departments did. Every ruling
above rests on independent retrieval matching quoted line numbers and byte counts. Only two
reports named the artefact they measured, and live and local differ by 124 bytes and an
inline-script hash. If the six bodies measured two different files, the confirmations are
coincidence and this position falls entirely.
