# Auditing an existing manuscript

Use this when the user asks whether continuity broke, hands over a manuscript
written elsewhere or by another AI, or wants a handoff file built from a cold
project. The output is a findings list plus an updated `NOVEL_HANDOFF.md` — not a
rewritten manuscript. Do not fix prose during an audit unless asked; the user needs
to see what broke and decide.

## Pass 1 — build state

Read the manuscript in order, building the handoff file as you go: positions,
character knowledge, object locations, story clock, planted clues. Building state
forward is what surfaces breaks — you catch a leak because you know, at that point
in the reading, that the character hadn't been told yet.

## Pass 2 — check these six failure classes

**Knowledge leaks.** A character acts on, references, or reacts to information they
were never given. The most common and most damaging break. Check every scene where
a character deduces something suspiciously fast.

**Timeline breaks.** Events out of order, travel that takes no time, day/night
inconsistency, characters in two places, seasonal or weather contradictions,
durations that don't add up.

**Object and physical-state drift.** An item is in two places, an injury vanishes,
clothing or possessions change without cause, a vehicle appears without arriving.

**Character contradiction.** Established facts changed silently — age, background,
relationship history, name spelling, profession. Also motivation reversals with no
scene between them.

**World-rule violations.** A constraint established early is broken later without
acknowledgment: a technology limit, a magic cost, a political structure, a distance.

**Voice drift.** Compare early, middle, and recent prose on the axes in
`style-dna.md`. Report drift direction concretely — "chapters 9–12 name emotions
directly about four times per chapter; chapters 1–8 almost never do" — rather than
"the voice has changed."

## Pass 3 — report

Group findings by severity:

- **Breaks canon** — contradicts something written; needs a decision from the user
- **Risks a break** — ambiguous or under-specified; will cause trouble if unresolved
- **Drift** — style or tone movement, possibly intentional

For each: where it appears (chapter and scene), what conflicts with what, and the
narrowest fix. Where two passages contradict, present both and recommend which to
keep, with a reason — but let the user choose, since one of them may be the version
they prefer and the fix propagates.

Then record the confirmed decisions in Canon Changes and the unresolved ones in
Continuity Warnings, so the next writer doesn't build on a contested fact.

This last step is what makes an audit worth doing. A findings report is a document
about a problem; an updated `NOVEL_HANDOFF.md` is the problem being fixed. The next
session will read the handoff file and will not read your report, so anything that
lives only in the report — a corrected Style DNA, a rejected fact, an open question
— has not actually been recorded. Write the conclusions into the file itself, mark
rejected material as rejected rather than deleting the memory of it, and leave the
story state where the manuscript actually left it rather than where the audited
draft claimed it was.

Where the audit reveals a systemic cause rather than a one-off mistake — a stale
Style DNA that told the other tool to write purple prose, a missing
prohibited-drift list, a knowledge boundary that was never written down — fix the
cause too, and say which finding it explains. Otherwise the same chapter comes back
next month.

## When the project is cold

If there's no handoff file and no outline, build the file from the manuscript alone
and be aggressive with `UNKNOWN` — especially for intent (which clues were meant to
pay off, which threads were abandoned deliberately). Then ask the user a short,
prioritized list of questions: the five or six unknowns that most constrain the next
scene. Don't ask thirty questions; ask the ones that block writing.
