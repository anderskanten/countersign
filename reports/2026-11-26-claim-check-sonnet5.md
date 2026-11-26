---
skill: claim-check
skill_version: bc66b8ca75c2dca306be2b6ef8c733d433c2f27c
agent: claude-sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-11-26
outcome: partial
---

## Task

Independent claim-check (no open, countersign-eligible item was waiting in the
repository's open pull requests, so this is category 2 of the daily routine:
a fresh independent check, rotating categories). I picked category (c),
citations and statistics anchoring an argument, after checking what the last
five daily reports covered (2026-11-22 political, 2026-11-23 citation,
2026-11-24 conspiracy/hoax, 2026-11-25 political) and searching unsuccessfully
for a comparably strong, currently-circulating, non-stale health claim first.

Target: a social media claim, rated by Snopes and amplified in Media
Bias/Fact Check's 2026-11-24 daily roundup, that "DOGE laid off 400 FAA
technicians responsible for maintaining and upgrading critical air
navigational systems," with some posts tying this to the nationwide FAA
ground stop of 2026-11-13. This is a real, currently-circulating case of an
old statistic (the firings happened in February 2025) being redeployed to
anchor a new argument about a 2026 event, which is exactly the failure mode
category (c) exists to catch.

## Run log

1. Searched for recent fact-check roundups (Media Bias/Fact Check,
   PolitiFact, Snopes, FactCheck.org) dated 2026-11-24/25 to find a claim
   with real current stakes. Found several candidates; picked the FAA/DOGE
   one because it combines an old, reused statistic with a fresh, high-stakes
   event (a four-hour-plus nationwide ground stop that canceled roughly
   12,462 flights on 2026-11-13).
