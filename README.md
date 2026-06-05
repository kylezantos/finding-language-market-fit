# Finding Language-Market Fit

A skill for writing and auditing product copy that speaks your customer's language, not your own. Based on Matt Lerner's Language-Market Fit framework.

## Context

When you spend months inside a product, the words that feel obvious to you (feature names, internal shorthand, domain idioms) drift away from the words your prospect actually uses when they go searching for the problem you solve. The copy starts sounding right to the team while reading as noise to the person who just landed on your site.

Good copy closes that gap. It uses the prospect's exact words, the verbs, nouns, and emotional beats already in their head, so the moment they land their brain says *"this is for me."* That is the work this skill does: pull you out of your own vocabulary and back into theirs, using Matt Lerner's Language-Market Fit framework as the backbone.

## What it does

Two modes, depending on whether you are starting fresh or fixing existing copy.

### Compose: write new copy together

Extract enough customer reality to write copy grounded in real language, not marketing instinct. Walks through:

1. **Customer context.** Who is buying this, what is happening in their life when they start looking, and what they were doing before.
2. **Triggers and raw material.** The specific moment they go searching, plus any real customer language you have (interviews, support tickets, competitor reviews on G2, Capterra, or Reddit).
3. **Headline generation.** 5 to 8 options, each mapped to a specific customer struggle, with honest labels for which are grounded in real quotes and which are inferred.
4. **Extension.** Subheadline, benefit lines, and CTA built out from the winning direction.
5. **Stress-test.** Reading the copy as a skeptical prospect, naming the biggest risk, and suggesting what to A/B test first.
6. **Validation.** A 5-second comprehension test you can run with 3 to 4 people before committing.

The finished package is delivered as a clean, self-contained HTML file you can open, share, or hand off.

### Audit: tear apart existing copy and rebuild

Point it at a URL or paste in copy. The skill fetches the page, catalogs every piece of copy (headline, body, CTAs, nav, social proof, microcopy), then asks who the audience actually is before analyzing.

Every finding includes:
- The exact copy that is failing, quoted
- What is wrong in one sentence (company-centric? too abstract? wrong audience?)
- What the prospect is thinking at that moment
- 2 to 3 rewrite options, ranked by how grounded they are in real customer language

It ends with a prioritized fix list (headline first, CTA next, supporting copy by impact) and honest flags for gaps you cannot fix without real customer input, plus where to go find it. The report comes back as an HTML file with severity-tagged findings.

## Core mental filters

Every line the skill writes or evaluates gets run through these:

1. Would someone Googling their problem recognize this in under 2 seconds?
2. Can I point to a specific customer struggle this line addresses?
3. Does this complete *"Now you can ___"* (customer-centric) or *"Our product is ___"* (company-centric)?
4. Could a competitor paste this on their site and have it still make sense? (If yes, it is not specific enough.)
5. If I showed this for 5 seconds, could the reader explain the product in their own words, or would they just repeat mine?

Before any line reaches you, it passes two checks. A **platitude kill list** catches company-speak ("seamless," "powerful," "intuitive," "revolutionary," "best-in-class") and forces concrete rewrites. An **anti-AI voice check** catches generation tells (the em dash, filler words, the negation pivot) so the copy reads like a person wrote it, not a model.

## Who it's for

- **Founders writing their first landing page** who know the product cold but not how customers talk about it
- **Designers auditing copy on a site they didn't write** who need a structured way to say *"this section is broken, here's why"*
- **PMs working on positioning** who have a pile of customer interviews and need help mining them for headline-ready language
- **Anyone who has written a headline that felt fine to the team and flat to everyone else**

## Install

### One command (all agents)

```bash
npx skills add kylezantos/finding-language-market-fit
```

Auto-detects your installed agents and installs to each. Works with Claude Code, Codex, OpenCode, Cursor, Gemini CLI, Windsurf, and [35+ more](https://github.com/vercel-labs/skills).

### Target specific agents

```bash
npx skills add kylezantos/finding-language-market-fit -a claude-code
npx skills add kylezantos/finding-language-market-fit -a codex -a opencode
```

### Manual install

Copy the entire repo contents into a `language-market-fit/` directory in your agent's skills path:

| Agent | Path |
|-------|------|
| Claude Code | `~/.claude/skills/language-market-fit/` |
| Codex | `~/.codex/skills/language-market-fit/` |
| OpenCode | `~/.config/opencode/skills/language-market-fit/` |
| Cursor | `~/.cursor/skills/language-market-fit/` |
| Gemini CLI | `~/.gemini/skills/language-market-fit/` |
| Windsurf | `~/.codeium/windsurf/skills/language-market-fit/` |

Or clone:

```bash
git clone https://github.com/kylezantos/finding-language-market-fit.git ~/.claude/skills/language-market-fit
```

Then invoke with `/language-market-fit` in any coding agent.

## Usage

```
/language-market-fit                       # Asks which mode
/language-market-fit compose               # Write new copy
/language-market-fit audit                 # Audit existing copy (asks for URL/source)
/language-market-fit audit https://...     # Audit a specific URL
```

## What's inside

```
SKILL.md             # Core flow: mental filters, gotchas, compose + audit modes
reference.md         # Platitude kill list, interview framework, headline examples, 5-second test
anti-ai-tells.md     # Voice check that keeps copy from sounding generated
artifact-template.md # Clean product-UI HTML template for the final deliverable
```

## Works with any agent

The skill runs the same way across agents. Mode selection uses tappable options where the agent supports them and a plain-text question where it does not. The copy package or audit report is written as a self-contained HTML file in your working directory, and opens in your browser automatically when the agent can.

## Credit

Built on Matt Lerner's [Language-Market Fit](https://mattlerner.substack.com/) framework. This skill turns his ideas into an interactive workflow for use inside coding agents.

## License

MIT
