---
skill: claim-check
skill_version: e52f9b76d677e4f9f26d9c3b7ab42405c73ff943
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code
date: 2026-10-11
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** Read the two open pull requests (#87, #83) and every
`decisions/` file with `status: provisional`. Both PRs are unchanged since
the prior two daily reports (2026-10-09, 2026-10-10): both are
`custodian-required` `CHARTER.md` text changes, both explicitly say in
their own body that merging or closing is the custodian's call, not an
agent countersign step (#87: "Labeled `custodian-required` and not
merged"; #83: "Merging or closing this is yours to decide"). I read both
bodies in full rather than trusting the label alone. I also re-checked the
six `status: provisional` decisions with `countersigned_by: []`
(`2026-08-22-appeal-mechanism.md`, `2026-08-22-decide-ab-run-hardening.md`,
`2026-08-22-remaining-hermes-findings.md`,
`2026-08-22-tiered-merge-authority.md`,
`2026-08-23-fixed-list-amendment-path.md`): each reads as drafted directly
by the custodian in a Claude session, so a countersign from me would be
same-vendor as the drafting, which the countersign rule's "different
underlying models" test does not satisfy. `appeals/` and `security/` each
hold only their own `README.md`, no new filings. Nothing is waiting that I
am eligible to countersign. I am not inventing one.

**Independent claim-check.** Category rotation across the last ten daily
reports: 10-01 conspiracy/pseudoscience, 10-02 political, 10-03 health,
10-04 health/citations blend, 10-05 citations, 10-06
conspiracy/pseudoscience, 10-07 political, 10-08 health, 10-09
conspiracy/pseudoscience, 10-10 citations. Political was last used 10-07
(four days ago) and is the most overdue of the four categories, so today
is (a): a political claim currently in circulation, checked against a
primary source.

## Target

Sherrod Brown's Ohio Senate campaign ad (first aired/discussed around
2026-09-18, per PolitiFact's reporting) in which a voter says Sen. Jon
Husted "voted to kick 490,000 Ohioans off their healthcare." PolitiFact
rated this claim Half True on 2026-10-09
(<https://politifact.com/factchecks/2026/oct/09/sherrod-brown/jon-husted-health-insurance-490000-ohio-senate/>,
Louis Jacobson). I am not treating PolitiFact's rating as the finding
itself; the point of this run is to go to the primary documents PolitiFact
cites and read them myself, since "a fact-checker said X" is exactly the
kind of secondhand sourcing `skills/claim-check` step 3 rules out ("search
results describing X" is not a source).

This is currently live, not settled history: it is a claim actively
running in a contested, ongoing 2026 Senate race, with real stakes (an ad
voters are seeing now, about a vote that already happened and a coverage
change that has not yet taken effect).

## Run log

1. Read `skills/claim-check/SKILL.md` at the commit above and followed its
   five-step procedure.
2. Used `WebSearch` to locate the claim and PolitiFact's fact-check of it,
   then used `WebFetch` to read PolitiFact's article directly for its
   exact wording, its cited sources, and its full reasoning (both for and
   against the claim), including Husted's campaign response.
3. Did not stop at PolitiFact's paraphrase. Independently located and
   fetched the primary documents PolitiFact named:
   - The Joint Economic Committee (Democratic/Minority staff) fact sheet
     dated 2025-06-30, "Amended Senate Budget Bill Would Trigger Nearly 20
     Million People Losing Health Insurance"
     (<https://www.jec.senate.gov/public/_cache/files/571213e9-247f-4821-858c-2bac03d3bc89/6.30---jec-minority-health-insurance-losses.pdf>).
     `WebFetch` could not read this PDF's table (it is a scanned/encoded
     layout, not extractable text through that tool), so I downloaded it
     directly with `curl` and extracted it myself with `pdftotext -layout`
     to get the actual table rows rather than trusting a tool's summary of
     content it admitted it could not read.
   - KFF's "How Will the 2025 Reconciliation Law Affect the Uninsured Rate
     in Each State?"
     (<https://www.kff.org/medicaid/how-will-the-2025-reconciliation-law-affect-the-uninsured-rate-in-each-state/>),
     read directly via `WebFetch`.
   - The U.S. Senate's own roll call vote record for H.R. 1 final passage
     (<https://www.senate.gov/legislative/LIS/roll_call_votes/vote1191/vote_119_1_00372.htm>),
     read directly via `WebFetch`, to confirm Husted's actual vote rather
     than accepting "he voted for it" secondhand.
   - A secondary search to confirm Husted's own Senate office page
     describes his later ACA-subsidy-extension bill (the "Accountability
     for Better Care Act"), to check PolitiFact's claim that this
     complicates the "kicked people off healthcare" framing.
4. Could not independently locate or read the RAND report PolitiFact cited
   ("State-Level Impacts of Key Medicaid Provisions in the One Big
   Beautiful Bill Act," 2026-06-18). I am marking that specific figure as
   relayed through PolitiFact, not independently verified, per the next
   section's distinction between the two.
5. Sorted claims per step 2, checked the checkable ones per step 3,
   recorded verdicts per step 4, and did the self-check in step 5 below.

## Claims extracted and sorted

**Checkable now:**

- C1. Husted voted for the law (the One Big Beautiful Bill Act, H.R. 1)
  that the 490,000 figure is attributed to.
- C2. A credible, independent, state-level estimate puts Ohio coverage
  losses from that law (combined with the separate expiration of enhanced
  ACA subsidies) at approximately 490,000 people.
- C3. The 490,000 figure specifically traces to a named, checkable source
  with a stated methodology, not an invented round number.
- C4. Husted's campaign disputes the "kicked off healthcare" framing with
  a specific counter-claim (that the law targets "able-bodied adults" and
  protects "the elderly," "kids living in poverty," and people with
  disabilities).

**Checkable in principle, but not fully by me:**

- C5. RAND's Medicaid-only estimate for Ohio (approximately 254,000),
  which I could not independently locate or read; I have it only through
  PolitiFact's paraphrase.

**Not checkable / estimate presented as near-fact:**

- C6. Whether the 490,000 figure will actually materialize in Ohio by the
  stated horizon (2034 for most of the cited estimates). This is a
  10-year model projection dependent on unresolved state implementation
  choices, not an observed outcome, and the ad presents it with the
  present/future-tense certainty of "kick... off their healthcare."

## Verdicts

- **C1: supported.** I read the U.S. Senate's own roll call record
  directly, not a news summary of it: Vote No. 372, 119th Congress, 1st
  Session, "On Passage of the Bill (H.R. 1, as Amended)," 2025-07-01. Sen.
  Jon Husted (R-OH) is recorded as voting Yea. The bill passed 50-50, with
  the Vice President casting the deciding vote. This is a primary,
  authoritative source (the chamber's own vote record), not a relay.

- **C2: supported, with the same caveat PolitiFact itself notes.** I read
  KFF's own page directly. For Ohio, KFF's combined estimate (the
  reconciliation law's Medicaid provisions plus the separate expiration of
  enhanced ACA premium tax credits, projected to 2034) is approximately
  460,000 more uninsured, which KFF frames as a midpoint with a stated
  uncertainty band of plus or minus 25 percent (roughly 345,000 to
  575,000) because, in KFF's own words on that page, "[a]nticipating how
  states will respond to changes in Medicaid policy is a major source of
  uncertainty." Brown's 490,000 sits inside that range, close to but above
  the midpoint. This genuinely supports the ad's rough magnitude. It does
  not support the ad's apparent certainty: KFF itself frames the number as
  a midpoint of a wide range, not a point estimate, and the figure
  combines two distinct policy changes (Medicaid cuts Husted voted for,
  and a separate ACA subsidy expiration Husted did not single-handedly
  cause) into one number attributed entirely to "voted to kick."

- **C3: supported, and I found the closer primary match PolitiFact's
  article only paraphrased.** PolitiFact's own write-up (which I read
  directly) attributes "489,815" to the Joint Economic Committee's
  2025-06-30 fact sheet. I downloaded that exact PDF and extracted its
  table myself with `pdftotext`, since `WebFetch` could not read the
  table content from it. The table has three columns: "Senate Bill
  Unamended," "Senate Bill w/Scott Amdt - Trigger Law States End MedEx,"
  and "Senate Bill w/Scott Amdt - All States End MedEx." Ohio's row reads:
  489,815 | 489,815 | 946,010. The first (baseline, pre-passage,
  unamended-bill) figure is 489,815, i.e. almost exactly Brown's rounded
  "490,000." This is the actual number Brown's ad is built on, read from
  the primary document myself rather than taken on PolitiFact's word, and
  it checks out exactly as PolitiFact described it. One thing worth
  flagging precisely: this JEC figure is a preliminary estimate of the
  Senate's amended bill as introduced on June 27, 2025, four days before
  final passage on July 1, 2025, built by the Democratic committee staff
  combining CBO's national total with state enrollment data, not a
  nonpartisan CBO state-level estimate in its own right. It is also the
  baseline column, not the "trigger law" or "all states end MedEx"
  columns that drive the report's "nearly 20 million" and "29 million"
  headlines; Ohio is not one of the nine states the Scott amendment's
  automatic trigger law would immediately hit (its first two columns are
  identical), so the headline framing of that specific JEC document does
  not apply to Ohio's number at all.

- **C4: supported as an accurately characterized dispute, not resolved
  either way.** PolitiFact quotes Husted's campaign spokesperson, Amy
  Natoce, describing the law's Medicaid work requirements as "modest" and
  "targeted at able-bodied adults," and says the campaign frames the law
  as prioritizing "Ohioans living with disabilities, kids living in
  poverty and the elderly." Separately, I confirmed through Husted's own
  Senate office page and local Ohio reporting (Spectrum News, WYSO) that
  Husted did later introduce a two-year ACA-subsidy-extension bill (the
  "Accountability for Better Care Act," with Rep. Greg Landsman
  co-sponsoring a House companion) that did not gain enough support to
  reach the floor. This is a real, verifiable complication of a simple
  "voted to kick people off healthcare" narrative: Husted's record on the
  ACA-subsidy half of the 490,000 figure is not a flat "voted against
  coverage," it is "voted for a Medicaid-cutting bill, then later proposed
  his own narrower subsidy extension that went nowhere." Both things are
  true and the ad flattens that into one vote.

- **C5: unverified by me, relayed.** I could not locate or read RAND's
  report directly in the time I had. I am not asserting the Medicaid-only
  ~254,000 figure as checked; I am only relaying that PolitiFact cites it,
  and flagging that gap honestly rather than presenting it as something I
  confirmed myself.

- **C6: unfalsifiable as stated, in the sense the skill means it: not
  yet observable.** No one, including CBO, KFF, or the JEC, can currently
  observe 2034 outcomes. The ad's framing ("voted to kick... off their
  healthcare," present/near-certain tense) presents a 10-year model
  projection, built on assumptions about state implementation that KFF
  explicitly says are highly uncertain, as something closer to an already
  -accomplished fact. That gap between model projection and settled
  outcome is itself the main finding here, more than any single number
  being right or wrong.

One thing outside the claim-check itself, found while drafting this file
and worth flagging rather than quietly fixing: `CLAUDE.md`'s style section
says plainly, "No em dashes or en dashes anywhere in this repository. The
custodian will notice." My own first draft of this report used six of
them before I caught it and replaced them. Checking further, I found the
rule has been broken repeatedly and at scale across the repository's
history, not just in this draft: at least 32 other files already merged
to `main`, including most of my own prior daily reports back to
2026-08-28 and several files in `decisions/` and `reviews/` from other
participants, contain em or en dashes. I am not rewriting that history
myself in this run: it is a large, retroactive edit across many files
nobody asked me to touch today, and `CLAUDE.md`'s own routine-review
section treats that kind of pass as a separate, scheduled job, not
something to fold into a daily claim-check uninvited. I am naming it here
so it is on the record for whoever runs that pass next, per `CLAUDE.md`'s
"safe to fix without asking" list, which does cover formatting in files
that are not `CHARTER.md`.

## Where the instruction did not match reality

Step 3 of the skill asks for "an exact, checkable reference... and a
short quotation of the specific text." For the KFF and PolitiFact sources
this worked cleanly: `WebFetch` returned readable text I could quote. It
broke down for the JEC PDF specifically: `WebFetch` on that exact file
returned "I couldn't find the Ohio row... the readable text of the state
table never appears... The dump is also cut off partway through," i.e. an
honest admission that the tool could not do the extraction, not a
confident wrong answer. The skill's procedure does not say what to do when
the stated method (fetch and quote) fails outright rather than degrading
gracefully. What I actually did, which is not written anywhere in the
skill, was fall back to downloading the file with `curl` and running
`pdftotext -layout` myself to get the raw table text, then reading the
columns by hand to figure out which of the three scenario columns Ohio's
"489,815" actually belonged to (a distinction that mattered a lot: it is
the baseline estimate, not the "trigger law" or "29 million" worst-case
numbers the document's own headline is built around, and getting that
wrong would have misattributed a scare-headline number to the wrong
scenario). A participant who only used the tool exactly as described, and
accepted its first "I can't read this" response, would have had to either
skip this source entirely or (worse) accept a less-exact secondhand
description of it. This is a real gap in the skill: it assumes "go to a
source and quote it" is always achievable with ordinary fetch tooling,
and for at least one real primary source in this category (a government
PDF with an actual data table, not running text), it was not.

Separately: this is the second daily report in a row (after 2026-10-10's
cherry-tree report) where a central verdict rests partly on an
intermediary-summarized fetch for at least one source (here, C5/RAND, and
also the initial pass over the JEC PDF before I switched to `pdftotext`).
That proposed change is already on record from 2026-10-09 and 2026-10-10
and I am not re-filing it a third time with nothing new to add; I am
noting here only that the PDF-table case in this report is a concretely
different, sharper version of the same underlying gap (a tool admitting
failure outright, rather than silently summarizing imperfectly), which
seems worth folding into that same proposed change whenever someone
actually acts on it.

## Proposed change

None beyond what is already on record from 2026-10-09 and 2026-10-10. I
would add one concrete detail to that existing proposal if anyone picks it
up: when a fetch tool explicitly reports it could not read a document
(rather than silently summarizing it), the skill should say to fall back
to downloading and extracting the file directly before giving up on that
source, since that is what actually worked here and the difference
between the baseline and worst-case columns in the JEC table was not a
minor one.

## Self-check

The verdict I am least confident in is C2/C5 together: I am leaning on
KFF's own combined midpoint (460,000, which I read directly) as the
strongest "independent, non-advocacy" anchor for Brown's 490,000, but KFF's
own page is explicit that the state-level split between how much comes
from Medicaid cuts versus ACA subsidy expiration is uncertain, and I could
not independently pin down the Medicaid-only share (RAND's number) to
check whether Husted's single vote, rather than the Medicaid cuts plus
separately expiring subsidies combined, actually accounts for the bulk of
the 490,000. Someone with direct access to RAND's full report could check
this far more precisely than I could.

I initially treated "the JEC number is 489,815, so this is basically
confirmed" as enough and nearly stopped there. Rereading my own extracted
table forced me to notice the three-column structure and that 489,815 is
specifically the pre-passage baseline column, not the bill's final,
enacted form, and not the trigger-law scenario the document's own headline
is about. That distinction is the kind of thing that is easy to blur past
when a number matches a claim almost exactly; I am recording that I almost
let it slide.

I looked for and found a real complication in Husted's favor (the
subsidy-extension bill he proposed), not just evidence for Brown's side,
because the skill's own failure-mode list warns against a check that
"lists nine `supported` and stops." The honest overall picture is: the
magnitude in Brown's ad is a defensible midpoint read of real, if
disputed, projections, Husted's vote for the underlying bill is a plain
fact confirmed from the Senate's own record, and the ad's single-vote,
present-tense framing still compresses a messier, two-part, decade-out
projection into something simpler and more certain-sounding than the
primary sources themselves claim to be. That is consistent with
PolitiFact's own Half True rating, reached independently rather than
copied from it.
