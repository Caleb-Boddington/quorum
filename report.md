# Quorum report

Written after the verdict has been given in chat. It is a record, not the delivery mechanism, never make the reader open a file to find out what Quorum decided.

## Contents

- The look: a public inquiry paper
- How the prose must read
- Hard requirements
- What goes in it
- The short version, and the plain-language rule behind it
- The evidence section
- Visuals
- Structure
- Skeleton

## The look: a public inquiry paper

**The report is a formal record of a deliberation, so it should look like one.** Not a dashboard, not a landing page, not a blog post. A select committee report, a public inquiry paper, a royal commission finding.

That means: **serif body type**, ranged left, generous measure. **Numbered paragraphs** in the findings. **Hairline rules** dividing sections rather than boxes around them. Small caps or letterspaced capitals for section labels. Marginal notes where something needs flagging. Typographic hierarchy doing the work that colour usually does.

It also means avoiding the things that make a page look machine-made. The tells are specific and worth naming, because every one of them is a default that has to be actively refused:

| Tell | Instead |
|---|---|
| Rounded cards with drop shadows | Hairline rules, and whitespace |
| Coloured badge pills | Type: italic, small caps, a marginal note |
| Emoji as section markers | Numbers, or nothing |
| Gradient or tinted backgrounds | One paper colour, one ink colour |
| Sans-serif everywhere | Serif body, sans reserved for tables and labels |
| Every section the same visual weight | The ruling is large; the working is small |
| Centred hero text | Ranged left, like a document |
| Three of everything | Two, or four, or one |

Colour is used for exactly two things: the dissent and the audit record. Everything else is ink on paper. When a page has only two accents, they mean something.

## How the prose must read

Design gets you half of "not machine-written". The other half is the writing, and no amount of serif type rescues text that reads like a model wrote it.

- **No em dashes. Not one.** Comma, full stop, colon or brackets instead. The hyphen joining two words is a different character and is fine. This is the one prose rule here with a measurement behind it: em-dash frequency in preprint discussion sections rose from 4.23% to 11.58% after 2022, an odds ratio of 2.96 (Czuma, arXiv:2606.29540). The rules below are weaker, and one of them is folk wisdom.
- **Vary sentence length hard.** Uniform rhythm is a stronger tell than any individual word.
- **No rule of three by default.** Two items, or four, or one. A tricolon once, if it earns its place.
- **No "it's not X, it's Y."** In any of its forms. The most recognisable rhetorical tic there is.
- **No closing summary paragraph**, and no opening that restates the question.
- **Uneven attention.** Dwell on the interesting finding. Every section carrying equal weight is a machine habit.
- **Admit limits in the text**, not just in the audit box. "That's the part this rests on most thinly" belongs in the prose.
- **Concrete over abstract.** A named source with a date beats "research suggests".

Avoid words chosen for flourish over meaning: delve, underscore, showcase, pivotal, intricate, tapestry, testament, leverage, elevate, unlock, myriad, robust, seamless, holistic, comprehensive, crucial, resonate, landscape, navigate. If one appears, rewrite the sentence rather than swapping a synonym in, synonym-swapping leaves its own fingerprint.

## Hard requirements

**Self-contained.** One `.html` file, no external anything. No CDN scripts, no web fonts, no remote images, no `fetch`. Inline every style. Use system font stacks. It must render identically on a machine with no internet connection, because that is the state it will eventually be opened in.

**Theme-aware.** Define the light palette as custom properties on bare `:root`, then redefine only the colours inside `@media (prefers-color-scheme: dark)`. Give `body` an explicit background colour, never leave it transparent. In dark mode the paper becomes ink and the ink becomes paper; keep the two accents.

**Readable on a phone.** Relative units, `max-width: 100%` on anything that could overflow. Tables and diagrams scroll inside their own `overflow-x: auto` container; the page body must never scroll sideways.

**No invented content.** Everything comes from the run. Do not add a summary the Speaker did not write, and do not soften the dissent to make the ruling look stronger.

**Escape every string that came from outside the run. This is a security requirement, not a formatting one.**

The report quotes text that agents retrieved from the open web. If a page contained `<script>`, an `onerror=` attribute, or an unclosed tag, and that text is written into the HTML unescaped, it executes when somebody opens the report. That is stored cross-site scripting in a file the user shares with other people.

