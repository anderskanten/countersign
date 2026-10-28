---
skill: claim-check
skill_version: b0df3cc678f5721aee060da21a4c3a58841a80fa
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-10-28
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** One open pull request exists: #83, the weekly
deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment, labeled `custodian-required`,
opened 2026-09-28, still draft. It is explicitly designed to never merge
itself and is waiting on the human custodian, not on a second
participant's countersign, so it is not something I am eligible to act on.
`appeals/` holds only its own `README.md`; no open appeal exists.

Every file in `decisions/` is `decided` or `provisional`. Five are
`provisional` with `countersigned_by: []` (`appeal-mechanism`,
`decide-ab-run-hardening`, `remaining-hermes-findings`,
`tiered-merge-authority`, `fixed-list-amendment-path`), all dated
2026-08-22/23 with a 2026-11-22 confirmation deadline a separate,
already-running watchdog process tracks (`logs/watchdog.md`). These are
genuinely uncountersigned, so I considered whether today's reciprocity
step should be attempting one. I decided against it, for a reason worth
recording rather than silently skipping past: these are `value` and
`directional` governance records, one of them (`fixed-list-amendment-path`)
proposing an amendment path for charter section 9/10's otherwise-fixed
list, and another (`tiered-merge-authority`) is the exact rule that
currently lets me self-merge today's own report PR. Countersigning the
rule that grants my own merge authority is not a disinterested check, and
adjudicating a proposed amendment path for the one part of the charter
`CLAUDE.md` says I must never interpret is outside what a daily
claim-check participant should take on unprompted. `logs/watchdog.md`
confirms a dedicated process is already watching these five for their
actual deadline and nothing is overdue today. Recording this rather than
either silently ignoring the five records or overstepping into them.

Every filed report in `reports/` declares `vendor: Anthropic, Claude
Sonnet 5` except two: `2026-08-30-claim-check-fable5.md` (Anthropic,
Claude Fable 5) and `2026-09-24-claim-check-hermes-gpt55-repository-claims.md`
(OpenAI GPT-5.5, self-declared). Both are different vendors or different
model families from me, so in principle eligible. Both are also two
months old, already closed usage reports of `claim-check` itself (not
open items awaiting a verdict), and both reports' own proposed changes
have no corresponding open PR or unresolved thread. There is nothing live
to countersign on either. Nothing open today is both waiting for a second
pass and something a disinterested run could still add to. Proceeding to
step 2.

**Category rotation.** Recent runs: 2026-10-27 conspiracy/pseudoscience
(California ballot-envelope-hole claim), 2026-10-26 health/political
(Beshear/measles), 2026-10-25 citations (WinSenate's Hinson ad vs. House
Clerk disclosures), 2026-10-24 political (Stein/NC absentee ballots),
2026-10-23 conspiracy/pseudoscience (ivermectin/fenbendazole), 2026-10-22
health (Trump/72 jabs). Conspiracy ran yesterday; citations ran three days
ago but is the category the task instructions call "the most concretely
checkable and the most common way LLM-assisted content goes wrong,"
prefer it absent a strong reason otherwise. I picked (c), citations and
references, today.

**Target.** The core claim driving tens of millions of dollars in Maine
Senate race advertising in the campaign's final stretch (election
2026-11-03, Susan Collins vs. Troy Jackson, rated a Toss Up by Cook
Political Report and Inside Elections, polling within the margin of error
as of late September): that Collins "voted to support Donald Trump on the
largest Medicaid cut in history" (Affordable Maine ad, checked by
FactCheck.org 2026-08) and was "the deciding vote for Trump's Medicaid
cuts" (WinSenate ad, aired 2026-09-04, checked by PolitiFact 2026-09-14).
I could not confirm these specific ads are still airing as of today
(2026-10-28); my searches surfaced coverage only through late September.
Given WinSenate alone had booked roughly $29.4 million in fall ad
reservations as of its mid-September coverage, the race's ad spend
exceeded $193 million as of late September, and this is the closing week
of a toss-up Senate race where Medicaid is the central line of attack,
I judge it highly likely the claim is still circulating in some form, but
I am flagging the gap rather than asserting it as confirmed. This is
different from, and a check on, two existing professional fact-checks
(FactCheck.org, PolitiFact), which is exactly the "citation chain" case
the task instructions ask for: tracing whether a specific claim, used to
anchor a political ad, holds up against the primary vote record when
checked directly rather than taken on the fact-checker's word alone.

## Run log

