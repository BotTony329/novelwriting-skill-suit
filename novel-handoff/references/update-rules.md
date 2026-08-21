# Update, compaction, and file-splitting rules

`NOVEL_HANDOFF.md` has to stay readable at chapter 60 as easily as at chapter 3.
The failure mode is append-only growth: each session adds a summary, nothing is
removed, and after twenty sessions the file is a 15,000-word archive nobody reads —
at which point the system has quietly stopped working while still looking healthy.

The rule underneath everything: **the file describes the present, plus the minimum
history needed to write the future.**

## Update in place, section by section

**1. Project Snapshot** — overwrite every field. There is exactly one current
position. Never keep a history of positions here.

**2. Style DNA** — leave alone in a normal session. Revise only on genuine
evolution across multiple chapters, and log the revision in Canon Changes.

**3. Story So Far** — add events that constrain future writing; do not add events
that merely happened. Test: would a writer contradict something if they didn't know
this? If not, leave it out. Merge related bullets as the book grows — five bullets
about one investigation become one bullet with the outcome once it's settled.
Keep the three-way split (what happened / what characters believe / what only the
reader knows) intact; it is the section's whole value.

**4. Character State** — rewrite the character's block, don't append to it.
"Emotional state" and "current objective" hold one value each. When a character
leaves the stage for a long stretch, compress them to a one-line dormant entry with
where they were left and why.

**5. Knowledge Matrix** — update the instant information moves. When a fact becomes
known to everyone including the reader, delete the row; it can no longer cause a
leak. Add rows only for facts whose asymmetry matters.

**6. Open Plot Threads** — move resolved threads into the resolved list, compressed
to one line. Don't leave a resolved thread in place with a "RESOLVED" tag; the
section should be scannable as a list of what's still owed to the reader.

**7. Foreshadowing Ledger** — update status on plant, reinforcement, and payoff.
Resolved rows can be trimmed to one line after their payoff chapter is written.
Keep the "do not resolve early" list current — it's the part that prevents a new
writer from spending a clue the author was saving.

**8. Outline Progress** — update after every meaningful scene. Record deviations as
`MODIFIED` / `REPLACED` with a note on what actually happened. Completed acts can be
compressed to a summary line once the story is well past them.

**9. Canon Changes** — append-only by nature, but old entries can be dropped once
every affected chapter has been revised to match, since the change is then simply
canon.

**10. World Rules** — add only rules that constrain writing. Remove rules that were
speculative and never made it into the manuscript. Keep the "explicitly not
established" list — it tells future writers where they have freedom.

**11. Scene-Level Handoff** — rewrite completely. This section describes one moment.

**12. Next Writer Instructions** — regenerate from scratch each session. Stale
instructions are worse than none, because they read as current intent.

**13. Continuity Warnings** — remove warnings that no longer apply (a secret that
has now been revealed is no longer a leak risk). Keep the list under about ten
items; if it's longer, the low-value ones are hiding the dangerous ones.

**14. Recent Changes Log** — one short entry per session, newest first. Keep about
five sessions in detail; compress older ones to a single line each, and drop them
entirely once the events are reflected in the sections above.

## Size discipline

A healthy handoff file for a mid-length novel sits somewhere around 1,500–3,000
words. If it's growing past that and the book isn't unusually large, something is
being appended rather than updated — usually Story So Far or the Recent Changes Log.

When you notice it, compact during a normal update rather than asking permission:
merge, delete what's no longer current, compress old log entries. Mention it in one
line so the user knows the file was pruned, not corrupted.

## Splitting into satellite files

Start with a single `NOVEL_HANDOFF.md`. One file is portable — the user can paste it
into any tool, attach it to any chat, email it to a co-writer. That portability is
worth more than tidiness for most projects.

Split when the file genuinely outgrows a single read, typically past roughly 100k
manuscript words, a dozen tracked characters, or a heavy worldbuilding load:

- `STYLE_GUIDE.md` — Style DNA (section 2)
- `CHARACTERS.md` — Character State (4) and speech patterns
- `WORLD_CANON.md` — World Rules (10) and Canon Changes (9)
- `OUTLINE_STATUS.md` — Outline Progress (8)
- `FORESHADOWING.md` — Foreshadowing Ledger (7) and Open Plot Threads (6)

When splitting, `NOVEL_HANDOFF.md` stays the entry point and keeps: Project
Snapshot, Knowledge Matrix, Scene-Level Handoff, Next Writer Instructions,
Continuity Warnings, Recent Changes Log — plus a linked index of the satellite
files with a one-line note on what each contains and when to read it. A new writer
should still be able to start a scene having read only the entry file, and know
exactly which satellite to open if they need more.

Record the split itself in Canon Changes so nobody later finds `CHARACTERS.md` and
assumes the handoff file is out of date.

## Multi-writer hygiene

- Stamp each update with date and writer/model in the log entry, so a later reader
  can tell which model produced which state and spot systematic drift.
- If you find the file contradicting the manuscript, fix the file to match the
  manuscript, and note the correction in the log — a stale handoff means someone
  wrote without updating, and the user should know that happened.
- Never delete another writer's `UNKNOWN` by guessing. Fill it only from the
  manuscript or from the user.
