# Q1 record: CI/CD investment timing

Rapporteur tier. Ran before the discipline-framework line was agreed, so this run does not
carry it. Stage 0 pre-authorised for the whole batch, see test-plan.md.

## The framed question

A five-person software team currently deploys to production manually over SSH on Friday
afternoons. Should the team spend two sprint-weeks now building an automated CI/CD pipeline,
or keep deploying manually until the team grows past eight people?

## Rapporteur report

## Position
Automate now, but not the two-sprint-week version on offer, build a minimal scripted deploy
(single command, health check, automatic rollback) in 2-4 days, then extend it
incrementally. Reject both options as framed.

## The options I considered
- **Build the full two-sprint-week pipeline now** (as proposed) - kept as the baseline to beat.
- **Wait until headcount passes eight** (as proposed) - kept as the baseline to beat.
- **Do nothing indefinitely** - dropped. Manual SSH deploys concentrate risk in one person's
  hands and one weekly window regardless of headcount; the risk doesn't wait for a trigger.
- **Do the opposite: freeze Friday deploys, deploy manually on a safer day** - a genuine
  zero-cost partial fix, worth doing immediately regardless of what else happens, but
  doesn't remove the human-error surface, only its timing.
- **Minimal automation now (my position)** - a scripted deploy captures most of the risk
  reduction for a fraction of the cost, and isn't wasted effort: it's the seed of a fuller
  pipeline, extended incrementally rather than rebuilt.
- **Measure first, then decide** - instrument deploy frequency and incident rate for one
  sprint before committing engineering time. Reasonable, but the failure mode (a bad Friday
  deploy) is already well understood industry-wide; measuring delays a cheap fix for a known
  risk.
- **Hand it to someone better placed: migrate to a managed platform** (Render, Fly, Railway,
  Heroku-style) with git-push deploys built in. Strong option if migration cost is low, could
  make the whole two-sprint question moot, but I have no information on the current hosting
  stack, so I can't confirm it's viable here. Flagged as the biggest unknown, not dismissed.
- **Contract someone to build it** - avoids the opportunity cost to the five engineers, but
  adds cost and handoff risk for a job that's genuinely small if scoped down. Dropped in
  favour of doing the minimal version in-house.

## What I found against my own position
A minimal script might not hold: five people means limited ops depth, and "2-4 days" could
balloon if the deploy has real complexity (migrations, multiple services). If the
elite-performer benefit DORA describes comes from mature pipelines (tests-gated,
environment-staged), a bare script might not deliver it. But the mechanism DORA describes is
smaller, more frequent, lower-stakes changes, a rollback-capable script directly attacks
that, and a full pipeline adds marginal value a five-person team with modest traffic doesn't
yet need. The scoped-down build survives the attack; the case for building nothing does not.

## The assumptions this rests on
- That "two sprint-weeks" is the right size for this problem, not an assumption the team
  should challenge, likely oversized for a five-person deploy.
- That eight people is a meaningful trigger at all, rather than an arbitrary number, nobody
  has shown that manual deploys become unsafe specifically at headcount nine.
- That growth to eight is actually planned and funded, if not, the "wait" option never
  resolves.
- That deploys are currently painless, if Friday SSH deploys already cause weekend
  incidents, "wait" has a live cost today, not a future one.
- That in-house build is the only route, migrating hosting could dissolve the question,
  unverified here.

## Confidence
[Certain]: GitHub Actions gives 2,000-3,000 free minutes/month on Free/Pro/Team plans
(GitHub's own billing docs, retrieved this session), cost is not the blocker. DORA (Google
Cloud, dora.dev, updated Jan 2026) frames speed and stability as correlated, not traded off.

[Likely, not directly verified]: The specific "elite performer" numbers (sub-day lead time,
around 5% change failure rate, 19% of teams) came from secondary write-ups (Octopus, GetDX)
summarising the DORA report, not the primary report text itself, which was fetched and found
not to state the numeric thresholds. Treat the direction as solid, the exact figures as one
hop removed from source.

[Guessing]: The claim that Friday deploys are riskier than other days is industry folklore
repeated widely with no single traceable origin study. No identifiable source found for a
quantified version. Directionally plausible, used that way, not as data.

