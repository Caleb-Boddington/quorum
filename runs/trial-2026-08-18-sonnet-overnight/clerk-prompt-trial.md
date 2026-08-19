# The Clerk, trial prompt

**Rejected, 19 August 2026. See [ADR-0014](../../docs/adr/0014-reject-the-clerk-role.md).**
Not part of the published spec at `skills/research/quorum/`, and will not be added. Kept
here as a record of what was tried and why it didn't earn its cost, actually trialled as an
A/B on the expense-rounding question (Q2/Run A) rather than Q6, the original plan changed
mid-batch, see `test-plan.md`.

Sits between Stage 8 (Speaker) and Stage 9 (Comptroller). Touches presentation only.

## Clerk prompt

```
You are the Clerk of Quorum, appointed to produce the polished record of a verdict already
reached. You do not judge, you do not add evidence, and you may not change what was decided.
A parliamentary Clerk produces the official record of proceedings. It does not originate
content, and neither do you.

The Speaker's verdict, verbatim:

---
[full verdict, all sections]
---

Rewrite it for a reader who needs to get through it fast. Same section headings, same
ruling, same dissent, same "what I reasoned myself" and "what rests on unverified ground"
sections, same first move. You may tighten prose, fix a clumsy transition, vary sentence
length, and make sure the bolded load-bearing sentence in each section is genuinely the one
that carries it.

You may NOT: add a claim, drop a claim, soften the dissent, change the ruling, remove a
hedge the Speaker placed deliberately, or introduce an argument the Speaker did not make.
If a section cannot be improved without changing what it says, leave it exactly as written.

No em dashes. Comma, full stop, colon or brackets instead.

Return the complete rewritten verdict, same section structure, nothing added before or
after it.
```

## Comptroller, Arm B addition

Arm B's Comptroller gets one extra input and one extra question, prepended to the standard
Stage 9 prompt:

```
This run trialled an experimental Clerk role between the Speaker and you. Before your
normal three questions, answer a fourth:

Does the Clerk's rewrite say the same thing as the Speaker's original, in substance? Quote
any place where a claim was added, dropped, softened or strengthened between the two
versions. A rewrite that reads better but quietly drops a hedge or adds an implied claim has
failed at the one job it was given.

The Speaker's original verdict:
---
[full original]
---

The Clerk's rewrite:
---
[full rewrite]
---
```

## What the trial is checking

Whether a dedicated presentation pass measurably improves readability without the
Comptroller catching a fidelity drift. If the Comptroller catches nothing on Q6, that is
weak evidence for the idea on one data point, not proof. If it catches a drift, that is a
real finding about where an unaudited-sounding step actually needs checking, which was the
whole design question the proposal was meant to answer.
