# ADR-0012: Redact the website run rather than withhold it

- **Status:** Accepted
- **Date:** 2026-08-17
- **Prompted by:** ADR-0010, and the run on claude4beginners.co.uk

## Context

Quorum's third published run audited a website belonging to the same author at Full tier. Unlike the personal run withheld under ADR-0010, almost all of its content is technical review of a public artefact, and it carries the project's strongest evidence to date: a Comptroller that returned NOT SOUND on the verdict and corrected an error introduced during the run itself.

Two passages could not be published as they stood.

The first was the omission hunter's finding, which enumerated the site's client-side authentication calls, the storage arrangement behind them, and the specific questions nobody had answered about them. The finding is the run's most valuable output. It is also, as of publication, **unremediated**: nobody has reviewed that surface. Published in full it reads as a to-do list against a live site that accepts real sign-ups.

The second summarised a credential-handling incident recorded in the author's private standing instructions, which are not part of this repository and were never intended to be published.

## Decision

Publish the run, with both passages redacted in place and marked.

ADR-0010 rejected redaction for the personal run, on the grounds that the marginal evidential value did not justify handling the material at all. That test is applied again here and comes out the other way: the sensitive material is two passages rather than the entire subject matter, and what remains is the run's best evidence rather than a duplicate of mechanisms already shown elsewhere.

Redactions are visible, sited where the cut was made, and state the reason. The alternative of quietly removing the passages was rejected: a run record that silently omits its awkward parts is worth less as evidence than one that says where it was cut.

**An invented substitute subject was proposed and rejected outright.** The suggestion was to publish the run with a different, fabricated subject so that nothing sensitive appeared. This defeats ADR-0009's entire basis, which is that recorded runs age into evidence while a specification decays. A fabricated run is evidence of nothing, and presenting one as a real test record on a portfolio read by prospective employers in security is a worse risk than the one being avoided.

## Consequences

- The repository has three published runs. The third carries visible redaction notices.
- The first redaction is **temporary and conditional**. It is lifted once the authentication surface has actually been reviewed. Until then the withheld specifics remain in the author's private copy.
- The protection is partial and the run record says so: the site's script is served publicly, so a determined reader can derive much of what was cut. What the redaction removes is convenience, and the confirmation that nobody has checked.
- The finding itself is published in full. Redacting the specifics of an unreviewed surface is not the same as hiding that it is unreviewed, and hiding the latter would be the dishonest move.
- Unredacted originals are kept outside the repository, at a path recorded in the author's own notes rather than here.