[Judgement]: The minimal-script sizing and the two-sprint-week estimate being oversized are
the Rapporteur's read, not a cited figure.

## What would change my mind
Confirmation that the current stack is a poor fit for scripted or managed deploy (e.g.
stateful multi-service orchestration genuinely needing staged environments) would push
toward the fuller build now. Confirmation that headcount growth to eight is funded and
near-term would weaken the urgency case somewhat, though not resolve the Friday-deploy risk
in the interim.

## SOURCES
- dora.dev, "DORA Metrics Overview," Google Cloud, updated 5 January 2026, PRIMARY
  (publisher's own program page, fetched directly, did not contain the numeric elite/low
  thresholds).
- GetDX, "Highlights from the 2024 DORA State of DevOps Report" and Octopus Deploy,
  "Understanding the 4 DORA Metrics", JOURNALISM/INTERESTED PARTY (Octopus sells deployment
  tooling, used only as a pointer to the DORA numbers, not as the source of record).
- GitHub Docs, "About billing for GitHub Actions", PRIMARY (GitHub's own documentation,
  fetched directly).
- REJECTED: cicdcost.com, cicdcalculator.com, comparetiers.com, getpricepulse.com,
  undated-feeling aggregator/content-marketing sites with "2026" pricing round-ups and no
  stated methodology, not used for any figure.
- REJECTED: AlgoSec, Firewall Times, Nokia blog on "human error causes X% of outages", wide
  variance (40-75%), data-centre-outage scope not deployment-specific, no traceable primary
  study. Reported as "no identifiable source" rather than cited as fact.

---

## Shadow Rapporteur report

## What is missing
No CI, only CD. A scripted deploy with health-check-and-rollback says nothing about whether
the code being deployed was tested before it shipped. Automating the push without gating it
on a test suite makes bad code ship faster, not safer, and the report never names this as a
different problem.

Database migrations. Automatic rollback is close to free for a stateless app and genuinely
hard the moment a deploy includes a schema change. Five-person teams running SSH deploys
almost always have this.

Access and audit, not just error. The report frames the danger as a capacity problem, one
person's hands, and skips the security problem: who holds standing SSH keys to production,
what happens when someone leaves, whether there's any record of who deployed what.

Nobody asked whether incidents are actually happening. The report flags "deploys are
currently painless" as an assumption but never proposes finding out, cheaply, by asking the
team, before recommending 2-4 days of build.