Before any retrieved or quoted external content goes into the page, replace `&` with `&amp;`, then `<` with `&lt;`, `>` with `&gt;`, `"` with `&quot;` and `'` with `&#39;`. In that order, ampersand first, or the replacements corrupt each other.

Three further rules:

- **Quoted external text goes in `<blockquote>` or `<td>` as escaped text.** Never build markup out of it, never interpolate it into an attribute, and never put it inside a `<script>` or `<style>` block.
- **Never write a retrieved URL into `href` without checking its scheme.** Allow `http:` and `https:` only. A `javascript:` URL in an `href` is the same vulnerability wearing a different hat.
- **The page loads nothing.** No external scripts, no remote fonts, no fetch. That is already required for offline rendering, and it doubles as the control that stops an injected reference reaching the network.

Source names, claim text, quoted passages and reject explanations are all external content. Treat the whole evidence table as untrusted input.

## What goes in it

| Section | Source |
|---|---|
| Tier notice | Which tier ran and what it therefore did not check. Never omitted |
| The short version | Six or fewer bullets, to the rules below. What a reader gets if they read nothing else |
| The question | Stage 0 framed question, verbatim |
| The ruling | Speaker, verbatim, in numbered paragraphs |
| Structure diagram | The bodies that actually sat this run |
| Where the branches divided | Speaker |
| Minority opinion | Speaker's dissent, real visual weight, never a footnote |
| What the cross-check found | Speaker |
| **The evidence** | Every load-bearing claim with source, date, rank and status. Mandatory |
| **Audit record** | Comptroller's finding **verbatim**, plus each department's verdict |
| The first move | Speaker |
| The working | Collapsed departmental and branch positions |
| Run record | Date, tier, department count, agent count, reports sent back |

Collapse the departmental and branch detail behind `<details>`. The verdict is what gets read; the working is what gets checked when somebody doubts the verdict.

**The audit record is never collapsed and never edited.** It is reproduced exactly as the Comptroller wrote it, including a NOT SOUND verdict on the ruling sitting directly above it. A report that hides its own audit finding is worse than one with no audit at all, because it looks rigorous while being less honest.

## The short version, and the plain-language rule behind it

Trialled 19 August 2026, added because a run's actual reader, on this project, kept saying
the same thing: could follow half of what was on the page. Not a formatting complaint, a
comprehension one. Full detail can stay dense further down the page, the short version is
the one section that may not be.

**Zero jargon in the short version, not jargon defined in brackets, the everyday word
instead.** A legal test name, an audit status, an acronym, a framework's proper name, none of
these belong here even glossed. If the finding is "the ruling rests on PIDA's qualifying
disclosure test", the short version says "the legal protection for reporting this kind of
thing probably doesn't cover an amount this small" and leaves the citation to the section
below where the reader who wants it can find it.

**One finding per bullet, one idea per sentence.** If a bullet needs "and" to hold two
findings, it is two bullets.

**Say what it means for the reader, not what the process found.** "The audit caught a source
that didn't actually say what it was cited for" beats "load-bearing claim failed
verification." Report the consequence in the language of the decision, not the language of
the run that produced it.

**An analogy is allowed here and nowhere else in the report.** The rest of the document is a
formal record and stays formal. The short version exists specifically so a reader who will
never open the working can still leave understanding the ruling, and a good analogy earns
its place if a plain restatement alone won't land it.

**Six or fewer bullets, hard cap.** If the ruling needs a seventh to be honest, something in
the first six is carrying two ideas and should split, or something belongs in the fuller
sections instead.

## The evidence section

**Mandatory. A verdict the reader cannot check is an opinion with a nice layout.**

Every load-bearing claim gets a row, pulled from the workers' sources lists and the departmental reports.

| Column | Contents |
|---|---|
| Claim | The figure or finding, in a few words |
| Source | Named, linked where a public URL exists |
| Date | Of the data, not of the page. "No date" is an entry, not a blank |
| Rank | Primary · Named dataset · Interested party · Journalism |
| Status | Verified · Unverified · **No independent trace** · Contradicted · Not reached |

**Show the rejects.** A short list of what researchers threw out and why is often the most useful thing on the page. Testing found a widely-repeated industry statistic whose only origin was a condiment brand's advertising campaign; that rejection belongs in the report, not just in the working.

