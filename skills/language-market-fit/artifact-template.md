# HTML Artifact Template

The final deliverable for both modes is a single self-contained HTML file. Clean product-UI aesthetic: system fonts, card-based, scannable, restrained. No external requests, no frameworks, no animation beyond subtle hover. Everything inline in one file.

## When to generate

- **Compose:** after the package is settled (headline chosen, package built, stress-tested). Not mid-iteration.
- **Audit:** after the prioritized fix list is complete.

Every line of copy in the artifact must have already passed the [Anti-AI Voice Check](anti-ai-tells.md) and the [Platitude Kill List](reference.md). The artifact is a presentation surface, not a place to relax the standard.

## How to write and open it

1. Build the full HTML by adapting the skeleton and components below. Include only the sections that apply.
2. Write it to the current working directory as `language-market-fit-[mode]-[slug].html`, where `[mode]` is `compose` or `audit` and `[slug]` is the product name in kebab-case (for example `language-market-fit-compose-acme-crm.html`).
3. Open it: `open "language-market-fit-[mode]-[slug].html"`. If `open` is unavailable (non-macOS), skip it and report the file path so the user can open it themselves.
4. Tell the user the path and give a one-line summary of what the artifact contains.

Do not fabricate a date or metrics. If you do not have a real date, omit the date line. Use the product/customer one-liner for the subtitle instead.

---

## Shared skeleton

Paste this as the file shell. Swap the `<main>` content per mode using the components below.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[Product] · [Copy Package | Copy Audit]</title>
<style>
:root{
  --bg:#FBFBF9; --surface:#FFFFFF;
  --ink:#19191C; --ink-2:#55555E; --ink-3:#8C8C95;
  --line:#ECEBE6; --line-2:#DEDDD7;
  --accent:#3E3AC9; --accent-soft:#EEEDFB;
  --grounded-bg:#ECFDF3; --grounded-line:#A6EFC5; --grounded-ink:#067647;
  --inferred-bg:#FEF6EE; --inferred-line:#F7D9AE; --inferred-ink:#B54708;
  --p0-bg:#FEF3F2; --p0-line:#FECDCA; --p0-ink:#B42318;
  --p1-bg:#FFF4ED; --p1-line:#F9D9AE; --p1-ink:#B93815;
  --p2-bg:#FFFAEB; --p2-line:#FEDF89; --p2-ink:#B54708;
  --p3-bg:#F7F8FA; --p3-line:#E7E9EF; --p3-ink:#475467;
  --radius:12px; --radius-sm:7px; --radius-lg:16px;
  --shadow:0 1px 2px rgba(16,18,24,.04), 0 2px 6px rgba(16,18,24,.05);
  --font:ui-sans-serif,system-ui,-apple-system,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  --mono:ui-monospace,SFMono-Regular,"SF Mono",Menlo,Consolas,monospace;
}
*{box-sizing:border-box;margin:0;padding:0}
html{-webkit-font-smoothing:antialiased;text-rendering:optimizeLegibility}
body{background:var(--bg);color:var(--ink);font-family:var(--font);font-size:16px;line-height:1.6;padding:48px 24px 96px}
.wrap{max-width:760px;margin:0 auto}

/* header */
.eyebrow{display:flex;align-items:center;gap:8px;font-size:11px;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--ink-3)}
.eyebrow .dot{width:6px;height:6px;border-radius:50%;background:var(--accent)}
.doc-title{margin:14px 0 8px;font-size:clamp(28px,4.5vw,40px);font-weight:680;letter-spacing:-.02em;line-height:1.08}
.lede{font-size:16px;color:var(--ink-2);max-width:54ch}
.rule{height:1px;background:var(--line);margin:32px 0}

/* sections */
.section{margin-top:40px}
.section-label{display:flex;align-items:baseline;gap:10px;font-size:12px;font-weight:650;letter-spacing:.04em;text-transform:uppercase;color:var(--ink-3);margin-bottom:16px}
.section-label::after{content:"";flex:1;height:1px;background:var(--line)}

