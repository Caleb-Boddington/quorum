# ADR-0008: The Rapporteur tier replaces Quick as the recommended cheap tier

- **Status:** Accepted
- **Date:** 2026-08-17
- **Note:** Proposed from measured evidence, approved to build, and the Comptroller set the shipping condition below.
- **Evidence:** [Baseline test](../testing.md#baseline)

## Context

A measured baseline put one agent with a strong prompt against a full Quick run on the same question. The single agent caught a legal trap that all five convergence agents had missed, listed three options no department later proposed, and cost roughly a tenth as much.

Quick still won, but every one of its additional catches came from the **checking** layers. None came from having three departments instead of one investigator.

## Decision

Build a tier that keeps every check and replaces the research tier with one deep pass.

Eight agents: a Rapporteur who investigates, a Shadow Rapporteur appointed to oppose, an Auditor, three branches, a Speaker and a Comptroller. Names taken from parliamentary practice, where a rapporteur investigates and reports to a committee and a shadow rapporteur scrutinises that report from an opposing position.

## Alternatives considered

- **Seven agents, folding the adversarial work into the Auditor.** Rejected: it collapses the checking-versus-judging distinction from ADR-0006, which is the rule the whole tier structure rests on.
- **Leave Quick as the cheap tier and add this as a fourth.** Rejected. It is not a smaller Quick, it is a better one, and keeping both would make the choice harder for no gain.

## Result, measured head to head

Rapporteur beat Quick on the same question with two fewer agents. It produced the arithmetic no Quick department had attempted, which reframed the whole question, and twelve options against Quick's scattered handful.

The checking layers then checked each other unprompted: the Auditor caught an arithmetic error in the Rapporteur's own numbers, the Judiciary caught the Shadow overreaching on a threshold argument, and the Comptroller caught the Speaker falsely declaring it had originated nothing.

## Shipping condition, imposed by the Comptroller

The first build audited the Rapporteur but not the Shadow. The Shadow then introduced genuinely new material, none of it verified by anybody, and the Speaker's single largest edit came from that unaudited half.

Ruling: **one audited half and one unaudited half is worse than no shadow at all**, because the unaudited half arrives wearing the authority of a checking layer. The Auditor now covers both papers. Applied before the tier shipped.
