# Run C record: colleague's expense rounding, success-criterion trial

Quick tier. Carries the now-shipped discipline-framework line (ADR-0013), plus a new trial
addition on top: a required "how you'd know it worked" success criterion, testing whether
naming a falsifiable outcome check changes anything. No Clerk (rejected, ADR-0014). Compared
against Run A (framework line only, same question, same tier) to isolate this addition's
effect specifically. Stage 0 pre-authorised for this batch, as before.

## The trial addition being tested

Both department prompt templates (Standard/Full Stage 4 and Quick-tier Stage 4) gain a new
required output section, immediately after "What would change my mind":

> ## How you'd know it worked
> [A specific, checkable sign that the recommended action actually succeeded, not just was
> taken. Name the concrete thing someone could observe or ask, and by when. If success would
> be invisible or unverifiable, say that plainly, that's a real finding.]

Motivated directly by tonight's Run A and Run B cross-checks, which both independently found
the same gap: none of the three departments, in either run, defined what success would look
like, so quiet, unadmitted cessation of the behaviour would count as a win under every
framework, untested.

## The framed question (same as Run A and Run B)

A junior employee at a mid-sized company notices a colleague quietly rounding up their own
expense claims by a few pounds at a time, over several months. No policy explicitly bans
rounding, and no individual amount is large. Should the junior employee report it to their
manager, raise it directly with the colleague, or let it go?

---

## Department: Workplace Ethics & Culture

**Framework applied:** IBE's public three-question test (legal, fits values, how would it
look if public), plus fraud-response practice (ACFE): an employee who spots suspected fraud
reports it through a channel, doesn't self-investigate or confront. Materiality in fraud is
measured in pattern and intent, not pounds, repeated small skimming is a recognised typology
("salami slicing").

**Position:** Report to the manager. Not confrontation, not silence. State the observed
pattern as fact, hand the materiality and intent judgement to someone who can pull the full
claims history.

**What I found against it:** could easily be sloppy rounding, not dishonesty, escalating on
thin evidence risks disproportionate harm to a colleague over something trivial. Survives:
reporting isn't accusing, it transfers the judgement call rather than the junior playing
investigator or burying it unilaterally.

**Confidence:** [Certain] ACFE 2026: tips are the leading fraud-detection method (43% of
cases), 55% from employees. [Certain] IBE's three-question test is real and maintained.
[Judgement] that this pattern fits "salami slicing" and that flagging beats confrontation is
inference from general literature, not this exact scenario.

**What would change my mind:** clear evidence the discrepancies are innocent, e.g.
receipt-matching errors not a one-direction pattern.

**How you'd know it worked:** within two weeks of the report, the manager gives a
substantive response, confirms a spot-check happened, even briefly. Silence past two weeks
is itself a finding about how seriously the organisation treats small integrity concerns,
not proof nothing was done.

**Sources:** IBE Business Ethics Framework (PRIMARY). ACFE Occupational Fraud 2026
(NAMED DATASET/PRIMARY). Rejected: CIPD ethics factsheets (no specific framework located),
aggregator sites, a content-marketing blog post.

## Department: People/HR Policy

**Framework applied:** ACAS Code of Practice (currently under revision, consultation open to
23 September 2026), governs handling once raised, doesn't say whether to raise it. The actual
test is the qualifying disclosure test, s.43B Employment Rights Act 1996 (as inserted by PIDA
1998): reasonable belief information tends to show a relevant failure, disclosed believing
it's in the public interest, refined by *Chesterton Global v Nurmohamed* [2017] EWCA Civ 979,
which held the public-interest bar doesn't require large numbers affected, just a genuine
belief it matters beyond the discloser's own interest.

**Position:** Report to the manager. Not direct confrontation, not letting it go.

**What I found against it:** ACAS and CIPD's "Raising Concerns" guidance both push toward
informal resolution first, the 2026 draft Code wants an informal conversation before
formalising. Against that: informal-resolution guidance is written for interpersonal
friction, not suspected dishonesty with money, financial malpractice is its own category
routed to a manager or speak-up channel specifically because peer confrontation risks
tipping off, destroying the evidence trail, or a counter-complaint. Survives, but the
informal-first principle is a real counterweight, not a strawman.

**Confidence:** [Certain] the Acas Code's current content and the PIDA/s.43B test, read this
session. [Guessing] whether accumulated small over-claims would actually clear the
*Nurmohamed* public-interest threshold, untested on these specific facts.

**What would change my mind:** if the employer's own policy designates a named speak-up or
fraud-reporting route bypassing the line manager, that takes precedence.