/* chips */
.chip{display:inline-flex;align-items:center;gap:5px;font-size:11px;font-weight:650;letter-spacing:.03em;text-transform:uppercase;padding:3px 8px;border-radius:999px;border:1px solid transparent;white-space:nowrap}
.chip--grounded{background:var(--grounded-bg);border-color:var(--grounded-line);color:var(--grounded-ink)}
.chip--inferred{background:var(--inferred-bg);border-color:var(--inferred-line);color:var(--inferred-ink)}
.chip--p0{background:var(--p0-bg);border-color:var(--p0-line);color:var(--p0-ink)}
.chip--p1{background:var(--p1-bg);border-color:var(--p1-line);color:var(--p1-ink)}
.chip--p2{background:var(--p2-bg);border-color:var(--p2-line);color:var(--p2-ink)}
.chip--p3{background:var(--p3-bg);border-color:var(--p3-line);color:var(--p3-ink)}

/* hero headline */
.hero{background:var(--surface);border:1px solid var(--line-2);border-radius:var(--radius-lg);box-shadow:var(--shadow);padding:28px 28px 24px;position:relative}
.hero-head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:16px}
.hero-kicker{font-size:11px;font-weight:650;letter-spacing:.1em;text-transform:uppercase;color:var(--ink-3)}
.hero-line{font-size:clamp(24px,3.6vw,32px);font-weight:680;letter-spacing:-.02em;line-height:1.12;color:var(--ink)}
.hero-maps{margin-top:14px;padding-top:14px;border-top:1px dashed var(--line-2);font-size:14px;color:var(--ink-2)}
.hero-maps b{color:var(--ink);font-weight:600}

/* key-value brief */
.kv{display:grid;grid-template-columns:130px 1fr;gap:10px 20px;background:var(--surface);border:1px solid var(--line);border-radius:var(--radius);padding:20px 22px}
.kv dt{font-size:12px;font-weight:650;letter-spacing:.03em;text-transform:uppercase;color:var(--ink-3);padding-top:1px}
.kv dd{font-size:15px;color:var(--ink)}

/* alternates */
.alt-list{display:flex;flex-direction:column;gap:2px}
.alt{display:flex;justify-content:space-between;align-items:flex-start;gap:14px;padding:14px 4px;border-bottom:1px solid var(--line)}
.alt:last-child{border-bottom:none}
.alt-text{font-size:16px;font-weight:560;color:var(--ink)}
.alt-maps{font-size:13px;color:var(--ink-3);margin-top:3px}

/* package grid */
.grid{display:grid;gap:14px}
.grid.two{grid-template-columns:1fr 1fr}
.card{background:var(--surface);border:1px solid var(--line);border-radius:var(--radius);padding:18px 20px}
.card-label{font-size:11px;font-weight:650;letter-spacing:.06em;text-transform:uppercase;color:var(--ink-3);margin-bottom:8px}
.card-body{font-size:16px;color:var(--ink)}
.benefit .struggle{font-size:13px;color:var(--ink-3);margin-bottom:4px}
.benefit .struggle::before{content:"↳ ";color:var(--inferred-ink)}
.benefit .resolution{font-size:16px;font-weight:540;color:var(--ink)}
.cta-card{background:var(--accent-soft);border-color:transparent}
.cta-card .card-body{font-weight:600;color:var(--accent)}

/* callout (stress-test, validate) */
.callout{background:var(--surface);border:1px solid var(--line);border-left:3px solid var(--accent);border-radius:var(--radius);padding:18px 22px}
.callout h4{font-size:13px;font-weight:650;letter-spacing:.03em;text-transform:uppercase;color:var(--ink-2);margin-bottom:10px}
.callout p{font-size:15px;color:var(--ink-2);margin-bottom:8px}
.callout p:last-child{margin-bottom:0}
.callout .q{color:var(--ink);font-style:italic}

