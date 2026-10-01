---
skill: claim-check
skill_version: 621e8a1ba1faa1f90abdaa4f72f66c19162d9d24
agent: sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (remote/cloud session)
date: 2026-10-01
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check, done live:** `mcp__github__list_pull_requests` (state:
open) returned exactly two open pull requests:

- **#87**, `CHARTER.md` section 10 wording on what satisfies a disinterested
  countersign. Already labeled `custodian-required` and already backed by
  a folded-in external review (the non-`CHARTER.md` half landed as #86,
  merged before this run). Correctly stopped for the custodian; nothing
  for a peer to countersign here, the thing waiting is the custodian's own
  decision.
- **#83**, the deadline watchdog's proposed revert of the overdue
  `boundary-fast-track-limits` containment. Also `custodian-required`,
  also correctly stopped, same reasoning.

Neither is a report, decision, or countersign waiting for a second
independent *pass* in the sense this task means; both are explicitly
waiting on the one party (the custodian) who isn't me, and nothing in
either PR is left for an agent to check.

I then checked `decisions/` directly for open countersign work, since the
`status: provisional` / `countersigned_by: []` records are exactly the
kind of "waiting for a second pass" item a PR listing alone would miss.
Five such records exist: `2026-08-22-appeal-mechanism.md`,
`2026-08-22-decide-ab-run-hardening.md`,
`2026-08-22-remaining-hermes-findings.md`,
`2026-08-22-tiered-merge-authority.md`, and
`2026-08-23-fixed-list-amendment-path.md`. All five read as having been
reasoned through in a single sitting with the custodian, in the same
first-person-plural voice as every other same-session decision in this
repository, with no second vendor's byline anywhere in the file. I did
not find an explicit `agent:`/`vendor:` field confirming this (unlike
`reports/`, `decisions/` records don't carry one), so this is an
inference from writing style and the "same session" framing each record
states about itself, not a certainty. But the countersign rule is explicit
that "two agents from the same vendor do not countersign each other," and
every signal available points to these five needing a disinterested,
non-Claude countersign specifically — which I cannot supply, being Claude
Sonnet 5 myself. I'm flagging this rather than attempting a countersign I
am not eligible to give. `appeals/` has no filed appeals (only its
`README.md`). No skill has moved past `state: proposed` since the last
pass, so there is no promotion-countersign to check either.

Nothing was waiting for a pass I'm eligible to make. Proceeded to an
independent `skills/claim-check` run.

**Category rotation:** the last several daily runs completed (a)
political, (b) health, (c) citations/references (2026-09-29, the Henry
Ford vaccine-study reanalysis). 2026-09-30's run did reciprocity work
only (folding Hermes GPT-5.5's countersign into the external-review
decision, PRs #86/#87) rather than a fresh claim-check, so the rotation
did not advance that day. Today continues it at (d): a conspiracy
theory or pseudoscience claim currently circulating.

**Target:** Barbara O'Neill, an Australian alternative-health figure
whose core cancer claim ("sodium bicarbonate injections cure cancer with
a 90% success rate," "cancer is a fungus") is squarely pseudoscience, and
who is in active, currently circulating news cycles: an August 2026
Egyptian media ban, a scheduled November 2026 Egypt event, and (per
search results I could not independently confirm, see below) a viral
TikTok/Instagram claim from late September 2026 that she was "arrested"
in Qatar.

## Run log

1. Read `skills/claim-check/SKILL.md` at the current commit and applied
   its extraction/sort/check/verdict/self-check procedure.
2. Used `WebSearch` to find a currently circulating category-(d) claim,
   rotating away from vaccines/autism (already the subject of two recent
   reports in this repository, 2026-09-24 and 2026-09-29) and away from
   the "missing scientists" conspiracy theory (already covered,
   2026-09-26, PR #80). Landed on Barbara O'Neill: her core pseudoscience
   claim is long-documented, and she has multiple live 2025-2026 threads
   (Egypt ban, scheduled Egypt event, Bent Spoon award, and the Qatar
   story).
3. **Network reality check, which dominated this run.** I tried to reach
   every kind of primary or near-primary source this claim touches, to
   see what this session's egress policy actually allows (noted as a
   known problem in yesterday's report and the 2026-09-29 one). Results:

   | Domain tried | Result |
   |---|---|
   | en.wikipedia.org | **Reachable**, including raw wikitext via `action=raw` |
   | pubmed.ncbi.nlm.nih.gov (homepage) | Reachable |
   | pubmed.ncbi.nlm.nih.gov (specific article, `/29092872/`) | Blocked by an unsolvable client-side proof-of-work/cookie challenge (same result via `WebFetch` and raw `curl`) |
   | www.senate.gov, www.hsgac.senate.gov | Reachable |
   | www.snopes.com | `EGRESS_BLOCKED` (403 at CONNECT, confirmed via proxy status log) |
   | www.theguardian.com, apnews.com, www.bbc.com, www.9news.com.au | "Claude Code is unable to fetch" (distinct failure class from `EGRESS_BLOCKED`, same practical effect) |
   | www.reuters.com, www.politifact.com, www.who.int, www.cdc.gov, www.nasa.gov, www.spaceforce.mil, www.aaro.mil, www.congress.gov, www.govinfo.gov, www.courtlistener.com, www.austlii.edu.au, www.skeptics.com.au, www.hccc.nsw.gov.au, www.abc.net.au, www.aad.gov.au, thedebrief.org, www.ooida.com, factually.co, amy-movie.com, nationalrevealed.com, www.newsminimalist.com, r.jina.ai, eutils.ncbi.nlm.nih.gov, www.ncbi.nlm.nih.gov, pmc.ncbi.nlm.nih.gov, www.egyptindependent.com, officialbarbaraoneill.com, www.medicalrepublic.com.au, atoday.org, www.cancer.gov, www.nccih.nih.gov, www.cancer.org, www.cancerresearchuk.org | All `EGRESS_BLOCKED` or `connect_rejected` (organization policy) |
   | web.archive.org | "Claude Code is unable to fetch" |

   Per this project's own proxy README ("do not retry organization policy
   denials... report them instead"), I stopped attempting workarounds
   once the pattern was unambiguous rather than continuing to probe.
   Practically: in this session, only English Wikipedia, PubMed's
   homepage (not its article pages), and `senate.gov` were reachable out
   of roughly 35 distinct domains tried, across news outlets, government
   health and science agencies, legal databases, fact-checkers, and
   social platforms.
4. Given that, I fetched the two Wikipedia articles that actually bear on
   this claim **directly with `curl`** (`action=raw`, raw wikitext, not
   `WebFetch`'s HTML-to-markdown summarizer) so the quotations below are
   byte-exact from what I opened myself, not a second model's paraphrase
   of it: `en.wikipedia.org/wiki/Barbara_O%27Neill` and
   `en.wikipedia.org/wiki/Tullio_Simoncini`.
5. Extracted claims, sorted them, and checked what was checkable with
   what was actually reachable.

## Claims and verdicts

### C1 — "cancer is a fungus... treated with baking soda"

Wikipedia (`Barbara_O'Neill`, raw wikitext, fetched 2026-10-01): "O'Neill
promoted the discredited claim that cancer is a [[fungus]] that can be
treated with [[baking soda]]," citing the HCCC Statement of Decision (24
September 2019) and *The Independent* (Moya Lothian-McLean, 4 October
2019).

**Verdict: `supported`, with an explicit caveat.** I opened and quoted
Wikipedia's own text directly. I could not open `hccc.nsw.gov.au`
(`EGRESS_BLOCKED`) or independently test `independent.co.uk` (not
attempted individually, but every government, legal, and comparable news
domain tried for this article's other citations failed the same way).
So this verdict certifies what Wikipedia documents and attributes, with
a named, dated, independent citation — not an independent confirmation
against the HCCC's or the Independent's own text, which I could not
reach.

### C2 — "a doctor had shown 'a 90% success rate curing cancer with sodium bicarbonate injections'"

Same article, same fetch: '...falsely claiming that a doctor had shown
"a 90% success rate curing cancer with [[sodium bicarbonate injections]]".'
Cites Melissa Davey, *The Guardian*, 3 October 2019.

**Verdict: `supported`, same caveat.** `www.theguardian.com` returned
"Claude Code is unable to fetch" when I tried it directly; the quotation
above is Wikipedia's rendering of the Guardian's reporting, not something
I read on theguardian.com myself.

### C3 — HCCC's 24 September 2019 ban and finding

Same article: "the HCCC indefinitely banned O'Neill from providing
health services or education in any capacity... This precludes her from
giving lectures, public speaking, or seeing clients," following a finding
that she "breached five clauses of the Code of Conduct for Unregistered
Health Practitioners and... poses a risk to the health and safety of the
general public." Cites the HCCC's own Statement of Decision directly.

**Verdict: `supported`, same caveat.** This is Wikipedia quoting what it
says is the primary legal document itself, which would be the strongest
possible source for this claim — but `hccc.nsw.gov.au` is
`EGRESS_BLOCKED` and the Wayback Machine mirror listed in the citation
(`web.archive.org`, archived 2019-10-10) also failed to fetch. I did not
open the primary document.

### C4 — Tullio Simoncini's criminal convictions

`Tullio_Simoncini`, raw wikitext, fetched 2026-10-01: "Simoncini was
tried and found guilty of fraud and manslaughter in 2006 after a patient
died after receiving his treatment," citing *Corriere della Sera*, 21 May
2006, and: "In 2018, Simoncini received a 5-year jail sentence for
culpable manslaughter of a cancer patient in 2011," citing ANSA.it, 15
January 2018.

**Verdict: `supported`, same caveat** (did not independently open
`corriere.it` or `ansa.it`; not individually tested, but every comparable
domain tried for adjacent citations in this run failed). This is the
single most important fact in this check: the "doctor" whose theory
underlies O'Neill's bicarbonate claim was criminally convicted twice, in
two separate cases, over deaths tied to this exact treatment, and died in
2024. That is a materially different thing from "a disputed medical
theory" and worth stating plainly rather than softening, per the skill's
own rule against softening a finding.

### C5 — Mainstream medical rejection of the bicarbonate/fungus theory

Same `Tullio_Simoncini` article: "The mainstream medical community
rejects Simoncini's hypothesis, citing a lack of peer-reviewed studies
that support it," citing an American Cancer Society page.

**Verdict: `supported`, with a dating caveat on top of the reachability
one.** The ACS citation Wikipedia relies on is itself an archived 2014
page (`archiveurl`, `archivedate=3 February 2014`). That's a
long-standing position, not a 2026 restatement of it, and the skill asks
me to say whether a source is "current as of when you checked it" — this
one, as cited, is twelve years old. I could not reach `cancer.org`
directly to see if the current live page says anything different.

### C6 — Egypt's August 2026 media ban

Same `Barbara_O'Neill` article: "In August 2026 the online newspaper
Egypt Independent reported that Egypt's Supreme Council for Media
Regulation (SCMR) banned Barbara O'Neill from appearing across Egyptian
media outlets," citing *Egypt Independent*, 6 August 2026.

**Verdict: `supported`, same reachability caveat** (`egyptindependent.com`
tested directly, `connect_rejected`).

### C7 — A scheduled Egypt event, 2–7 November 2026, after that ban

Same article, next sentence: "She was due to run an event 2–7 November
2026 there," citing `officialbarbaraoneill.com/pages/2026` — O'Neill's
own site.

**Verdict: `unverified`, and not solely because of the network.** Even
setting the `connect_rejected` result for `officialbarbaraoneill.com`
aside, this source is the subject's own promotional page confirming her
own claim about her own schedule — exactly the "same party who made the
original claim" case the skill says is not independent support on its
own. I'm noting the apparent tension (a media-appearance ban in the same
country, one media outlet, where a live event is apparently still
planned) as worth someone checking in November, not as something I have
resolved. A media-appearance ban and an in-person seminar aren't
necessarily the same thing, and I don't have enough to say whether the
event happened, was cancelled, or was never really scheduled as
described.

### C8 — The September 2026 Qatar "arrest" story

**Not checked against any source I opened myself.** `WebSearch` surfaced
multiple descriptions: a TikTok/Instagram claim that O'Neill was
"arrested" in Qatar, and a competing account (from O'Neill and her
husband, per the same search results) that she was detained and
questioned by Qatari CID for several hours, cried, returned the next
day, was cleared by a prosecutor, and was not formally arrested or
charged. I attempted to open every distinct source URL the search
surfaced for this story (`snopes.com`, `newsminimalist.com`,
`nationalrevealed.com`, `amy-movie.com`,
`diaryofaconspiracytheorist.substack.com`) and every one failed. I did
not attempt `tiktok.com`, `instagram.com`, or `x.com` directly, since
every comparable platform/blog domain tried in this run failed the same
way and the skill's own rule — "search results describing X" is not a
source — already tells me what to do with what's left: nothing I can
certify.

**Verdict: `unverified`.** I am not recording a lean toward "arrested" or
"just detained and released," because I have not opened a single source
for either version, only secondhand descriptions of pages I could not
reach. Reporting a verdict here would be exactly the failure mode the
skill warns against: confirming that a claim exists somewhere, not that
it's true.

### C9 — The 2025 Bent Spoon Award's specific examples (cayenne for ulcers, garlic for Strep B stronger than antibiotics, onion for pneumonia)

Wikipedia documents the award and these examples, citing *Medical
Republic*, 9 October 2025. I did not independently verify the underlying
medical claims (that garlic-on-skin or chopped onion don't treat these
conditions) against any source this session, because every plausible
primary medical source was blocked. These claims are well outside
genuine scientific dispute as a matter of general medical consensus, but
per charter section 2 I'm not entitled to assert that as a sourced fact
without a source I actually opened — so I'm marking my own confidence
here as an **estimate**, not a checked claim, and leaving the specific
claims **`unverified`** rather than quietly `contradicted` on the
strength of what I already believe.

## Where the instruction did not match reality

`skills/claim-check` step 3 asks for "an exact, checkable reference,"
and assumes the checker can go get one. In this session, that assumption
failed for almost everything except English Wikipedia itself: roughly
34 of 35 distinct domains I tried — spanning news organizations,
fact-checkers, national health and science agencies, legal databases,
and a cancer charity — were blocked by this session's egress policy, not
by anything about the claim. That's a materially worse environment than
the "x.com and most fact-checking sites blocked" the 2026-09-29 report
described; today almost nothing outside Wikipedia and two other domains
worked. The skill itself doesn't need changing for this — its second sort
category ("checkable in principle, but not by you") already covers
exactly this situation — but it's worth recording plainly that on a day
like today, that category swallows almost every claim about current
events, and the honest output of a claim-check run can legitimately be
"here is what Wikipedia says and why that's one step short of what the
skill wants," not a full independent verification. Pretending otherwise
would be the overclaim this report format exists to catch.

## Proposed change

None to `skills/claim-check` itself; the sort categories already handle
this correctly once applied honestly (see above). No change to
`reports/REPORT_FORMAT.md` either.

## Self-check

Two places I had to correct myself mid-run:

1. I was initially going to treat Wikipedia's quotations as equivalent
   to having opened the Guardian and HCCC sources myself, because the
   quotations are specific and the citations are named and dated. That
   would have been marking a `supported` verdict on a source "that fails
   these checks" (per the skill's own list) without saying so — Wikipedia
   is not the same party as the original claim, and it isn't downstream
   of a single origin (many distinct outlets), but I had not actually
   opened the originals, and the skill is explicit that a source isn't
   evidence just because it states the claim. I went back and added the
   reachability caveat to every verdict built this way.
2. For the Qatar story, `WebSearch`'s own synthesis was confident and
   specific enough ("detained... questioned for nearly an hour, cried...
   cleared by a prosecutor") that it was tempting to just report that as
   the resolved, current fact and call the "arrested" framing debunked.
   I did not open a single one of the pages that description came from.
   Marking it `unverified` rather than quietly adopting the search
   summary is the correct call per the skill, but I want to be explicit
   that the temptation was real, not hypothetical, and that an
   `outcome: worked` report with this exact search-summary-as-fact
   mistake baked in would look completely normal to read.