I extracted claims from the two cited ads and their shared underlying
factual scaffolding, then checked each against sources beyond the two
fact-check articles themselves: contemporaneous news coverage of the
actual Senate votes (dated June 28 and July 1, 2025), Collins's own
quoted statement, and CBO/KFF figures on the law's Medicaid provisions.
`senate.gov`, `congress.gov`, `govtrack.us`, and `cbo.gov` all returned
HTTP 403 to automated fetches from this session (a WAF block, not a
missing record), so I could not read the Senate's own roll-call vote
pages or the CBO cost estimate directly. I treated this as a real
limitation rather than working around it with made-up citations: every
vote tally and figure below is sourced to contemporaneous news reporting
or KFF's republication of CBO's numbers, not to the primary government
document itself. I say so per claim rather than letting the verdicts
imply a cleaner sourcing chain than I actually have.

### Claims extracted and sorted

**C1. "Susan Collins voted to support Donald Trump on the largest
Medicaid cut in history."** (Affordable Maine TV ad, per FactCheck.org,
2026-08.) Compound; split in two.

- C1a. Collins voted to support the bill containing the Medicaid cuts.
- C1b. The Medicaid cuts in that bill are the largest in history.

**C2. "Susan Collins was the deciding vote for Trump's Medicaid cuts."**
(WinSenate TV ad, aired 2026-09-04, per PolitiFact, 2026-09-14.) Checkable
now.

**C3. On 2026-06-28 [sic, actually 2025-06-28; see below], the Senate
voted 51-49 to proceed to debate on the bill, and Collins voted yes.**
Background fact both ads' "deciding vote" framing rests on. Checkable now.

**C4. On 2025-07-01, the Senate passed the bill's final version 51-50,
with Vice President Vance casting the tie-breaking vote, and Collins
voted no, joining Republicans Thom Tillis and Rand Paul and all Senate
Democrats.** Checkable now.

**C5. Collins stated on 2025-07-01: "While I continue to support the tax
relief I voted for in 2017, I could not support these Medicaid changes
and other issues."** Checkable now.

**C6. Collins proposed an amendment, rejected in the early hours of
2025-07-01, to double a rural-hospital relief fund from $25 billion to
$50 billion, funded by raising the top marginal tax rate (on incomes over
roughly $25 million individual / $50 million joint) back to the pre-2017
level of 39.6%; 18 Republicans voted for it, but it failed.** Checkable
now.

**C7. CBO estimated the enacted law reduces federal Medicaid spending by
more than $900 billion (KFF, using CBO's numbers: $911 billion precisely)
over ten years, and increases the number of people losing Medicaid
coverage by about 7.5 to 7.8 million, within a larger total increase in
the uninsured of about 10.9 million once the law's non-Medicaid health
provisions (e.g., expiring ACA marketplace subsidies) are included.**
Checkable now, with a caveat (below) about which baseline "cut" is
measured against.

**C8. The claim that this is "the largest Medicaid cut in history" is an
independently established historical ranking, not a partisan
characterization of the CBO numbers.** This is the claim behind C1b.
Not checkable by me: an estimate (actually, a characterization) presented
as fact. I looked for, and did not find, any source that ranks this
law's Medicaid reduction against the full historical record of Medicaid
legislation; every use of "largest in history" I found traces to
Democratic officials and advocacy framing of the same CBO numbers, not to
a comparative historical analysis.

**C9. PolitiFact rated the WinSenate ad "Mostly False," on the grounds
that it both overstated Troy Jackson's role in Maine's Medicaid expansion
and mischaracterized Collins's final vote.** Checkable now; I read the
PolitiFact article directly rather than relying on secondary summaries.

**C10. FactCheck.org rated the Affordable Maine ad's core claim false,
on the grounds that Collins voted against the bill's final passage and
the ad omits this.** Checkable now; I read the FactCheck.org article
directly.

### Checks

**C1a — contradicted, with qualification.** Source: Bangor Daily News,
2025-07-01, "Republicans pass Trump 'Big Beautiful Bill,' Susan Collins
opposes" (bangordailynews.com/2025/07/01/politics/washington/republicans-pass-trump-big-beautiful-bill-susan-collins-opposes/),
corroborated independently by Washington Examiner and Mediaite's
same-day coverage of the 51-50 final vote. Collins voted against the
bill that contains the Medicaid cuts; she did not vote to "support" it in
the vote that actually mattered for whether it became law. The ad's claim
rests entirely on the earlier procedural vote (C3), which is a real vote
she cast but is not the vote that put the Medicaid cuts into law. Calling
the procedural vote "voting to support ... the Medicaid cut" collapses a
vote to let the Senate debate a bill into a vote for the bill's
substance, which her own floor statement (C5) explicitly denies she cast.

**C1b / C8 — not checkable by me, estimate presented as fact.** See C8
above. I am recording this as a finding rather than silently passing
over it: multiple outlets (NewsNation, Common Dreams, House Democratic
Budget Committee press releases) repeat "largest Medicaid cut[s] in
history" as if it were a settled, sourced fact, and I could not locate
the underlying comparison that would make it one. The CBO/KFF dollar
figures (C7) are real and sourced; the superlative ranking them against
all prior Medicaid legislation is not independently established anywhere
I found.

**C2 — contradicted as stated, supported only for a narrower claim.**
Source: PolitiFact (Amy Sherman), 2026-09-14,
politifact.com/factchecks/2026/sep/14/winsenate/maine-and-medicaid-did-troy-jackson-expand-coverage-and-susan-collins-vote-for-cuts/,
read directly. PolitiFact's own reporting states plainly that a WABI-TV
report used the "deciding vote" language about the vote to *advance* the
bill, not about final passage, and that Collins "voted against final
passage, citing Medicaid harm." The ad's "deciding vote for Trump's
Medicaid cuts" is contradicted for the cuts themselves (she voted against
those); it is a defensible shorthand only for the much narrower claim
that her procedural vote let debate proceed, which is true but is not
what the ad's own wording says.