/* audit finding */
.finding{background:var(--surface);border:1px solid var(--line);border-radius:var(--radius);padding:20px 22px;margin-bottom:14px}
.finding-head{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.finding-head .num{font-variant-numeric:tabular-nums;font-weight:680;color:var(--ink-3);font-size:14px}
.finding-head .title{font-size:16px;font-weight:620;color:var(--ink)}
.quote{font-family:var(--mono);font-size:14px;background:#FAFAF7;border:1px solid var(--line);border-radius:var(--radius-sm);padding:11px 14px;color:var(--ink-2);margin-bottom:12px}
.quote::before{content:"“";color:var(--ink-3)}.quote::after{content:"”";color:var(--ink-3)}
.finding-what{font-size:15px;color:var(--ink);margin-bottom:6px}
.finding-why{font-size:14px;color:var(--ink-2);margin-bottom:14px}
.rewrites{display:flex;flex-direction:column;gap:8px}
.rewrite{display:flex;align-items:flex-start;gap:10px;font-size:15px}
.rewrite .arrow{color:var(--grounded-ink);font-weight:700;line-height:1.5}
.rewrite .txt{color:var(--ink);flex:1}

/* priority list */
.priority{display:flex;flex-direction:column;gap:10px}
.prow{display:flex;gap:14px;align-items:flex-start;background:var(--surface);border:1px solid var(--line);border-radius:var(--radius);padding:14px 16px}
.prow .badge{flex:none;width:24px;height:24px;border-radius:7px;background:var(--ink);color:#fff;font-size:13px;font-weight:680;display:flex;align-items:center;justify-content:center;font-variant-numeric:tabular-nums}
.prow .pbody .ptitle{font-size:15px;font-weight:600;color:var(--ink)}
.prow .pbody .pdesc{font-size:14px;color:var(--ink-2);margin-top:2px}

/* footer */
.footer{margin-top:56px;padding-top:20px;border-top:1px solid var(--line);font-size:13px;color:var(--ink-3)}
.footer b{color:var(--ink-2);font-weight:600}

@media(max-width:560px){
  body{padding:32px 18px 64px}
  .kv{grid-template-columns:1fr;gap:4px 0}
  .kv dd{margin-bottom:8px}
  .grid.two{grid-template-columns:1fr}
  .alt{flex-direction:column;gap:4px}
}
</style>
</head>
<body>
<div class="wrap">
  <!-- MAIN CONTENT GOES HERE -->
</div>
</body>
</html>
```

---

## Compose layout

Assemble `<main>` in this order. Skip any block you do not have.

```html
<header>
  <div class="eyebrow"><span class="dot"></span>Language-Market Fit · Copy Package</div>
  <h1 class="doc-title">[Product name]</h1>
  <p class="lede">[One line: who it's for + the situation they're in]</p>
</header>
<div class="rule"></div>

<!-- The brief -->
<section class="section">
  <div class="section-label">The brief</div>
  <dl class="kv">
    <dt>Product</dt><dd>[one sentence]</dd>
    <dt>Customer</dt><dd>[who + situation]</dd>
    <dt>Trigger</dt><dd>[what makes them act]</dd>
    <dt>Before → after</dt><dd>[workaround → outcome]</dd>
    <dt>Raw material</dt><dd>[sources, or "inference only"]</dd>
  </dl>
</section>

<!-- The chosen headline -->
<section class="section">
  <div class="section-label">The headline</div>
  <div class="hero">
    <div class="hero-head">
      <span class="hero-kicker">Recommended</span>
      <span class="chip chip--grounded">Grounded</span>
    </div>
    <div class="hero-line">[The headline]</div>
    <div class="hero-maps">Maps to: <b>[the specific customer struggle]</b></div>
  </div>
</section>

<!-- Alternates -->
<section class="section">
  <div class="section-label">Alternates</div>
  <div class="alt-list">
    <div class="alt">
      <div><div class="alt-text">[Headline option]</div><div class="alt-maps">[struggle it maps to]</div></div>
      <span class="chip chip--inferred">Inferred</span>
    </div>
    <!-- repeat per alternate -->
  </div>
</section>

<!-- The package -->
<section class="section">
  <div class="section-label">The package</div>
  <div class="grid">
    <div class="card"><div class="card-label">Subheadline</div><div class="card-body">[subhead]</div></div>
    <div class="grid two">
      <div class="card benefit"><div class="struggle">[the struggle]</div><div class="resolution">[benefit line]</div></div>
      <div class="card benefit"><div class="struggle">[the struggle]</div><div class="resolution">[benefit line]</div></div>
      <div class="card benefit"><div class="struggle">[the struggle]</div><div class="resolution">[benefit line]</div></div>
      <div class="card cta-card"><div class="card-label">Primary CTA</div><div class="card-body">[CTA text]</div></div>
    </div>
  </div>
</section>

<!-- Stress-test -->
<section class="section">
  <div class="section-label">Stress-test</div>
  <div class="callout">
    <h4>Reading this as a skeptical prospect</h4>
    <p class="q">“[what a prospect would think scanning the headline]”</p>
    <p><b>Biggest risk:</b> [the risk in this version]</p>
    <p><b>Test first:</b> [what to A/B test and why]</p>
  </div>
</section>

<!-- Validate -->
<section class="section">
  <div class="section-label">Before you launch</div>
  <div class="callout">
    <p>Run the <b>5-second test</b>: show the headline to 3-4 people for 5 seconds, then ask what the product does. If they repeat the words back instead of explaining in their own words, comprehension has not landed. Iterate.</p>
  </div>
</section>

<div class="footer">
  Built with the <b>language-market-fit</b> skill. Grounded lines come from real customer language; inferred lines are best-guess and should be validated before launch.
</div>
```

---

## Audit layout

```html
<header>
  <div class="eyebrow"><span class="dot"></span>Language-Market Fit · Copy Audit</div>
  <h1 class="doc-title">[Product or page name]</h1>
  <p class="lede">[the page's job + who lands on it]</p>
</header>
<div class="rule"></div>

<!-- Context -->
<section class="section">
  <div class="section-label">Context</div>
  <dl class="kv">
    <dt>Who lands here</dt><dd>[reader + situation]</dd>
    <dt>Their problem</dt><dd>[in their words]</dd>
    <dt>Desired action</dt><dd>[the one action]</dd>
  </dl>
</section>

<!-- Findings, ordered by impact -->
<section class="section">
  <div class="section-label">Findings by impact</div>

  <div class="finding">
    <div class="finding-head">
      <span class="num">01</span>
      <span class="chip chip--p0">Highest impact</span>
      <span class="title">[short name of the problem]</span>
    </div>
    <div class="quote">[exact copy that's failing]</div>
    <div class="finding-what">[what's wrong, one sentence]</div>
    <div class="finding-why">[what the prospect is thinking/feeling here]</div>
    <div class="rewrites">
      <div class="rewrite"><span class="arrow">→</span><span class="txt">[rewrite, most grounded]</span><span class="chip chip--grounded">Grounded</span></div>
      <div class="rewrite"><span class="arrow">→</span><span class="txt">[rewrite option 2]</span><span class="chip chip--inferred">Inferred</span></div>
    </div>
  </div>
  <!-- repeat per finding, severity chip p0→p3 by impact -->
</section>

<!-- Priority fix list -->
<section class="section">
  <div class="section-label">Fix in this order</div>
  <div class="priority">
    <div class="prow"><span class="badge">1</span><div class="pbody"><div class="ptitle">Headline</div><div class="pdesc">[the fix + why it's first]</div></div></div>
    <div class="prow"><span class="badge">2</span><div class="pbody"><div class="ptitle">CTA</div><div class="pdesc">[the fix]</div></div></div>
    <div class="prow"><span class="badge">3</span><div class="pbody"><div class="ptitle">Supporting copy</div><div class="pdesc">[the fix]</div></div></div>
    <div class="prow"><span class="badge">4</span><div class="pbody"><div class="ptitle">What's missing</div><div class="pdesc">[the gap]</div></div></div>
  </div>
</section>

<!-- Language gaps -->
<section class="section">
  <div class="section-label">Where to get real customer language</div>
  <div class="callout">
    <p>[What you couldn't fix without real customer words, and the fastest place to find them: which review sites, what to search, which interview questions.]</p>
  </div>
</section>

<div class="footer">
  Built with the <b>language-market-fit</b> skill. Rewrites marked <b>Grounded</b> use customer language you provided; <b>Inferred</b> rewrites are best-guess and should be validated against real customer words.
</div>
```

---

## Gotchas for the artifact

- **Do not relax the copy standard for the artifact.** Every line still passes the voice check. A polished HTML wrapper around AI-sounding copy is worse, not better, because it looks finished.
- **Do not invent content to fill a section.** If there are only two headline alternates, show two. If you have no real customer quotes, do not manufacture a "Grounded" chip. The chips are a trust signal; a false one breaks the whole point of the framework.
- **Do not add charts, scores, or fake metrics.** This skill produces copy and judgment, not analytics. A "conversion score: 87" with no data behind it is the exact dishonesty the framework exists to fight.
- **Keep it one file.** No CDN fonts, no external scripts, no image links. It has to open offline and survive being emailed around.
