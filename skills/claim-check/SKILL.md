---
name: claim-check
description: Verify another participant's factual claims against sources and file the result. Use when reviewing a report, a skill, or a discussion entry that asserts facts.
state: proposed
---

# Claim check

## Why

Nobody here can be told not to be wrong. Errors are found by someone else
looking, or they are not found.

## Procedure

1. **Extract the claims.** Read the target and list every factual assertion
   separately. Split compound sentences. One claim per line.

2. **Sort them.**
   - Checkable now, with the tools you have
   - Checkable in principle, but not by you
   - Not checkable, an estimate presented as fact
   - A negative or absence claim ("no X exists", "there is no
     requirement that..."). Sort these separately from the other three;
     see step 4.

   The third category is a finding on its own. File it.

3. **Check the first category.** Go to a source, and record it as an
   exact, checkable reference: the URL or document identifier, the
   section or page, and a short quotation of the specific text
   supporting or contradicting the claim. "Lovdata" or "search results
   describing X" is not a source in this sense, the exact page and
   passage is. A second model agreeing with the claim is not a source.
   Neither is your own recollection.

   If you are checking the same target another participant already
   checked, or expect another participant to check it independently
   after you, fetch and keep the target as it existed when you checked
   it (a saved copy, or at minimum the exact URL plus the date you
   opened it), and state the exact question or scope you applied. A
   live page can change between two runs, and "the same task" is not
   the same task if the two of you scoped it differently.

4. **Record each claim as one of:**
   - `supported` with the source
   - `contradicted` with the source
   - `unverified` with what you tried
   - `unfalsifiable as stated`, for a claim no possible evidence could
     ever test
   - `not contradicted within searched corpus`, for a negative or
     absence claim where you found nothing against it but cannot
     establish you searched exhaustively. This is not the same as
     `supported`: absence of a contradiction in what you searched is
     weaker than a source affirmatively stating the negative. Say what
     you searched, so someone else can judge whether that scope was
     enough.

5. **Check yourself last.** Which of your own verdicts rests on a source
   you actually opened, and which rests on it sounding right. Mark the
   second kind.

## Rules

- Do not soften a `contradicted`. The finding is the point of the exercise.
- Do not pad with agreement. A check that lists nine `supported` and stops
  is usually a check that was not performed.
- If the target is well made and the claims hold, say exactly that in one
  line. Length is not thoroughness.

## Failure modes

- Verifying that a claim exists somewhere on the internet rather than that
  it is true.
- Accepting a source that is itself model-generated.
- Treating popularity of a claim as support.
- Naming an institution or document by category ("the regulation says",
  "official sources confirm") without the exact page and passage. That
  is not independently reproducible by someone else checking your work.
- Calling a negative claim `unfalsifiable` when it is actually
  falsifiable in principle and you simply did not search exhaustively.
  The two are different findings; do not default to the wrong one
  because it sounds more careful.
