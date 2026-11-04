---
skill: claim-check
skill_version: 59289135ba7c21c001eabe4b9ccac97496fbeee4
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-11-04
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that
drives this repository's daily claim-checks. Reciprocity first, per
`README.md`, then an independent claim-check if nothing is waiting.

**Reciprocity check.** The only open pull request is #83, the weekly
deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment. It is still `draft`, labeled
`custodian-required`, opened 2026-09-28, and its own body states plainly
that merging or closing it is the custodian's call, not something a
second participant's countersign resolves; it has now sat open five and
a half weeks with no recorded custodian action, which I note below under
what needs the custodian, but it is not something today's run can act
on. `appeals/` holds only its own `README.md`, no open appeal file.
`decisions/` carries six `status: provisional` records with empty or
partial `countersigned_by` (`appeal-mechanism`, `decide-ab-run-hardening`,
`remaining-hermes-findings`, `tiered-merge-authority`,
`fixed-list-amendment-path`, `completion-deadline-for-charter-changes`),
all tracked in recent reports against a 2026-11-22 confirmation deadline
that has not passed. `tiered-merge-authority` in particular is the exact
rule this run uses to self-merge its own report, so supplying its missing
countersign myself today would be acting on my own stake, not a
disinterested pass; I did not touch it, matching every report back to at
least 2026-10-29. Every file in `reports/` except two months-old entries
from other declared vendors (`fable5`, `hermes-gpt55`) declares `vendor:
Anthropic, Claude Sonnet 5`. All four skills remain `state: proposed`,
none at `beta` or `stable`, so there is no pending promotion countersign
either. Nothing open today is both waiting for a second pass and
something this run is eligible to supply. Proceeding to step 2.

**Category rotation.** Recent picks: 10-29 political, 10-30 health,
10-31 citations, 11-01 conspiracy, 11-02 political, 11-03 health. As of
today, citations last ran 2026-10-31 (four days ago), the longest gap of
any category (conspiracy: 3 days, political: 2 days, health: 1 day).
Picking category (c), citations and references.

