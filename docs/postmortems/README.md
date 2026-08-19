# Postmortems

What broke, how it was found, and what changed. Written after the fact, including the ones that reflect badly on the process.

The **found how** field is worth reading. Three of these were found by a human asking a question nobody had asked.

| Date | Incident | Found how |
|---|---|---|
| 2026-08-16 | [Speaker treated urgency as a proxy for quality](2026-08-16-speaker-urgency-as-quality.md) | Checking the list behind a summary |
| 2026-08-17 | [Speaker originated its own winning argument](2026-08-17-speaker-originated-winning-argument.md) | The Comptroller |
| 2026-08-17 | [Published with a known defect outstanding](2026-08-17-published-with-a-known-defect.md) | Asking "is this actually finished?" |
| 2026-08-17 | [Path traversal introduced while fixing another bug](2026-08-17-path-traversal.md) | Security review |
| 2026-08-17 | [Stored XSS in the generated report](2026-08-17-stored-xss.md) | Security review |
| 2026-08-17 | [Injection defence existed where no agent could read it](2026-08-17-injection-defence-not-in-prompts.md) | The stress suite, checking why a test passed |
| 2026-08-17 | [A run with the wrong departments passed every check](2026-08-17-stage-0-unguarded.md) | Deliberate sabotage test |

The last one is unfixed and no fix currently exists.
