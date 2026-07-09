# Anti-AI Voice Check

Run this on every line of copy before you show it or write it to an artifact. The goal is copy that reads like a sharp person said it, not smooth generated prose with nobody home.

This is distilled for conversion copy (headlines, subheads, benefits, CTAs, landing-page body). It pairs with the [Platitude Kill List](reference.md): that catches *marketing* tells like "seamless" and "faster," this catches *generation* tells like the em dash and the negation pivot. A line can pass one and fail the other. Run both.

---

## The core mechanism: the delete-test

Most of this check is one move. Take the suspect word out. If the sentence means the same thing and reads clean, cut it. If removing it changes the meaning or the rhythm, keep it.

Run the delete-test on filler first:

`actually`, `really`, `just`, `very`, `simply`, `truly`, `basically`, `essentially`, `literally`, `significant`, `straightforward`, `genuinely`, `incredibly`, `absolutely`, `pivotal`, `crucial`, `interesting`

These almost never survive in copy. They pad the line and signal that the writer is reaching for emphasis the words themselves should be carrying.

---

## High-smell words (verify in context, usually replace)

These are the generated-marketing register. When you catch one you usually have a platitude nearby too. Replace with the plain verb or the concrete thing.

`leverage`, `utilize`, `facilitate`, `empower`, `unlock`, `supercharge`, `elevate`, `foster`, `spearhead`, `showcase`, `synergy`, `robust`, `seamless`, `cutting-edge`, `next-generation`, `revolutionary`, `innovative`, `world-class`, `delve`, `multifaceted`, `tapestry`

Metaphor-only tells (fine literally, a tell as metaphor): `navigate`, `landscape`, `momentum`. "Navigate the form" is fine. "Navigate your growth journey" is a tell.

Connectors that signal generated prose, rare in real copy: `furthermore`, `moreover`, `additionally`, `consequently`, `remarkably`. Cut them or split the sentence.

Plain replacements: `use`, `help`, `run`, `build`, `connect`, `combine`, `cut`, `show`. Or name the actual thing.

---

## Punctuation (firm for copy)

No em dash. No double hyphen. The em dash is the single clearest generated-text fingerprint right now, and copy is short enough that you never need it. Use a comma, a period, parentheses, or two sentences.

---

## Banned sentence shapes

These read as generated no matter what you fill them with.

- **The negation pivot, in all its costumes:** "X isn't Y, it's Z" / "Not X, but Y" / "Not only X, but also Y" / "Not because X, but because Y." One tell, many disguises. Avoid all of them.
- **"The [superlative] X is..."** openings.
- **Starting with "The" and rolling into a broad generalization.**
- **Scaffolding that announces the insight before delivering it:** "Here's the thing," "The key insight is," "What makes this different is."
- **Filler openers:** "It's worth noting," "It is important to note," "In today's [adjective] world," "At the end of the day," "Needless to say."

---

## Structural tells (landing-page body, emails)

- **Over-explaining.** If a sentence only restates or interprets the sentence before it, cut it. Copy cannot afford a single dead line.
- **Summary endings** that recap what the reader just read.
- **Uniform sentence length.** Vary it. One short line. Then a longer one that earns its length.
- **Rhetorical questions used as transitions.**

---

## The carve-outs (do not over-correct)

A maximalist banlist produces its own kind of AI tell: copy sanded so smooth the voice is gone. Hold these exceptions.

- **Three-part parallel structure is good copy when every part is concrete.** "Sleep more. Stress less. Live better" (Calm) passes because each part is a real outcome. "Kick bad habits. Get healthy ones" passes. The tell is three *abstract, interchangeable* parts: "Powerful. Simple. Limitless." Concrete triad: keep it. Abstract triad: kill it.
- **Fragments and one-word lines are good copy.** The rule against uniform sentences is about variety, not about forcing complete sentences. "No setup. No training. Just go." is fine.
- **Voice beats compliance.** If a line sounds like a real person said it out loud, it passes even if it technically trips a flag. Do not rewrite a line with voice into a line that is merely clean.

---

## Running the gate

Before any headline, subhead, benefit line, or CTA is shown or written to the artifact:

1. Em dash or double hyphen present? Remove it.
2. High-smell word? Delete-test, or replace with the concrete thing.
3. Negation-pivot or banned shape? Rewrite.
4. Filler word? Delete-test.
5. Say it in your head. Person, or brand pretending to be one?

Do this silently. The user should only ever see copy that already passed. If a line you like keeps failing, that usually means the underlying claim is abstract. Fix the claim, not the wording.
