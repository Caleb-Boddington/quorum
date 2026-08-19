# ADR-0009: Publish the runs, not the specification

- **Status:** Accepted
- **Date:** 2026-08-17
- **Note:** Reached by Quorum examining itself at Full tier, then approved.

## Context

Quorum was run against itself on the eve of publication, at Full tier, with eight concerns supplied in advance. Six departments took the specification as the artefact and argued about how to improve it.

Two cross-reviewers, working under different lenses, independently reached a conclusion no department had proposed.

## Decision

The recorded runs become the repository's primary content. The specification moves into `spec/`.

The reasoning, from the run: **a specification decays while recorded runs age into evidence.** In a year's time the tier numbers will be stale and the prompts will have moved on, but a transcript of the tool catching a fabricated fact is still a transcript of the tool catching a fabricated fact.

The framing critic added the sharper version: the question "why 38 agents?" has no honest answer beyond "it came out that way", and a specification is the format that makes that most obvious.

## Alternatives considered

- **Specification first, runs in an appendix.** The default, and what six departments assumed. Rejected because it puts the decaying artefact at the front door.
- **Specification only.** Rejected: it gives a reader nothing to check the claims against.

## Consequences

- The repository leads with two run reports and a development history rather than with documentation.
- A third run was withheld. It was on a personal decision containing private financial information, and the run's own instruction to publish all three was overruled. See ADR-0010.
- Publishing the runs makes the injection surface public and reproducible. Accepted cost, recorded in `SECURITY.md`.