## The case against
The report's own Confidence section undercuts itself: it dismisses "measure first" because
the failure mode is "already well understood industry-wide", then separately rates
"Friday deploys are riskier" as [Guessing, no traceable study] and rejects other sources on
identical grounds. Strongest opposite case: freeze Friday deploys immediately at zero cost
(the report's own suggestion), then measure for one sprint before writing any script.
Doesn't fully win, a known cheap fix beats waiting when the fix is 2-4 days, but the report
dismisses measurement faster than its own sourcing standard allows elsewhere.

## The sourcing
GitHub Actions minutes confirmed against current GitHub pricing pages. DORA elite-performer
numeric thresholds circulate across a cluster of secondary sites (getdx, scrums.com,
cicd.watch, multitudes, gitrecap) that mostly cite each other rather than DORA's own report,
matching the Rapporteur's own caveat. Friday-deploy-risk folklore has no traceable origin,
also matching the Rapporteur's caveat. Nothing here contradicts the report; its self-grading
was accurate.

## What survives
The core minimal-scripted-deploy call survives. What doesn't survive is the claim that this
is a complete answer to "CI/CD": it's a CD answer to a CI/CD question, with migrations,
testing gates and access control left for later without saying so.

---

## Audit Office finding

**Verdict:** Rapporteur PASS. Shadow Rapporteur PASS WITH QUALIFICATION.

**Load-bearing claims checked:** GitHub Actions free minutes confirmed exact against
GitHub's own billing docs (2,000 Free / 3,000 Pro-Team). DORA primary source confirmed to
state only relative multipliers, not the absolute elite-performer thresholds the secondary
sites report, matching the Rapporteur's caveat. Shadow's claim of a citation cluster
(getdx, cicd.watch, multitudes, gitrecap and others repeating the same figures without
tracing to dora.dev) confirmed likely accurate. Friday-deploy-risk claim: unverified for
both reports, no traceable origin study found either way.

**Fidelity:** Rapporteur answered its brief and its conclusion follows its own evidence;
self-grading matched direct verification. Shadow genuinely opposed rather than restating,
three real scope gaps plus one internal-consistency challenge. That inconsistency claim is a
fair category point in principle, but the specific reasoning it attributes to the Rapporteur
does not appear in the Rapporteur report text as audited, so it could not be checked against
source.

**The fault:** Shadow's central inconsistency claim rests on Rapporteur reasoning not
present in the audited text, unverified rather than false. Rapporteur: none.

---

## Branch deliberations

### Executive (consequence)

**Position:** Build the minimal scripted deploy now, in 2-4 days, and freeze Friday deploys
starting this week. Both moves happen inside the current sprint, not as a two-week project.
Test gating, migration handling, access control and any managed-platform move get sequenced
afterward, each scoped separately with an owner and a trigger, not bundled into one build.

**What the departments got wrong:** The Shadow's four gaps are real but not one task.
Bundling them recreates the false single-build choice the Rapporteur correctly rejected once
already. Migration safety blocks nothing until the first schema change hits the pipeline, so
it doesn't belong in week one. The Shadow's fourth point, asking the team whether incidents
are happening, is a precondition that should have gated the whole investigation, not a peer
bullet alongside build items.

**The condition:** Holds only if a single engineer can own the 2-4 day build without
pulling the other four off sprint work. If nobody can touch deploy scripting solo in that
window, the estimate is fiction and sequencing collapses back into the two-sprint block this
position exists to avoid.

### Legislature (the question and its price)

**Position:** Reject the question as framed. The investigation answered a narrower question
than the one asked, and nobody voted on the narrowing.

**What the departments got wrong:** The question says CI/CD; the investigation and
recommendation address only CD, a scripted deploy with rollback. That collapse from
build-and-test automation to deploy automation was made by what got investigated, not by any
owned decision. The eight-person headcount trigger in the original framing is never
justified by anyone. On cost: the two-sprint option is roughly ten person-weeks of a
five-person team, a quarter of two sprints' total capacity, and that figure never appears
stated against the alternative. The zero-cost check, asking the team whether Friday deploys
are actually causing incidents, was not costed against the 2-4 day build either, despite a
[Guessing]-tagged claim sitting underneath the build recommendation.

**The condition:** Holds only if the team's presenting pain is deploy mechanics, not
pre-deploy verification. If the real failure mode is bad code reaching Friday in the first
place, the CD-only scope was the wrong instrument from the start.

### Judiciary (soundness)

**Position:** The Rapporteur's reasoning holds wherever it stayed inside its own confidence
tags, and breaks once: the Friday-freeze recommendation is a firm action item resting on
evidence tagged [Guessing, no traceable study], with no scrutiny applied to it that the
report withholds elsewhere. The Shadow's inconsistency charge does not survive: it requires
the Rapporteur to have both rejected "measure first" via bad reasoning and never considered
it at all, the Shadow's own point 4 says the option was never proposed. Omission and
rejection-by-bad-reasoning cannot both be true of the same option, and Audit's finding of no
textual trace is consistent with omission, not a hidden rejection.

**What the departments got wrong:** Rapporteur applied its confidence-tagging discipline
inconsistently, rigorous on GitHub Actions and DORA, absent where the Friday-freeze
recommendation needed it most. Shadow's inconsistency claim only works if "never proposed"
and "rejected on bad grounds" are the same event; they aren't, and the claim should not have
been advanced in that form. Shadow's CD-only scope point is untouched by any of this and
stands.

**The condition:** Holds only if Audit's account of the source text is accurate. If a fuller
reading later surfaces the reasoning the Shadow described, the inconsistency claim is
reinstated and this ruling reverses on that point.

---

## Speaker's verdict

### Tier and what it didn't check
This ran at Rapporteur tier: one investigator, one opposing Shadow, one auditor covering
both, three branches reasoning over the record. No separate department cabinet, no second
investigator's independent coverage, cross-checking absorbed into the Shadow's opposition
rather than a dedicated cross-checker.

### The Ruling
Build the minimal scripted deploy in 2-4 days, not the two-sprint pipeline, but ask the
five-person team a single free question before committing to anything else: has a Friday
deploy actually caused a weekend incident? That question costs nothing and resolves the
weakest piece of evidence in the case. Once answered, build the script, and treat testing
gates, migration safety and access control as separate follow-on items, each with its own
owner and trigger. The eight-person headcount threshold in the original framing is
unjustified by anyone in this record and should be dropped as a real trigger.

### Where the branches pulled against each other
Executive and Judiciary converge on the core call: build the minimal script now. Legislature
pulls the other way, arguing the investigation quietly answered a smaller question than the
one asked. Executive treats the CI/CD to CD-only narrowing as fine to proceed on, sequencing
the rest afterward. Legislature says that narrowing was never a decision anyone owned, and
the two-sprint option (roughly ten person-weeks, a quarter of two sprints' capacity) was
never weighed against the near-free alternative of asking the team first. Judiciary accepts
the minimal build but catches that the Friday-freeze recommendation specifically rests on
evidence tagged [Guessing, no traceable study].

### The dissent
Legislature's strongest form: the question said CI/CD, the answer given was CD-only, and
nobody voted on that swap. If the team's real problem is bad code reaching Friday, not the
mechanics of pushing it, a rollback script fixes the wrong layer and the fuller build would
have been closer to right. For this to win outright, the team would need to report that
their actual incidents trace to insufficiently tested code, not deploy mechanics. If true,
the ruling reverses: priority becomes a testing gate, not a deploy script.

### What the cross-review caught
The Shadow caught real gaps: no CI (only CD), no migration handling, no mention of who
holds standing SSH keys, no proposal to ask the team before building. All survive audit
untouched. Shadow's own sharpest attack, an inconsistency in how the Rapporteur weighed
folklore-strength evidence, did not survive Audit's check against the source text, and
Judiciary showed why: it requires the option to have been both never-proposed and
rejected-on-bad-grounds, which can't both be true. Judiciary then found a real version of
the same problem elsewhere: the Friday-freeze action item rests on [Guessing] evidence with
no scrutiny applied.

### What I reasoned myself
The specific move of asking the team before freezing Fridays, rather than freezing first and
asking later, is the Speaker's synthesis, not a department's. Shadow proposed asking the
team as one of four gaps; Judiciary separately flagged the Friday-freeze evidence as weak.
Neither put those findings in sequence; combining them is the Speaker's construction. Small
step, both halves trace to departmental findings, does not carry the ruling alone.

### What rests on unverified ground
The Friday-deploy-risk claim stays unverified by Audit in either direction, and the 2-4 day
sizing is the Rapporteur's judgement call, not a checked figure. Both are load-bearing.

### The first move
This week, before any code is written: one team member asks the other four, directly,
whether a Friday deploy has caused a weekend incident in the last few months. If yes, freeze
Friday deploys immediately and start the 2-4 day script. If no, the urgency case weakens and
the team should decide deliberately, not by default, whether CD-only or a testing-gated
build is the right next step.

---

## Comptroller's audit of the verdict

**Verdict:** SOUND WITH QUALIFICATION.

**What the ruling rests on that it should not:** nothing asserted as fact fails audit. The
Friday-deploy-risk claim stays tagged [Guessing] throughout and is disclosed correctly.

**On what the Speaker reasoned itself:** accurate on attribution, correctly sized. But the
sequencing doesn't fully hold: "The Ruling" states the script gets built regardless, while
"The first move" makes the build conditional on a "yes" answer. Those two passages disagree
on whether the answer actually gates anything.

**What nobody answered:** Executive's condition (the 2-4 day estimate holds only if one
engineer can own it without pulling the other four off sprint work) never appears in the
verdict, though the timeline depends on it. Judiciary's own reversal condition is also
dropped.

**What the verdict understates:** Legislature's cost point (ten person-weeks never weighed
against asking the team first) is relayed but never actually weighed or resolved, just
reported as an omission.

---

**Run complete.** Rapporteur tier, 1 investigator, 1 shadow, 1 auditor, 3 branches, 1
Speaker, 1 Comptroller, 8 sub-agents.
