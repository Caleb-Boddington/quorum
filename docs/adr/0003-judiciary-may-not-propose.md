# ADR-0003: The Judiciary may not propose anything

- **Status:** Accepted
- **Date:** 2026-08-16

## Context

Three branches with separate mandates only stay separate if something stops them drifting. The likeliest drift is the Judiciary: an agent asked to rule on whether reasoning holds will naturally begin suggesting better reasoning, at which point it has become a second Executive and the structure has lost a third of its value.

## Decision

The Judiciary is explicitly barred, in its mandate, from proposing any plan or any answer. It tests what the others produce and rules on whether it holds. Nothing else.

## Alternatives considered

- **Allow it to propose, but only after ruling.** Rejected: an agent that knows it will propose a solution reasons towards the problem its solution fits.
- **Rely on the mandate wording without an explicit prohibition.** Rejected as too weak. The prohibition is stated as a prohibition, in capitals, with the reason attached.

## Consequences

- The constraint has held across every run, including one where the Judiciary had strong views on the answer and confined itself to ruling that neither answer was soundly established.
- This is the clearest instance in the design of a control that works because it removes a capability rather than adding a check.
- In assurance terms it is separation of duties: the body ruling on soundness cannot author what it rules on.