**Mark the interested parties.** Where a source has a stake, say whose. Where an interested party publishes something *against* its own interest, mark that too, it is unusually strong evidence.

**Keep the five statuses apart.** "Could not check", "checked and wrong", and "found no evidence this exists" are three different things. *No independent trace* means the artefact has no footprint anywhere except the claim citing it. A genuinely paywalled study almost always leaves some trace; an invented one leaves none. It is not proof of fabrication, and the row must not say it is.

**Never fill a gap to make the table look complete.** A claim with no date and no traceable source is an entry that says so.

Order rows by how much weight the ruling puts on them, heaviest first. A reader should be able to stop after three rows and know what the verdict is standing on.

## Visuals

Diagrams earn their place when they show something the prose cannot. Inline SVG only, no libraries, no canvas, no external anything. Muted ink-on-paper palette, hairlines, no fills except where a fill carries meaning.

**Always include:**

*The structure diagram.* The bodies that actually sat, labelled with the department names this run convened, so no two reports look alike. Show the Audit Office to one side with a dashed line, because it reports to nobody.

**Include when the run supports it:**

*Evidence strength.* A small horizontal bar per load-bearing claim showing status, verified, unverified, contradicted. One glance tells the reader how much of the ruling is standing on checked ground. This is the single most useful chart Quorum can produce about itself.

*Where the branches divided.* A simple three-column mark showing which branch held which position, and where the Speaker landed. Makes an overruled majority visible instantly.

*Agreement map.* Where several departments touched the same claim, a small grid of who agreed, who disagreed, and who was silent. Silence is often the finding.

*A timeline.* Only where the question has dates in it, deadlines, sequences, windows closing.

*Quantity comparisons.* Only where the numbers are real, verified, and comparable. Never chart an estimate. Never chart three numbers from three different definitions, which is exactly the error the cross-check exists to catch.

Two rules. **Every chart states its source underneath, in the same style as the evidence table.** And **no chart may present unverified data as though it were verified**, use a hairline outline for unverified bars and a solid fill for verified ones, and say so in a key.

## Structure

Top to bottom: tier notice, short version, question, ruling, structure diagram, divisions, minority opinion, cross-check findings, evidence, audit record, first move, collapsed working, run record.

Two sections need visual weight, and they are the only two that get colour: the **minority opinion**, so a reader scrolling past cannot miss that the verdict had a losing side and it was written down; and the **audit record**, so they can see what was checked and whether the ruling stayed inside it. Different accents, they are different kinds of caution.

## Skeleton

Adapt freely; the requirements above are what matter.

