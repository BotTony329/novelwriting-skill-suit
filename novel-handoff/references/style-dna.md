# Deriving Style DNA from a manuscript

Style DNA is the section that decides whether a different model's prose reads like
the same book. It fails in one predictable way: someone writes "literary, tense,
cinematic" and the next model produces its own idea of literary, tense, and
cinematic — which is generic AI prose with atmosphere words. Adjectives don't
transfer between models. Behaviors do.

The test for every line you write in this section: **could a different model follow
this without having read the manuscript?** "Restrained emotional tone" fails.
"Emotion is shown through a physical action and then the paragraph ends — the
feeling is never named in the following sentence" passes.

## What to read

Sample 1,500–3,000 words of recent prose plus one earlier passage for comparison.
Recent prose is what the book has become; the earlier passage tells you whether the
voice has drifted, and in which direction. If they differ, the recent voice is
canonical unless the user says otherwise, and the drift itself is worth a note.

Prefer passages of different types — a dialogue scene, an action or tension scene,
and a quiet reflective one. Habits that hold across all three are the book's real
voice. Habits that appear in only one are scene-mode rules, which are also worth
recording ("sentences shorten sharply during physical danger").

## What to measure

Read for patterns rather than counting mechanically, but stay concrete:

**Sentence rhythm.** Roughly how long is a typical sentence? Does the book run
uniform, or alternate long and short? What changes under tension? Where do the long
sentences appear — reflection, description, both? Are fragments used, and for what?

**Paragraph density.** Sentences per paragraph. Whether dialogue paragraphs are
shorter than narration. Whether single-line paragraphs are used for emphasis, and
how often (once a page reads as a habit; once a chapter reads as an event).

**Dialogue-to-narration ratio.** Roughly what proportion of a scene is spoken.
Whether characters answer questions directly or deflect. Whether tags are plain
("said") or varied, how often action beats replace tags, and whether dialogue
carries exposition or resists it.

**Interiority.** How thoughts appear: italicized direct thought, free indirect
style, narrated summary, or almost nothing. How much of a page is interior. Whether
the narrator explains a character's feelings or leaves them implicit.

**Description.** Which senses actually appear — most books lean on two, and naming
which two is more useful than "vivid sensory detail." How many lines a room gets.
Metaphor frequency: one per page, one per scene, one per chapter. Whether
comparisons are drawn from a consistent domain (many good books do this — machinery,
water, weather, the body).

**Emotional explicitness.** Whether feelings are named ("she was furious") or
enacted ("she set the cup down too carefully"). This single axis is the most common
place AI continuations break voice, because models default to naming.

**Transitions and architecture.** How scenes open — mid-action, with setting, with
dialogue. How they close — image, line of dialogue, revelation, unfinished gesture.
How time passes between scenes. Scene break markers.

**Character voice.** For each major character: sentence length, vocabulary
register, what they avoid saying, question-asking habits, whether they interrupt.
Only record patterns that recur; a memorable one-off line is not a voice rule.

**The book's private conventions.** Most manuscripts have one or two habits that
belong to no general category — flat questions written without question marks,
scene breaks marked a particular way, chapter titles spelled out in words,
dialect rendered in a specific spelling, a refusal to use contractions in
narration, a recurring number or object. These are the highest-signal entries in
the whole section, because they are what makes the prose feel like one hand wrote
it, and they are the first thing a different model erases — not out of
carelessness, but because they look like typos or inconsistencies to be tidied.
Hunt for them deliberately and write them down as explicit rules with an example.
If you can't find any, say so; not every book has them.

## Turning observations into rules

Write each rule so it constrains a decision the next writer will actually face.

| Weak | Usable |
| --- | --- |
| Literary and atmospheric | Environment gets 2–3 lines max, then a character acts |
| Emotional, moving | Emotion is named by the narrator at most once per chapter, usually never |
| Snappy dialogue | Exchanges run 1–2 lines per turn; characters answer a different question than the one asked |
| Cinematic pacing | Sentences under 10 words dominate during physical action; no interiority mid-action |
| Rich prose | One metaphor per scene, drawn from weather or machinery |

## The prohibited-drift list

This is the highest-leverage part of the section, because it targets the specific
ways *this* book gets ruined rather than general bad writing. Write each entry as a
concrete pattern someone could catch in a diff.

Recurring AI failure modes worth naming when they'd violate the book's voice:

- Naming the emotion right after showing it ("she slammed the door. She was angry.")
- "He realized that…" / "She knew then that…" as a revelation delivery mechanism
- Closing a scene on a summarizing abstraction about what it all meant
- Rhetorical questions in narration as a tension substitute
- Em dashes and ellipses in every other paragraph
- Tricolon rhythm ("the cold, the dark, the silence") used as default emphasis
- Camera direction in prose ("the camera pulls back," "we see")
- Characters delivering the theme out loud in dialogue
- Adjective stacking (two or three adjectives before most nouns)
- Weather or lighting mirroring emotion on every page
- Every character speaking in the same balanced, articulate register
- Sudden escalation of vocabulary at emotional peaks

Only list what actually threatens this manuscript. A book that genuinely uses
italicized direct thought shouldn't have it banned; a comic novel may want its
characters over-articulate. The list is a fence around this book's identity, not a
universal style guide.

## Revising Style DNA

Style should be revised when the manuscript has genuinely evolved — not when a
single scene reads differently because it's a different kind of scene. Look for the
pattern holding across two or more recent chapters before rewriting the rules.

When you do revise, record it in Canon Changes with old and new, so a later writer
who reads an early chapter doesn't "correct" the book back to its first draft voice.

## When a planning document is the source of the drift

A stale tone note in an outline — "lyrical, cinematic, emotionally sweeping,"
written before a word was drafted — will keep producing drifted prose no matter how
good the Style DNA section is, because the outline is the file people hand to a new
tool first. Fixing the handoff file alone treats the symptom.

When you find one, tell the user plainly: the note describes a book they didn't
write, it is the single largest ongoing risk in the project, and it will re-infect
every handoff. Offer to annotate the outline at the point of the offending text —
a one-line note under the tone note saying it predates drafting and pointing to the
current Style DNA — so the warning travels with the file that causes the problem.
Don't silently rewrite their outline; it is a planning document they own, and the
divergence may be something they want to resolve the other way, by revising the
prose.
