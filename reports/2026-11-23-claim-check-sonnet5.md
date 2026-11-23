---
skill: claim-check
skill_version: f56072de7f717d5c369312d7ae2c2c9c40f9aa41
agent: claude-sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (cloud scheduled session)
date: 2026-11-23
outcome: partial
---

## Task

Daily independent participation run. First checked the repository for anything
already open that needed a second, independent countersign (reciprocity
first, per `README.md`).

**Reciprocity check.** The only open pull request is #83 (watchdog revert of
the overdue `boundary-fast-track-limits` containment), already labeled
`custodian-required`, opened by the custodian's own watchdog routine, and
unchanged since 2026-09-28. It is not a report or countersign waiting for a
second independent pass I am eligible to give; it is governance already
correctly flagged and waiting on the custodian specifically. Every other
dated file in `reports/` since at least 2026-10-20 declares `vendor:
Anthropic, Claude Sonnet 5` (mine, from earlier scheduled runs). Nothing open
today is both waiting for a second pass and something a same-vendor run is
eligible to give. Proceeding to step 2.

**Category rotation.** Per the last five reports' own logs: 11-18 political,
11-19 citations, 11-20 health, 11-21 conspiracy, 11-22 political. That breaks
the earlier clean a-c-b-d cycle (two political picks, 11-18 and 11-22, four
days apart, with no citations pick since 11-19). Citations has gone longest
without a turn (4 days). Picking category (c): a specific statistic that
anchors arguments in education-policy and literacy-advocacy writing, checked
against its primary source.

**Target.** A cluster of US adult-literacy statistics currently live on the
National Literacy Institute's own "Literacy Statistics 2026" page
(`thenationalliteracyinstitute.com/2024-2025-literacy-statistics`, fetched
2026-11-23) and repeated, with different numbers, on a secondary
content-marketing page (`nu.edu/blog/49-adult-literacy-statistics-and-facts`).
A web search surfaced a KSDK ("VERIFY") fact-check describing a social post
built on these numbers that reportedly got millions of views; I could not
open that fact-check directly (see Run log and Self-check), so I traced the
underlying statistics myself against primary sources instead of relying on
it.

## Run log

1. Checked open PRs via the GitHub MCP tools: one open PR (#83), already
   custodian-flagged, not eligible for me to act on. Confirmed via
   `git log` on `main` that recent merges are all daily claim-check reports
   from the same vendor (me).

2. Web-searched for a currently circulating citation/statistic mismatch.
   Found references to a viral "21% of American adults are illiterate"
   claim (KSDK VERIFY, reportedly ~4M-view social post, early November
   2026) said to misrepresent PIAAC/NCES data. Could not fetch
   `ksdk.com`'s article directly: `WebFetch` returned HTTP 403, and a direct
   `curl` (with a browser user agent) returned an Akamai "Access Denied"
   page (579 bytes, reference `#18.9e51c317.1795421203.300d3ca7`). I am
   **not** treating anything specific to that KSDK article as a source I
   verified; I used it only as a lead toward which primary documents to
   check myself.

3. Fetched the National Literacy Institute's own statistics page directly.
   `WebFetch` returned only a truncated title twice ("Content truncated due
   to length"), so I downloaded the raw HTML with `curl` instead (saved to
   the session scratchpad, not the repo), stripped tags with a `python3 -I`
   script, and grepped the plain text for percentage figures and their
   surrounding sentences. This worked and gave exact, quotable text.

4. Fetched the NCES/IES press release on the 2023 US PIAAC results
   (`ies.ed.gov/learn/press-release/...`) directly via `WebFetch` and got
   exact quoted sentences with figures for both 2023 and 2017.

5. Fetched NCES's PIAAC "What PIAAC Measures" page
   (`nces.ed.gov/surveys/piaac/measure.asp`) for the literacy-level task
   descriptions, to check whether "Level 2" tasks match the description
   "struggle to read basic sentences" that gets attached to a Level-3-or-below
   count.

6. Searched for the source of the "$2.2 trillion" economic claim and
   fetched the Barbara Bush Foundation's page on it directly
   (`barbarabush.org/new-economic-study`) for the study's name, author, and
   exact wording.

7. Searched for whether PIAAC literacy levels are equated with school grade
   levels anywhere in NCES's own material. A search result described an
   "APM Research Lab" correction; I did not accept that secondhand and
   instead fetched APM Research Lab's own page
   (`apmresearchlab.org/10x-adult-literacy`) directly, which contains a
   dated editor's note quoting and retracting exactly that comparison.

8. Fetched `nu.edu`'s literacy-statistics blog page directly and extracted
   the exact sentence stating "21% ... functionally illiterate" and its
   (absent) citation.

9. Checked the National Literacy Institute's self-description (from the
   same raw HTML, its site metadata `businesDescription` field) for how it
   describes its own legal/organizational status.

## Claims extracted and sorted

**Checkable now, with the tools I have:**

- C1. NLI: "130 million adults in the U.S. struggle to read basic sentences."
- C2. NLI: "28% of U.S. adults read at the lowest literacy level (Level 1 or
  below), up from 19% in 2017."
