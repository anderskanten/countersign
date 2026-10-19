# Deadline watchdog: run log

Weekly, Mondays 07:00 UTC. Model: Claude Sonnet 5. Read-only unless a
deadline is overdue; it never merges a provisional decision itself.

Since 2026-08-25 it runs three checks:

1. Boundary/emergency-action deadlines (`CHARTER.md` section 9).
2. Charter completion deadline, 30 days (`CHARTER.md` section 10).
3. Provisional-decision confirmation deadline, 90 days (`skills/decide`).

Run 2026-08-24 predates checks 2 and 3.

| Run date | Checks | Overdue | Action taken |
|---|---|---|---|
| 2026-08-24 | 1 | none | none |
| 2026-08-31 | 1, 2, 3 | none | none |
| 2026-09-07 | 1, 2, 3 | none | none |
| 2026-09-14 | 1, 2, 3 | none | none |
| 2026-09-28 | 1, 2, 3 | check 1 | PR #83 opened, custodian-required |
| 2026-10-19 | 1, 2, 3 | none (check 2 courtesy window) | courtesy email sent |

## Entries

### 2026-08-24 (check 1 only)

Read all 9 decision files. One boundary action with a stated deadline:
`2026-08-22-boundary-fast-track-limits.md`, due 2026-09-22, not yet
passed. Nothing overdue. No PR, issue or comment opened.

### 2026-08-31

Check 1: same single deadline, 2026-09-22, 22 days out. Check 2: five
decisions carry quoted charter text and a countersign; in every case the
text is already present verbatim in the live `CHARTER.md`, so all were
skipped. Check 3: five provisional decisions carry the explicit
deadline 2026-11-22; a sixth, `completion-deadline-for-charter-changes`,
computes to about 2026-11-23. None overdue. No action.

### 2026-09-07

Same result. Check 2 additionally noted that
`external-review-as-disinterested-countersign.md` is not eligible
because `countersigned_by` is empty and status is `open`. No action.

### 2026-09-14

Same result. Check 1: deadline 2026-09-22 now 8 days out. Check 3: six
provisional decisions, all about two months from their deadlines. No
action.

### 2026-09-28

Check 1: the 2026-09-22 deadline on
`decisions/2026-08-22-boundary-fast-track-limits.md` has passed.
Checked `decisions/`, `reviews/`, and this log for a recorded real beta
against a further emergency boundary action, or a second disinterested
countersign of that decision specifically; found neither. A 2026-09-24
external review
(`reviews/2026-09-24-hermes-gpt55-watchdog-deadline-review.md`) reached
the same reading and was watching for this run to act on it. Opened
[PR #83](https://github.com/anderskanten/countersign/pull/83),
`watchdog/revert-boundary-fast-track-limits`, proposing the revert of
the two `CHARTER.md` section 9 paragraphs that decision added, labeled
`custodian-required`, not merged. Added a dated note to the decision
file's "What happened" recording the same, without changing its
`status` field.

Check 2: same five decisions carry quoted charter text with a
non-empty countersign (a sixth new decision since the last run,
`countersign-section-required`, amends `skills/decide`, not
`CHARTER.md`, so it is not a check-2 candidate at all); in every case
the text is already present verbatim in the live `CHARTER.md`, so all
were skipped. None overdue.

Check 3: six provisional decisions. Five carry the explicit deadline
2026-11-22; `completion-deadline-for-charter-changes` computes to
about 2026-11-23. None overdue. No action.

### 2026-10-19

Check 1: PR #83 (opened 2026-09-28, proposing the revert of the overdue
`boundary-fast-track-limits` containment) is still open, still draft,
not merged or closed. No new boundary/emergency deadline found in any
other decision file. No new action.

Check 2: re-read the live `CHARTER.md` section 10 completion-deadline
paragraph (unchanged since last run). Walked every decision file again
for a `## Decision` section quoting proposed `CHARTER.md` text with a
non-empty `countersigned_by`. Six candidates found; five already have
their quoted text present verbatim in the live `CHARTER.md` (adopted
directly by the custodian outside this mechanism) and were skipped.
The sixth, `decisions/2026-08-25-external-review-as-disinterested-countersign.md`,
is not yet applied: its countersign was recorded 2026-09-24, which is
25 calendar days before today, inside the 23-30 day courtesy window
and not yet past the 30-day auto-apply threshold. PR #87 (opened
2026-09-30, labeled `custodian-required`) already carries this exact
change and is still open. Sent one courtesy email to the custodian
flagging that the 30-day mark falls around 2026-10-24 and that this
routine will treat it as an automatic-completion-deadline candidate at
that point if PR #87 is still open. No merge attempted; none was due.

Check 3: six provisional decisions. Five (`appeal-mechanism`,
`decide-ab-run-hardening`, `remaining-hermes-findings`,
`tiered-merge-authority`, `fixed-list-amendment-path`) carry the
explicit deadline 2026-11-22, still over a month out. The sixth,
`completion-deadline-for-charter-changes`, computes to about
2026-11-23 and in any case already carries a non-empty
`countersigned_by` (ChatGPT, disclosed partial stake), so it would not
need action under this check even once its deadline passes. None
overdue. No action.

## Upcoming

- **~2026-10-24**: `external-review-as-disinterested-countersign`
  passes 30 days since its countersign (2026-09-24). If PR #87 is
  still open then, the next run should treat it as an
  automatic-completion-deadline candidate under `CHARTER.md` section
  10 check 2, re-verify eligibility mechanically, and apply it if
  clean.
- **2026-11-22 / -23**: the six provisional decisions reach their
  90-day deadline.
- Whatever the custodian decides on PR #83 (merge or close) is the
  next thing to fold back into this log.
