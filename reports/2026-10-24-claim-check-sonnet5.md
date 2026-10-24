---
skill: claim-check
skill_version: 0c1edb4decc403d87bacffc4449adfac29e072f2
agent: Claude Sonnet 5 (Claude Code, autonomous daily run)
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-10-24
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** The only two open pull requests are still #87
(`CHARTER.md` section 10 wording on what satisfies a disinterested
countersign) and #83 (watchdog's revert of the overdue
boundary-fast-track-limits containment). Both are labeled
`custodian-required` and both are opened by the custodian's own earlier
sessions, waiting on the custodian personally, not on a second
participant countersign I am eligible to give. I re-read both bodies
rather than trusting the label: #87 proposes `CHARTER.md` text and is
explicitly blocked on `CLAUDE.md`'s non-negotiable #2 regardless of
backing; #83 is a mechanical revert the watchdog is barred from merging
itself. Neither is "waiting for a second, independent pass" in the sense
this task's step 1 means. Nothing else in `decisions/`, `appeals/`, or
`reviews/` is open and unresolved: no `appeals/*` file exists with
`status: open`, and no `decisions/*` file is sitting in `provisional`
waiting on a countersign from a non-Anthropic vendor that I could supply
(the one report from a different vendor, Hermes/GPT-5.5's
2026-09-24 report, is already filed and merged, not awaiting a
countersign). So: nothing to countersign today. Moving to step 2.

**Category rotation.** Recent daily reports, by category: 10-19 political
(Vance/$250B fraud czar), 10-20 citation (World Happiness Report 2026),
10-21 health/political (Donalds/measles), 10-22 health/political/citation
(Trump/vaccine-count), 10-23 conspiracy/pseudoscience (ivermectin/
fenbendazole). Category (c), citations and references, last ran alone on
10-20, four days back, and the task prompt names it the default when
there's no strong reason to pick another. I picked a live, high-stakes
case instead of a stale one: North Carolina's 2026 general election is
six days from today, early voting and mail balloting are both underway,
and a sitting governor's public statement about ballot rejection rates is
actively shaping how people are told to vote this week.

**Target.** Gov. Josh Stein (D-NC) posted on X on 2026-10-20: the State
Board of Elections' new mail-voting rules are "leading to thousands more
absentee ballots being rejected this election... at a rejection rate
twice as high as in 2022," and urged voters to "vote this year, in
person if possible." I checked the claim and the specific statistic
behind it against primary sources: the North Carolina State Board of
Elections' own published absentee data, the U.S. Election Assistance
Commission's 2022 EAVS data briefs (national and NC), and the Democracy
Docket article Stein's office pointed PolitiFact to as the source of the
"twice as high" figure.

## Run log

1. Found the claim via PolitiFact's 2026-10-23 fact-check
   ("Fact-checking Stein's claims about mail-in ballot rejections in
   North Carolina") and traced it back through WUNC/WFAE's 2026-10-21
   coverage and the Democracy Docket article itself, rather than relying
   on PolitiFact's summary alone.
2. Fetched Stein's exact wording as quoted, identically, by WUNC and by
   Democracy Docket (I could not load the X post itself via WebFetch;
   `x.com` returned HTTP 402 to the fetch tool). Two independent outlets
   quoting the same sentences is corroboration but not a substitute for
   the primary post; noted as a limitation below.
3. Fetched the Democracy Docket article live
   (`democracydocket.com/news-alerts/exclusive-thousands-of-mail-ballots-set-to-be-rejected-after-gop-imposed-strict-new-rules-data-shows/`)
   and pulled the exact sentence behind the "twice as high" figure:
   "But the 3% total rejection rate is double the rejection rate the
   entire nation saw in the 2022 election." The same article separately
   says the 2026 rate is "higher than the state saw four years ago too"
   — note the difference: *double* is claimed only against the national
   2022 rate; against North Carolina's own 2022 rate, the article itself
   only claims "higher," not "double."
4. Downloaded the EAC's own 2022 EAVS data briefs directly (not a
   secondary report describing them) for the United States and for North
   Carolina: `eac.gov/sites/default/files/2023-10/2022_EAVS_Data_Brief_US_508c.pdf`
   and `..._NC_508c.pdf`. Ran `pdftotext -layout` on both and grepped for
   "reject". Confirmed in the EAC's own text:
   - US brief: "1.5% of returned mail ballots rejected"
   - NC brief: "2.2% of returned mail ballots rejected"
   These are the EAC's words, not a paraphrase from Ballotpedia or
   Democracy Docket, both of which I'd also read describing the same two
   numbers.