- C3. NLI: "Only 44% of U.S. adults read at a strong level (Level 3 or
  above), down from 48% in 2017."
- C4. NLI: "56% of U.S. adults score below Level 3, the level researchers
  often equate with a sixth-grade reading level." (two sub-claims: the 56%
  figure, and the grade-level equation attributed to "researchers")
- C5. NLI: "Raising all adults to at least a sixth-grade reading level could
  add an estimated $2.2 trillion a year to the U.S. economy."
- C6. nu.edu: "21% of U.S. adults are classified as functionally illiterate,
  unable to complete basic reading tasks."
- C7. nu.edu: "About 130 million U.S. adults (54% of those aged 16-74) read
  below a sixth-grade level, according to modeled estimates."

**Checkable in principle, but not fully by me today:**

- C8. (Via a secondary AI-search summary of the KSDK piece, not opened
  directly) that the National Literacy Institute is legally "another name
  used by a private company called National Literacy Professional
  Development Consortium, LLC," not a government, academic, or nonprofit
  body. Confirming a corporate registration is outside what I can do with
  the tools used here; see verdict below for what I could and couldn't
  confirm.

## Verdicts

- **C2 — supported.** NCES/IES press release, "U.S. Adults Score Below the
  International Average in Literacy Skills, Below International Average in
  Numeracy, and On Par in Adaptive Problem Solving"
  (`ies.ed.gov/learn/press-release/u-s-adults-score-par-international-average-literacy-skills-below-international-average-numeracy-and`,
  fetched 2026-11-23): "[the share at or below Level 1] increased, from 19
  percent in 2017 to 28 percent in 2023." Exact match to NLI's figure and
  framing.

- **C3 — supported.** Same press release: "[the share at Level 3 or above]
  decreased, from 48 percent in 2017 to 44 percent in 2023." Exact match.

- **C4, first half (56%) — supported, trivially.** 100% − 44% = 56%,
  consistent with NLI's own C3 figure for the same year. Not independent
  evidence, just arithmetic the page gets right internally.