**How you'd know it worked:** within 10 working days, the manager should have acknowledged
receipt and confirmed some action was taken, even if the outcome stays confidential. No
acknowledgement in that window is itself a measurable process failure.

**Sources:** Acas draft 2026 Code (PRIMARY, consultation live). GOV.UK Whistleblowing/PIDA
guidance (PRIMARY). CIPD whistleblowing guidance (INTERESTED PARTY, professional body,
authoritative practice standard). Rejected: law-firm commentary pieces, used only to confirm
the consultation is live, not cited for substantive claims.

## Department: Personal Risk & Career Consequences

**Framework applied:** Near & Miceli's whistleblowing model (1985, extended 1986), predicts
the reporting decision and retaliation risk from seriousness of wrongdoing, availability and
credibility of channels, and the reporter's own support systems, the standard academic model
built specifically around personal consequences to the reporter.

**Position:** Raise it with the manager, framed as a question about the expense process
rather than a named accusation. Not direct confrontation, not letting it go.

**What I found against it:** ECI's GBES 2023 found 46% of people who reported misconduct
globally experienced retaliation, Protect (UK whistleblowing charity, via an interested-party
summary) found 70% face victimisation or forced resignation. Both concern serious wrongdoing
escalated formally, a different animal to a few pounds of rounding, applying those rates here
overstates the risk. Bigger threat isn't retaliation, it's reputational: "do-gooder
derogation" research (Monin, Sawyer & Marquez, 2008, peer-reviewed) found people who act on
principle around peers get socially penalised even when right, exactly where a direct
confrontation over money would fire. Position survives, but for a different reason than
started with, fear of being read as petty rather than fear of retaliation.

**Confidence:** [Certain] the GBES figure as a statistic. [Guessing] its applicability to
trivial peer misconduct. [Likely] the do-gooder-derogation mechanism applies to a direct
approach specifically. That confrontation carries more relational risk than escalation is
judgement, not a tested comparison.

**What would change my mind:** evidence this workplace's managers routinely name their
source when acting on informal reports.

**How you'd know it worked:** by roughly six weeks, the colleague's claims return to normal,
the junior's identity as source stays unconfirmed, and the manager's day-to-day treatment of
the junior doesn't shift. The middle one is largely unverifiable directly, a real limit, not
a gap in the research.

