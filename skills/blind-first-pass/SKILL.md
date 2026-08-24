---
name: blind-first-pass
description: Produce an independent answer to a shared question before reading any other participant's answer. Use whenever several agents are working the same question and the value depends on their answers being independent.
state: proposed
---

# Blind first pass

## Why

When several models answer the same question, the answers are only worth
comparing if they were formed separately. Read the others first and you
will drift toward them. The drift feels like being persuaded. It usually
is not.

## Procedure

1. **Seal the room.** Do not open the thread, the other reports, or the
   discussion. If you have already read them, say so and stop. You cannot
   file a first pass on this question anymore.

2. **State the question in your own words** in one sentence. If you cannot,
   the question is underspecified. File that instead of an answer.
   Alongside your paraphrase, quote the exact question text you were
   actually given, verbatim, with its source (issue, PR, or decision
   record). The paraphrase is for your own understanding; the verbatim
   quote is what lets someone else check whether two participants were
   actually answering the same question or two differently-worded
   versions of it that only look the same.

3. **Answer.** Give your position and the reasoning that produced it.

4. **Mark every claim.** Sourced, or estimate. No third category.

5. **Name your strongest objection to yourself.** Not a hedge. The specific
   thing that, if true, would make your answer wrong. If you cannot find
   one, you have not understood your own position well enough to file it.

6. **Commit before reading anything else.** File your answer as a pull
   request or commit before opening the other participant's answer.
   The timestamp on that commit is what makes "before reading anything
   else" checkable by someone other than you, instead of a claim you
   are just making about yourself. If you draft locally first, commit
   before you look, not after.

## After exposure

Read the others. If you change position, file a second entry that states
what changed your mind and which specific argument did it. "On reflection"
is not an answer to that question.

The first pass stays in the record either way.

## Failure modes

- Producing a self-objection that is actually a caveat. "This may not apply
  in all cases" is not an objection. "This fails if X, and X is common" is.
- Hedging the whole answer so that no position can be wrong. A first pass
  that cannot be refuted has no value here.
- Skipping step 5 because the answer feels obvious. Obvious answers are
  where herding is hardest to detect.
- Paraphrasing the question toward whichever wording makes your
  preferred answer look right, instead of quoting it verbatim alongside
  the paraphrase.
- Committing locally, reading the other answers, then pushing the
  commit after. Only the public, timestamped commit counts as
  "before"; a local draft is not checkable by anyone else.
