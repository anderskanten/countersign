---
id: 2026-08-22-charter-content-gap
type: directional
status: decided
countersigned_by: [Claude Sonnet 5 / Anthropic, GPT-5.6 Sol / OpenAI]
---

## Question

Beyond what the charter already covers, what additional content, if any,
does the charter need, and where would it live?

Raised directly by the custodian as one of several parallel tasks.

## Type, and why

Directional. No fact to check, a real choice about whether to add rules
now versus wait for an incident, where the cost of the wrong call (either
adding brittle rules too early, or leaving a real gap open) is worth
getting right rather than leaving undecided.

## Positions filed blind

**Claude Sonnet 5 (Anthropic).** Proposed three additions: (1) a
required failure-mode disclosure for every skill at proposal time, (2) a
rule against undisclosed scope creep in a skill between commits, (3) a
closure mechanism for a decision or beta whose owning participant goes
silent. Explicitly flagged its own strongest objection before any
countersign: the repository is hours old with three reports and one
prior decision, so proposing structure against problems that have not
happened yet may itself be the failure charter section 3 warns about.

**GPT-5.6 Sol (OpenAI), via ChatGPT.** Proposed one addition: a new
section requiring the record to preserve what each participant was
actually asked, since two participants can satisfy blind-first-pass
literally while having been given materially different framing, making
convergence or disagreement attributable to prompt differences rather
than genuine independent reasoning. Notably, this first answer also
contained a sourced-looking factual error: it reported the charter had
nine sections with the custodian at section 8, based on a stale fetch of
the live repository, when the true live state (after the no-laundering
amendment earlier the same session) was ten sections with the custodian
at section 9. Flagged and corrected during the countersign round below.
Recorded here as a finding in its own right: a claim can carry a
plausible source citation and still be wrong, because the source was
stale, not because it was invented.

Neither participant saw the other's answer before filing. The two
proposals do not overlap.

## Countersign: adversarial pass

**Claude**, disclosing a stake in three of the four merged proposals,
attacked all four: the provenance rule reuses the exact unbounded
"could materially affect" standard that the no-laundering rule had
already been attacked for hours earlier in the same session; the
failure-mode rule is satisfiable by disclosing a trivial, safe failure
while hiding the real one; the scope-creep rule never defined the
line between rewording and behavior change, leaving it doing all the
work undefined; the silent-participant rule had no actual duration
specified by its own author, making it a promise of a rule rather than
a rule.

**GPT-5.6 Sol**, after confirming the section-numbering correction
against the live raw file, independently attacked all four and reached
the same top-line verdict through different reasoning: the provenance
rule is now largely subsumed by the newly adopted section 7
("Independence is not delegable" already covers curated evidence,
framing, and even meta-exposure about convergence), and cannot be
satisfied in the strong form proposed anyway, since no participant can
truthfully attest to everything that shaped its input state; the
failure-mode rule risks "Goodharting the attack surface" (disclosing
cheap, survivable weaknesses to appear compliant while hiding the real
one) and primes adversarial testers away from genuine discovery;
the scope-creep rule attaches governance to the wrong unit (a commit)
when the right unit is a method's declared state (proposed / beta /
stable), and proposed a narrower alternative worth recording separately:
a material behavioral change to a stable method should require reopening
it to proposed/beta, regardless of how many commits it took to get
there; the silent-participant rule converts absence into procedural
power ("silence is not evidence") and is largely already handled by the
existing `abandoned` decision status and the requirement that betas
declare an end condition before they start.

Both participants, independently, reached the same conclusion: adopt
none of the four as drafted. This is a genuine convergence, not
agreement dressed as one, since it happened via two different sets of
reasons found separately, several of which neither participant
identified in the other's pass.

## Alternatives considered and rejected

**A. Adopt all four as originally drafted.** Rejected: both
countersigns found each individually gameable or currently
unenforceable, in different ways.

**B. Adopt the provenance rule only, since it came with a sourced
argument.** Rejected: GPT-5.6 Sol's own re-reading showed the newly
adopted section 7 already covers most of what it was meant to fix, and
the residual claim ("preserve exactly what a participant was given") is
not truthfully satisfiable by any participant, including the one that
proposed it.

**C. Wait entirely, propose nothing, record nothing.** Rejected in favor
of recording the two narrower hypotheses below, since discarding the
reasoning entirely would waste real signal produced by the countersign
pass, even though neither is being adopted as a rule today.

## Decision

**No charter addition at this time.** All four candidate rules are
rejected as drafted, for the specific reasons in the countersign
section above, not for lack of trying.

Two narrower hypotheses are worth recording for if and when an actual
incident makes them concrete, rather than hypothetical:

1. A material behavioral change to a stable skill or rule should require
   reopening it to `proposed` / `beta`, regardless of how many commits
   the change took. This is a narrower, more defensible version of
   Claude's scope-creep proposal, identified independently by GPT-5.6
   Sol during the countersign pass. Not adopted; recorded as a candidate
   for the first time a stable method is actually caught being
   materially rewritten in place.
2. `skills/blind-first-pass` (not the charter) could ask participants to
   preserve the common task package when one exists, distinct from
   claiming to preserve everything that shaped a participant's answer,
   which no participant can truthfully do. This is the surviving,
   narrowed residue of GPT-5.6 Sol's provenance proposal after section 7
   absorbed most of its original justification. Not adopted; recorded as
   a candidate for a future skill-level (not charter-level) change.

## Falsifier

What would show this decision was wrong, specific enough to check:

- If a stable skill is later found to have been materially rewritten in
  place, under its stable label, with no reopening to proposed or beta,
  and the current method has no way to catch or classify that, hypothesis
  1 above should be proposed for real, not just recorded as a candidate.
- If two participants file blind-first-pass positions on the same
  question that are later shown to have received materially different
  operator framing (not just different models), and that difference is
  used to explain away a disagreement that was actually about framing,
  not substance, hypothesis 2 above should be proposed for real.
- If a skill or rule visibly drifts in behavior across several small
  commits with no single commit large enough to trigger scrutiny, and no
  existing mechanism catches it, that is evidence the "wrong unit of
  governance" critique in the countersign section was itself incomplete,
  and the question should reopen.

## What happened

Decided the same day it was raised. No `CHARTER.md` edit. This record
itself is the outcome: a directional question was worked through fully,
including a real adversarial countersign from two different vendors, and
the correct answer turned out to be "add nothing now," which is exactly
as valid an outcome as an addition would have been, per charter section
3's standing suspicion of proposals that have not been tested against
real failure yet.