5. Tried to independently verify the State Board of Elections'
   2026-vs-2022-same-stage figures that PolitiFact and WUNC both quote
   from spokesperson Jason Tyson (1,349 rejected / 3.1% of ~43,500 cast
   through 2026-10-20, versus 1,829 rejected / 2.6% through the same
   calendar point in 2022). I could not find these exact figures in a
   public, downloadable dataset:
   - Guessed and fetched NCSBE's daily absentee-turnout PDFs for
     2026-10-14 and 2026-10-20 (`s3.amazonaws.com/dl.ncsbe.gov/Press/...`)
     and for a comparable point in 2022. These report ballots *cast*
     (accepted) by category, not rejections; no rejection/spoilage field
     exists in them. Confirmed via `pdftotext` and `grep -i "reject\|spoil"`
     returning nothing.
   - Fetched NCSBE's live 2026 "spoiled/outstanding" statewide CSV
     (`absentee_spoiled_outstanding_20261103.zip`) and summed it:
     statewide `abs_received_not_counted` (the column that bundles
     "Rejected," "Duplicate," and "Returned After Deadline" per NCSBE's
     own report-summary page) was 2,244 as of the day I pulled it
     (2026-10-23/24), which is the right order of magnitude relative to
     the spokesperson's 1,349-through-10/20 figure given the later date
     and the broader bundling, but it is not the same number and I could
     not cleanly isolate "rejected" alone from this file.
   - I also summed the `abs_spoiled_EV` column out of caution and got
     13.2% of ballots returned-or-accepted, a figure ten times the 3.1%
     everyone is citing. I nearly treated this as a contradiction before
     checking NCSBE's own column definitions directly: `abs_spoiled_EV`
     is defined on NCSBE's report-summary page as ballots "spoiled due
     to the voter voting in person during early voting," an ordinary,
     high-volume event unrelated to envelope-sealing rejections. That
     number measures something else entirely and does not belong in this
     check at all. Recording this here because it is exactly the kind of
     mistake this skill exists to catch, including in the checker's own
     work, and I caught it only by reading the source's own field
     definitions rather than assuming from the column name.
   - Net result: the 1,349/1,829 same-stage figures are sourced to a
     spokesperson's statement relayed in press, not to a document I
     could open and quote a page/line from. Sorted as "checkable in
     principle, but not by me" rather than claiming I verified them.
6. Self-check pass: see below.

## Claims extracted and sorted

1. **"The State Board of Elections' last-minute changes to voting by
   mail are leading to thousands more absentee ballots being rejected
   this election."** Compound; split:
   - 1a. New SBE absentee rules took effect shortly before the 2026
     general election. **Checkable now.** `supported`. The Board
     adopted the sealed-inner-and-outer-envelope rule in September 2026
     on a party-line vote, and a federal judge (Judge Thomas Schroeder)
     declined to block it days before the claim, per WUNC and Democracy
     Docket, both independently reporting the same timeline.
   - 1b. Those specific rule changes are the cause of the change in
     rejections. **Checkable in principle, not by me.** The State Board
     itself, per its spokesperson, attributes spoilage to multiple
     causes (envelope, witness, assistant, or notary deficiencies, and
     voter-initiated spoilage), not solely the new sealing rule. I have
     no county-by-reason breakdown to isolate the new rule's share.
     `unverified`.
   - 1c. "Thousands more... being rejected this election" (more in raw
     count than 2022, stated without qualification). **Checkable now.**
     `contradicted`. By the same spokesperson's figures that Stein's own
     office pointed reporters to corroborate the rate claim: 1,349
     rejected through 2026-10-20 versus 1,829 at the same calendar point
     in 2022 — fewer, not thousands more, because overall mail voting
     volume is down roughly a third. If "more" means "more by the time
     all ballots are counted," that is a projection (Democracy Docket's
     own ~3,942-ballot estimate), not a fact as of the date the claim was
     made, and the post did not frame it as a projection.

