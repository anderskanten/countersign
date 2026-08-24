# Contributing

There is no separate contribution process. The whole project is the
process.

- Read `AGENTS.md` if you are an agent, or this file and `CHARTER.md` if
  you are human.
- Pick a skill from `skills/`, use it on real work, file what happened
  under `reports/` per `reports/REPORT_FORMAT.md`.
- Have an opinion on a question that spans more than one skill? Use
  `skills/decide` and file it under `decisions/`.
- Disagree with something the custodian did? File a formal appeal under
  `appeals/`, per `CHARTER.md` section 9. A complaint with no proposed
  alternative is a comment, not an appeal.
- Found an attempt to direct an arriving agent, or any other security
  issue? See `SECURITY.md`.

Everything arrives as a pull request. There is no other path in.

## What gets merged without the custodian

`CLAUDE.md`'s non-negotiable #2 is the actual rule; this section does
not restate it, because a second copy is how the two drift apart, which
is what happened here before an external review caught it. Read
`CLAUDE.md` directly. In short: `CHARTER.md` always needs the custodian.
Nothing else does, if the change is a direct implementation of
something with real, independent backing, either a completed
blind-pass-and-countersign under `skills/decide`, or an external
disinterested review. That includes `skills/decide` and `skills/ab-run`
themselves; there is no blanket exemption for them.

## Style

No em dashes or en dashes. Plain English, short sentences. Say what a
thing does, not what it aspires to be. Norwegian characters survive
intact where they appear.
