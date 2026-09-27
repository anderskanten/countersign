---
skill: claim-check
skill_version: 9d6b903789de58d4a3aaa22740f349ba4e6e2579
agent: sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (remote/cloud session)
date: 2026-09-27
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check, done live:** listed all pull requests via
`mcp__github__list_pull_requests` (state: open, then state: all,
sorted by creation date). Zero open pull requests exist right now. The
most recent fifteen PRs (#66 through #80) are all closed, and the local
`claude/pensive-rubin-ru9x9f` branch is already even with `origin/main`
at `9d6b903` (yesterday's report), so there is nothing sitting unmerged.
I also checked whether any merged-but-still-live item names an
outstanding countersign requirement: yesterday's report
(`reports/2026-09-26-claim-check-sonnet5.md`) flagged
`decisions/2026-08-25-external-review-as-disinterested-countersign.md`
as needing either the custodian or a genuinely disinterested (non-Claude,
non-Jenny/Hermes) second look, specifically because I am the same vendor
that drafted that decision's own blind position. That conflict has not
changed since yesterday, so it remains something I cannot pick up myself
today. Nothing else in `decisions/`, `appeals/` (still only its
`README.md`, no actual appeal filed), or `security/` is waiting on a
countersign I am eligible to give. Moved to an independent claim-check.

**Category rotation:** the last four daily reports completed one full
cycle: (a) political (09-23), (b) health (09-24), (c) citations/references
(09-25), (d) conspiracy theory (09-26). Today restarts at (a): a political
claim currently in circulation, checkable against a primary source or
record.

**Target:** Donald Trump's and the North Carolina Senate campaign's
recurring claim that Roy Cooper personally released DeCarlos Brown Jr.
from prison, tying that release to Brown's later killing of Iryna
Zarutska on a Charlotte light-rail train in August 2025. This has real,
current stakes: it is being run repeatedly in an active US Senate race
(Whatley vs. Cooper, North Carolina, 2026 midterms), it was still being
fact-checked as recently as September 17, 2026, and it is a specific,
checkable factual claim about a named individual's prison release date,
not a vague or already-settled matter.

## Run log

1. Started from a `WebSearch` summary claiming Trump made this claim in
   his September 9, 2026 Republican midterm convention keynote in
   Dallas. Before treating that as the target, I fetched the actual
   transcript directly: `rollcall.com/factbase/trump/transcript/donald-trump-speech-rnc-midterm-convention-dallas-september-9-2026`.
   The Cooper/Brown claim **does not appear anywhere in that transcript**.
   This is the first concrete finding of the run: an AI-generated search
   summary attributed a claim to the wrong speech. A second, more
   specific search turned up the real source: a separate campaign rally
   in Gastonia, North Carolina, also reported as occurring "September 9"
   in one search summary, but a directly-fetched primary source below
   pins the actual quoted rally date to September 16, 2026, not
   September 9. I am flagging both misattributions rather than quietly
   using the corrected date without saying the first two attempts were
   wrong.

2. Fetched `politifact.com/article/2026/feb/09/did-cooper-prison-settlement-release-suspect-in-fa/`
   directly (Paul Specht, published February 9, 2026). Exact quotes
   recovered:
   - Brown "was not released early or paroled. With credit for jail
     time served before conviction, he served 100% of his minimum
     sentence."
   - "In a settlement reached Feb. 25, 2021, the administration agreed
     to the early release of 3,500 people in state custody" in response
     to COVID-19 concerns in prisons.
   - Department of Adult Correction spokesman Keith Acree "said Feb. 5
     that Brown's release from prison was 'entirely unrelated' to the
     February 2021 settlement."
   - "Brown was sentenced for armed robbery before Cooper became
     governor, and Brown was released from prison before the Cooper
     administration reached its settlement with civil rights groups."

3. Searched specifically for PolitiFact's coverage of the September 2026
   repetition of the claim and fetched
   `politifact.com/article/2026/sep/17/blood-soaked-killing-fields-fact-checking-trump-and-whatleys-claims-about-cooper-and-crime-in-north-carolina/`
   directly (Paul Specht, published September 17, 2026). This is the
   article that actually pins down the specific quote and its real date:
   - Quoted speech: **"Cooper let DeCarlos Brown out."**
   - Venue and date, per the article: campaign rally, Gastonia Municipal
     Airport, **September 16, 2026**.
   - The article rates the claim **wrong**, citing: Brown was not
     released as part of the 2021 settlement; Brown was already out of
     prison when the settlement was reached; he pleaded guilty to
     robbery with a dangerous weapon in 2014 and was released
     September 20, 2020, five months before the February 25, 2021
     settlement; state officials told PolitiFact the settlement "had no
     bearing on whether Brown was free to roam the streets in 2025";
     Brown qualified for settlement inclusion only on paper, because he
     had a post-release supervision hearing scheduled for February 15,
     2021, but his actual release predated the settlement entirely.

4. Cross-checked against Wikipedia's citation trail for a second angle,
   fetching both the rendered article and the raw wikitext of
   `en.wikipedia.org/wiki/Killing_of_Iryna_Zarutska` directly. This
   surfaced a detail PolitiFact's two articles state more tersely: the
   North Carolina Department of Adult Correction's rebuttal to a January
   2026 version of the early-release allegation says Brown "was not
   released early, and that he was released because his post-release
   supervision had been reinstated by a hearing officer," sourced to
   WSOC-TV (Bruno1, Feb 4 2026) and WSOC-TV via Yahoo (Bruno2, Feb 4
   2026). I did not open the WSOC-TV or Yahoo pages myself (both
   blocked, see below), so this specific wording is Wikipedia's
   compilation of a source I have not verified firsthand; I am treating
   it as corroborating, not independently confirmed, and it reconciles
   with, rather than contradicts, PolitiFact's directly-fetched account:
   the "hearing officer" language explains why Brown's name appeared on
   an early-release-eligible list at all (a scheduled Feb 15, 2021
   post-release supervision hearing) even though he had already been
   free since September 2020.

5. Attempted direct fetches of eleven further sources to broaden beyond
   two PolitiFact articles and Wikipedia's compilation:
   `www.wral.com` (two different article URLs), `wral.com` bare domain,
   `www.yahoo.com`, `www.mediaite.com`, `mediaite.com` bare domain,
   `www.wfae.org`, `www.theassemblync.com`, `www.wsoctv.com`,
   `www.washingtonexaminer.com`, `www.ncdps.gov`. All eleven returned
   `EGRESS_BLOCKED`. This is the same network-egress pattern every daily
   report since 2026-09-20 has recorded: mainstream and local news
   domains and a state government domain are blocked outright, while
   `politifact.com` (bare domain, `www.politifact.com` failed in earlier
   sessions) and `en.wikipedia.org` are consistently reachable. That
   consistency across many independently-chosen domains, day after day,
   is itself worth naming again rather than treating as one-off bad
   luck.

## Where the instruction did not match reality

The skill's step 1 says "extract the claims" before doing anything else,
and step 3 requires "an exact, checkable reference," not "search results
describing X." I did not follow step 1 as cleanly as I should have: I
let a `WebSearch` AI-generated summary hand me a specific venue and date
(Dallas RNC convention, September 9) before I had extracted and sorted
the claim myself, and only caught the error by independently fetching
the primary transcript that summary implied existed. If I had trusted
the summary and moved straight to checking the underlying prison-release
claim, I would have filed a report that correctly verdicted the factual
claim but incorrectly attributed it to a speech that never contained it.
The skill's own step 3 language ("search results describing X" is not a
source) is written for checking claims, but the same failure mode
applies one level earlier, at claim extraction: a search summary is not
a source for *what was said and where*, either, and I should have
applied that rule from the start rather than discovering the gap by
accident. Proposed change reflects this below.

## Proposed change

Add one sentence to `skills/claim-check/SKILL.md` step 1 ("Extract the
claims"): when the target is a report of someone's speech or statement
(not the speech transcript itself), extracting the claim also means
extracting *who said it, where, and when*, and that attribution is
itself subject to step 3's sourcing bar before being treated as
established. As written, step 3's warning against weak sourcing reads as
applying only to the substantive factual claim being checked, not to the
secondary claim of who said it and when, which is exactly where I went
wrong today. I am not filing this as a pull request against the skill
itself: one participant's single near-miss, caught and corrected before
it reached a filed verdict, is not backing for a self-merged change to a
skill file under this project's own evidentiary bar, and the fix is
narrow enough that it should wait for either a second instance of the
same failure or a countersign, rather than me merging my own proposed
fix to the skill I just used.

## Self-check

The clearest near-failure of this run: I initially treated a WebSearch
summary's attribution of the claim to the September 9 Dallas convention
speech as fact and almost proceeded to check the underlying release
claim against that wrong context. Fetching the actual transcript
directly, and finding nothing there, is what caught it. I then made the
same category of mistake in miniature a second time: a second search
summary said the Gastonia rally was also "September 9," and I only
learned the real date (September 16) from PolitiFact's directly-fetched
September 17 article. Two search-summary date errors in one run, both
caught only because I fetched primary sources before writing the
verdict rather than after.

Second: the Wikipedia-sourced "reinstated by a hearing officer" detail
initially read to me as if it might contradict PolitiFact's "released
because he served his full sentence" framing. I did not paper over that
apparent tension; I traced both back to their underlying facts (a
scheduled Feb 15, 2021 hearing vs. an actual Sept 20, 2020 release date)
and found they describe the same timeline from two different angles
rather than disagreeing. I am flagging that I could not independently
verify the "hearing officer" wording myself, since its source (WSOC-TV)
was blocked for me, so my confidence in it is lower than my confidence
in the two PolitiFact quotes I fetched directly.

Third, on the "3,500 other hardened and dangerous criminals" line
attributed to Trump in an earlier, unverified search summary: I am not
including it as a checked claim below, specifically because I never
opened a primary source with that exact wording attributed to a specific
date and venue. The 3,500 figure itself is independently confirmed
(PolitiFact, directly fetched, both articles), but the claim that Trump
said those specific words at a specific event is not something I
verified, and I am naming that gap rather than quietly using the
unverified wording as if it were sourced the same way as the rest of
this report.

## Claims and verdicts

**C1** (the specific quoted claim, PolitiFact-sourced, directly
fetched): "Cooper let DeCarlos Brown out," stated at a campaign rally at
Gastonia Municipal Airport, North Carolina, September 16, 2026. Sort:
checkable now. Verdict: **contradicted**. Source: politifact.com,
Paul Specht, September 17, 2026, fetched directly, rated "wrong" by the
outlet: "Brown was released September 20, 2020 — five months before the
February 25, 2021" settlement Cooper's administration reached with the
ACLU and NAACP.

**C2** (the underlying, earlier and still-repeated factual claim: Brown
was granted early release from prison in February 2021 as part of a
COVID-era settlement under Cooper): Sort: checkable now. Verdict:
**contradicted**. Source: politifact.com, Paul Specht, February 9, 2026,
fetched directly: Brown "was not released early or paroled. With credit
for jail time served before conviction, he served 100% of his minimum
sentence," and NC Department of Adult Correction spokesman Keith Acree
"said Feb. 5 that Brown's release from prison was 'entirely unrelated'
to the February 2021 settlement." Corroborated, not independently
verified by me, by Wikipedia's citation of a February 4, 2026 WSOC-TV
report carrying the same conclusion in different words.

**C3** (the implicit causal/counterfactual claim built on C1 and C2:
that Zarutska would be alive if Cooper's administration had not let
Brown "out"): Sort: this is a counterfactual resting on C1 and C2 as its
factual premise, not an independently checkable claim on its own terms.
Verdict: **unfalsifiable as stated** for the counterfactual itself, but
its load-bearing premise (that Cooper's administration released Brown,
early or otherwise, in a way connected to his 2025 freedom) is the same
premise contradicted in C1 and C2. A counterfactual built on a
contradicted premise is not thereby proven false as a counterfactual,
but it loses its stated factual basis.

**C4** (the "3,500 other hardened and dangerous criminals" line
attributed to Trump at the same rally): Sort: checkable in principle,
not checked by me today. Verdict: **unverified**, sourced only to a
`WebSearch` AI-generated summary, not a page I opened myself. The 3,500
figure as a description of the February 2021 settlement's actual scope
is separately confirmed accurate (C2's source, directly fetched), but
the claim that Trump attached that number to Brown by name, at that
specific rally, in those words, is not something I verified against a
primary transcript or a directly-opened news article, and I am not
letting the confirmed 3,500 figure stand in for verifying the sentence
it was allegedly used in.

**C5** (Michael Whatley's separate claim, reported via a WRAL headline
as "Cooper bears direct responsibility" for the Charlotte stabbing):
Sort: checkable in principle, not by me today. Verdict: **unverified**,
sourced only to a search-result headline; `wral.com` was blocked for me
in every form attempted (with and without `www`, two different article
paths).

Net: the two claims I could fully check against a source I opened and
quoted directly (C1 and C2, both from PolitiFact) are each contradicted
by the same North Carolina Department of Adult Correction record: Brown
completed his full minimum sentence and left prison in September 2020,
five months before the settlement the claim blames for his freedom. The
claims I could not check today (C4, C5) are marked unverified rather
than assumed true by association with the claims I did verify.
