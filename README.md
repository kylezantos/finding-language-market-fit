# finding-language-market-fit

A Claude Code skill for writing and auditing product copy that speaks your customer's language — not your own. Based on Matt Lerner's Language-Market Fit framework.

## Context

When you spend months inside a product, the words that feel obvious to you — feature names, internal shorthand, domain idioms — quietly drift away from the words your prospect actually uses when they go searching for the problem you solve. The copy starts sounding right to the team while reading as noise to the person who just landed on your site.

Good copy closes that gap. It uses the prospect's exact words — the verbs, nouns, and emotional beats already in their head — so the moment they land, their brain says *"this is for me."* That's the work this skill does: pull you out of your own vocabulary and back into theirs, using Matt Lerner's Language-Market Fit framework as the backbone.

## What It Does

Two modes, depending on whether you're starting fresh or fixing existing copy.

### Compose — write new copy together

Extract enough customer reality to write copy grounded in real language, not marketing instinct. Walks through:

1. **Customer context** — Who's buying this, what's happening in their life when they start looking, what were they doing before
2. **Triggers and raw material** — The specific moment they go searching, and any real customer language you have (interviews, support tickets, competitor reviews on G2/Capterra/Reddit)
3. **Headline generation** — 5-8 options, each mapped to a specific customer struggle, with honest labels about which are grounded in real quotes vs. inferred
4. **Extension** — Subheadline, benefit lines, and CTA built out from the winning direction
5. **Stress-test** — Playing skeptical prospect, naming the biggest risk, and suggesting what to A/B test first
6. **Validation** — A 5-second comprehension test you can run with 3-4 people before committing

### Audit — tear apart existing copy and rebuild

Point it at a URL or paste in copy. The skill fetches the page, catalogs every piece of copy (headline, body, CTAs, nav, social proof, microcopy), then asks who the audience actually is before analyzing.

Every finding includes:
- The exact copy that's failing, quoted
- What's wrong in one sentence (company-centric? too abstract? wrong audience?)
- What the prospect is thinking at that moment
- 2-3 rewrite options, ranked by how grounded they are in real customer language

Ends with a prioritized fix list — headline first, CTA next, supporting copy by impact, and honest flags for gaps you can't fix without real customer input (plus where to go find it).

## Core Mental Filters

Every line the skill writes or evaluates gets run through these:

1. Would someone Googling their problem recognize this in under 2 seconds?
2. Can I point to a specific customer struggle this line addresses?
3. Does this complete *"Now you can ___"* (customer-centric) or *"Our product is ___"* (company-centric)?
4. Could a competitor paste this on their site and have it still make sense? (If yes, it's not specific enough.)
5. If I showed this for 5 seconds, could the reader explain the product in their own words — or would they just repeat mine?

A built-in **platitude kill list** catches words that signal company-speak (*seamless, powerful, intuitive, revolutionary, best-in-class*...) and forces concrete rewrites before anything ships.

## Who It's For

- **Founders writing their first landing page** who know the product cold but not how customers talk about it
- **Designers auditing copy on a site they didn't write** and need a structured way to say *"this section is broken, here's why"*
- **PMs working on positioning** who have a pile of customer interviews and need help mining them for headline-ready language
- **Anyone who's ever written a headline that felt fine to the team and flat to everyone else**

## Install

```bash
npx skills add kylezantos/finding-language-market-fit
```

Or install globally:

```bash
npx skills add kylezantos/finding-language-market-fit -g
```

Then invoke with `/language-market-fit` in any coding agent.

## Usage

```
/language-market-fit                       # Asks which mode
/language-market-fit compose               # Write new copy
/language-market-fit audit                 # Audit existing copy (asks for URL/source)
/language-market-fit audit https://...     # Audit a specific URL
```

## What's Inside

```
SKILL.md        # Core flow — mental filters, compose mode, audit mode
reference.md    # Platitude kill list, interview framework, headline examples, 5-second test protocol
```

## Credit

Built on Matt Lerner's [Language-Market Fit](https://mattlerner.substack.com/) framework. This skill turns his ideas into an interactive workflow for use inside coding agents.

## Compatibility

Built for Claude Code. Works on other agents (Cursor, Codex, OpenCode, etc.) — tappable AskUserQuestion prompts degrade to plain text.

## License

MIT