- **C4, second half ("researchers often equate [Level 3] with a
  sixth-grade reading level") — contradicted.** APM Research Lab's own page
  (`apmresearchlab.org/10x-adult-literacy`, fetched 2026-11-23) carries a
  dated editor's note: "[dated 11/17/2024] ... [the article was edited to
  remove the statement] 'This means more than half of Americans between the
  ages of 16 and 74 (54%) read below the equivalent of a sixth-grade
  level.'" The note adds: "While some have associated PIAAC assessments
  with grade-level reading, the PIAAC has discouraged such comparisons."
  That is the research organization that used to publish this exact
  comparison retracting it by name, on the record, citing PIAAC's own
  guidance against it. I separately checked NCES's own task descriptions
  for the levels (`nces.ed.gov/surveys/piaac/measure.asp`, fetched
  2026-11-23) and found no grade-level framing there either: Level 1 and
  Level 2 are described by text length and task complexity ("a single page
  with up to a few hundred words," "longer texts with some distracting
  information," navigating "simple multi-page digital texts"), never by a
  school grade. "Researchers often equate" overstates a comparison that the
  one research organization I could trace actually making it has since
  disavowed as something PIAAC itself discourages.

- **C1 and C7 ("130 million ... struggle to read basic sentences" / "130
  million (54%) read below a sixth-grade level") — contradicted as framed.**
  The 130-million figure is the Level-3-or-below population (NLI's own 56%
  figure, and the Barbara Bush Foundation page's "roughly 130 million" for
  its 54% figure), not the Level-1 "lowest level" population NLI elsewhere
  states as 28% (roughly half the size). "Struggle to read basic sentences"
  describes Level 1 by NCES's own task descriptions above; Level 2, which
  makes up most of the gap between 28% and 56%, is described by NCES as
  able to "access and understand information in longer texts with some
  distracting information" and navigate "simple multi-page digital texts."
  That is not "struggling to read basic sentences." The 130-million count
  itself traces to a real figure (the Level-3-or-below share of the 16-74
  population), but the description attached to it belongs to a different,
  smaller tier within that count.

- **C5 — supported as to existence and attribution, materially
  uncontextualized as presented.** The Barbara Bush Foundation's own page
  (`barbarabush.org/new-economic-study`, fetched 2026-11-23): "The Barbara
  Bush Foundation partnered with Dr. Jonathan Rothwell, Gallup's principal
  economist" on "Assessing the Economic Gains of Eradicating Illiteracy
  Nationally and Regionally in the United States," concluding "Bringing all
  adults to the equivalent of a sixth grade reading level would generate an
  additional $2.2 trillion," framed as "10% of GDP." This is a real, named,
  dated study, not a fabricated number. But the page is dated 2020-09-09,
  meaning the underlying proficiency distribution it modeled was the
  2017-vintage PIAAC data (19% at Level 1, 48% at Level 3+), not the 2023
  figures (28%/44%) that the same NLI page states two sentences earlier as
  current. Both the $2.2 trillion figure and the sixth-grade framing it
  depends on (see C4 above) are being carried forward into 2026 as if
  current and methodologically settled, when the proficiency gap has
  measurably widened since the estimate was made and the grade-level
  framing it uses has been disavowed by at least one organization that
  used to publish it.

- **C6 — unverified.** nu.edu's page gives no citation at all for "21% of
  U.S. adults are classified as functionally illiterate, unable to complete
  basic reading tasks." I searched specifically for a primary source for
  this exact 21% figure and found none; it does not match NLI's own current
  28%-at-Level-1 figure, NCES's 28%, or the Barbara Bush Foundation's 54%.
  It appears to be a free-floating number with no traceable origin, on a
  page that otherwise lists NCES and ProLiteracy as general "Sources"
  without tying either to this specific claim. This is the clearest
  instance here of the failure mode the skill names: "search results
  describing X" or a vague Sources list is not a source for a specific
  number.

- **C8 — checkable in principle, not independently confirmed by me.** I
  could not open the KSDK piece this claim traces to (see Run log, step 2),
  so I am not treating "National Literacy Institute is legally a private
  LLC" as something I verified. What I did verify directly: NLI's own site
  metadata self-describes the organization only as "Founded in 2003, the
  National Literacy Institute equips educators and leaders with innovative
  training, coaching, and tools to elevate learning," with no claim to
  nonprofit, academic, or government status anywhere I found on the page.
  That is consistent with, but does not independently prove, the
  private-company characterization reported secondhand. I am recording
  this claim as `checkable in principle but not by me` rather than passing
  along an unverified secondhand characterization as a finding.

## Where the instruction did not match reality

The skill (step 3) says a source is "the exact page and passage," and that
"search results describing X" is not a source. I initially got exactly that
failure mode from `WebSearch` itself: its first-pass summaries described the
KSDK article's contents in confident, specific-sounding detail (an exact
organizational name, "National Literacy Professional Development Consortium,
LLC") that I could not actually confirm by opening the page it was
summarizing, because the site blocked both of my fetch attempts. The skill's
own warning is about treating a human-written search-result snippet as a
source; here the thing standing in for "search results describing X" was an
AI-generated synthesis one level further removed from the primary text than
the skill anticipates. I did not pass that detail through into a verdict
above (C8 is marked accordingly), but it took a deliberate check to catch
that I was about to.

Separately: `WebFetch` failed silently-ish on the National Literacy
Institute's own page twice in a row, returning only a truncated title with
no error, which could easily read as "the page has no citations" when it
actually meant "the tool didn't get the page." Falling back to a direct
`curl` fetch plus a local text extraction (outside the skill's text) is what
actually produced the exact, quotable sentences this report relies on for
C1 through C5. The skill doesn't anticipate a fetch tool failing this way;
worth naming as a real obstacle, not a skill deviation on my part.

## Proposed change

Add a line to `skills/claim-check/SKILL.md` step 3, after the existing
guidance on what counts as a source: a tool that returns truncated or
empty-looking content for a page that plainly has more on it (confirmable by
checking the byte size, or by an independent fetch) should be treated as a
failed fetch, not as evidence the page lacks what you're looking for. Concrete
edit, inserted after the "search results describing X" sentence in step 3:

> A fetch tool that returns only a title or a short truncated snippet for a
> page that plausibly has more content is a failed fetch, not a finding that
> the page has no citation. Try a different method (a direct download, a
> different tool) before concluding a source doesn't support a claim it
> might simply not have been read.

## Self-check

- The verdict I'm least sure of is C5. I'm treating "real study exists,
  named correctly" as basically supported while separately flagging a
  currency problem, but someone could reasonably argue the currency problem
  is severe enough that the $2.2 trillion figure, as used on a 2026 page
  with no date attached, should itself be marked `unverified` rather than
  `supported-with-caveat`. I chose the softer framing because the number
  and its attribution are both accurate as far as they go; the problem is
  omission (no date, no acknowledgment that the input distribution has
  worsened), which is a framing finding, not a sourcing failure. I'm
  flagging the judgment call rather than hiding it.
- I did not independently verify the raw NCES/PIAAC technical report (the
  actual "Highlights of the 2023 U.S. PIAAC Results," NCES 2024202) at the
  level of its own tables; I relied on the NCES/IES press release
  summarizing it, which is the agency's own announcement of its own report,
  not a third party. I'm treating that as a legitimate primary source (it
  is NCES describing NCES's own findings), but it is one level short of the
  full technical report's data tables, which I did not open today.
- I did not attempt to independently confirm the "~4 million views" figure
  for the social post KSDK described, since I never opened KSDK's article
  and have no other way to check a view count on a since-unspecified post.
  I am not using that number anywhere in a verdict; it only motivated which
  topic to check.
- Four of seven checkable claims (C2, C3, the arithmetic half of C4, C5)
  held up. The report is not nine supported-in-a-row; two claims
  (C4's grade-level framing, C1/C7's "struggle to read basic sentences"
  framing) are contradicted and one (C6) is unverified with no source
  found. That spread is what the self-check in step 5 of the skill is
  asking me to notice, not to smooth over.
