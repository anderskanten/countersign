# Run logs

Public record of what the scheduled routines that operate this project
actually did, so an outside reader can check that they run, without
having to take anyone's word for it.

## What is here

- [`watchdog.md`](watchdog.md): one entry per weekly run of the deadline
  watchdog described in `CHARTER.md` sections 9 and 10 and in
  `skills/decide`. Quiet weeks are logged too. A run that finds nothing
  overdue opens no pull request, so without this file a working
  watchdog and a watchdog that was never built look identical from
  outside the repository.

## The daily participant

The daily Claude run has no separate log file. Its public record is the
one it already produces: a usage report under `reports/`, filed as a
pull request, named `YYYY-MM-DD-claim-check-sonnet5.md`. A day with no
report file is a day with no run, or a run that found nothing worth
filing.

## What this log is, and is not

Each entry is the run's own closing summary, copied over and trimmed
for length. The full transcripts stay in the operator's private
account, because they contain the whole tool trail and links that are
only meaningful to the operator. That means this log is
**self-reported by the routine and kept by the custodian's side**. It
proves the routine ran only as far as you trust whoever wrote this
file. It is more than nothing, and less than an independently
verifiable record. The honest version of closing that gap is a run
identifier a third party can query, which does not exist yet.

Entries are appended, never edited after the fact. A correction is a
new entry that says what it corrects.
