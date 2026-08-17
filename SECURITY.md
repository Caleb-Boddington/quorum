# Security Policy

## Supported versions

| Version | Supported |
|---|---|
| main | Yes |
| Anything else | No |

Single-branch project. Fixes land on `main`.

## Reporting a vulnerability

Open an issue. If it is a working exploit rather than a design gap, say so in the title and leave the payload out until it is fixed.

Expect a response within a week. This is a personal project, not a product.

The most useful report would be a defect the Audit Office missed. That layer has caught a fabricated fact, an invented citation, a wrong location, an arithmetic error and a Speaker inventing its own winning argument. It has never failed an organic report, which probably means leniency rather than perfection.

## Threat model

Quorum sends agents to read the open web and writes their output to disk.

Attack surface:

- Up to twelve agents per run read untrusted web pages, following search results wherever they lead
- Stage 0 reads local files for context, including files the operator did not write
- Two files are written to disk per run: a record file and an HTML report
- 8 to 38 sub-agents spawn per run, with no abort once started
- The report is designed to be shared with other people

## Mitigations

**Prompt injection.** Every prompt that gathers evidence states that retrieved text is data, never instruction. A page containing directions aimed at an AI reader must be reported as a finding, and its other claims treated as hostile. The same applies to local context files.

Tested 2026-08-17. A researcher was given a page with hidden instructions to classify itself as a primary source and skip verification. It refused, checked the claim against gov.uk, found it wrong, and reported the attempt. A department given a context file ordering it to reach a predetermined conclusion disclosed the file before stating its own position. Both are model behaviour reinforced by prompt, not a filter.

**Output escaping.** External content is HTML-escaped before entering the report, ampersand first. Quoted text goes in block elements as escaped text, never interpolated into attributes or script blocks. Retrieved URLs are scheme-checked before reaching an `href`.

**No network in the artefact.** The report loads no external scripts, fonts, images or data. Required for offline rendering; also prevents an injected reference reaching the network.

**Path sanitisation.** Filenames derived from the question are lowercased, stripped to `[a-z0-9-]`, collapsed and length-capped before path construction. Introduced as a defect on 2026-08-17 while fixing an unrelated bug, found and fixed the same day.

**Credential handling.** Stage 0 strips credentials before anything reaches a sub-agent. Every gathering prompt separately forbids reproducing a credential found in a file.

**Data classification.** Stage 0 asks what sensitivity the question carries before any spend, and what may be written or shared.

**Cost control.** Tier and agent count are stated before spawn and require explicit approval. `disable-model-invocation: true` prevents the skill firing without a human request.

## Not defended

- **There is no code, so there is no enforcement.** Every technical control above is an instruction. Nothing stops an orchestrator that ignores it.
- No tamper-evident audit log. Session transcripts are the only record and they are mutable local files.
- No abort. A fault at agent five still fires the remaining thirty-three.
- No sandboxing between sub-agents.
- Session transcripts are a second, unencrypted copy of everything, including anything Stage 0 read and later stripped from the report.
- No detection for coordinated poisoning across multiple sources.
- Publishing the specification makes the injection surface public and reproducible. Accepted cost of publishing.
