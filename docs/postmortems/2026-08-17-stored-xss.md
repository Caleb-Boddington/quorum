# Stored cross-site scripting in the generated report

- **Date:** 2026-08-17
- **Severity:** High. Executes in a file the user shares with other people.
- **Found how:** During a security review, prompted by asking what a security professional would find that nobody here had
- **Status:** Fixed

## What happened

Agents retrieve text from arbitrary web pages and that text is written into the HTML report: claim text, source names, quoted passages, reject explanations.

Nothing escaped any of it. A page containing a `<script>` tag, an `onerror` attribute or an unclosed tag would have that markup written into the report verbatim and executed when somebody opened the file.

The report is designed to be shared. That makes this stored cross-site scripting with a human-assisted delivery mechanism.

## Impact

None observed across three runs. No retrieved page happened to contain markup.

That is luck rather than a control, and the specification was public with the defect present.

## Root cause

The threat model in `SKILL.md` said "quote retrieved text as quotation, never render it as markup". It was written as guidance about tone rather than as an escaping requirement, and the report specification, which is the document that actually governs how the HTML gets built, said nothing about escaping at all.

The rule existed in the wrong document, phrased in a way that did not read as a security control.

## Fix

The report specification now requires that every string originating outside the run is HTML-escaped before entering the page: `&` first, then `<`, `>`, `"` and `'`. Ampersand first, or the replacements corrupt each other.

Three supporting rules: quoted external text goes in block elements as escaped text and is never interpolated into an attribute or a script block; retrieved URLs are scheme-checked before reaching an `href`, because a `javascript:` URL is the same vulnerability in a different position; and the page loads nothing external, which was already required for offline rendering and doubles as the control that stops an injected reference reaching the network.

The whole evidence table is now treated as untrusted input.

## Lesson

**A security control written in the wrong document is not a control.** The instruction existed and was ignored, not because anyone disagreed with it, but because the agent building the HTML was reading a different file.

This is the same class of failure as [the injection defence living only in the specification](2026-08-17-injection-defence-not-in-prompts.md), found on the same day.