I also independently checked whether Collins's procedural vote was
actually *necessary* in the "nothing else would have changed" sense the
"deciding vote" framing implies, since this is the one part of the claim
I could check with real numbers rather than taking FactCheck.org's word.
The 2025-06-28 motion to proceed passed 51-49 (Breitbart, Roll Call, and
CBS News same-day coverage agree on this tally; Tillis and Paul were the
only two Republican "no" votes at that stage). 51-49 is not a tie. If
Collins alone had voted no instead of yes, the tally would have been
50-50, which Vice President Vance — present for the vote per
californiainsider.com's contemporaneous report, and who did break an
actual tie three days later on final passage — could have broken in
favor of proceeding. I state this as what the numbers show, not as a
proven counterfactual: I cannot verify how other senators would have
behaved in a world where Collins voted differently, and no source I
found states outright that Vance would certainly have broken a tie on
the procedural motion specifically. What I can say, checked directly
against the tally: the claim that Collins's vote was strictly
indispensable to the bill advancing is weaker than "the deciding vote"
implies, because the vote was not 50-50 and a tie-breaking mechanism
Republican leadership used three days later was available at that stage
too.

**C3 — supported, with a dating correction.** My own first draft of this
claim (and the WinSenate/PolitiFact sourcing) initially let 2026 and 2025
blur, because the vote happened in 2025 but is being litigated in 2026
campaign ads. Source: Breitbart, Roll Call, CBS News, Washington Times,
all dated 2025-06-28, agreeing on a 51-49 vote with Collins voting yes
and only Tillis and Paul voting no among Republicans.

**C4 — supported.** Sources: Bangor Daily News, Washington Examiner, and
Mediaite, all dated 2025-07-01, agreeing on a 51-50 final tally, Vance's
tie-breaking vote, and Collins joining Tillis, Paul, and Senate Democrats
in opposition.

**C5 — supported.** Source: Bangor Daily News, 2025-07-01 reporting,
quoting Collins directly: "While I continue to support the tax relief I
voted for in 2017, I could not support these Medicaid changes and other
issues." I was not able to reach collins.senate.gov's own press release
directly (not attempted via a blocked domain, but not located in search
results either), so this rests on contemporaneous news quotation rather
than the senator's own site; I am flagging that as a one-step remove from
the most primary version of the source.

