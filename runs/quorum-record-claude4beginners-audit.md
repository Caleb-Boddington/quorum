# Quorum record: claude4beginners.co.uk audit

Run date 17 August 2026. Tier: FULL, 38 agents. This file is the authoritative record of
what each body actually produced. If anything in a later agent's context disagrees with this
file, this file wins.

> **Redacted before publication, 17 August 2026.** Two passages are withheld and both are
> marked in place, with the reason, at the point they were cut. Nothing else has been altered,
> reworded or reordered: no finding was softened, no verdict changed, and the Comptroller's
> NOT SOUND finding is reproduced in full. What was removed is (1) the specific enumeration of
> an authentication surface whose review is still outstanding, and (2) a personal
> credential-handling incident belonging to the author rather than to Quorum. See ADR-0012.
>
> The redactions are deliberately visible. A run record that quietly omits its awkward parts is
> worth less than one that says where it was cut and why.

---

## The framed question

Does https://claude4beginners.co.uk/, as live on 17 August 2026, (a) cover Claude accurately
and completely, and (b) present visual and interaction design that reads as a deliberately
designed object rather than a generated template, when judged by a stranger arriving cold?

A free beginner's guide to Claude: one self-contained HTML page carrying all its own CSS,
348,810 bytes served, roughly 18,000 words of prose (26,030 words of text including
apparatus), fifteen numbered parts plus About, What has changed and Feedback, all behind
hash anchors on ONE URL, plus two hand-maintained scripts and a database client. Written by
Caleb Boddington, 22, a UK sport media graduate with no professional tech experience moving
into cyber security. It doubles as a portfolio piece employers read via LinkedIn and GitHub.
89 unique visitors on 16 August 2026, the only day ever measured. His girlfriend has read it
and likes it; that is the only reader feedback in existence, and nobody has ever been
observed using it.

Coverage standard set by the author: Parts 00 to 11 beginner-complete, nothing skipped for
being obvious, no jargon unexplained, every platform covered. Parts 12 to 14
power-user-complete, with two suspected gaps named by him: how to get skills from GitHub,
and what a repository is.

