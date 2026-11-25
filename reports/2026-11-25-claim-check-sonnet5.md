---
skill: claim-check
skill_version: 6d97dbd6c18d845a22fc38e9f8582009ddc28d8a
agent: claude-sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (cloud scheduled session)
date: 2026-11-25
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that
drives this repository's daily claim-checks. Reciprocity first, per
`README.md`; an independent claim-check if nothing is waiting.

**Reciprocity check.** Two pull requests are open: #83 (the watchdog's
overdue `boundary-fast-track-limits` revert, opened 2026-09-28) and #144
(the watchdog's provisional-decisions-deadline PR, opened 2026-11-23,
laying out ratify/revert options for five decisions, still a draft). Both
are opened by the project's own watchdog routine under the account
`anderskanten`, both are already labeled `custodian-required`, and both
are explicitly addressed to the custodian, not to a participant
countersign. Read PR #144's full body: it is a set of diffed options
("ratify" / "revert" for each of five decisions) with no instruction
aimed at a reading agent, so no `security/` entry is warranted. Neither
PR is something I am eligible to act on (I did not write either, but
they are not countersign requests, they are custodian decisions
pending). `decisions/`, `appeals/` (only its README, no open appeal
files), and all four `skills/*` (all still `state: proposed`, none in
`beta` awaiting a countersign) were checked and hold nothing waiting
either. Of the reports in `reports/`, essentially all are filed by this
same scheduled task (`claim-check-sonnet5`); I am not eligible to
countersign my own prior work, and there is no other vendor's report
currently sitting unreviewed. Nothing eligible is waiting, so I moved to
an independent check.

**Category rotation.** The last several reports (2026-11-20 through
2026-11-24) covered, in order: pseudoscience/conspiracy, health,
political, citation, pseudoscience/conspiracy. I picked political this
run, specifically a sitting cabinet official's recent on-record
statistical claims about immigration enforcement, since that combines
real current stakes with primary government data to check it against.

## Run log

Target: statements by U.S. Secretary of Homeland Security Markwayne
Mullin on the "Ruthless Podcast," reported October 1, 2026 by Fox News
and The Daily Wire, plus a related, more loosely sourced claim
circulating about the same underlying dispute (how many people were
"illegally released" under the Biden administration).

I could not locate the Ruthless Podcast audio or a transcript directly
(searched for the episode by host/guest/date; found none). I am relying
on two independent outlets' direct quotes and paraphrases of the same
appearance, not the primary recording. That is a real limitation, noted
in the self-check below, not papered over.

### 1. Extracted claims

1. "Under the Biden administration, 97% of individuals DHS encountered
   were released within 27 hours." (Paraphrased identically by both
   outlets; neither gives a direct Mullin quote or a DHS source for this
   specific figure.)
2. Direct quote, Mullin, Ruthless Podcast, per The Daily Wire: "Under
   President Trump, we've arrested, so far ... 2,210 terrorists in this
   country."
3. Direct quote, same appearance, per Fox News: "There's a difference
   between a suspected terrorist and a terrorist watch list," and,
   of the 2,210: "These were terrorists" (not merely watchlist hits).
4. A separately circulating, related claim: that the Biden
   administration "illegally released" or "allowed in" approximately 20
   million people. This is attributed inconsistently across sources I
   found: a Media Bias/Fact Check piece dated November 14, 2026 rates a
   "20 million illegally released" claim "BLATANT LIE" and attributes it
   to Mullin without quoting him directly or linking a primary source;
   other reporting attributes "approximately 20 million... allowed" to
   Vice President Vance, not Mullin; a Breitbart interview is reported
   (secondhand, I could not open the original) as having Mullin give a
   range of "10 to 23 million... probably in the 20s" for total people
   who entered, a different quantity (entries, not releases) than either
   the MBFC or Vance framing.

### 2. Sorting

- Claims 1 and 2: checkable in principle against official U.S.
  government immigration-enforcement data; partially checkable by me
  (I have no access to the underlying case-level data behind either
  number, but can check them against the nearest public, sourced
  comparison figures).
- Claim 3: an interpretive/categorical claim (these are confirmed
  terrorists, not watchlist hits) rather than a number; checkable
  against how DHS's own statistics describe the category, not
  checkable against case files I don't have.
- Claim 4: sorted separately before checking, per the skill's
  instruction to separate negative/uncertain claims. This one is not a
  negative claim, but its sourcing is unresolved: I could not confirm
  which named person said approximately what, where, or when, with a
  single primary citation. I am treating the attribution itself as
  unverified rather than forcing a verdict onto a claim I can't pin to
  one speaker and occasion. The demographic figures invoked around it
  (how many unauthorized immigrants are actually in the country) are
  independently checkable regardless of attribution, so I checked those.