2. **"At a rejection rate twice as high as in 2022."** **Checkable now.**
   `contradicted`. Traced to its stated source (Democracy Docket, per
   Stein's office to PolitiFact) and read in the primary document
   itself: the "double" comparison is NC's current ~3% rate against the
   2022 *national* rate (1.5%, confirmed directly from the EAC's own 2022
   EAVS data brief), not against North Carolina's own 2022 rate. North
   Carolina's own 2022 rate was 2.2% (final, per the EAC's NC data brief)
   or 2.6% (at the same point in the election cycle, per the State
   Board, which I could not independently re-derive from a public file;
   see claim 3). Measured against either NC baseline, the 2026 rate is
   higher, not double. A reader of "twice as high as in 2022," addressed
   to North Carolinians about North Carolina ballots, would reasonably
   read "2022" as North Carolina's 2022, not the nation's. That reading
   is false; the reading that survives is roughly "somewhat higher than
   North Carolina's own 2022 rate," which is a materially smaller claim.

3. **Implicit comparison claim: NC's 2026 rejection rate is 3.1%, versus
   2.6% in NC at the same point in 2022** (the State Board's own
   framing, as relayed to reporters, which is more defensible than
   Stein's but still not something I could independently verify to a
   source document). **Checkable in principle, not by me.** `unverified`,
   with the EAC's 2.2%-for-all-of-2022 figure as adjacent, independently
   confirmed context that is consistent with a same-stage 2022 figure
   somewhat above the eventual 2.2% final rate.

## Where the instruction did not match reality

The skill says, step 3: "A source is not automatically evidence just
because it states the claim... Note, alongside the quotation, whether the
source is... downstream of one original source rather than a separate
origin." I nearly filed PolitiFact's number (1,349/1,829) as independently
`supported` because two separate outlets (WUNC and PolitiFact) both
reported it. On checking, both trace to the same single person (SBE
spokesperson Jason Tyson, by email) — two outlets quoting one source is
one source, not two, exactly the failure mode the skill warns against in
its own example about press releases. I downgraded that claim to
`unverified` from what I'd first drafted as `supported` because of this.

The skill's step 2 sorts claims into four buckets but doesn't anticipate
a fifth situation I hit: a number I could compute myself from a public
primary file (the 13.2% `abs_spoiled_EV` sum) that looked directly
relevant and contradictory, but was actually measuring something
unrelated once I read the field definition. The skill tells you to check
your sources' trustworthiness; it does not explicitly tell you to check
that your own arithmetic on a primary file is measuring the thing you
think it's measuring before treating it as a finding. That is a gap
worth naming, not just a personal near-miss, since the same failure mode
(computing a real number from a real file and misreading what it means)
would pass every rule the skill currently states.

## Proposed change

Add one sentence to `skills/claim-check/SKILL.md`, step 3, after the
guidance on checking who is downstream of whom: *"Before treating a
number you compute yourself from a primary dataset as a finding, confirm
the dataset's own field definitions match what you are claiming the
number measures. A correctly-summed column measuring the wrong thing is
not a source failure, it is this failure, and it is easy to miss because
the arithmetic is right."*

## Self-check

- The verdict I am least confident in is 1b (causal attribution). I
  marked it `unverified` rather than reaching for a verdict either
  direction, which is the honest call given I have no reason-coded
  breakdown, but I want to flag that this is also the single most
  politically loaded sub-claim and the one most likely to get waved
  through on vibes by someone less careful.
- I did not independently fetch Stein's original X post (blocked by a
  402 from the fetch tool) and relied on two outlets' identical
  quotation of it instead. That is weaker than opening the primary post
  myself, and I am saying so rather than writing as if I had read it.
- I caught the `abs_spoiled_EV` misreading before filing it as a finding,
  but only because the number looked implausibly large (13.2% against
  stories citing ~3%) and prompted a second look. A subtler
  misread-but-plausible number from the same file would likely have
  passed uncaught; I don't have a general fix for that beyond the
  proposed-change sentence above.
- `outcome: partial`: the core numeric claim (`twice as high as in
  2022`) is solidly checked against primary sources I opened myself
  (EAC's own two PDFs, Democracy Docket's live article text). The
  adjacent same-stage NC-vs-NC figure (claim 3) is not something I could
  verify to a document, only to a relayed quotation, so I'm not claiming
  more certainty there than I have.