Hard constraints, unchangeable, any recommendation breaching one is unusable: no framework,
no build step beyond one Python script, no libraries, no third-party scripts beyond the
database client and the font stylesheet, no analytics, reading works completely without
JavaScript, fixed typefaces (Fraunces, Newsreader) and palette (ink #161A2E, paper #F4F5EF,
oxblood #8C2F39, marker #F2D64B, moss #2F6B5F, nothing grey), no scroll-reveal fades,
prefers-reduced-motion honoured, never scroll-jack. Design thesis: an evening-class handbook,
properly typeset, explicitly not a SaaS landing page.

Prior record: this is the fourth review convened in three days. A five-advisor design council
ruled on 16 August 2026 and its verdict is the design of record. Three of its increments
remain unbuilt: the per-part reader apparatus (present on five of fifteen parts), 6 to 8 drawn
diagrams, and an observation session watching one real beginner, which is the only instrument
anyone has proposed for measuring whether the guide works.

## The six departments

1. Product accuracy. 2. Curriculum and coverage. 3. Visual design. 4. Interaction and
front-end craft. 5. Accessibility and performance. 6. Discoverability and trust.

Anonymisation map used at Stage 6: A = Interaction, B = Product accuracy, C = Discoverability,
D = Visual design, E = Accessibility, F = Curriculum.

---

# Stage 1: the three briefs

**EXECUTIVE.** To every department, three things attached to every finding: exact location in
guide.html (part, section, anchor), estimated edit hours for one self-taught person working
alone, and whether it is one edit or repeats across all fifteen parts. Then: which errors
actually stop a beginner mid-step versus which are cosmetic staleness, and which will go stale
again inside three months and what a recheck costs each time. Does any missing content force
renumbering or reordering, which breaks the pager, saved reading positions and inbound links.
Which fixes are single CSS-variable edits and which need markup threaded through 18,000 words.
What ordering dependency exists between finishing the reader apparatus and drawing the
diagrams, and does either block the other. Which accessibility failures make the site unusable
today as opposed to imperfect. Which discoverability items have lead time outside the author's
control, indexing, cache, image regeneration, because those start first regardless of size.
Finally, from all six: name the one change with the largest reader effect per hour spent, and
separate what must ship before the next deploy from what can wait a month.

**LEGISLATURE.** The definition problem first. "Covers all aspects": departments 1 and 2 must
state their completeness standard before auditing, in writing. Is it Anthropic's own product
surface, what a beginner needs to get one useful outcome, or parity with a competitor course?
These give different verdicts. If the standard is "everything Anthropic ships", say so plainly,
because that standard has no end and expires monthly. "Top tier design": departments 3 and 4
must name whose eye, a designer's, an employer's, or a nervous 45-year-old beginner's, and the
named comparison set. A verdict of "reads generated" is unusable unless you say who it read
that way to. Cost, which nobody has priced: every department gives hours for one self-taught
person and whether it needs the guide rewritten or a line changed, separating "wrong" from
"absent" from "would be nicer". The question behind the question: this is the fourth review in
three days and the reader count is one. Departments 2 and 6, what would one observed beginner
tell us that a fourth expert review cannot? If the answer is "most of it", say so.

**JUDICIARY.** Every department, before findings: state your retrieval receipt, which URL,
fetched when, at what viewport, JS on or off. Every claim about the site's current state must
quote the retrieved text or markup; a claim not traceable to a quoted line will be struck.
Separate fact from judgement per finding, labelled verifiable defect (contradicts a cited
external source or a stated constraint) or aesthetic preference; unlabelled judgements are
treated as taste. For quality claims, state the falsifier: what observation would prove you
wrong. "Reads AI-generated" needs a named comparator page, the specific shared attribute, and
how a reader checks it. Specifically: department 1 cites the Anthropic doc URL and its date for
every menu path, price and feature name, flagging anything unverifiable as unverified rather
than correct. Department 2 gives its source for "what a beginner must contain", with its own
reasoning admissible only if declared. Department 5 runs the measurements, contrast ratios as
numbers against the fixed palette, payload figure, JS-off result, not estimates. Department 6
confirms the no-tracking claim by listing every outbound request the live page makes. All:
name any finding that contradicts the 16 August council verdict and say why it should reopen.

---

# Stage 4 and 5: the six audited departmental positions

Each report is followed by its Audit Office verdict. No report failed audit, so none was sent
back. Every qualification below travels with its report and may not be revised away.

## Department 1: Product accuracy

**Position.** The guide's product facts are accurate. One error must be fixed before the next
deploy; everything else is staleness or absence, and the stamp is the real long-run liability.

WRONG, ship first. Part 02, privacy: the guide says turning off training means past
conversations "won't be" used, "including ones you've already had". Anthropic's privacy
documentation (privacy.claude.com/en/articles/12109829, retrieved 17/08/2026, PRIMARY,
relative timestamp only) says "Your data will still be included in model training that has
already started and in models that have already been trained". The guide is more reassuring
than the truth on the one decision it tells the reader to make deliberately. Two sentences,
one location, 15 minutes.

STALE. Part 02, "Where you switch between Opus and Sonnet". Four models ship: Fable 5, Opus 5,
Sonnet 5, Haiku 4.5. One edit, 5 minutes.

ABSENT, not wrong. The plan table's Pro line omits Cowork, Design, Science, Research and
Microsoft 365. Also absent: Settings > Reflect and Settings > Time and focus (both 09/07/2026),
draft editing (12/06/2026). Claude Mythos 5 is invitation-only and defensibly omitted. One
table edit plus three sentences, 40 minutes.

UNVERIFIED, do not edit. Model choice as a Pro benefit: the pricing page lists
Fable/Opus/Sonnet/Haiku with availability spanning Free while also selling "additional Claude
models" as Pro. Unresolvable without a Free account, 30 minutes to test. Also unverified: the
six-screen Settings list as complete, the Styles names "Concise" and "Formal", and whether the
four Anthropic file skills are pre-enabled.

STAMP. Fifteen identical "Checked against Claude's own apps and help pages: August 2026"
strings, no day, no per-part variation. Anthropic shipped on 37 dated days between 04/05 and
11/08/2026. Replace fifteen strings with one dated line in the header, 45 minutes, and it stops
recurring. Largest reader effect per hour after the privacy fix.

Confidence: high on the privacy error, the model-picker staleness and the pricing omissions,
all quoted from PRIMARY Anthropic pages read 17/08/2026. Low on the four unverified items. The
hours are judgement, not measurement. Six of eleven Anthropic help pages publish relative
timestamps only, so the yardstick itself is undated and the department inherits that drift.

What would change its mind: a Free-account screenshot showing the model picker offering only
one model; an Anthropic revision stating that opting out purges data from trained models, which
would cancel the only must-ship item.

**AUDIT: PASS WITH QUALIFICATION.** Privacy error CONFIRMED, guide Part 02 line 2464 of the
served HTML reads "Turned off, they won't be, including ones you've already had", against
Anthropic's contrary text. Pricing omissions CONFIRMED: claude.com/pricing Pro block reads
"Includes Claude Code, Includes Claude Cowork, Includes Claude Design, Includes Claude
Science... Access to Research, Ability to use more Claude models, Claude for Microsoft 365".
Prices match exactly. Stamps CONFIRMED by independent fetch: exactly fifteen instances, plus
one front-matter variant, no DD/MM/YYYY anywhere. The 37 dated shipping days CONFIRMED by
count. Incognito 30-day retention: the FIGURE is correct but the SOURCE is wrong. Article
8664678 is "Change the model, effort, and thinking settings" and mentions neither incognito nor
retention; the claim is carried by article 12260368.
FAULT: the department resolved a worker disagreement by asserting its researcher "read article
8664678 directly". That article does not cover the claim. The researcher had flagged that
several unnamed support articles were read via search snippet; the department converted that
unnamed uncertainty into a specific direct-read claim it could not have checked. The figure
survives on a different article. Additionally, the report does not state a completeness
standard in writing, which the brief demanded explicitly, and does not separate errors that
stop a beginner mid-step from cosmetic staleness.

## Department 2: Curriculum and coverage

**Position.** Fix what the site promises and cannot deliver, then instrument, then chase the
remaining surface. Trusting the researcher on sequence, not the scrutineer: instrumentation
measures whether a part is read, but cannot tell you a named route is unfinishable, and two of
these defects are unfinishable routes.

Must ship before the next deploy, roughly 6 hours:
1. Part 08 GitHub skills. The site says "plain text files: you download one and upload it".
   Anthropic 12512180 says ZIP the folder, then "+", "+ Create skill", "Upload a skill". Wrong,
   not merely absent. 3 to 4h.
2. Part 11 glossary, which promises "a translation of every word this manual has thrown at you"
   and omits repository, plugin, MCP, Cowork, Git, worktree and CLAUDE.md. 1h, and the largest
   reader effect per hour on this list.
3. Prompt-injection callout duplicated into Parts 08 and 09. Both grant Gmail, Drive and file
   access before the defence arrives in Part 10. 0.5h. Duplicate, never move: moving renumbers
   four parts.
4. Define Cowork at its Part 01 first use. 0.5h.

Within a month, absent power-user surface for Parts 12 to 14: MCP and custom connectors 3h;
Office add-ins for Excel, Word, PowerPoint and Outlook 3h; effort level and extended thinking
2h; Research mode 2h; Claude in Chrome 2h; voice and dictation 1.5h; share and unshare chats
1h; Mac Cowork skill recording 1h; break reminders, monthly recap and active sessions 1h.
Thin: Cowork task walkthrough 3h; web search 1h; Cowork scheduled tasks 1h; chat search 0.5h;
beta labelling 0.5h. No renumbering anywhere; every item appends inside an existing part.

Confidence: verified against retrieved Anthropic article bodies and the delivered HTML, with
the GitHub-skills contradiction and glossary omissions quoted from both sides. Declared as
judgement and unsourced: that a beginner needs all consumer-facing items, since Anthropic
publishes no beginner curriculum. One observed beginner would tell us most of what a fifth
review would; they would not tell us the ZIP route exists.

What would change its mind: evidence the fifteen absences are editorial decisions rather than
oversights. The author's changelog and internal notes were not read.

**AUDIT: PASS WITH QUALIFICATION.** All five load-bearing claims CONFIRMED against an
independent fetch of the live page. Anthropic 12512180 does describe the ZIP route; a skill is
a folder containing SKILL.md, zipped, corroborated independently by the anthropics/skills
repository. The guide's exact wording sits at live line 4501 and adjacent text supplies no
steps, delegating instead to a prompt. The glossary promise is verbatim and runs seventeen
bolded terms; repository, plugin, Cowork, Git, worktree and CLAUDE.md all appear in the guide
and are all absent from it. ONE CORRECTION: MCP is not a valid glossary omission, because the
guide never uses the word, so it cannot breach a promise scoped to "every word this manual has
thrown at you". Zero occurrences of "MCP" CONFIRMED. The injection warning exists once, at
#p8-inject inside Part 10, CONFIRMED, and the slugs are already out of step with the labels, so
the scrutineer's inherited-renumbering point also holds. Both cited academic papers pass the
trace test and nothing in the report depends on them.
FAULT: two scrutineer findings were dropped without mention, the Part 05 obsolescence caused by
the 10 July memory redesign, and the six "Do this now" blocks stopping at Part 04. The first is
a wrong-class item that the report's own logic ranks above every absence it lists. The
completeness standard is not restated in the report and its exclusions (API, Console, Bedrock,
SSO/SCIM, enterprise admin) never appear. Only the first four findings carry a label; the
fourteen-item month list carries none.

## Department 3: Visual design

**Position.** To a working editorial designer's eye, this does not read as generated. The tell
would be token-driven poverty (Starlight: 7 sizes, 12/13/14/16/24/64; Mintlify: Tailwind's
12/14/16/18/24/36), and this page is the opposite: 53 spacing literals, 37 size declarations,
Fraunces at "WONK" 1, hanging-punctuation: first, an feTurbulence grain at opacity .22 under
multiply. Nobody generates that.

Trusting the researcher over the scrutineer, but cutting the programme. The scrutineer is right
that four reviews for one reader is taste-churn, and wrong that only the measure is a defect.
Two findings are self-contradictions in the source, not preferences, and they cost 1.1 hours
combined.

Ship before next deploy, 2.1 hours total:
1. Measure. `--measure: 72ch` computes to 775px against a 768px box, so the cap never binds;
   measured 95, 99, 100, 103, 113, 113 characters per line and an independent average of 114.
   Set 62ch plus the three literals (`.col.wide`, `.pager`, `main max-width: 54rem`). 1 hour.
   Largest reader effect per hour on the site.
2. h4. `.96rem` = 15.36px heading over 19px body, 3.64px smaller than what it heads. 0.1 hour.
3. Plate colours on the contents grid. `.part[data-group="start"] { --plate: #E8DFC6 }` and six
   siblings exist, `data-group` is on `.nav-group` in the markup, yet all eighteen tiles compute
   rgb(234,236,227) and all seven blocks compute identical border-top 1px and padding 20.8px 0.
   The system is built and withheld from the navigation screen. 1 hour.

Defer indefinitely: the 6 to 10 hour scale rebuild across 19 rendered sizes (twelve inside a
4px band, smallest step 1.029x), and the three low-saturation tokens (#5E6375 at 10.9%,
#4A4F63 at 14.5%, #D3D6C9 at 13.7%, against oxblood's 49.7%), which contradict the author's
stated "nothing grey" rule. Both are real. Neither is visible to a stranger arriving cold, and
121 uses rippling through dark mode and print is where a solo author breaks the site.

Confidence: every computed value verified, measured twice independently on the measure.
Contrast all at or above AA, so nothing here is an accessibility fix wearing a design coat.
Declared as judgement: that 62ch is the right target. The 66-character rule is Bringhurst
asserting it, never tested; Dyson and Haselgrove was not retrieved (403). The bound leaned on
is WCAG 2.2 SC 1.4.8 verbatim, "no more than 80 characters", plus Butterick's own 45 to 90.

**AUDIT: PASS WITH QUALIFICATION.** SC 1.4.8 quoted accurately and its Level AAA status
correctly implied. Line 170 `--measure: 72ch` and line 639 `main { max-width: 54rem }`
CONFIRMED; computed main 864px, padding 48px, paragraph 768px, 72ch = 774.97px, so the cap
never binds. The auditor ran its own Range walk inside Part 03 and got 108, 95, 106, 103, 99,
112, 99, 106, 102, a third independent confirmation. h4 CONFIRMED as declared, with some
component h4s computing 13.44px. The seven `--plate` declarations at lines 1009 to 1015
CONFIRMED as existing on `.part[data-group=...]` only, with all seven `.nav-block`s returning
unset. Butterick's "45 to 90 characters" CONFIRMED verbatim.
FAULT, AND IT IS SUBSTANTIVE: the auditor set `--measure` to 62ch in the live page and re-walked
the same paragraphs, getting 98, 80, 91, 91, 100, 87, 92, 89, 89. At 55ch it got 72 to 84. THE
PRESCRIBED FIX LEAVES LINES ABOVE THE 80-CHARACTER BOUND THE RECOMMENDATION RESTS ON. 62ch is
unsourced and, by measurement, insufficient for its own stated standard. Additionally, no
finding carries the required VERIFIABLE DEFECT or AESTHETIC PREFERENCE label, and only one
falsifier is supplied, none for the central quality claim "does not read as generated".

## Department 4: Interaction and front-end craft

**Position.** Ship four small fixes before the next deploy, then stop polishing interaction and
go draw diagrams. Judged by one eye: a hiring manager who tabs through the page on a phone,
because that is the only stranger whose opinion converts.

Both internal disputes checked by the department itself in the served v1.051 markup. Theme
flash: the researcher is right. `</head>` is line 136, `<body>` line 137, the first `<script>`
is line 5956, and the theme block sits inside it. The repaint is structural, not a measurement
question; the scrutineer recorded absent paint entries, which is missing data. No-JS pager: the
researcher is right. `js-paged` gates `.find`, `.platpick`, `.part` and `.plat-body` (lines
360, 394, 785, 881) and never gates `.pager`. The only rule hiding it is
`body.landing .pager { display: none !important; }` (line 731), and `.landing` is set by script.
Shipped markup is `<a class="prev" href="#p0"><span>Previous</span><b></b></a>`, so with JS off
a reader gets a live bordered bar reading PREVIOUS and NEXT with empty oxblood titles under
them.

Ship now, 1.5h total: grid overflow at 320px, `minmax(min(19rem,100%),1fr)`, 0.25h, with two
workers independently measuring scrollWidth 347 at a 320px viewport. `.js-paged` on `.pager`
and `.copy`, 0.5h. Theme code into head, 0.5h. Two `behavior:"smooth"` calls that ignore
reduced motion, 0.25h.

Wait a month: roving tabindex across the four tablists, 2h, genuinely wrong per the ARIA tabs
pattern but no reader has hit it. Focus rings on `.start-grid a` and `.pager a`, 0.5h, cosmetic
since the UA ring still shows. Tile transition parity, absent not broken.

Largest reader effect per hour is the grid overflow, and it must land before diagram work so
SVGs are authored against a layout that holds at 320px. Apparatus and diagrams do not block
each other in either direction. Fourth review, one reader: this is the last interaction pass
that earns its keep.

**AUDIT: PASS WITH QUALIFICATION.** Independent retrieval matched the researcher's byte counts
exactly. Script order CONFIRMED: `</head>` line 136, `<body>` 137, first `<script>` 5956 of
6855 lines, with theme init at line 5990 inside that inline script and nothing in head touching
theme. The repaint is structural. `js-paged` CONFIRMED as appearing only against `.find` (360),
`.platpick` (394), `.part` (785), `.plat-body` (881) plus print and reduced-motion variants,
with no rule gating `.pager` or `.copy`; line 731 and the markup at 5925 CONFIRMED exactly. The
department was right to overrule its scrutineer. Line 275 `minmax(19rem, 1fr)` and line 640
`body { overflow-x: clip; }` CONFIRMED. Two `scrollIntoView({ block: "center", behavior:
"smooth" })` at lines 6413 and 6442 CONFIRMED. Sources clean, nothing load-bearing rests on an
interested party, and the department's "my own retrieval" claim is credible because every line
number it quotes matches.
FAULT: four omissions. No finding carries the required VERIFIABLE DEFECT or AESTHETIC
PREFERENCE label. Falsifiers are one global note rather than one per quality claim. D6, the
reader apparatus present on five parts of fifteen, is absent from both buckets with no reason
given, and it is the exact work the ordering question was about. The scrutineer's unchanged-hash
defect, where a nonsense anchor renders Part 00 while the address bar keeps the bad hash, is not
addressed anywhere.

## Department 5: Accessibility and performance

**Position.** The site passes on the things it was suspected of failing and fails on one thing
nobody suspected. Ship the modal focus trap before the next deploy. Everything else can wait a
month.

Ranking resolved rather than averaged: the sign-in gate does not trap Tab. From the last
control in `.gate`, Tab reaches BODY, and three more Tabs land on `A.board-begin`, whose centre
hit-tests to content entirely behind the fixed overlay. That is SC 2.4.11 Focus Not Obscured
(Minimum, AA) plus 2.4.3, and it strands a keyboard user with no visible focus ring and no
signposted way back. 1.5 to 2 hours, one edit in accounts.js. The scrutineer never opened the
modal, so its "one defect worth fixing" verdict is a ranking made over an untested surface;
that weakens the conclusion, not the finding, and the tab ARIA defect is real.

Ordered: 1. Modal focus escape, SC 2.4.11 / 2.4.3, unusable today, 2h. 2. Focus drops to BODY
on every part change, contents link and pager both, SC 2.4.3, one render() edit covering all 18
parts, 2h. 3. `.copy.done` white on moss at 2.29:1 in dark against 4.5:1, SC 1.4.3, one CSS
line, 0.2h. 4. Input and select borders at 1.35 light and 1.46 dark against 3:1, and they are
the control's sole boundary, SC 1.4.11, swap to a token already at 5.45:1, 0.3h. 5. Margin
contents links 23.1px centre-to-centre against 24px, SC 2.5.8, fails by 0.9px, 0.2h. 6. Twelve
`role="tab"` with zero `aria-controls` and zero `role="tabpanel"`, SC 4.1.2, repeats across 4
tablists and about 30 panels, 2h. Largest reader effect per hour is item 2, one function,
fifteen parts.

The palette is exonerated. Marker never carries text. Oxblood clears 4.5:1 in every role, both
modes. 190.3 KiB landing, 90,976 bytes brotli. All 18 parts render with JS off, reflow clean at
320px on every route.

Confidence: every ratio, byte count, hit-test and activeElement reading measured in Chromium on
the live 17 August build. Declared as judgement: that item 1 outranks item 6, and that the
missing h1 on 17 of 18 routes, plus header and footer nested inside main so there is no banner
and no contentinfo, plus a title that never changes, is the largest orientation gap despite
compelling no success criterion.

**AUDIT: PASS WITH QUALIFICATION.** SC 2.4.11 CONFIRMED as existing at Level AA, but the
department OVER-CLAIMED it: the normative text requires the focused component to be "not
entirely hidden", and a centre hit-test proves only partial obscuring, which is SC 2.4.12 at
Level AAA. SC 2.4.3 carries the finding regardless, so the must-ship item survives its own
citation error. accounts.js VERIFIED independently at 25,434 bytes and 568 lines: zero
occurrences of `inert`, zero `aria-hidden`, zero Tab keydown handler, one keydown listener for
Escape only, guarded by `!REQUIRE_ACCOUNT` which is false so it fires. Lines 94 to 96 set role
dialog, aria-modal true and aria-labelledby on a script-created div, absent from served HTML so
JS-off readers never meet it. `.copy.done { background: var(--moss); color: #fff; }` CONFIRMED;
the auditor computed #FFFFFF on #2F6B5F as 6.20:1, and 2.29:1 is #FFFFFF on the dark-mode moss
#6FB9A7, which the report attributes to dark correctly. SC 2.5.8 CONFIRMED at AA with a 24 by
24 threshold measured centre-to-centre, so 23.1 fails. Twelve tabs, four tablists, zero
tabpanel, zero aria-controls, two SVGs without aria-hidden and zero img elements all CONFIRMED.
WebAIM handling adequate, interest declared, no conclusion resting on it.
FAULT: three specifics. The top-ranked citation exceeds its evidence, as above. The VERIFIABLE
DEFECT and AESTHETIC PREFERENCE labels the researcher supplied were dropped in compression. And
SC 1.1.1 at Level A, on the two unlabelled decorative SVGs, verified real and costed at 0.2h,
was dropped silently while Level AA items were ranked. Relegating the h1 and landmark gap to
the Confidence section was legitimate, because the department declared it, priced it and said
it compels no criterion.

## Department 6: Discoverability and trust

**Position.** The privacy claim holds, and search is not the channel. Both workers measured the
signed-out load independently and got the same four resources: fonts.bunny.net plus three
same-origin scripts. No beacon, no analytics, no cookie. "No tracking pixels, no advertising,
and no analytics script" is TRUE as written. The scrutineer is right that the search results
page is lost and wrong about the conclusion: distribution here is a link pasted into LinkedIn
and GitHub, so the social card IS the search result, and that reorders everything.

Ship before the next deploy, in this order:
1. Verify the deploy. Live is 348,810 bytes with a different inline-script hash from local's
   348,934. The deployed build is not the current source. Nothing below is provable until that
   is reconciled. 0.5h, once.
2. og.png says "Eleven parts", the site ships fifteen, and "Manual" contradicts "Guide". 1 to
   2h, and the only item with real external lead time: Facebook, LinkedIn, X and Slack caches
   take days to weeks, some needing manual re-scrape. Start it first regardless of size.
   Largest reader effect per hour in this remit.
3. Feedback form carries zero `data-netlify` or `netlify-honeypot`, and `/__forms.html` is 404.
   Sole contact route, plausibly silently discarding messages. 0.5 to 1h, once.
4. No mailto, LinkedIn or GitHub link anywhere in the markup. An employer arriving via the
   portfolio has nowhere to go. 0.5h, once.

Then one 45-minute sitting, worth doing only because it is cheap: sitemap.xml plus the Sitemap
line in robots.txt, og:site_name, twitter:title, twitter:description, a wording fix for the
signed-in case, and a licence carve-out for code. Reject: fifteen URLs (6 to 12h, breaks every
inbound link, buys entry to a results page already lost), JSON-LD, per-part social images.

On the fourth-review question: one observed beginner cannot tell us whether the form delivers.
They can tell us whether they would ever paste the link, which is the entire distribution
problem.

Confidence: request list verified by two methods and two workers; header set, image contents,
robots.txt at 23 bytes, sitemap 404, absent form attributes and the byte and hash mismatch all
verified. Declared as judgement: that social sharing outweighs indexing, resting on 89 visitors
with no referrer column in the traffic log. Unverified: whether the form errors or fails
silently, signed-in cookie behaviour, and absolute Google index status.

**AUDIT: PASS WITH QUALIFICATION.** Form finding CONFIRMED: the sole form tag is
`<form class='say' id='sayForm' method='POST' name='feedback'>`, with zero occurrences of
`data-netlify` or `netlify-honeypot`, and `/__forms.html` returns 404. The auditor read
Netlify's current documentation and checked the two alternative registration routes the
researcher might have missed, the hidden static form and the `form-name` hidden input: the page
has the hidden input but NOT the hidden static form, so neither route registers it. The finding
stands. og.png CONFIRMED at 81,259 bytes reading "A BEGINNER'S MANUAL" and "Eleven parts", against
the page's own meta description, board-meta and Extent line all saying "Fifteen parts". Zero
`mailto:`, zero `linkedin`, zero `github.com` CONFIRMED. Both Google quotations CONFIRMED
verbatim on Google's own domain, and the auditor traced the fragment quote to the specific page
the researcher had left unnamed. Absence from search for the bare domain CONFIRMED, with
absolute Google index status correctly left unverified.
FAULT: two. The labels were dropped, so the compressed report carries no VERIFIABLE DEFECT or
AESTHETIC PREFERENCE marking on any numbered item. And "nothing below is provable until that is
reconciled" OVERSTATES: both workers measured the live origin, and the auditor reproduced the
og.png, form markup, robots.txt, sitemap 404 and missing contact links against the live host
without touching the author's local file. A stale deploy means the author cannot safely edit
locally and assume parity; it does not make the measurements unreliable. The department has
conflated the two. Separately, "TRUE as written" on the privacy statement is one notch too high:
neither worker created an account, so the signed-in path is untested, and the researcher itself
said the "one request" heading understates for a signed-in reader. The correct wording is true
for the signed-out load, unverified signed in. The report's own Confidence block says exactly
that, so the Position paragraph contradicts its own hedge.

---

# Stage 6: the six cross-reviews

Six reviewers, each with a distinct lens, each seeing all six reports anonymised as A to F.

## The sceptic

Bets against Report D's finding 1. D asserts `--measure: 72ch` resolving to 775px "against a
768px box", then reports measured lines of 95 to 113 characters in that column, which requires
an average glyph advance of 6.8px or 0.36em at 19px. The sceptic argues no serif sets that
narrow and a realistic 0.48em gives about 84 characters in 768px, so either the 768px box is
the wrong element or the counts came from a wide viewport. It also notes D leans on WCAG 1.4.8,
which is Level AAA.
Strongest: E, for per-item success criteria measured on the live build, finding a defect nobody
suspected and exonerating what it was sent to convict. Biggest blind spot: D, which proves the
page is not generated by counting 53 spacing literals and an feTurbulence grain in the
stylesheet, none of which the cold stranger in the question reads.
ALL SIX MISSED: C found the deployed file differs from local by 124 bytes and a script hash,
and nobody applied that. Only A and C name the artefact they measured; D and F name none. Six
sets of "verified" numbers may describe two different files. Stamp every measurement with URL,
byte length, hash and time, or the reports are not comparable.

## The omission hunter

Nobody reviewed the site as a piece of software that authenticates strangers. The account layer
signs users up, signs them in, resets passwords and stores per-reader progress, all from the
browser. Six reports touched this surface and all walked past it: E opened the sign-in gate and
graded its focus trap, C counted the requests it made. None of them asked the questions that
surface actually raises.

> **[REDACTED, 17 August 2026.]** Four sentences are removed here: an enumeration of the
> client-side authentication calls, the storage arrangement behind them, and the specific
> unanswered questions the finding listed. They are withheld because the finding is
> **unremediated** — as of publication nobody has reviewed that surface, so publishing the
> specific list would amount to a to-do list against a live site. It will be restored once the
> review has happened. Note honestly that this is a speed bump rather than a wall: the site's
> script is served publicly and a determined reader can derive most of it. What is withheld is
> the convenience, and the confirmation that nobody has checked.

The unredacted conclusion stands, and is the reason this was the run's largest finding: the
account layer is the one part of the site everybody treated as fixed rather than as a choice.
The traffic does not require logins, and deleting the feature would delete the entire liability.
It matters more here than on most sites, because the author is applying for cyber security roles
and hands hiring managers this URL.
Strongest: D, the only report answering the generated-or-designed question with a falsifiable
test rather than a fix list, naming its own weakest finding and refusing the 6 to 10 hour
rebuild. Biggest blind spot: C, which owned the data-handling remit, verified the no-tracking
claim on the signed-out load, then parked signed-in behaviour as unverified; the account system
was inside its scope and it stopped at the door.
ALL SIX MISSED: security review, and the prior question of whether accounts should exist.

## The arithmetic checker

Fetched the live page to settle the byte dispute. HOUR TOTALS, which nobody had:

| Report | Ship now | Deferred | Total |
|---|---|---|---|
| A Interaction | 1.5 | 2.5 | 4.0 |
| B Product accuracy | 0.25 | 2.0 | 2.25 |
| C Discoverability | 2.5 to 4.0 | 0.75 | 3.25 to 4.75 |
| D Visual design | 2.1 | 6.0 to 10.0 | 8.1 to 12.1 |
| E Accessibility | 2.0 | 4.7 | 6.7 |
| F Curriculum | 5.0 to 6.0 | 22.5 | 27.5 to 28.5 |
| **Total** | **13.35 to 15.85** | **38.45 to 42.45** | **51.8 to 58.3** |

Excludes the rejected fifteen-URL split. F alone is roughly half the programme.
BYTES SETTLED: live is 348,810 uncompressed, brotli 90,730 measured today. C is exactly right.
E's "190.3 KiB landing" matches nothing served and E's brotli figure is 246 bytes off, so E
measured a post-JS or partial quantity and labelled it page weight. C's 124-byte local gap is
what a version stamp costs, so blocking all four items behind it may be a wasted 0.5h gate.
320px IS NOT A CONTRADICTION: E scoped "every route" to the eighteen part routes; A and D
measured the contents grid on the landing screen, which is not one of them. E is under-scoped,
not wrong.
D'S FIX MISSES D'S OWN TARGET: 62ch is 667px, about 98 characters, still over Butterick's 90 and
over the 80 D quotes from SC 1.4.8. Roughly 50ch hits 80. D's hour buys a fail.
Route count inconsistency: E says both "18 parts" and "fifteen parts" for the same fix; D counts
eighteen tiles; fifteen plus About and Feedback is seventeen.
Strongest: E, every claim carrying a measured value, a criterion and a method, with its ranking
argued rather than averaged. Biggest blind spot: F, whose month list is 22.5 hours, close to
everything the other five ask for combined, and which never prices what happens if none of it
ships.
ALL SIX MISSED: all six claim "largest reader effect per hour" for a different item and no two
share a denominator, so six local maxima are being sold as one global one. Ship-now alone is
roughly fourteen hours and about twenty separate edits to one 349KB file with no tests, by a
part-time author. That is not one deploy. It is a month.

## The framing critic

"Is it correct and does it look designed?" are both properties of the object, and both were
answerable, which is why they were asked. The question that matters is relational: does a
stranger finish it, and can anyone who matters reach the author afterwards? C found no mailto,
LinkedIn or GitHub link anywhere in the markup and ranked it fourth. Under the better framing it
is item one, everywhere, and costs half an hour. That is the test of whether the framing was
wrong. It would have produced different work: C's deploy mismatch and social card, D's
113-character measure, E's focus escape and A's 320px overflow all survive as completion and
conversion defects, while F's month list of fifteen absent features almost entirely dies.
Roughly half the proposed hours evaporate.
Strongest: C, the only report that overturned its own remit rather than executing it, and the
one that found the byte and hash mismatch. Biggest blind spot: F, proposing about 26 hours of
additions to an 18,000-word beginner guide without once asking whether a beginner reaches Part
11, and admitting the changelog was never read, so it cannot distinguish an omission from a
decision.
ALL SIX MISSED: every department found things to ADD. Not one proposed cutting anything. Gaps
are findable and excess is not, so six incentives pointed the same way. Combined, they prescribe
more hours than the author has, on a site with one known reader.

## The practitioner

Six departments have costed roughly twenty hours of edits into one 349KB file with no tests, no
staging, and a deploy that is a human dragging a zip. NOBODY COSTED THE DEPLOY. Every report's
clock stops at "the edit is made", not "the live page was checked and still works".
The first thing a practitioner does is the thing none of them writes down: download the
currently-live file and keep it as the rollback zip, before touching anything. There is no
version control pushing to the host, so the only way back from a bad deploy is a copy you
already had. C found live is 348,810 bytes against local 348,934 with a different inline-script
hash. That is not a tidy-up item inside C's remit; it is the fact that the file six departments
propose editing is not the file serving readers. Deploy the local source and you silently
revert whatever is in production, and nobody knows what it was.
Second, do not ship this as one zip. A's minmax at 320px, D's 62ch measure plus three literals,
and E's reflow and contrast measurements all touch the same layout. E verified 320px reflow on a
build that A and D's edits invalidate. Ship in slices of related CSS, check the live page after
each, keep the previous zip.
Third, the order is wrong everywhere. Content fixes (B's privacy error, F's ZIP route) are
text-only, zero layout risk, and independently deployable. They go first, alone, as a rehearsal
of the deploy itself.
Strongest: C, the only report that checked what is actually deployed against what is on disk.
Biggest blind spot: D, which defers the scale rebuild because "121 uses rippling through dark
mode and print is where a solo author breaks the site", then proposes changing `--measure` plus
three hard literals and switching on a plate-colour system that has never once rendered. It
names the exact failure mode and then walks into it, with no way to view dark mode or print
before the zip lands.
ALL SIX MISSED: the deploy is the riskiest step in the programme and it is uncosted, unrehearsed
and unrecoverable. A fifth review is not the risk here. One sitting of twenty edits followed by a
zip drag is.

## The future reader

August 2027, what actually happened. He stopped editing in October 2026, somewhere around the
third course instalment and the first A+ exam. The site never said so. An employer opened it in
spring 2027, hit Part 08's skills instructions, and found them wrong against the live product.
The portfolio piece became evidence he does not maintain things.
The fix that broke something else is B's. Collapsing fifteen per-part "August 2026" strings into
one dated header line removes the only per-part audit trail on the page. After that, a single
edit to Part 03 refreshes the date for all fifteen, so the header asserts currency for fourteen
parts nobody opened. The redundancy B called a liability was the honest part.
F's 25-hour month list shipped at zero. Nobody does that unpaid while sitting exams. F's ZIP
route rewrite was itself stale by spring, because F treated Anthropic's current upload UI as
fixed background while its own report counted 37 shipping days in 100.
Five of six reports measured pixels: 347px scrollWidth, 113 characters, 2.29:1. Durable,
permanent, and not what decided anything.
Strongest: C. Biggest blind spot: A, which optimises one hiring manager on a phone while C shows
there is no mailto, LinkedIn or GitHub link in the markup, polishing the experience of a reader
who cannot reach the author, then declaring review closed.
ALL SIX MISSED: the guide has no way to fail loudly and no way to end. No analytics is fixed, so
a broken font host, a dead form or a year of drift are all silent. Not one report proposed the
cheap honest move: a dated "written August 2026, unmaintained since" line the author can set
once and walk away from. Every report assumed continued authorship.

---

# Unresolved audit objections travelling to the branches

No report failed audit, so none was sent back. Six reports carry PASS WITH QUALIFICATION and
every fault above travels attached. The four that bear most directly on the ruling:

1. **Department 3's prescribed measure fix is insufficient by measurement.** Its own auditor set
   62ch on the live page and got lines up to 100 characters, against the 80-character bound the
   recommendation cites. The arithmetic cross-reviewer independently computed the same and put
   the correct figure near 50ch. Two bodies, agreeing, against the department.
2. **Department 5 over-cited its top finding.** SC 2.4.11 requires the focused component to be
   entirely hidden, and a centre hit-test does not establish that. SC 2.4.3 carries the finding,
   so the defect survives but the criterion does not.
3. **Department 6 conflated a stale deploy with unreliable findings.** Its auditor reproduced
   every measurement against the live host without touching the local file.
4. **Every department dropped the required VERIFIABLE DEFECT / AESTHETIC PREFERENCE labels** in
   compression, except in part Department 1 and 2. The Judiciary demanded them explicitly, so
   any branch treating an unlabelled item as established fact is doing so without the marking the
   brief required.

Also carried: Department 1 attributed a correct figure to an article that does not contain it;
Department 2's MCP glossary item is invalid because the guide never uses the word; Department 4
dropped its own researcher's apparatus finding without explanation; Department 5 dropped a Level
A criterion while ranking Level AA ones.

# Material gathered at Stage 0 and deliberately withheld from the departments

Passed to the branches now, clearly labelled, because the omission hunter's finding turns on it.
This is UNAUDITED documentation written by the author, not a finding of this run, and no
department or auditor has checked it:

- The project's own notes state that the relevant database protections are configured. Self-
  authored, and not checked by anybody this run.
- The project keeps a `SECURITY.md`, described in its own instructions as a record of an earlier
  scanner's findings and what was done about each, indicating some prior security review took
  place.

> **[REDACTED, 17 August 2026.]** A third item is removed: it summarised a credential-handling
> incident recorded in the author's private standing instructions, which are not part of this
> repository and were never intended to be published. The incident was handled at the time. It
> is withheld because it is personal operational history rather than evidence about Quorum, which
> is the same test ADR-0010 applied to the withheld personal run.

The omission hunter's point stands regardless: no department in THIS run examined the
authentication surface, and none of the above has been verified this session.