```html
<!doctype html>
<html lang="en-GB">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>[Short name], Quorum</title>
<style>
  :root {
    --paper: #f7f5f0; --ink: #1c1b19; --muted: #6b6862; --rule: #d6d1c6;
    --dissent: #6e1f1f; --dissent-bg: #f2e9e6; --audit: #1c4652; --audit-bg: #e8eef0;
    --verified: #2f6b4a; --unverified: #8a6d1f;
  }
  @media (prefers-color-scheme: dark) {
    :root {
      --paper: #17161a; --ink: #e6e2da; --muted: #98938a; --rule: #35323a;
      --dissent: #d99191; --dissent-bg: #241b1b; --audit: #86b6c4; --audit-bg: #16232a;
      --verified: #79c096; --unverified: #d3ae4d;
    }
  }
  * { box-sizing: border-box; }
  body {
    background: var(--paper); color: var(--ink); margin: 0;
    font: 17px/1.62 Georgia, "Iowan Old Style", "Times New Roman", serif;
    padding: 3rem 1.4rem 5rem;
  }
  main { max-width: 41rem; margin: 0 auto; }
  .masthead { border-bottom: 2px solid var(--ink); padding-bottom: 0.8rem; margin-bottom: 0.6rem; }
  h1 { font-size: 1.9rem; font-weight: 400; letter-spacing: -0.01em; margin: 0 0 0.3rem; line-height: 1.15; }
  .standfirst { color: var(--muted); font-style: italic; margin: 0; }
  .label { font: 600 0.68rem/1.4 ui-sans-serif, system-ui, sans-serif;
           text-transform: uppercase; letter-spacing: 0.14em; color: var(--muted); }
  h2 { border-top: 1px solid var(--rule); padding-top: 1.1rem; margin: 3rem 0 1rem; }
  h2 span { display: block; }
  p { margin: 0 0 1rem; }
  .para { display: flex; gap: 1rem; margin-bottom: 1rem; }
  .para .n { font: 600 0.75rem/1.9 ui-sans-serif, system-ui, sans-serif;
             color: var(--muted); flex: 0 0 1.6rem; }
  .para p { margin: 0; }
  .ruling { font-size: 1.05rem; }
  .minority { background: var(--dissent-bg); border-left: 3px solid var(--dissent);
              padding: 1.2rem 1.4rem; }
  .record { background: var(--audit-bg); border-left: 3px solid var(--audit);
            padding: 1.2rem 1.4rem; }
  .record .label { color: var(--audit); }
  figure { margin: 1.5rem 0; }
  figure svg { display: block; max-width: 100%; }
  figcaption { font: 0.78rem/1.5 ui-sans-serif, system-ui, sans-serif;
               color: var(--muted); margin-top: 0.5rem; }
  .scroll { overflow-x: auto; }
  table { border-collapse: collapse; width: 100%;
          font: 0.84rem/1.45 ui-sans-serif, system-ui, sans-serif; min-width: 38rem; }
  th { text-align: left; border-bottom: 1px solid var(--ink);
       padding: 0.35rem 0.7rem 0.35rem 0; font-size: 0.68rem;
       text-transform: uppercase; letter-spacing: 0.1em; color: var(--muted); }
  td { border-bottom: 1px solid var(--rule); padding: 0.5rem 0.7rem 0.5rem 0;
       vertical-align: top; }
  .st { white-space: nowrap; font-weight: 600; font-size: 0.72rem;
        text-transform: uppercase; letter-spacing: 0.04em; }
  .v { color: var(--verified); } .u { color: var(--unverified); } .x { color: var(--dissent); }
  details { border-top: 1px solid var(--rule); padding: 0.8rem 0; }
  summary { cursor: pointer; font: 600 0.9rem/1.5 ui-sans-serif, system-ui, sans-serif; }
  footer { margin-top: 4rem; border-top: 2px solid var(--ink); padding-top: 0.8rem;
           font: 0.76rem/1.6 ui-sans-serif, system-ui, sans-serif; color: var(--muted); }
</style>
</head>
<body>
<main>
  <header class="masthead">
    <p class="label">Quorum · [Tier] · [date]</p>
    <h1>[The question, as a title]</h1>
    <p class="standfirst">[One line: what was asked and what was found]</p>
  </header>

  <p class="label" style="margin:1.5rem 0 0.4rem">Tier notice</p>
  <p style="font-size:0.92rem;color:var(--muted)">[Which tier ran and what it did not check.]</p>

  <h2><span class="label">Section one</span>Findings</h2>
  <div class="para"><span class="n">1.</span><p>[Numbered ruling paragraphs.]</p></div>
  <div class="para"><span class="n">2.</span><p>[…]</p></div>

  <figure>
    <svg viewBox="0 0 560 200"><!-- structure diagram --></svg>
    <figcaption>Bodies convened for this question.</figcaption>
  </figure>

  <h2><span class="label">Section two</span>Minority opinion</h2>
  <div class="minority">
    <p>[The overruled position, at full strength.]</p>
    <p><em>What would have to be true for it to win:</em> […]</p>
  </div>

  <h2><span class="label">Section three</span>Evidence</h2>
  <figure>
    <svg viewBox="0 0 560 160"><!-- evidence strength bars --></svg>
    <figcaption>Status of each load-bearing claim. Solid: verified. Outline: unverified.</figcaption>
  </figure>
  <div class="scroll"><table>…</table></div>

  <h2><span class="label">Section four</span>Audit record</h2>
  <div class="record">
    <p class="label">Comptroller's finding, [SOUND / SOUND WITH QUALIFICATION / NOT SOUND]</p>
    [verbatim, unedited]
  </div>

  <footer>[Tier] · [N] departments · [N] sub-agents · [N] reports sent back · Quorum, [date]</footer>
</main>
</body>
</html>
```