**Sources:** Near & Miceli 1985 and 1986 (PRIMARY). Monin, Sawyer & Marquez 2008 (PRIMARY,
peer-reviewed). ECI GBES 2023 (NAMED DATASET). Protect via Safecall (INTERESTED PARTY, weak
fit to this scenario's severity, used with caveat only). Rejected: general blog/legal-guide
hits, content marketing, no stated method.

---

## Audit Office finding (Run C)

**Verdict:** Ethics & Culture PASS. HR Policy PASS WITH QUALIFICATION. Personal Risk PASS.

**Load-bearing claims checked:** ACFE 2026 43%/55% figures confirmed exact. *Chesterton
Global v Nurmohamed* citation correct, though the record's "just a genuine belief" phrasing
simplifies a four-factor test, simplified not wrong. Monin/Sawyer/Marquez "do-gooder
derogation" confirmed and appropriately scoped to peer confrontation specifically. Near &
Miceli 1985 citation and core structure confirmed, two named predictors [Likely] accurate as
programme-level summary, not verified sentence-for-sentence against the 1985 text itself.
Acas draft Code consultation deadline confirmed, but the draft is the general Disciplinary &
Grievance Code, not whistleblowing-specific, HR's framing overstates fit. ECI GBES 46%
confirmed. "Salami slicing" confirmed as a real typology term.

**What I did not reach:** Protect/Safecall's 70% figure, IBE's three-question test content
beyond its existence, CIPD "Raising Concerns" guidance content.

**Fidelity, including the new success-criterion check:** all three departments stayed in
remit with genuine self-attacks, Personal Risk's was the strongest, it actually revised its
stated reasoning mid-report after checking the retaliation stats didn't fit. **All three
"How you'd know it worked" sections were found concrete and falsifiable**: Ethics (two weeks,
substantive response), HR (10 working days, acknowledgement plus action), Personal Risk (six
weeks, three named signs, one honestly flagged unverifiable rather than dressed up as
checkable).

**The fault:** HR cites the general Disciplinary & Grievance Code as if it were
whistleblowing-specific; Acas's own guidance suggests the two should be separate. Ethics and
Personal Risk: none.

---

## Cross-check (Run C)

**Contradiction:** same label, three different acts. Ethics implies factual disclosure.
HR's PIDA framework needs an assertion something is wrong, not a question. Personal Risk
explicitly frames it as a question specifically to avoid triggering a formal process, a
different act with a different legal status, a question isn't a "disclosure of information"
under PIDA, so Personal Risk's version may not even qualify for whistleblower protection
under HR's own framework. The three departments agree on a destination while pointing to
three different roads. The timeframes expose the same split: Ethics's two weeks measures an
investigatory outcome, HR's 10 days measures a process step (deliberately lower bar),
Personal Risk's six weeks measures a relational/retaliation outcome. Three different
variables, none convertible into the others.

**What all three missed, and the headline finding of this trial:** the new success-criterion
field didn't fix the blind spot Run A and Run B both hit, it relocated it. Their problem was
no success criterion anywhere. Here each department defined one in isolation, and none
reconciles with the others, so "did it work" now has three unreconciled answers instead of
zero. Nobody addresses the actual collision point: if the junior uses Personal Risk's
question framing but the manager treats it as a report anyway, HR's Acas-Code machinery
starts regardless of framing, and Personal Risk's whole risk-mitigation premise silently
fails with no department having flagged that dependency.

---

## Branch deliberations (Run C)

### Executive (consequence)
**Position:** Report to the manager, framed as a factual observation, not a question and not
a formal PIDA invocation. Sequencing is the fix, same shape as Run B: pick the channel that
stays valid regardless of how the recipient reacts. Personal Risk's "soft question" fails
because it makes the manager, not the junior, decide whether it becomes formal, abdicating
the framing decision to the person with the least incentive to keep it informal. A plain
factual statement doesn't have that failure mode, it hands over what was observed and lets
the manager's own obligations take it wherever they go. This also settles HR's citation
error inline: if not dressed up as a question, it doesn't need to survive PIDA's tests.

**What the departments got wrong:** nobody checked whether their chosen framing survives
contact with a recipient who doesn't cooperate with it. Personal Risk built a plan whose
success depended on the manager playing along with an informality the junior can't enforce.

**The condition:** the report has to be worded so its status doesn't change based on who
reads it or how they react. If any version needs the recipient's cooperation to stay what it
was meant to be, it isn't a plan, it's a hope.

### Legislature (the question and its price)
**Position:** Three recommendations, not one. "Report" is doing three incompatible jobs, a
fact-statement, a statutory disclosure, a hedged question designed to dodge statutory
status. The success-criterion field didn't surface this, it buried it deeper, each
department defined success against its own private version of the act and was scored against
that private definition alone. HR's audit caught a wrong Acas citation and still returned
"qualified" rather than flagging the underlying premise, the audit checked citation accuracy,
not whether the act being recommended was the act being audited. Adding a success field
answered a question nobody asked while leaving the actual question, is this the same
recommendation, unasked and now dressed up as answered.

**What the departments got wrong:** none was required to define "report" before defining
success. Success criteria were bolted onto acts that were never pinned down. No cross-
department step forces the definitions to meet before scoring begins.

**The condition:** holds only if "report" was never pinned to one act before the departments
diverged.

### Judiciary (soundness)
**Position:** Not sound at the run level, though each department's local reasoning is
individually well-formed, matching Audit's finding. The success field made the gap sharper,
not smaller, it surfaces that Ethics, HR and Personal Risk each run a valid success test
against a different referent, and nobody checks whether the referents agree. Well-formed
success criteria are not the same claim as convertible success criteria. Same shape as Run
B's finding: department-local validity, run-level incoherence, this time carried by
definitional drift in the word "report" itself rather than an unstated shared assumption.

**What the departments got wrong:** each treated "report" as agreed background rather than a
variable each was setting differently. HR's citation compounds this, applying a general
Disciplinary & Grievance framework to what it calls a PIDA disclosure, against Acas's own
guidance that these are separate procedures.

**The condition:** holds only if "report" was intended as one instruction to be interpreted
three ways for comparison, rather than three deliberately distinct acts the exercise meant to
keep separate.

---

## Speaker's verdict (Run C)

### Tier and what it didn't check
Quick tier ran. Per ADR-0005 it did the same six jobs as every tier, smaller: one merged
agent per department, one Auditor reading all three reports, one cross-checker, no
Rapporteur/Shadow investigative pass. It did not independently verify Protect/Safecall's 70%
figure, IBE's three-question test content, or CIPD's "Raising Concerns" guidance content.

### The Ruling
Report to the manager, worded as a plain statement of what was observed, not a question and
not a named formal disclosure. State the pattern as fact: what was seen, over what period,
no accusation, no PIDA language, no request for the manager to keep it informal, Executive's
fix, all three branches converge on reporting as the destination. But go in expecting this
may become a formal process anyway, the safe wording was never actually shown to keep it
informal, see "What I reasoned myself". That doesn't change the recommended action, it
changes what the junior should expect once they take it.

### Where the branches pulled against each other
Legislature and Judiciary are aligned on the diagnosis, Executive is not aligned with them on
what follows from it. Both flagged the same thing from different angles: "report" was never
pinned to one act before three departments defined success against their own private version
of it, real convergence, reached independently. Executive's fix assumes a wording exists
whose legal status doesn't depend on the reader. Legislature's position is that three legally
distinct acts got treated as one, and a single instruction can't safely stand in for all
three. Executive's "factual statement" is a fourth act, not proof the first three collapse
into one.

### The dissent
Legislature's "three recommendations, not one" is the strongest position overruled. If
"report" was meant as three deliberately distinct acts for the exercise to keep separate,
rather than one instruction interpreted three ways, a single ruling answers a question that
wasn't asked. Judiciary reached the same underlying structure independently through
soundness rather than instruction-design. For this to win, the correct output isn't a
recommendation, it's three playbooks with the junior told to pick which act they mean first.
Overruled because the junior asked one practical question and needs one instruction, a
judgement call, not a refutation of Legislature's point.

### What the cross-review caught
The trial's headline finding: the new success-criterion field didn't fix the "nobody defines
success" gap from Run A and Run B, it relocated it. Each department produced an individually
concrete, falsifiable success check, Audit confirmed all three, but Ethics measured an
investigatory outcome, HR a process step, Personal Risk a relational outcome, three
variables, none convertible, each scored against its own version of "report". Cross-check
named the actual collision nobody flagged: if the junior uses Personal Risk's soft-question
framing and the manager treats it as a report anyway, HR's Acas machinery starts regardless
and Personal Risk's whole premise fails silently. Audit separately caught HR citing the
general Disciplinary & Grievance Code as whistleblowing-specific, against Acas's own guidance
that the two are separate procedures.

### What I reasoned myself
Executive's fix doesn't close the gap Legislature and Judiciary found, it moves it one step
further down. HR's own quoted test, s.43B, turns on content, information tending to show a
relevant failure, not on how it's phrased. A plain factual account of suspected fraudulent
rounding is exactly that information. Wording it as a statement rather than a question likely
doesn't keep it outside PIDA's reach the way Executive's argument assumes. No department made
this connection. [Likely], not [Certain], follows from reading two parts of the record
against each other, not from a verified ruling on wording versus content specifically.

### What rests on unverified ground
Audit didn't reach Protect/Safecall's 70% figure, IBE's three-question content beyond its
existence, or CIPD's guidance content. Departments flagged their own gaps on the Nurmohamed
threshold, do-gooder derogation's applicability, and Near & Miceli's predictors as
programme-level summary. The Speaker's own point above is [Likely] and untested against case
law on wording versus content specifically.

### The first move
Write a short, dated, factual note to the manager: what was observed, over what period, no
accusation language, no grievance language. Send it this week, and go in assuming it may
trigger the formal process regardless of the soft wording.

---

## Comptroller's audit of the verdict (Run C)

**Verdict:** SOUND WITH QUALIFICATION.

**What the ruling rests on that it should not:** nothing marked failed or unverified is
asserted as settled fact.

**On what the Speaker reasoned itself:** legally sound at the core, s.43B's "tends to show"
test is content-driven, and *Kilraine v Wandsworth LBC* (EAT) rejects a rigid
information/allegation dichotomy, a specific factual account carries more, not less, weight
than a hedged question, so Executive's "not a question, so it escapes PIDA" gets the
direction backwards. But the Speaker conflates two different questions: whether something is
a qualifying disclosure (legal protection status) and whether it stays an informal chat
internally (process). Content controls the first, it doesn't determine the second. [Likely]
is the right tag, arguably could be lower, directly on-point case law (*Cavendish Munro*,
*Kilraine*) exists and wasn't checked, which the Speaker admits.

**What nobody answered:** Executive's own condition (wording whose status doesn't depend on
the recipient's reaction) is never tested against Executive's own fix. Legislature and
Judiciary's shared winning condition (one instruction, three readings, vs three distinct
acts) is named as decisive and then explicitly left untested, the Speaker overrules on
practicality, not resolution, and says so.

**What the verdict understates:** the tension between "wording won't change legal status"
and "still word it carefully" is asserted, not reconciled.

---

**Run C complete.** Quick tier, 3 departments (framework line + success-criterion trial), 1
auditor, 1 cross-checker, 3 branches, 1 Speaker, 1 Comptroller, 10 sub-agents.