### 3. Checking

**Claim 1 (97% released within 27 hours).**
Source: Lori Robertson, "Breaking Down the Immigration Figures,"
FactCheck.org, February 27, 2024
(https://www.factcheck.org/2024/02/breaking-down-the-immigration-figures/),
citing U.S. Department of Homeland Security Office of Homeland Security
Statistics (OHSS) data for the period February 2021 through October
2023. Exact quote: "But overall under Biden, through October, 35% of
those apprehended at the border have been released." The same article
gives the underlying counts: "The DHS data show 6.5 million encounters
at the U.S.-Mexico border in that time frame... About 2.5 million people
through October have been released into the U.S."

Corroborating, independently sourced figure for a near-identical window:
a wire report republished by Stars and Stripes and the Spokesman-Review
(January 6-7, 2024) put total CBP releases at roughly 2.3 million against
more than 6 million taken into custody (excluding about 365,000
unaccompanied minors transferred to HHS), i.e. also in the mid-30s
to high-30s percent range, not 97%.

Neither source covers the full Biden term (through January 2025, not
October 2023), and neither addresses a "released within 27 hours"
timing metric specifically; I found no DHS, CBP, or ICE published
statistic matching that exact framing. So: the *share* claimed (97%)
is far outside every DHS-sourced release-rate figure I could find for
an overlapping period (which cluster around 35-38%), which I am calling
**contradicted** on the share, with the caveat that the comparison
period is not identical. The specific **"within 27 hours" timing
claim is unverified**: I could not confirm that metric exists in public
DHS reporting at all, in either direction.

**Claims 2 and 3 (2,210 terrorists, as confirmed terrorists not
watchlist hits).**
Source: "Ask PolitiFact: How many people on the terrorist watchlist have
been stopped at the border?", PolitiFact, October 27, 2023
(https://www.politifact.com/article/2023/oct/27/ask-politifact-how-many-people-on-the-terrorist-wa/),
citing CBP data. Exact figures: "736" total nationwide "known or
suspected terrorist" (KST) watchlist encounters in FY2023 (484 at
northern land ports of entry, 80 at southern land ports of entry, 3
between ports on the northern border, 169 between ports on the southern
border); 98 southern-border between-ports encounters in FY2022; 15 in
FY2021. The article also states the official standard, sourced to the
Congressional Research Service: a "suspected terrorist" is someone
"reasonably suspected to be" involved in terrorist activity, i.e. a
watchlist hit is explicitly defined as not the same thing as a
confirmed terrorist.

Mullin's claimed total of 2,210 "terrorists" arrested under the Trump
administration (as of an interview roughly eight months into that term)
is well above any single fiscal year of Biden-era nationwide watchlist
encounters I could source (736 in FY2023, the highest year found), and
he explicitly asserts, without citing supporting data, that the 2,210
are confirmed terrorists rather than watchlist hits ("These were
terrorists") -- directly on the distinction his own department's cited
standard says cannot be assumed from watchlist status alone. I found no
published DHS dataset, charge list, or conviction record substantiating
either the count or the "terrorist" (as opposed to "watchlist hit" or
"watchlist-adjacent") classification. A July 1, 2026 Washington Examiner
piece reports a "1,900 'known terrorists'" figure from roughly three
months earlier, attributed to "a Cabinet official" rather than a direct
Mullin quote; I cannot confirm whether this is the same running tally
(plausible: +310 over three months) or a different metric, so I am not
calling this an inconsistency, only noting it as something I could not
resolve.

**Verdict: unverified**, with a documented, sourced tension between the
claim's category (confirmed terrorists) and the much smaller, differently
defined watchlist-encounter numbers that are the only comparable public
data I could find.

**Claim 4 (approximately 20 million "illegally released"/"allowed
in").**
**Verdict on attribution: unverified.** I could not confirm, from a
primary transcript, speech, or press release, who said approximately 20
million, in what words, where, or when. Sources disagree on the speaker
(Vance vs. Mullin) and on what is being counted (population currently in
the country vs. total people released vs. total people who entered).

Independently of attribution, the population figure itself is checkable.
Three separate, independently produced estimates of the current
unauthorized-immigrant population, all more recent than 2022:
- Pew Research Center, "U.S. Unauthorized Immigrant Population Reached a
  Record 14 Million in 2023," August 21, 2025
  (https://www.pewresearch.org/race-and-ethnicity/2025/08/21/u-s-unauthorized-immigrant-population-reached-a-record-14-million-in-2023/):
  "an all-time high of 14 million in 2023."
- Migration Policy Institute: unauthorized population reached a new peak
  of 15.8 million as of mid-2024 (cited via Stateline's report on MPI's
  estimate; MPI also revises its mid-2023 estimate to 14.7 million).
- U.S. DHS Office of Homeland Security Statistics, "Estimates of the
  Unauthorized Immigrant Population Residing in the United States:
  January 2018-January 2022," April 2024: 11.0 million as of January 1,
  2022.

All three, government and independent alike, put the resident
unauthorized population at 11.0 to 15.8 million across 2022-2024, not
20 million. If "20 million" is meant as the current population (how
Vance's reported wording frames it), it is **contradicted** by every
population estimate I found. If instead "20 million" means total
encounters/entries over the full Biden term (a different, larger
quantity, since it does not net out removals and returns), the closest
figure I found is a U.S. House Homeland Security Committee (then
Republican-controlled) factsheet, October 24, 2024, citing CBP data:
"10.8 million total encounters since FY2021." That is also well under
20 million, though I am flagging this source as a partisan committee
compilation of primary CBP data, not a primary CBP release itself, so it
carries less weight than the Pew/MPI/DHS population figures above.

### 4. Self-check

- My strongest sourcing is for claims 1-3: two independent outlets
  (Fox News, The Daily Wire) directly quoting or closely paraphrasing
  the same named appearance, checked against DHS-sourced figures I
  opened and quoted myself (FactCheck.org's Feb 2024 piece; PolitiFact's
  Oct 2023 piece). My weakest sourcing is for claim 4: I never located
  a single primary utterance, and I am reporting that gap rather than
  picking the attribution that fits the number best. That is the
  honest result, not the tidiest one.
- The DHS-sourced release-rate data I used for claim 1 runs through
  October 2023, not January 2025. A release rate could in principle
  have moved a great deal in the Biden administration's final fifteen
  months; nothing I found suggests it moved anywhere near 97%, but I
  have not independently checked that final period, so I am calling
  the share "contradicted" on the strength of the overlapping data I
  do have, not on data covering the exact same window as the claim.
- For claim 2, I did not call the 2,210 figure itself "contradicted,"
  only "unverified with a documented tension," because it is possible
  in principle that most of those arrests came from channels other than
  border watchlist screening (post-entry investigation, for example),
  which the PolitiFact watchlist-encounter numbers would not capture.
  Calling it outright contradicted would overstate what I can show.
- I trusted Pew's, MPI's, and DHS OHSS's self-reported headline numbers
  as I would any primary research organization's published figures,
  without re-deriving their underlying methodology myself.

## Where the instruction did not match reality

Step 3 of `skills/claim-check/SKILL.md` instructs: "go to a source, and
record it as an exact, checkable reference." That assumes a source
exists that states the same metric the claim uses. For claim 1, Mullin's
claim is built on a specific, named metric ("released within 27 hours")
that I could not find published anywhere, by DHS or anyone else, in
either direction. The skill's verdict list (`supported`, `contradicted`,
`unverified`, `unfalsifiable as stated`, `not contradicted within
searched corpus`) has no clean slot for "the claimed share is far
outside every comparable metric from the same official source family,
but the exact stated metric may not exist in public data at all." I
used `contradicted` for the share and `unverified` for the timing
framing separately, which is the closest fit, but the skill's wording
implicitly assumes a one-to-one source match that a claim built on an
invented or unpublished metric does not give you.

## Proposed change

In `skills/claim-check/SKILL.md` step 4, add a note after the five
verdict categories: when a claim's exact stated metric cannot be found
in any public source (by the claimant's own side or any other), say so
explicitly, and give the nearest comparable published metric with its
own source, rather than forcing the whole claim into `unverified`
(which undersells a large, sourced gap) or `contradicted` (which
overstates a comparison across two non-identical metrics). I split the
same claim into two verdicts above to work around this; a short
instruction to do that deliberately, rather than as an improvisation,
would make this reproducible.

## Self-check

Where I noticed I had deviated only when writing this up: I initially
drafted this report treating claim 4 as Mullin's own claim because the
MBFC headline and several secondary summaries all framed it that way.
Re-checking before filing, I found that at least one of my own earlier
search results separately attributed the "approximately 20 million"
wording to Vice President Vance, not Mullin, and that I had never
actually opened a primary source that put those words in Mullin's
mouth. That is exactly the kind of secondhand attribution the skill
warns against ("search results describing X" is not a source), and I
almost filed it as one. I corrected it by weakening the verdict to
"unverified on attribution" rather than deleting the claim, since the
underlying population figures are worth checking regardless of who
said it.
