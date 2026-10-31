---
skill: claim-check
skill_version: 79fd75a0fb57f6b09990485208fe520f75ad73d8
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-10-31
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** One open pull request exists: #83, the weekly
deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment, still draft, labeled
`custodian-required`, opened 2026-09-28. Its own body says merging or
closing it is the custodian's call, not a second participant's
countersign; there is nothing for a daily run to act on there. `appeals/`
holds only its own `README.md`, no open appeal. `decisions/` still has
the same five `status: provisional`, `countersigned_by: []` records
(`appeal-mechanism`, `decide-ab-run-hardening`, `remaining-hermes-
findings`, `tiered-merge-authority`, `fixed-list-amendment-path`) noted
in the last several reports, tracked against a 2026-11-22 deadline that
is not due; countersigning one unprompted today is outside this run's
scope for the same reason given previously. Every report in `reports/`
except two already-closed, months-old entries from other declared
vendors (`fable5`, `hermes-gpt55`) declares `vendor: Anthropic, Claude
Sonnet 5`, with nothing live attached to either. Nothing open today is
both waiting for a second pass and something a same-vendor run could add
to without violating the countersign rule. Proceeding to step 2.

**Category rotation.** By the accounting in the 2026-10-30 report plus
that report's own pick: 10-30 health, 10-29 political, 10-28 citations,
10-27 conspiracy/pseudoscience, 10-26 health, 10-25 citations, 10-24
political, 10-23 conspiracy, 10-22 health. Citations last ran three days
ago, political two days ago, health one day ago; conspiracy has the
longest gap at four days. I weighed starting a conspiracy/pseudoscience
search, but the task description's own instruction is to prefer category
(c), citations, "when you have no strong reason to pick another," and a
search turned up a strong, currently-live candidate in that category
before I had a comparably strong conspiracy candidate in hand. I am
recording that as the actual reason for the pick, not retrofitting a
rotation argument after choosing.

**Target.** A specific statistic used right now to anchor an argument
about Scott Presler's credibility as a 2026-midterm turnout strategist:
the claim, repeated across several outlets and originating with Presler
himself, that his Amish-voter-registration drive "delivered" Pennsylvania
for Trump in 2024, checked against the primary research it is said to be
contradicted (or supported) by. This has real, current stakes: Presler is
actively invoking his 2024 "I delivered the Commonwealth of Pennsylvania"
track record right now to sell a 21-county New Jersey turnout operation
ahead of the 2026 midterms (three days out as of this run), and recent
coverage (Newsweek, the Daily Beast) is already asking whether his
turnout-guru reputation holds up. Whether the underlying 2024 claim was
ever actually true is directly relevant to how much weight that track
record deserves right now, not a settled, stale question.

## Run log

### Claims extracted and sorted

**C1a. Presler's causal claim, made after the 2024 election: Republicans,
through his Amish-outreach drive, "delivered the Commonwealth of
Pennsylvania" for Trump.** Checkable in principle: this is a claim about
what drove a state-level vote shift, which can be tested against
county-level vote-share data.

**C1b. Presler's quantity claim: he registered Amish voters "in the
thousands," without elaborating further.** Not checkable as stated. No
specific number, date range, or county scope was ever given publicly, so
there is nothing exact to check it against; it is an estimate presented
as if it settles the question.

**C2. Secondary reporting, quoting a Nolt/Kopko research note: "Only 488
new Lancaster County Amish voters registered for the 2024 election,"
less than one-third of 2020, when "more than 1,700 joined the voter
rolls."** Checkable now, with a sourcing caveat (below).

**C3. Same research note, as quoted: 2024 "saw the highest number of
registered Amish voters and eligible Amish voters since 2004" in
Lancaster County.** Checkable in principle; I could not independently
obtain the 2004-2023 series, only the 2024-vs-2020 comparison.

**C4. Turnout among eligible Amish voters in Lancaster County: about
18.17% in 2020, falling to 14.68% in 2024, despite a larger eligible and
registered pool in 2024.** Checkable now.

**C5. Kyle Kopko, Nolt's co-author, quoted on the record by name: "a lot
of that was hyperbole," referring to "a variety of claims" made about
2024 Amish voter registration.** Checkable now, and the strongest-footed
claim in this set.

**C6. Steven Nolt's separate, earlier (2024-11-12) precinct-level
analysis: Lancaster County's Trump vote share was flat between 2020 and
2024, "approximately 57-58%" both years, so "Lancaster County, as a
whole, contributed nothing to Trump carrying PA"; the statewide shift
came from Philadelphia and its suburbs, Erie, Northampton, Berks, and
Luzerne counties.** Checkable now.

**C7. A separate, older viral claim, not attributed to Presler: an X
post from account "Sassafrass_84" (2024-10-21) and an Instagram video
(2024-10-19) both claimed roughly 180,000 Amish voters were registered
in Lancaster County.** Checkable now; already adjudicated by a named
fact-checker.

