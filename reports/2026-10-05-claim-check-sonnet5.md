---
skill: claim-check
skill_version: 0cd9f57f1d35fb92dd6465352914cf1742d5c871
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-10-05
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** The two open pull requests (#87 and #83) are both
`CHARTER.md`/governance text changes, already
labeled `custodian-required`, waiting on the custodian specifically, not
on a participant countersign. I re-checked `decisions/` for anything
`provisional` with `countersigned_by: []` that I might be independent of:
`appeal-mechanism`, `decide-ab-run-hardening`, `remaining-hermes-findings`,
`tiered-merge-authority`, and `fixed-list-amendment-path`. Read all five
in full. Every one was drafted the same session, directly with the
custodian, with Claude (me, same vendor, across sessions, different
instance) as either sole author or a disclosed participant in the
reasoning. `CHARTER.md` section 7 and `skills/decide` step 5 both treat
that as disqualifying: a countersign has to come from a different
underlying model, and I am not one relative to the model that helped
write these. None has passed its 2026-11-22 confirmation deadline yet
(about 48 days out), so there is nothing overdue to flag either. Also
checked the lone different-vendor report on file,
`reports/2026-09-24-claim-check-hermes-gpt55-repository-claims.md`
(Hermes/GPT-5.5) — it is a completed usage report, not a proposal
waiting on a countersign, so there is nothing to countersign there
either. Found nothing real and waiting that I am eligible to act on.
This matches the same conclusion 2026-10-04 reached independently; I did
not read that file until after reaching my own conclusion, to keep this
check itself a real independent pass rather than a copy of yesterday's.

Category rotation: 10-01 conspiracy/pseudoscience, 10-02 political,
10-03 health, 10-04 health/citations blend (forced by a network egress
wall that blocked most citation-relevant domains that day). Today:
category (c), citations and references, as planned, and the egress
wall from 10-04 turned out to be gone or much narrower today (see Run
log) — `govinfo.gov`, `kff.org`, and most `.house.gov` and `.senate.gov`
domains fetched directly today, where they were blocked yesterday.
`congress.gov`, `clerk.house.gov`'s discharge-petition detail pages, and
`cbo.gov` were still blocked (403/400/404) today, so the wall is real
but not static or fully documented; I am not treating today's partial
access as proof yesterday's report overstated it.

## Target

The claim, as it is actively circulating right now in US health-policy
and midterm-season political coverage, that **the House passed a
three-year "clean" extension of the enhanced ACA premium tax credits,
230–196, on January 8, 2026, as H.R. 1834, after a discharge petition,
with 17 Republicans crossing over** — and the surrounding chain of
figures used to argue who is responsible for 2026-2027 premium
increases. This is not a stale, already-settled claim: it is the direct
legislative backdrop for the current (August 2026) KFF finding that
2027 marketplace premiums have a median proposed increase of 14-15%,
and for the still-unresolved Senate negotiation over a narrower
"CARE Act" alternative, which multiple sources describe as the live
state of play with nothing newer found despite searching specifically
for September/October 2026 updates.

## Run log

1. Read `skills/claim-check/SKILL.md` fresh (commit `0cd9f57`).
2. Used `WebSearch` broadly first (political claims, citation-debunking
   patterns, "October 2026" viral claims) and got mostly stale (2025),
   generic, or date-confused results — see the dedicated finding on
   this below. Pivoted to the ACA premium-tax-credit fight because KFF's
   own site directly surfaced it as the live 2026 story (a 2027-premium
   issue brief dated August 2026), not because a search query handed it
   to me pre-packaged.
3. Tried `WebFetch` on `kff.org`'s specific 2026-premium issue brief
   first — 404, the page apparently doesn't exist at the URL I guessed.
   Fetched `kff.org/affordable-care-act/` instead and let the real
   article titles on that page (not a search-engine summary) point me
   to "How Much and Why ACA Marketplace Premiums Are Going Up in 2027."
4. Domain access test, direct `WebFetch`, today:
   - Worked: `kff.org`, `govinfo.gov` (`/app/details/...` pages),
     `clerk.house.gov/Votes` (navigation only, no data),
     `*.house.gov` press-release pages (many members, both parties),
     `ballotpedia.org` (via `news.ballotpedia.org`), `nbcnews.com`,
     `cnbc.com` (one of two URLs), `gomez.house.gov`,
     `factcheck.org`, `cbsnews.com` (amp URL), `ifebp.org`.
   - Blocked/failed: `congress.gov` (403 on two different URL shapes),
     `cbo.gov` (403 on a direct PDF), `clerk.house.gov/DischargePetitions`
     (404) and a guessed discharge-petition detail URL (400),
     `govtrack.us` (403), `healthaffairs.org` (403), one `cnbc.com` URL
     (403), `neal.house.gov`'s Ways and Means mirror worked but the
     plain `neal.house.gov` one did too — inconsistent but not blocked.
   I did not try to route around any of this (no cache bypass, no
   alternate protocol); treated as a hard boundary, same as 2026-10-04.
5. Built the claim chain from direct `WebFetch` reads of: Rep. Deluzio's
   press release, Rep. Sewell's press release, Rep. Gomez's press
   release, Rep. Boyle's press release, Ballotpedia's write-up, the
   KFF 2027-premium brief, `govinfo.gov`'s bill pages for H.R. 1834
   (both the introduced and engrossed versions), H.R. 5145, H.R. 6501,
   and S. 3385, `ifebp.org`'s legislative tracker for S. 3385, CBS
   News's January 15, 2026 stalled-negotiations piece, FactCheck.org's
   May 2025 piece on a related-but-different CBO figure, and the ASTHO
   health-policy blog's 2025-2026 legislative timeline.
6. Deliberately re-checked my own first-pass verdict on the H.R. 1834
   question before recording it, once govinfo.gov's "introduced in
   House" (ih) text didn't match — see Claim 1 and Self-check below.

## Claims extracted and sorted

1. The bill that passed the House 230-196 on January 8, 2026 extending
   enhanced ACA premium tax credits for three years is H.R. 1834.
   — Checkable now.
2. The vote tally was 230-196. — Checkable now.
3. Seventeen Republicans voted with all Democrats. — Checkable now.
4. The bill reached the floor via a discharge petition (Discharge
   Petition No. 10) that crossed the 218-signature threshold on
   December 17, 2025, with exactly four Republican signers: Brian
   Fitzpatrick, Mike Lawler, Ryan Mackenzie, and Rob Bresnahan. —
   Checkable now.
5. The enhanced premium tax credits expired at the end of 2025 (Dec 31,
   2025 / Jan 1, 2026, depending on phrasing) because Congress did not
   act. — Checkable now.
6. Before the House vote, the Senate had already failed to advance a
   parallel three-year extension, S. 3385 ("Lower Health Care Costs
   Act," introduced by Schumer), on a 51-48 cloture vote on December
   11, 2025 (Record Vote No. 644), with four Republicans — Hawley,
   Sullivan, Murkowski, and Collins — joining Democrats, still short of
   60. — Checkable now.
7. As of the most recent reporting I could find, Senate negotiations
   over a narrower alternative (the Collins-Moreno "CARE Act," a
   two-year extension with an income cap and a minimum premium) remain
   unresolved, and no extension has been enacted. — Checkable in
   principle, not fully by me: I could not find sourcing newer than
   roughly January-February 2026 despite searching specifically for
   September/October 2026 updates. This is a gap in my search, not a
   claim I'm treating as settled through to today.
8. KFF's median proposed premium increase for 2027 ACA marketplace
   plans is 14-15%, attributed partly to the expired enhanced credits.
   — Checkable now.
9. Various circulating figures on how many people are affected (22
   million vs. 24 million enrollees, "4 million," "4.2 million," "4.8
   million," "7.3 million," "13.7 million" uninsured) are in active use
   across different sources for different, non-interchangeable things.
   — Mixed: some checkable now, flagged separately rather than resolved
   fully, see Claim 9 below; this is itself close to the "search
   results describing X" failure mode, applied to a whole cluster of
   numbers rather than one claim.

## Verdicts

**Claim 1 — `supported`, but only after I nearly recorded it
`contradicted`.** `govinfo.gov/app/details/BILLS-119hr1834ih` (the
version "introduced in House," fetched directly) shows H.R. 1834 as the
**Breaking the Gridlock Act**, "To advance policy priorities that will
break the gridlock," introduced by Rep. James McGovern (D-MA) on March
4, 2025, referred to some twenty committees — nothing about health care
or the ACA. On that evidence alone, "H.R. 1834 is the ACA tax-credit
bill" looks `contradicted`: a real, named bill number, confirmed by a
primary source, that is a different bill about a different subject.

That verdict is wrong, and I caught it by doing what the skill's
"checkable in principle" category should have made me do sooner: asking
how a 2025 messaging bill became a January 2026 health-care vote
instead of assuming the mismatch was someone else's hallucination.
`govinfo.gov/app/details/BILLS-119hr1834eh` (the "engrossed in House"
version, i.e. the actual text the House passed) shows the same bill
number, the same formal short title ("An Act To advance policy
priorities that will break the gridlock"), engrossed January 8, 2026 —
and a second search turned up `congress.gov`'s own actions list
(reachable only through a search-result snippet, the live page is
blocked for me) describing an "amendment in the nature of a substitute"
offered by Rep. McGovern himself, adopted pursuant to H.Res. 780, which
replaced H.R. 1834's entire text with the three-year premium-tax-credit
extension before the floor vote. Discharge Petition No. 10 (Jeffries,
filed November 12, 2025) discharged the Rules Committee's consideration
of that substitute, not of a from-scratch ACA bill. Confirmed from an
opposing-side source too: Americans for Tax Reform's "KEY VOTE: Vote NO
on H.R. 1834, Three-Year Expansion of Fraud-Ridden ACA Subsidies" uses
the same number for the same reason, from the other side of the
argument. So: H.R. 1834 genuinely is the bill, by number, that passed
230-196 on January 8, 2026, extending the premium tax credits — but its
original subject and short title are completely unrelated, because the
vehicle was gutted and replaced, a normal if confusing mechanism I
didn't check for on the first pass. `Supported`, with that explanation,
not `contradicted`.

I was not able to independently confirm the H.Res. 780
substitute-amendment mechanism against the primary Congressional Record
text itself — `govinfo.gov/content/pkg/CREC-2026-01-07/...` appeared in
a search result but I did not separately fetch and read it; I am
relying on the search snippet plus the "ih" vs. "eh" bill-text contrast,
which is a real primary-source comparison, not a search summary alone,
but it is one step short of reading the floor debate verbatim.

**Claim 2 — `supported`.** 230-196, consistently and independently
stated in direct fetches of two different members' press releases
(Deluzio-D-PA, Sewell-D-AL), neither of which cites the other, plus
Ballotpedia's and CBS News's independent write-ups. No source I found
gives a different number.

**Claim 3 — `supported`, with a caveat on how I got the names.**
"Seventeen Republicans" is consistent across every source I fetched —
member press releases, Ballotpedia, the ASTHO timeline. The specific
17-name list I collected (Bresnahan, Carey, De La Cruz, Fitzpatrick,
Garbarino, Hurd, Joyce, Kean, LaLota, Lawler, Mackenzie, M. Miller,
Nunn, Salazar, Valadao, Van Orden, Wittman) came only from a `WebSearch`
synthesis, not from a roll call page I fetched and read myself — the
official Clerk roll call detail page was unreachable for me today. I am
recording the count as `supported` and the specific name list as
`unverified by me`, not folding them into one verdict.

**Claim 4 — `supported`.** The four-signer detail (Fitzpatrick, Lawler,
Mackenzie, Bresnahan) is consistent across a `WebSearch` synthesis, a
`resist.bot` petition-tracking page, and is implied correctly by the
math every source agrees on: Democrats held 214 seats, needed 218, and
needed exactly four Republicans. The December 17, 2025 date for
crossing the threshold is stated directly in Rep. Neal's (D-MA) press
release, which I fetched directly.

**Claim 5 — `supported`.** Stated identically, with no contradiction
found anywhere, across the KFF brief, multiple member press releases,
and `govinfo.gov`'s own bill summaries for H.R. 5145 and H.R. 6501 (both
reference the same expiration).

**Claim 6 — `supported`.** `govinfo.gov/app/details/BILLS-119s3385is`
confirms S. 3385 is the "Lower Health Care Costs Act," introduced by
Schumer on December 8, 2025, to extend the premium tax credit
enhancements through January 1, 2029 (a three-year extension from the
scheduled 2026 expiration). `ifebp.org`'s legislative tracker — a
neutral third-party bill tracker, not a party press release — gives
the exact official language: "Cloture motion... not invoked in Senate
by Yea-Nay Vote. 51-48 (Record Vote Number: 644)," dated December 11,
2025. The four Republican crossover names (Hawley, Sullivan, Murkowski,
Collins) came from a `WebSearch` synthesis only, same caveat as Claim
3 — I did not independently confirm the names against a roll-call page.

**Claim 7 — `not contradicted within searched corpus`, explicitly
weaker than `supported`.** Every source describing the CARE Act and the
stalled state of negotiations that I could find is dated January or
February 2026 (CBS News, January 15; ASTHO timeline, not explicitly
dated past early 2026). I searched specifically for September and
October 2026 developments and found nothing newer — not evidence that
nothing happened, only that I could not find it. I am not reporting
"still stalled" as a live, current fact; I'm reporting that the most
recent sourcing I could locate said so, and naming the gap.

**Claim 8 — `supported`.** Fetched `kff.org/affordable-care-act/`
directly: the live page itself lists "How Much and Why ACA Marketplace
Premiums Are Going Up in 2027" (originally published July 8, 2026,
updated August 3, 2026) stating a median proposed increase of 14-15%
across insurer filings in all 50 states and DC, with the expiration of
enhanced premium tax credits named as one contributing factor alongside
rising health care prices generally. This is KFF's own live page
content, not a search engine's paraphrase of it.

**Claim 9 — mixed, and the actual second-biggest finding of this
report.** The numbers in circulation for "how many people are affected"
are not one claim with one answer; they are at least four different,
non-interchangeable estimates that get flattened into interchangeable
round numbers in secondary coverage and especially in `WebSearch`
synthesis:
- CBO's May 11, 2025 estimate that **a specific, unrelated GOP
  reconciliation bill** would reduce insurance coverage by "at least
  8.6 million" by 2034 (direct quote, via FactCheck.org's fetched
  article, which itself is reporting on a May 2025 CBO memorandum).
- A separately-estimated 4.2 million increase in the uninsured
  specifically from enhanced-credit expiration, which Democrats in
  2025 added to the 8.6 million above to get "13.7 million," which
  FactCheck.org states plainly is improper because "their extension is
  not directly tied to the GOP bill before Congress."
- "4.8 million," "7.3 million," and "24 million total enrollees, 22
  million of whom receive the enhanced credit" all appear in different
  `WebSearch` results for different scopes (total uninsured vs. losing
  subsidized coverage specifically vs. total marketplace population)
  without the search tool distinguishing which is which.
I could not and did not try to adjudicate which of these, if any, is
the "right" current (2026) CBO estimate for the credits' expiration
alone — I did not get a live CBO document to open (cbo.gov was
blocked). The finding is narrower and, I think, more useful than
picking a winner: these numbers are being used interchangeably in
public discussion when they are not interchangeable, and a
reader — or an agent — relying on search-engine synthesis alone would
not be able to tell that from the search results.

## Where the instruction did not match reality

The skill's step 3 says a source is "the exact page and passage," and
warns specifically against "search results describing X." Today's
actual difficulty was not finding sources — it was that `WebSearch`'s
own synthesized summaries were **confidently, repeatedly wrong on a
specific, checkable detail** (asserting H.R. 1834 as fact, which
happened to be correct, but for a reason the summaries never surfaced,
making it indistinguishable from a hallucination until I fetched the
primary bill text myself) and **silently inconsistent on another**
(the uninsured-count cluster in Claim 9, where different queries
return different numbers with no indication they're answering
different questions). The skill's existing rule ("a second model
agreeing with the claim is not a source... search results describing X
is not a source") already covers this, strictly read, but it is
written with a human or a second LLM's prose output in mind; it is
worth being explicit that a search tool's own autogenerated "Based on
the search results..." narrative is exactly the same category of
non-source, even when — maybe especially when — it sounds confident
and the links underneath it are real.

## Proposed change

Add one sentence to `skills/claim-check/SKILL.md` step 3, after the
existing "'Lovdata' or 'search results describing X' is not a source"
line: **"A search tool's own generated summary of its results is the
same failure mode as 'search results describing X,' even when the
underlying links are real; open the page the summary claims supports
the point before recording a verdict, every time, not only when the
summary looks doubtful."** This is a direct instance of the failure
the line already names, not a new rule, so I'm not confident it clears
the bar for a real proposed change versus just restating the existing
rule more specifically. Flagging it as a candidate rather than being
sure it should merge as-is.

## Self-check

The real deviation: I had a `contradicted` verdict half-written for
Claim 1 after one `govinfo.gov` fetch, because the bill's "introduced"
title so plainly had nothing to do with health care that it read like
an open-and-shut case of a bad citation — the exact kind of finding
this skill rewards reporting cleanly. I kept it open only because the
same search synthesis I'd already caught being wrong elsewhere
(Claim 9) was insisting on this exact bill number too, and two
independent things being wrong about the same number in the same way
felt worth one more check before I committed to the more interesting
verdict. That is a bad reason to have gotten it right — it should not
require noticing a pattern across two unrelated claims to remember to
check a bill's full legislative history before calling a citation
false. The better habit is: never record `contradicted` on a specific
numbered-document citation without checking whether a procedural
mechanism (substitute amendment, discharge, renumbering) could explain
the mismatch, not only when something nags at you to look twice.

Second, smaller deviation: Claims 3 and 6's name lists are `WebSearch`
synthesis I did not verify against a roll call, which I've labeled
`unverified by me` rather than quietly folding into the `supported`
verdict on the vote count — but I did spend less effort trying to
reach the official Clerk roll-call pages than I spent on the bill-text
question, mostly because the count mattered more to the claim I was
actually checking than the names did. That's a defensible
prioritization, not a hidden shortcut, but it is a shortcut.
