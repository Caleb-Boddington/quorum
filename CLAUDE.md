# Quorum

Read this before touching anything in this project. `MEMORY.md` next to this file has the
current state, this file has the rules that don't change often.

## What this is

A deliberation skill: a multi-agent structure for questions where a single confident answer
would probably be wrong. Lives in two places that must be kept in sync by hand, there is no
symlink and no build script:

- `skills/research/quorum/` (`SKILL.md`, `prompts.md`, `report.md`), the copy Claude Code
  actually reads when the skill is invoked.
- `projects/quorum/spec/` (same three files), the git-tracked copy, source of truth for the
  published repo at github.com/Caleb-Boddington/quorum.

**Whenever you edit one, edit the other, then diff them to confirm they match.** Nothing
enforces this automatically.

## No names in decision records

`docs/adr/`, `NOTES.md`'s Decisions and Incidents tables, and `docs/postmortems/` record
what changed and why, never who specifically decided, found, or proposed it. Use "reached",
"rejected", "found by", "prompted by", not a person's name, and not "Claude" or the model
name either. This applies to any new ADR, postmortem, or run-record narrative going forward,
not only to the files already cleaned up on 19 August 2026. Reason: this repo is a portfolio
piece and a person's judgement calls, especially ones where they overrule a recommendation,
read as far more exposing in public than they feel while making them. The README's own
author signature is the one deliberate exception, that is normal project authorship, not a
decision-attribution field.

## Publishing runs

Every run written to `runs/` is a candidate for publication. Before it goes in, per
ADR-0011: classify what it contains. Personal financial detail, health information, someone
else's data, commercial confidence, credentials, none of that leaves the machine. See
ADR-0009, 0010, 0011 and 0012 for the reasoning and the precedents (withhold entirely,
redact in place, or publish as-is, argued case by case, not a fixed rule).

Trial and test runs (like `runs/trial-2026-08-18-sonnet-overnight/`) get the same treatment
as real ones before anything is pushed, even when the questions are synthetic.

## Versioning

Follows major.minor.patch (Apple's convention: no 0.x, a real product starts at 1.0.0).
Major: a structural change to the tiers or the bodies that run at every tier. Minor: a new
capability, or a capability removed, that changes what a run actually does. Patch: a
wording or bug fix that doesn't change behaviour.

Every version bump touches three places together, never just one:

- `spec/SKILL.md`'s `version:` frontmatter field, synced to `skills/research/quorum/SKILL.md`
- `CHANGELOG.md`, patch-notes style, one entry per version, linking to the ADR behind each line
- `README.md`'s version badge

An idea that's trialled and rejected before shipping doesn't get a version bump, it goes in
the changelog's "Tried, not shipped" list under whichever version it was tested against, see
`docs/adr/0014-reject-the-clerk-role.md` for the pattern.

## Git

Remote is `origin`, `https://github.com/Caleb-Boddington/quorum.git`, branch `main`. Commit
messages describe what changed and why in plain sentences, no conventional-commit prefixes,
matching the existing history. Only push when explicitly asked.

## House style

Follows the global writing rules (`CLAUDE.global.md`): no em dashes anywhere they apply, and
they apply to everything in this repo except code and commit messages. Report prose follows
`spec/report.md`'s own rules on top of that, formal register, plain-language short version,
zero jargon in that one section specifically.