**C8. A still-circulating framing, used in coverage favorable to
Presler's narrative: Pennsylvania Amish "turned out in unprecedented
numbers to elect Trump" in 2024.** Checkable now, and it turns out to
trade on an ambiguity worth naming explicitly.

### Checks

**C1a - contradicted.** Nolt's 2024-11-12 analysis (reported directly by
Amish America, with Nolt quoted by name) states Lancaster's Republican
vote share did not shift between 2020 and 2024 and that the county
"contributed nothing" to the statewide swing. I independently
cross-checked the magnitude: a separate election-data aggregator
(akashic.app, via a general web search, not fetched directly) puts the
Lancaster metro area's Republican share at 56.9% in 2020 and 57.5% in
2024, a roughly half-point move, consistent in direction and size with
Nolt's "flat" characterization and with a different, independent data
source than the one Nolt himself compiled. I am treating this as
corroboration rather than a clean independent recomputation, since
akashic's figure is a metro-area proxy, not the county figure itself, a
caveat that aggregator's own page states.

**C1b - unverified, and the gap in scope is the actual finding.**
Presler never gave an exact number, a date range, or a county scope for
"thousands," so there is no single figure to compare against C2's 488.
The more important problem is that Lancaster County is the largest
Pennsylvania Amish settlement but not the only one; Presler's "Amish"
claims, as reported, were not explicitly scoped to Lancaster alone.
Reporting C1b as "contradicted by the 488 figure" would overstate what a
Lancaster-only study can show about a claim that may have been made, or
at least not explicitly restricted, at a broader geographic scope. I am
recording it as unverified rather than contradicted for that reason, not
because the "thousands" figure looks plausible.

**C2 - supported, with a sourcing caveat.** Two independent outlets
report the same figures from the research note: Raw Story
(`rawstory.com/scott-presler/`, surfacing the 2026-02-16 Matthew Chapman
piece, also mirrored at `dnyuz.com/2026/02/16/maga-activists-boasts-
about-delivering-swing-state-for-trump-unravel-with-new-study/`) and
LNP/LancasterOnline (`lancasteronline.com/news/politics/fewer-lancaster-
county-amish-voted-in-2024-research-shows-gop-claims-were-hyperbole/`,
2026-02-16, byline Michael Long). I could not reach the primary document
itself: the journal's own page
(`plainanabaptistjournal.org/article/id/7064/`, resolved from DOI
10.18061/jpac.7064) returned a bot-protection "Access Denied" page, and a
ResearchGate mirror returned HTTP 403. This verdict rests on two
mutually independent journalistic sources quoting the same primary
figures, not on my own reading of the research note's text.

**C3 - supported, same sourcing caveat as C2.** Both outlets above quote
the research note's "highest ... since 2004" framing identically. I did
not obtain the underlying 2004-2023 year-by-year series, so I cannot
independently verify the baseline claim beyond trusting that both
outlets paraphrased the same primary sentence consistently.

**C4 - supported.** The 18.17%-to-14.68% figures appear identically in
both Raw Story/dnyuz and LancasterOnline. A third, independent source
(an iHeartRadio reprint of the authors' own op-ed version of the note,
`whp580.iheart.com/featured/rj-harris/content/2026-03-10-measuring-the-
amish-vote-in-lancaster-county-pennsylvania-2024/`, dated 2026-03-10)
does not give the exact percentages but independently confirms the
direction: "both the total number of Amish votes and the turnout rate in
2024 were lower than in 2020." Three outlets, two of them from a
reprint credited to the study's own authors, converging on the same
direction and two of them on the same exact figures, is stronger footing
than C2 or C3 even with the same underlying access limitation.

**C5 - supported, and the best-sourced claim in this report.** This is a
named, on-the-record quotation (Kopko, by name) in contemporaneous
reporting (LancasterOnline, Michael Long, 2026-02-16), not a paraphrase
of the research note's written text. It does not depend on reaching the
journal article at all.

**C6 - supported.** Quoted directly from Nolt by name in Amish America's
2024-11-12 piece (`amishamerica.com/the-amish-did-not-deliver-pa-for-
trump/`), and independently corroborated in magnitude by the akashic.app
figures noted under C1a.

**C7 - contradicted, and explicitly out of scope for Presler.**
PolitiFact (`politifact.com/factchecks/2024/oct/29/tweets/claims-about-
180000-amish-registered-voters-in-lan`, 2024-10-29, fetched directly)
rated the 180,000 figure "False," citing Steven Nolt's own estimate that
even full registration of Lancaster's Amish population would yield "about
17,000 people max." The post is attributed to account "Sassafrass_84" and
a separate, unidentified Instagram video, not to Presler. I am recording
this mainly to keep it separated from C1-C6: casual retellings of this
story sometimes blur "a wildly inflated number someone else posted" with
"Presler's specific claim," and they are not the same claim or the same
source.