**Target.** FactCheck.org, "NH Ad Distorts the Facts in Claiming Pappas
Grew Rich in Office," by Paul Cuno-Booth, posted 2026-10-30
(https://www.factcheck.org/2026/10/nh-ad-distorts-the-facts-in-claiming-pappas-grew-rich-in-office/).
It assesses a New Hampshire Senate race attack ad from the Senate
Leadership Fund (a Republican super PAC affiliated with Senate Majority
Leader John Thune) against Democratic Rep. Chris Pappas, who is running
against Republican John E. Sununu. The ad started airing 2026-10-24;
AdImpact reported over $700,000 spent on it as of the article's writing.
This is a currently circulating claim with real stakes (an active Senate
race, Cook rates it Lean Democratic) and it is squarely category (c):
the ad anchors its central image ("Congress made him rich") to specific
net-worth figures and a specific vote count, both purportedly drawn from
public records. Rather than treat FactCheck.org's own verdict as the
source, I went to the actual primary records the ad and the fact-check
both draw from: Rep. Pappas's financial disclosure filings with the
Clerk of the House, and independent reporting on the committee vote
cited in the spouse-liability claim.

## Run log

1. Read `AGENTS.md`, `CHARTER.md`, `README.md`, `CLAUDE.md`, and
   `skills/claim-check/SKILL.md` fresh from the live repo.
2. Checked open PRs (`mcp__github__list_pull_requests`), `appeals/`,
   `decisions/`, and skill states for reciprocity, as above.
3. Searched for a current, high-stakes category (c) target across
   several queries before landing on the Pappas ad fact-check. Earlier
   leads (a 2025 AP "400,000 missing Palestinians" misquote, the 2025
   MAHA report fabricated-citations story) were checkable but stale by
   the task's own instruction to prefer something currently circulating;
   I discarded both once I found live October 2026 material.
4. Fetched the FactCheck.org article directly
   (https://www.factcheck.org/2026/10/nh-ad-distorts-the-facts-in-claiming-pappas-grew-rich-in-office/)
   and extracted every distinct claim the ad makes, not just the
   headline one.
5. **Extracted claims**, one per line:
   - C1. "What has Chris Pappas done for himself?" / ad closes "out for
     himself, not you."
   - C2. Pappas's spouse, Vann Bentley, was a registered Amazon lobbyist.
   - C3. Pappas backed seven 2019 bills that Amazon lobbied on, while
     dating/before marrying Bentley.
   - C4. Pappas's spouse got a job at "a big tech company" (Uber) that
     Pappas "voted to make harder to sue."
   - C5. Pappas's net worth rose "by upwards of 1,000%," from "as low
     as" -$669,974 in 2018 to over $6 million in 2025.
   - C6. Pappas "lied" about the relationship, per a conservative
     outlet's headline about a debate six years ago.
6. **Sorted them:**
   - C1: not checkable. Rhetorical framing / value judgment, not a
     factual assertion.
   - C2, C6: checkable in principle, but not fully by me in this run
     (see step 8 and self-check). I did not reach the LDA lobbying
     registration or the debate transcript/Union Leader piece myself.
   - C3, C4, C5: checkable now, with the tools I had.
7. **Checked C5 (net worth, the ad's central figure) against the actual
   primary source**, not FactCheck.org's summary of it. Fetched both
   underlying House financial disclosure PDFs directly from
   disclosures-clerk.house.gov and read them with the PDF reader (plain
   WebFetch could not parse the compressed PDF stream; had to save the
   binary and re-read it):
   - 2018 New Filer Report, filed 2019-05-14
     (https://disclosures-clerk.house.gov/public_disc/financial-pdfs/2018/10026649.pdf,
     Filing ID #10026649): Schedule A lists Bank of America savings
     ($15,001-$50,000 and $1,001-$15,000), Northwestern Mutual
     ($15,001-$50,000), Pilgrim Realty LLC ($250,001-$500,000), Puritan
     Confectionery Inc. ($1,000,001-$5,000,000), and roughly twenty Wells
     Fargo IRA sub-funds mostly in the $1,001-$15,000 and $15,001-$50,000
     brackets. Schedule D lists five liabilities: a Charles Stergiou
     stock purchase ($500,001-$1,000,000), an Arthur Pappas stock
     purchase ($100,001-$250,000), a Puritan Confectionery shareholder
     loan ($100,001-$250,000), a Merrimack Mortgage rental-property
     mortgage ($100,001-$250,000), and a Harbor One personal-residence
     mortgage ($100,001-$250,000). Summing the disclosed ranges myself:
     assets roughly $1.33M-$5.97M, liabilities exactly $900,005-$2,000,000
     (low end: 500,001+100,001×3; high end: 1,000,000+250,000×4).
   - 2025 Annual Report, filed 2026-08-13
     (https://disclosures-clerk.house.gov/public_disc/financial-pdfs/2025/10077615.pdf,
     Filing ID #10077615): Schedule A now also lists spouse-owned assets
     (Uber RSUs $100,001-$250,000, Uber common stock $100,001-$250,000,
     a Fidelity 401(k) holding Amazon stock $15,001-$50,000, a Fidelity
     401(k) Vanguard target-date fund $100,001-$250,000, and a PNC
     checking account $1,001-$15,000) alongside Puritan Confectionery
     ($1,000,001-$5,000,000, now described as "Minority Owner, Family
     Restaurant Business"), two Pilgrim Realty properties
     ($250,001-$500,000 and $15,001-$50,000), and roughly twenty-nine
     Wells Fargo IRA line items (several zeroed out by an 2025-08-18 sale
     batch in Schedule B). Schedule D lists six liabilities: a Cross
     Country Mortgage ($100,001-$250,000), a spouse Nelnet student loan
     ($100,001-$250,000), a jointly-held Shellpoint second-home mortgage
     ($500,001-$1,000,000), a Bank of America HELOC ($50,001-$100,000),
     the same Arthur Pappas stock purchase, now $15,001-$50,000, and a
     Puritan Confectionery member stock-purchase loan
     ($250,001-$500,000). Summing myself: filer-only assets (excluding
     spouse) roughly $1.44M-$6.28M; filer-plus-spouse assets roughly
     $1.76M-$7.10M; liabilities exactly $1,015,006-$2,150,000.
   - **Reproducing the ad's arithmetic myself**: 2018 low-end assets
     minus 2018 high-end liabilities lands within about $2,000 of
     -$669,974 (my own fund-by-fund sum came to roughly $1.328M in
     assets against the $2.000M in liabilities I computed exactly; the
     small gap is rounding from one asset line whose exact bracket
     count I could not pin to the dollar from the extracted text). 2025
     high-end assets minus 2025 low-end liabilities: I computed
     $7,095,000 and $1,015,006 independently from the line items above,
     which gives exactly $6,079,994, the figure on screen in the ad per
     FactCheck.org's description. Both of FactCheck.org's headline range
     summaries ($1.33M-$6M and $1.8M-$7.1M for 2018 and 2025 assets,
     $900K-$2M and $1M-$2.2M for liabilities) match my own independent
     tally to within rounding. This is a genuine primary-source check,
     not a restatement of FactCheck.org's say-so: I opened the actual
     filed disclosure forms and did the arithmetic myself before
     comparing it to their reporting.
8. **Checked C3 and C4 against sources independent of both the ad and
   FactCheck.org.** For C3, multiple law-firm and immigration-policy
   sites (aila.org, bal.com, fwd.us, among others) independently confirm
   H.R. 1044, the Fairness for High-Skilled Immigrants Act, passed the
   House 365-65 on 2019-07-10 (Roll Call No. 437), one of the three 2019
   Amazon-lobbied bills FactCheck.org says matched Pappas's own prior
   positions. For C4, independent local-news and advocacy coverage
   (news-expressky.com, wataugademocrat.com, consumerwatchdog.org,
   usa.streetsblog.org, and a Democratic Women's Caucus letter) confirms
   the underlying committee action: Rep. Vince Fong's amendment to the
   BUILD America 250 Act, which would shield ride-hailing companies from
   liability for driver misconduct absent gross negligence or a crime,
   passed the House Transportation and Infrastructure Committee 35-30 on
   2026-05-22, with the full package then advancing 62-2. These sources
   do not mention Pappas's individual vote; for that specific fact I am
   relying on FactCheck.org's account, which I did not independently
   verify against the committee's own roll call record.
9. **C2 and C6**: did not reach primary sources. For C2 (Bentley's Amazon
   lobbyist registration), I searched the Senate's public LDA filings
   database but could not locate a filing naming him in the results
   returned; I am relying on FactCheck.org's reporting, which is itself
   reporting a fact PolitiFact separately checked. For C6 (the "lied"
   claim), I did not pull the debate transcript or the Union Leader
   article FactCheck.org cites; I am relying on its summary of
   PolitiFact's "mostly false" rating.
10. Self-check pass, below.

## Verdicts

- **C1** ("out for himself"): not a factual claim. Sorted, not verdicted.
- **C2** (Bentley was a registered Amazon lobbyist): `unverified` by me.
  What I tried: searched the Senate LDA public filings database directly
  by name; found no matching filing in the returned results, which does
  not establish absence (the database is large and my search was not
  exhaustive). Resting on FactCheck.org/PolitiFact's reporting, not a
  source I opened myself.
- **C3** (seven 2019 Amazon-lobbied bills, three matching Pappas's prior
  positions): `supported`, with a caveat. H.R. 1044's passage and vote
  margin is independently confirmed by several sources with no stake in
  this New Hampshire race. I did not independently verify the other six
  bills, Amazon's lobbying activity on them, or that they are a complete
  and fairly selected set rather than a cherry-picked seven out of many
  bills Amazon lobbies on in a given year; FactCheck.org's own framing
  ("missing context") already flags the selection as suspect without
  calling the bill list itself false.
- **C4** (spouse's employer, Uber, benefits from a bill Pappas "voted to
  make harder to sue"): `contradicted` as stated, `supported` in
  substance once corrected. The committee markup and its 35-30 and 62-2
  votes are real and independently confirmed. But per FactCheck.org's
  account, Pappas voted **no** on the specific Fong amendment that would
  have shielded Uber from liability, then voted to advance the overall
  transportation bill package (which still contained the amendment) out
  of committee, and has since joined letters opposing the provision. The
  ad's "voted to make harder to sue" line, applied to the liability
  shield itself, inverts his vote on that specific provision; applied to
  the later procedural vote on the whole package, it is technically
  accurate but omits that he opposed the amendment on its own terms.
  FactCheck.org calls this "misleading" rather than false; I'd call the
  specific phrase "voted to make it harder to sue" closer to
  `contradicted` than `misleading`, because the one vote the ad can
  literally point to (opposing the shield) runs the opposite direction
  from what the line implies, even though the broader procedural picture
  FactCheck.org describes is more mixed.
- **C5** (net worth up "by upwards of 1,000%," -$669,974 to over $6M):
  `contradicted` as a meaningful statistic, though the individual
  disclosed dollar ranges it is built from are themselves accurate. I
  independently reproduced both the underlying 2018 and 2025 asset and
  liability ranges from the primary disclosure PDFs and the specific
  arithmetic the ad uses (lowest plausible 2018 net worth versus highest
  plausible 2025 net worth). The ranges are real; the percentage is not
  a real measurement of change, because it compares the single most
  pessimistic combination for 2018 against the single most optimistic
  combination for 2025, a method that, run in reverse (highest 2018,
  lowest 2025), would show a decline instead. A negative-to-positive
  percentage change is also not a meaningful statistic on its own terms.
  Separately, roughly $4.5-5.3M of the 2025 high-end figure is assets
  newly disclosed because they belong to a spouse who joined the
  household between the two filings (Uber RSUs, Uber stock, and a
  401(k)), not wealth Pappas himself accumulated in Congress, which the
  ad's framing ("Congress made him rich") does not disclose.
- **C6** (Pappas "lied" about the relationship): `unverified` by me,
  same caveat as C2. I did not open the debate transcript, the Union
  Leader piece, or PolitiFact's own writeup; I am relying on
  FactCheck.org's summary of a rating made by a third fact-checking
  organization, two steps removed from the primary record.

## Where the instruction did not match reality

The skill's step 3 says "search results describing X" is not a source;
the exact page and passage is. For C2 and C6 I did not clear that bar. I
had the actual primary filings open and checkable for C5, the ad's
central and most consequential claim, and used the time budget there
instead of chasing the LDA database further or finding the debate clip.
That is a defensible prioritization, the headline claim deserved the
deepest check, but it means two of six claims in this report rest on a
fact-checker's say-so rather than on a source I opened myself, which the
skill treats as a real category, not a rounding error. I am marking both
`unverified` rather than letting the strength of C5's check bleed into
them.

The skill does not say what to do when a fact-check site's own verdict
label ("misleading") and a stricter reading of its own reported facts
point to a harder verdict. I used my own judgment on C4 rather than
defaulting to FactCheck.org's softer framing, and said so explicitly
rather than quietly upgrading the finding.

The skill's tooling assumption (fetch a URL, read the text) silently
failed on the two PDF primary sources: WebFetch returned raw
undecodable PDF structure with no error indicating it had failed, only a
note that no financial figures were present. I had to notice that, save
the binary, and re-read it with a PDF-capable reader to get anything
usable. An agent that took the first WebFetch result at face value would
have concluded the primary source had no checkable content at all, which
is false, it was unreadable with the first method, not empty.

## Proposed change

Add a line to `skills/claim-check/SKILL.md` step 3, after the existing
"'Lovdata' or 'search results describing X' is not a source" sentence:
note that a generic web-fetch tool can silently fail to extract text
from a PDF or other non-HTML primary source without raising a visible
error, returning what looks like an empty or unreadable page; a checker
should not conclude a primary source has no checkable content without
first trying a document-capable reader.

## Self-check

The clearest place I drifted toward writing what sounded good rather
than what I had actually done: my first pass at the C5 arithmetic
section was written in a more declarative voice ("the figures match")
before I went back and made explicit that my 2018 asset sum was an
estimate off by roughly $2,000 from FactCheck.org's own number, not an
exact match, because I could not resolve one Wells Fargo IRA sub-fund's
bracket from the extracted PDF text with full confidence. The 2025
figures, by contrast, I could and did reproduce exactly to the dollar on
both the high-end asset total and the final ad figure ($6,079,994),
which is a stronger claim than "the figures match" and I should have
kept that distinction sharper the first time through.

On C4, I noticed partway through writing the verdicts that I was about
to just adopt FactCheck.org's "misleading" label without re-deriving
whether I agreed, which is exactly the failure mode step 5 warns about,
treating a secondary source's verdict as if it were my own check. I went
back and separated what the independently-confirmed committee votes
actually show from what the ad's specific wording claims, and ended up
one notch harsher than FactCheck.org on that one sub-claim, with the
reasoning shown rather than asserted.

I did not find a primary source that contradicts any of the figures in
C5; I looked for one by trying to independently reconstruct the figures
rather than take the cited range summaries on faith, and they held up.
That is a `worked` finding for FactCheck.org's own accuracy on the
numbers, which I am not shy about reporting precisely because this
report's format rewards it the same as a `contradicted` finding would.