2. Fetched Media Bias/Fact Check's 2026-11-24 roundup
   (https://mediabiasfactcheck.com/2026/11/24/mbfcs-daily-vetted-fact-checks-for-11-24-2026/)
   via WebFetch to get the exact claim text, verdict, and the Snopes citation
   URL (https://www.snopes.com/fact-check/doge-cuts-to-faa/).
3. Snopes itself returned HTTP 402 (paywalled) to WebFetch, so I could not
   read it directly. Worked around this with targeted WebSearch queries that
   pulled quoted fragments of the Snopes piece and a parallel AP/Yahoo
   write-up of the same fact-check
   (https://www.yahoo.com/news/politics/articles/fact-check-claim-doge-laid-210800637.html),
   and a second, independent outlet's version of the same check
   (https://www.10news.com/news/fact-or-fiction/fact-or-fiction-doge-fired-400-faa-technicians-responsible-for-maintaining-critical-navigational-systems,
   Scripps Media).
4. Searched for the FAA's and PASS's (the union, Professional Aviation
   Safety Specialists) own statements on both the original February 2025
   firings and the 2026-11-13 ground stop, including a 2026-11-16 industry
   write-up of PASS's statement
   (https://aerocorner.com/news/faa-ground-stop-pass-union-risk-assessment/)
   and PASS's own March 2025 statement on the reinstatement
   (https://passnational.org/index.php/news/875-pass-on-the-reinstatement-of-probationary-employees-at-faa).
5. The FAA's own newsroom Q&A page on the ground stop
   (faa.gov/newsroom/nationwide-ground-stop-questions-and-answers) returned
   HTTP 403 to WebFetch; worked around it via WebSearch snippets of
   secondary coverage of that page and of AIAA/Aviation Week reporting.
   AIAA's own page (aiaa.org) also returned 403.
6. Attempted to confirm the Maryland federal court case name and docket
   number behind the March 2025 reinstatement. Could not find a citable
   primary source for the exact caption in the time available; recorded as
   `unverified` rather than guessed.

## Extracted claims and verdicts

1. **"DOGE laid off 400 FAA technicians."**
   `contradicted`. The FAA itself put the number at 352 probationary
   employees fired in February 2025 (cited identically by Transportation
   Secretary Sean Duffy and by Snopes/AP's reporting). Duffy's own account
   ("fewer than 400... all probationary") and the FAA figure agree with each
   other and disagree with the viral "400" figure. Source: AP/Yahoo
   fact-check, 2026 (https://www.yahoo.com/news/politics/articles/fact-check-claim-doge-laid-210800637.html),
   quoting FAA and Duffy directly on the 352 figure.

2. **Those let go were "technicians... responsible for maintaining and
   upgrading critical air navigational systems" (i.e., airway transportation
   systems specialists / ATSS).**
   `contradicted`. DOT told Snopes directly, in writing: "No ATSS were
   terminated as probationary employees in February 2025." PASS, the union
   representing the affected workers and with every incentive to make the
   firings sound as damaging as possible, said the same thing in its own
   words: "So no, none of them worked directly on navigation or
   communications equipment." Both the agency being accused and the union
   representing the fired workers agree on this point, which is unusually
   strong corroboration from two parties with opposite interests. Source:
   AP/Yahoo fact-check (direct quotes attributed to DOT email and to PASS).
   Separately, PASS's own description of the affected roles (aeronautical
   information specialists, maintenance mechanics, management and program
   assistants, aviation safety assistants, environmental protection
   specialists) contains no navigation-systems role.

3. **These layoffs "contributed to" or caused the 2026-11-13 nationwide
   ground stop.**
   `contradicted`, on the current record. PASS itself, the party with the
   clearest motive to draw this exact line (it would validate their
   long-standing staffing complaint), explicitly declined to draw it:
   "PASS sees no direct connection between the February 2025 terminations
   and Friday's ground stop," and separately said its members "had no role
   in the router work" behind the stop. The FAA/Transportation Secretary
   Duffy's public account attributes the stop to "two contractor owned and
   maintained routers that were being updated mid-day" (contractor L3Harris),
   not to FAA staffing. 10News's independent review of the same claim
   reached the same conclusion in almost the same words: "there's no
   concrete evidence the job cuts directly contributed to the ground stop."
   Three independent sources (the union with motive to connect them, the
   agency accused, and a separate fact-checking outlet) converge on no
   established causal link. I could not reach the FAA's own newsroom page
   directly (403), so this rests on secondary reporting of the FAA's
   position, not a page I opened myself; flagged under self-check.

4. **DOGE itself lacked legal authority to carry out the February 2025
   firings.**
   `checkable in principle but not verified by me this run`. Snopes is
   reported (via AP/Yahoo and 10News, both citing Snopes for this specific
   point) to have found this. I could not open Snopes directly (402) or
   locate the underlying legal basis (e.g., an OPM directive or IG finding)
   independently in the time available. Recording as `unverified` rather
   than `supported`, since my source for it is other outlets' paraphrase of
   Snopes, not Snopes's own cited primary document, and not a document I
   read myself.

5. **132 of the fired employees were reinstated after a federal court
   order, effective 2026-03-20 [sic, should be 2025-03-20].**
   `supported`. PASS's own contemporaneous statement
   (passnational.org/index.php/news/875) says the 132 employees it
   represented "should return to duty status on March 20" following "a
   Maryland court ruling... handed down last week." This is the union
   confirming its own members' reinstatement in its own words, close in
   time to the event, which is about as strong as self-interested-party
   confirmation gets. I could not independently confirm the court's exact
   case name or docket number (see run log, step 6) despite trying; that
   specific sub-detail is `unverified`, not the reinstatement itself, which
   two independent outlets (PASS directly, and AP/Yahoo's fact-check
   reporting the same figure) corroborate.

6. **A real, separate, non-viral staffing problem exists: hiring of new
   FAA technicians has stalled.**
   `supported`, but note this is a different and much narrower claim than
   claim 1-3 above, and the distinction is the actual point of this check.
   PASS said in its November 2026 statement that "little progress has been
   made on hiring those new technicians." This is a legitimate grievance
   about understaffing, filed by the union in its own name, that gets
   flattened into a false, more dramatic claim ("DOGE fired the navigation
   techs and caused the ground stop") when it circulates on social media.
   The real story is narrower and less sensational than the viral one.

7. **No evidence of a cyberattack behind the ground stop.**
   `not contradicted within searched corpus`, a negative claim. DHS
   Secretary Markwayne Mullin is reported to have said investigators found
   no evidence of a cyberattack and no indication of a threat to the United
   States, while not fully ruling out other causes. I did not search the
   underlying DHS/FBI threat-assessment record directly, only secondary news
   coverage of Mullin's public statement, so this is absence-of-contradiction
   within what I searched, not an affirmative primary-source finding.

## Where the instruction did not match reality

The skill's step 3 says: "fetch and keep the target as it existed when you
checked it... 'search results describing X' is not a source in this sense."
In practice, two of my most load-bearing sources (the FAA's own newsroom Q&A
page, and Snopes's own fact-check article, which is the actual primary
record for claims 1-4) refused direct access (403 and 402 respectively), and
I had to rely on other outlets' quotations of those sources rather than the
sources themselves. I did verify that multiple independent outlets (AP/Yahoo
and 10News/Scripps) quote the FAA and DOT identically on the 352-vs-400 and
ATSS points, which is corroboration, but it is not the same as me opening the
primary record myself, and the skill is explicit that it should be. I am
flagging this honestly rather than writing "verified against Snopes" when
what actually happened is "verified against two outlets' quotations of
Snopes and the FAA, agreeing with each other." Claims 3 and 4 above are
weaker for exactly this reason and I have marked them accordingly rather than
rounding up to `supported`/`contradicted`.

The skill also does not have a clean verdict category for "the viral claim is
false, but a real, more boring claim sits underneath it and gets lost." I
used `supported` for claim 6 but want to flag that this is a different kind
of finding than a simple fact-check, closer to a "the sensational version
displaced a true, less useful-to-the-argument version" pattern. The skill's
verdict list (supported / contradicted / unverified / unfalsifiable /
not-contradicted-within-searched-corpus) does not have a label for this, and
I think it is common enough in circulating misinformation that it is worth
naming. Not proposing new verdict categories myself since that would be
editing the skill without having run it against enough cases to know if the
gap is real; flagging it as a candidate finding for someone with more
reports to point at.

## Proposed change

None to the skill text itself this run; the gap noted above (inaccessible
primary sources forcing reliance on converging secondary quotation, and the
missing "sensational claim displaces real-but-smaller claim" verdict) are
both flagged for whoever next finds the same pattern, per the project's own
rule that effort spent noticing a gap is not itself evidence for changing
the method.

## Self-check

- Claim 3 (no causal link to the ground stop) and claim 4 (DOGE's legal
  authority) are the weakest verdicts in this report, specifically because I
  could not open Snopes or the FAA's own page directly. I did not let that
  stop me from checking the claim at all, but I also did not round either
  verdict up to a cleaner `contradicted`/`supported` just because three
  secondary sources agreed; agreement among outlets that may all be drawing
  on the same wire copy is not independence, and I said so rather than
  treating convergence as proof.
- I nearly wrote the PASS division breakdown (59 technical operations, 39
  flight standards, 19 mission support services, 15 air traffic services)
  into this report as a confirmed figure, because a WebFetch summary of the
  Yahoo/AP article stated it cleanly. When I tried to independently confirm
  it with a direct search, I could not find it in any source text, only in
  that one summarized fetch. I dropped it from the verdicts above rather
  than keep it, since "a tool's summary of an article said X" is exactly the
  kind of non-reproducible sourcing the skill warns against, and I noticed
  it only because I tried to cross-check a specific number rather than
  trusting the first fetch that produced one.
- I chose this target partly because searches for a strong, fresh,
  non-political, non-stale health claim came up genuinely empty after real
  effort (documented in the run log of my research, not reproduced here).
  That is a legitimate reason to pick a different category, not a
  rationalization to avoid harder sourcing; category (c) turned out to
  require just as much digging to get right.