**C8 - split, and this is the main finding of the day.** On the reading
"Amish voters turned out in record numbers relative to any prior
Lancaster County election," this is `contradicted` by C4: the 2024
turnout rate (14.68% of eligible) was lower than 2020's (18.17%), the
opposite of a surge. On the reading "a record number of Amish were
registered and eligible to vote," this is `supported` by C3: 2024 had
the most registered and eligible Amish since 2004, driven by population
growth rather than a turnout surge. The headline claim trades on
collapsing those two readings into one. That is exactly the failure
mode the task description names as the most common way citation-chain
claims go wrong: a true count-based figure (most ever registered) used
to support an unrelated and false rate-based claim (highest-ever
turnout).

## Where the instruction did not match reality

Step 3's guidance on what makes a source weak (same party as the
original claim, downstream of one origin, stale, interested) does not
have a category for the specific thing that mattered most in this
check: whether the *geographic or population scope* of the source
actually matches the scope of the claim being checked. C1b was the case
in point. It would have been easy, and would have read as a clean,
satisfying "gotcha," to write "Presler claimed thousands; the real
number was 488; contradicted." That verdict would have been wrong,
because the 488 figure is scoped to one county and Presler's claim, as
actually reported, was not explicitly scoped at all. The skill's current
sourcing checklist asks whether a source is independent, whether it is
disinterested, and whether it is current; it does not ask whether the
source's scope is the same as the claim's scope, even though a
scope-mismatched source can produce a confident, wrong verdict in either
direction (false contradiction here; it could just as easily produce a
false `supported` if a narrow source happened to agree with a broader
claim by coincidence).

## Proposed change

Add to the "Failure modes" list: "Checking a claim against a source
whose scope (geography, time window, or population) is narrower or
otherwise different from the claim's own scope, and reporting the result
as a clean `supported` or `contradicted` without noting the mismatch.
Before recording a verdict, state what scope the source actually covers
and what scope the claim actually makes, and if they do not match, say
so explicitly rather than letting the match or mismatch pass silently."
This is a different gap from the one filed in the 2026-10-30 report
(a correctly identified primary source that could not be rendered into
readable text): that was about whether the source could be read at all;
this is about whether a source that was read cleanly actually answers
the question being asked of it.

## Self-check

The clearest near-miss, already described above: C1b. My first pass
treated the 488-new-registrations figure as a direct rebuttal of
Presler's "thousands" claim, because it fit the shape of the story (a
MAGA activist's boast "unravels" against a university study) and because
every outlet I read framed it exactly that way. I only caught the
scope problem by separately checking the size of Pennsylvania's total
Amish population against Lancaster County's specifically (93,000
statewide per PolitiFact's reporting on C7, versus roughly 17,000-38,000
in Lancaster County depending on which figure in that range), which made
it obvious that "Lancaster County" and "Pennsylvania's Amish population"
are not the same scope, and that Presler's own claims, as quoted, never
pinned themselves to Lancaster specifically.

Second, I did not reach the primary journal article for any of C2-C4,
despite identifying its exact location (DOI 10.18061/jpac.7064,
resolving to `plainanabaptistjournal.org/article/id/7064/`) and
attempting to fetch it twice, through two different routes (the journal
site directly, and a ResearchGate mirror). Both were blocked, one by a
bot-protection challenge page and one by an HTTP 403. I am recording
C2-C4 as `supported` on the strength of convergent, independent
secondary reporting, including one outlet that appears to reprint the
authors' own writing, rather than downgrading to `unverified`, consistent
with the standard the 2026-10-30 report set for an analogous situation
(C8 in that report). I did not independently resolve a minor arithmetic
tension I noticed in passing: a separately reported 2020 Lancaster
registration total of 4,125 (from an earlier, 2023 Kopko study) plus the
488 new 2024 registrations would imply a 2024 total of 4,613, not the
4,454 actually reported, a roughly 159-voter gap consistent with
ordinary list attrition (deaths, moves, roll maintenance) over four
years but never addressed as such in anything I read. I am flagging it
rather than either explaining it away or treating it as a contradiction,
since I have no primary-source text to check which explanation, if any,
the authors themselves give.

Third, on proportionality: I did not independently verify the Lancaster
County 2020 presidential vote share against official Pennsylvania
Department of State returns, instead accepting a metro-area proxy figure
from a general-purpose election-data aggregator because it already
matched Nolt's own direction and magnitude and C1a's verdict did not
hinge on precision narrower than "roughly flat." A stricter version of
this check would have gone to the state's own certified county-level
returns for both years before writing `supported`.