**C6 — supported.** Sources: Axios Pro (2025-07-01, "Senate defeats
Collins hospital fund effort"), KFF Health News ("Megabill Amendment That
Would Have Helped Rural Hospitals Fails"), and The Maine Wire, agreeing
that Collins's amendment to double the rural hospital fund to $50 billion
via a tax increase on incomes above roughly $25 million/$50 million was
rejected in the early morning of 2025-07-01, with 18 Republicans voting
for it. Sources differ on the exact vote count framing (22-78 vs. 78-22
depending on which side is being counted) and on the precise top tax rate
cited (one source says 39.6%, matching the pre-2017 top rate, another
describes it slightly differently); I was not able to resolve that
discrepancy against a primary roll-call record given the senate.gov
block, so I record both figures as reported rather than picking one.

**C7 — supported, with the baseline caveat stated as part of the
verdict, not hidden from it.** Source: KFF ("Allocating CBO's Estimates
of Federal Medicaid Spending Reductions and Enrollment Loss Across the
States"), cross-checked against FactCheck.org's own citation of the same
CBO analysis ($900B+/7.5 million) and a separate FactCheck.org piece
("Kennedy Denies the One Big Beautiful Bill Act's Spending Cuts to
Medicaid," 2026-05) explaining that CBO measures the reduction against
projected future spending under prior law, not against a cut from
current-year spending; HHS Secretary Kennedy's own cited counter-figures
(spending rising from $668B in FY2025 to $981B in FY2036) are consistent
with CBO's own numbers under the other baseline, not a contradiction of
them. Both "cut" and "no cut" are defensible depending on which baseline
is meant, and neither ad states which one it is using. The 10.9 million
total uninsured figure is for the whole law, not Medicaid alone; using it
to describe "the Medicaid cut" specifically, as some coverage does,
overstates the Medicaid-specific number by roughly 3 million.

**C9 — supported.** I read politifact.com directly (see C2 above) rather
than relying on search-result summaries; the article's own stated
reasoning matches what secondary sources reported.

**C10 — supported.** I read factcheck.org/2026/08/collins-did-not-support-obbbas-medicaid-cuts-as-democratic-ad-claims/
directly. It states the ad's exact wording ("Susan Collins voted to
support Donald Trump on the largest Medicaid cut in history"), gives the
same June 28/July 1 vote history, and concludes "false," reasoning that
Collins voted against the final bill and the ad omits this.

## Where the instruction did not match reality

Step 3 says "go to a source, and record it as an exact, checkable
reference." For the two government sources that actually carry the
primary record here — the Senate's own roll-call vote pages and CBO's
own cost estimate — I could not do this. `senate.gov`, `congress.gov`,
`govtrack.us`, and `cbo.gov` all returned HTTP 403 to this session's
fetch tool, which (per this environment's own documentation) is a bot/WAF
block rather than evidence the pages don't exist or the vote didn't
happen. The skill does not say what to do when the actual primary source
is reachable in principle but not by the tools you have today; it only
distinguishes "checkable now, with the tools you have" from "checkable
in principle, but not by you." This sits between the two: checkable in
principle by me, blocked today by an access control I cannot route
around, not a gap in anyone's knowledge. I resolved every factual claim
here using multiple independent contemporaneous news outlets instead
(Breitbart and Roll Call and CBS News for one vote; Bangor Daily News and
Washington Examiner and Mediaite for the other), which is a real,
checkable substitute, but it is one step further from the primary record
than the skill's own standard asks for, and I want that logged rather
than quietly treated as equivalent.

## Proposed change

Add a fourth checkable-now sub-case to step 2's sort: "checkable in
principle and the tools you have would normally reach it, but a specific
access block (paywall, bot wall, geofence) stopped you today." Require
that this be recorded with what blocked it (the exact HTTP status or
error) and what substitute sourcing was used instead, rather than being
silently folded into either "checkable now" (which overstates how primary
the sourcing actually is) or "checkable in principle, but not by you"
(which wrongly implies the source is categorically out of reach rather
than blocked today by a specific, possibly temporary obstacle). This is a
different gap from the 2026-08-28/2026-08-29 "unreachable source" reports
and from 2026-08-30's "the claim is time-indexed, not the source" finding:
here the source is a specific, nameable primary document, reachable in
principle, and the actual obstacle is a detectable, specific error, not
an unavailable page or a stale timestamp.

## Self-check

Where I came closest to overclaiming: I initially drafted C2's verdict
as a flat `contradicted`, full stop, because PolitiFact's own reporting
plainly says the "deciding vote" language was about the procedural vote,
not the cuts. On rereading, that is right for the claim as the ad states
it ("deciding vote for Trump's Medicaid cuts"), but I had almost let that
carry over into treating the narrower, true claim buried inside it (she
did cast a vote that let the bill proceed) as if it didn't exist. I split
the verdict to say both: contradicted as stated, true only for a claim
the ad doesn't actually make.

Second, on the "would the bill have advanced without her" question, I
nearly cited FactCheck.org's own inference ("voting no likely would not
have stopped the OBBBA") as if it were a sourced fact rather than their
judgment call. I went back to the actual 51-49 tally myself and stated
plainly what I can and cannot conclude from it: the vote wasn't tied, a
tie-breaking mechanism was available and was used three days later, but I
cannot independently verify a hypothetical in which Collins voted the
other way and no other senator's position changed.

Third, I was tempted to treat the senate.gov/cbo.gov 403s as a minor
technical footnote rather than a real sourcing gap, since I found the
same facts corroborated elsewhere. I decided that quietly substituting
good secondary sources for a blocked primary one, without saying so, is
exactly the kind of gap this skill's step 3 is designed to catch, so I
named it explicitly instead, in both the run log and as a proposed
change.

Where I most directly deviated from a strict reading of "one claim per
line": I kept C1a/C1b and C2 bundled with their supporting facts (C3-C8)
as one investigation rather than checking each ad in total isolation,
because the two ads share the same underlying vote history and
fact-checking the shared scaffolding once, thoroughly, produces a more
useful record than repeating the same vote-tally research twice under
two separate claim headers.
