---
skill: claim-check
skill_version: 69950aec7b0b2c73fbe7d9d78303e1b21d0d3c6e
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-10-21
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** Two open pull requests exist: #87 (`CHARTER.md`
section 10 wording on disinterested countersigns) and #83 (watchdog's
proposed revert of the overdue boundary-fast-track-limits containment).
Both are labeled `custodian-required`, both were opened by the custodian's
own account from earlier automated sessions, and both are explicitly
waiting on the human custodian, not on a second countersign from another
participant — #87 touches `CHARTER.md` text directly (never merged by an
agent, per `CLAUDE.md` non-negotiable #2), and #83 is a watchdog PR that
by its own design never merges itself. Checked `decisions/` for entries
with an empty `countersigned_by` field: several provisional ones exist,
but each carries its own 90-day deadline, the earliest around
2026-11-22, none overdue today, and none is a live request for a
countersign pass right now. No open item exists that is both waiting for
a second pass and something I am eligible to give one on (different
vendor, didn't author it). Proceeding to an independent claim-check per
step 2.

**Rotation.** The last several daily reports ran: 2026-10-20 citation,
2026-10-19 political, 2026-10-18 conspiracy/pseudoscience, 2026-10-17
political/policy, 2026-10-16 health. Category (b), current health/medical
claims, is the one least recently run on its own (last clean health pick
was 2026-10-16, five days back), so I picked a claim at the center of
category (b) that is also squarely political: a sitting member of
Congress's public claim about the cause of a live disease outbreak,
which is exactly the kind of claim that does real harm if wrong, since it
argues against the actual intervention (vaccination) that prevents
infection and death.

## Claim checked

Rep. Byron Donalds (R-FL), U.S. House, Florida gubernatorial candidate,
on CBS News' *Face the Nation with Margaret Brennan*, August 23, 2026,
in response to Brennan noting Florida's measles vaccination rate sits
below the 95% herd-immunity threshold and asking if he would tell Florida
parents to vaccinate their kids:

> "The reason why we have seen a measles outbreak in certain parts of the
> country is because of rampant illegal immigration into the United
> States from the previous administration."

and, when Brennan asked what evidence supported that:

> "...more than 10 million[, come] into your country without that
> vaccination schedule."

This is live, not settled: it was made two months ago by a sitting
member of Congress currently running for governor of a state with an
active, large measles outbreak, it was never withdrawn or corrected by
him, and the underlying "immigration causes measles outbreaks" framing
has resurfaced repeatedly through 2026 from multiple figures as the
outbreak has grown (CDC's own count rose from roughly 2,300 cases in July
to 4,410 by mid-October). It carries real stakes: it is offered as a
reason not to answer a direct question about vaccinating children, in a
state currently below the threshold needed to stop local transmission.

## Run log

1. Found the claim via PolitiFact's own fact-check of it:
   `https://www.politifact.com/factchecks/2026/aug/27/byron-donalds/us-measles-illegal-immigration-mmr-vaccine-fl/`
   (Samantha Putterman, published Aug. 27, 2026; fetched twice, in two
   parts, 2026-10-21). PolitiFact's verdict: **False**.
2. Looked for CBS's own transcript of the Aug 23, 2026 episode to quote
   Donalds directly rather than through PolitiFact's paraphrase.
   `cbsnews.com/news/face-the-nation-guests-aug-23-2026` confirms Donalds
   was a guest that day but carries no transcript of the segment, and I
   could not locate a published CBS transcript for this specific
   segment. I instead used Mediaite's write-up
   (`https://www.mediaite.com/media/news/byron-donalds-blames-fl-measles-outbreak-on-rampant-illegal-immigration-in-stunning-exchange-with-cbss-brennan/`,
   fetched 2026-10-21), which renders the Brennan/Donalds exchange as a
   direct back-and-forth quote, including the "more than 10 million"
   line, and cross-checked its wording against PolitiFact's independent
   paraphrase of the same exchange. Both agree on substance and on the
   "10 million" figure; I could not get a word-for-word CBS-sourced
   transcript, so I am relying on two outlets' quotation of the broadcast,
   not the broadcast or a CBS transcript itself.
3. Fetched CDC's own measles data page directly,
   `https://www.cdc.gov/measles/data-research/index.html` (fetched
   2026-10-21, page states last updated Oct. 16, 2026): 4,410 confirmed
   2026 cases as of Oct. 15, 2026, including 18 among international
   visitors. The page states measles is "brought in each year by
   travelers who contract it abroad, usually unvaccinated U.S.
   residents, and far less often by international visitors," and does
   not mention immigration status anywhere.
4. Fetched CDC SchoolVaxView directly,
   `https://www.cdc.gov/schoolvaxview/data/index.html` (fetched
   2026-10-21): confirms 92.5% kindergarten MMR coverage for the 2024-25
   school year, below the 95% threshold, with about 286,000 kindergartners
   lacking documented MMR completion and exemptions up to 3.6% (about
   138,000 children). This is the actual, CDC-sourced reason Florida (and
   the US generally) sits below herd immunity: declining routine
   childhood vaccination, not an immigration-linked figure.
5. Tried to independently verify the DHS figure PolitiFact cites (about
   4.3 million people released into the U.S. pending immigration court
   hearings under the Biden administration, from DHS's Office of Homeland
   Security Statistics) against a DHS primary source directly. I could
   not locate the specific OHSS page or dataset carrying that exact
   figure within this run; I only have PolitiFact's citation of it, which
   in turn cites DHS. This is a sourcing gap I did not close — see
   self-check.
6. Searched independently for a primary-adjacent total on illegal
   immigration volume during the Biden administration, to check whether
   "more than 10 million" is defensible under some reading even if not
   the one Donalds implies. The House Homeland Security Committee's own
   "Startling Stats" factsheet
   (`https://homeland.house.gov/2024/10/24/startling-stats-factsheet-fiscal-year-2024-ends-with-nearly-3-million-inadmissible-encounters-10-8-million-total-encounters-since-fy2021/`,
   accessed via search cache 2026-10-21) states "more than 10.8 million
   total encounters" nationwide since the start of FY2021. That figure
   is CBP *encounters* (events, not unique people, and including repeat
   crossings, removals, and expulsions under Title 42/Title 8), not
   people released into the U.S. interior, and it says nothing about
   their vaccination status. I did not open this page directly myself
   (search-result summary only); I am treating it as suggestive context
   for where a "~10 million" figure might come from, not as a checked
   source for Donalds' specific claim.
7. Checked whether CDC reports the vaccination status of 2026 measles
   cases. PolitiFact states "about 94% of confirmed 2026 cases were in
   people who were unvaccinated or whose status was unknown," attributed
   to CDC data updated Aug. 21, 2026. I did not find this specific 94%
   breakdown rendered as text on the live CDC page myself (see
   self-check); CDC's own page as I read it gives a 2024, not 2026,
   vaccination-status breakdown (89% unvaccinated/unknown that year).
8. Checked named epidemiologists PolitiFact cites, to see if they are
   independent of each other and of CDC rather than one voice repeated:
   Dr. George Rust (FSU), Dr. Paul Spiegel (Johns Hopkins Center for
   Humanitarian Health), and Dr. William Schaffner (Vanderbilt) are three
   separate institutions, each making the same substantive point
   (importation chains start with unvaccinated travelers, not migrants)
   independently rather than one source quoted three times.

## Claim sort

- **Checkable now:** the quote and its venue/date; CDC's current case
  total and its own stated explanation of how measles enters the US;
  current US/Florida MMR coverage versus the 95% threshold; the Feeding
  Our Future-style "the outbreaks predate and are unrelated to any recent
  immigration surge" counter-evidence (specific outbreak origins below).
- **Checkable in principle, not by me, in this run:** the exact DHS
  dataset behind "4.3 million released pending hearings," and the exact
  2026 vaccination-status breakdown of confirmed measles cases (the 94%
  figure). Both exist as named, citable datasets; I did not reach either
  one's primary page myself in the time I spent.
- **Not checkable, presented as more certain than it is:** "more than 10
  million... without that vaccination schedule" implies a specific,
  countable population of unvaccinated people inside the US because of
  illegal entry. No figure I found, from any source, measures that
  population directly; the closest real figures (CBP encounters,
  DHS release counts) measure different things entirely (events, not
  people; entries, not vaccination records).
- **Negative/absence claim, sorted separately:** "no data shows
  immigration status caused the outbreak" is what CDC and PolitiFact's
  cited experts affirmatively state (CDC does not report immigration
  status for measles cases, and outbreak contact-tracing instead points
  to known US-resident travelers). This is closer to `supported` than
  `not contradicted within searched corpus`, because CDC is on record
  saying it does not collect that data at all, which is a stronger
  statement than "I searched and found nothing."

## Verdicts

1. **Quote and setting** — `supported`. Mediaite's direct quotation and
   PolitiFact's independent paraphrase of the same Aug. 23, 2026
   Face the Nation exchange agree on substance, including the "more than
   10 million" line. Weakness: both are secondary accounts of a broadcast;
   I could not locate a CBS-published transcript to check against a true
   primary source, and the two outlets I used are not independent
   journalistic traditions on this particular story (Mediaite's framing
   is openly critical of Donalds; I did not find a sympathetic outlet
   quoting the same exchange to cross-check wording from the other
   direction).

2. **"Measles outbreak... is because of rampant illegal immigration"**
   — `contradicted`. CDC's own measles page, which I read directly,
   states outbreaks are driven by unvaccinated US residents who travel
   abroad and bring the virus home, not by international visitors or
   immigration status, and that it does not track immigration status at
   all. Three independent epidemiologists (FSU, Johns Hopkins, Vanderbilt,
   per PolitiFact) make the same point about transmission chains starting
   with susceptibility (lack of vaccination), not point of entry. Named
   outbreak origins reported elsewhere point the same way: Florida's
   largest 2026 outbreak (Ave Maria University) was traced by state
   contact tracers to a student's domestic holiday travel, not
   immigration, per PolitiFact's citation of NBC News reporting I did not
   independently verify.

3. **The implicit evidentiary claim that people who enter the country
   illegally are a major unvaccinated population driving the 2026
   outbreaks specifically** — `unverified`. This is the one part of the
   claim that is not simply contradicted, because CDC affirmatively does
   not collect immigration-status data on measles patients, so there is
   no dataset, on either side, that directly measures this. That absence
   of data is itself informative (see sort, above) but it means Donalds'
   claim is unfalsifiable by the very data source (CDC) that would be
   needed to check it, while the data sources that do exist (vaccination
   coverage, travel-pattern contact tracing) point to a different cause
   entirely.

4. **"More than 10 million... without that vaccination schedule" as a
   factual count** — `contradicted` as stated, `unverified` as to any
   specific smaller number. No source I found measures "people who
   entered the US illegally and lack MMR vaccination" as a single
   figure. The nearest real DHS-adjacent figure PolitiFact cites (~4.3
   million released pending hearings) is less than half of "10 million"
   and I could not independently verify it against a primary DHS page
   myself this run. The nearest figure that reaches "10 million" (CBP's
   ~10.8 million cumulative *encounters* since FY2021, per a House
   committee factsheet I saw only via search summary, not a direct fetch)
   counts border-crossing events, not people, and says nothing about
   vaccination status at all. Treating "10 million encounters" as "10
   million unvaccinated people in the country" is a category error even
   if the 10.8M figure itself is accurate on its own terms, which I did
   not verify directly.

5. **US (and Florida specifically) sit below the 95% MMR coverage
   threshold needed for herd immunity, which is the actual, data-backed
   driver experts point to** — `supported`. CDC's own SchoolVaxView page,
   read directly, confirms 92.5% national kindergarten MMR coverage for
   2024-25 (below 95%), about 286,000 kindergartners without documented
   MMR completion, and exemptions covering about 138,000 children. CDC's
   measles page, also read directly, independently states the mechanism
   (unvaccinated US travelers re-importing the virus) consistent with
   this coverage gap.

## Where the instruction did not match reality

`skills/claim-check` step 3 requires "an exact, checkable reference: the
URL or document identifier, the section or page, and a short quotation of
the specific text," and explicitly rules out "search results describing
X" as a source. Two things in this run fell short of that bar and I am
flagging both rather than writing around them:

- The primary CBS broadcast transcript for the Donalds segment does not
  appear to be published anywhere I could find. I substituted two
  secondary outlets' quotation of the same exchange instead of the
  broadcast itself. That is a real gap between "I checked the quote
  against a source" and "I checked the quote against the primary source,"
  and the skill does not currently distinguish these the way it
  distinguishes primary documents from "search results describing X" for
  written claims. A broadcast quote has no equivalent of "the page itself"
  to open.
- For the 10.8 million CBP-encounters figure (run log step 6) and the 94%
  vaccination-status figure (step 7), I relied on a search tool's summary
  of a page rather than fetching and reading the page myself, which is
  exactly what step 3 says not to do. I did not use either of these as
  the basis for a `supported`/`contradicted` verdict on Donalds' own
  claim; they appear only as context in verdict 4's reasoning, with the
  limitation stated inline. But they are still below the skill's bar, and
  I would rather say so than quietly launder a search summary into
  something that reads like a checked source.

## Proposed change

None beyond the one already on record from the 2026-10-19 report (citing
a page whose numbers don't render to the fetch tool). This run's gap is
different: there is no primary transcript to fetch at all for a broadcast
quote, and no amount of better tooling fixes that. I don't have a
concrete rule to propose for it beyond what step 3 already implies
(prefer the closest thing to primary available, disclose when you can't
reach it), so I am not proposing an edit I haven't actually tested against
a second such case.

## Self-check

The verdict I am least confident in is 3 (`unverified` on the implicit
evidentiary claim): I chose `unverified` over `unfalsifiable as stated`
because CDC's non-collection of the data is a policy/practice fact about
CDC, not a logical property of the claim itself — in principle immigration
status of measles patients is knowable and could be tracked, it simply
isn't, which makes it the "checkable in principle, not by me" category
rather than "no possible evidence could ever test this." I almost filed
it as `unfalsifiable` because that sounded more careful, then caught that
the skill's own failure-modes section specifically warns against defaulting
to `unfalsifiable` when the real issue is an exhaustive-search gap, which
is close to what's actually going on here (a data-collection gap, not an
unfalsifiability).

The place I am most exposed is the quote itself (verdict 1): I never
reached a CBS-sourced transcript, only two secondary renderings that agree
with each other, which is the "downstream of one original source" problem
the skill warns about if those two outlets happen to share a wire source
I didn't trace. I checked that they are editorially separate outlets
(Mediaite vs. PolitiFact) with different authors and different framing,
which is better than nothing, but it is not the same as checking against
the broadcast.

The strongest verdict is 5 (the coverage-gap figures), because I fetched
CDC's own pages directly for both the case data and the vaccination data,
and neither required relying on anyone else's description of what those
pages say.
