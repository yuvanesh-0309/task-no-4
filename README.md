<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>UX Case Study — Shop Easy</title>
<style>
:root{--ink:#141414;--paper:#f6f5f1;--white:#fff;--purple:#9674ff;--yellow:#e9f83a;--muted:#66645e;--line:#d9d7d0}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:var(--paper);color:var(--ink);font:15px/1.55 Arial,sans-serif}
.wrap{width:min(1120px,calc(100% - 40px));margin:auto}
.top{border-bottom:1px solid var(--line);background:var(--white)}
.nav{height:68px;display:flex;align-items:center;justify-content:space-between}
.logo{font-weight:800;letter-spacing:-.05em;font-size:17px;text-decoration:none;color:var(--ink)}
.logo i{font-style:normal;display:inline-grid;place-items:center;background:var(--yellow);border:1px solid var(--ink);width:30px;height:30px;margin-right:8px}
.nav a:not(.logo){color:var(--ink);text-decoration:none;font-size:12px;margin-left:22px}
.label{font:10px monospace;text-transform:uppercase;letter-spacing:.12em;color:var(--muted)}
.hero{padding:58px 0 50px;border-bottom:1px solid var(--line)}
.hero-grid{display:grid;grid-template-columns:1.1fr .9fr;gap:40px;align-items:center}
.badge{display:inline-block;background:var(--purple);border:1px solid var(--ink);box-shadow:3px 3px var(--ink);padding:6px 10px;font:10px monospace;text-transform:uppercase}
.hero h1{font-size:clamp(42px,6vw,70px);line-height:.96;letter-spacing:-.065em;margin:20px 0 15px}
.hero p{color:var(--muted);max-width:610px}
.brief{background:var(--yellow);border:1px solid var(--ink);box-shadow:5px 5px var(--ink);padding:20px}
.brief h2{font-size:14px;margin:0 0 8px}
.brief p{font-size:12px;margin:0;color:#37372f}
.meta{display:flex;gap:9px;flex-wrap:wrap;margin-top:19px}
.meta span{font:10px monospace;border:1px solid var(--ink);padding:5px 8px;background:var(--white)}
section.block{padding:50px 0;border-bottom:1px solid var(--line)}
.section-head{display:flex;justify-content:space-between;gap:30px;align-items:end;margin-bottom:22px}
.section-head h2{font-size:clamp(28px,4vw,42px);letter-spacing:-.055em;line-height:1;margin:5px 0 0}
.section-head p{max-width:400px;color:var(--muted);font-size:13px;margin:0}
.flow{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
.step{border:1px solid var(--ink);background:var(--white);padding:16px;min-height:130px}
.step b{display:block;font:11px monospace;margin-bottom:10px}
.step p{font-size:12px;color:var(--muted);margin:0}
.screens{display:grid;grid-template-columns:1fr auto 1fr;gap:22px;align-items:center}
.screen-card{background:var(--white);border:1px solid var(--ink);padding:18px}
.screen-card h3{font-size:15px;margin:0 0 12px}
.phone{border:2px solid var(--ink);border-radius:20px;background:#fff;padding:15px 12px;max-width:300px;margin:auto;min-height:340px;box-shadow:4px 4px var(--ink)}
.phone-top{display:flex;justify-content:space-between;font-size:10px;font-weight:bold;margin-bottom:18px}
.promo{background:var(--purple);padding:14px;color:white;border:1px solid var(--ink);font-size:16px;font-weight:bold;line-height:1.1}
.promo small{display:block;font-size:9px;margin-top:8px}
.tilegrid{display:grid;grid-template-columns:repeat(4,1fr);gap:5px;margin:12px 0}
.tile{background:#f1f0ed;border:1px solid var(--line);text-align:center;padding:8px 2px;font-size:8px}
.tile i{font-style:normal;display:block;font-size:16px}
.old-icons{display:flex;justify-content:space-around;padding:10px 0;border-top:1px solid var(--line);font-size:16px}
.search{border:1px solid var(--line);padding:7px;font-size:9px;color:#888;margin-bottom:9px}
.clean-promo{background:var(--purple);color:white;border:1px solid var(--ink);padding:17px 12px;font-weight:bold;font-size:16px}
.product{display:flex;gap:8px;margin-top:10px}
.product div{flex:1;background:#f2f1ed;border:1px solid var(--line);padding:12px 4px;text-align:center;font-size:8px}
.cta{display:block;text-align:center;background:var(--yellow);border:1px solid var(--ink);padding:8px;margin-top:10px;font-size:10px;font-weight:bold}
.new-nav{display:flex;justify-content:space-around;border-top:1px solid var(--line);padding-top:11px;margin-top:16px;font-size:14px}
.new-nav span:first-child{background:var(--purple);border:1px solid var(--ink);padding:2px 5px;margin-top:-3px}
.arrow{font-size:24px}
.issues{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.issue{display:grid;grid-template-columns:38px 1fr;gap:12px;background:var(--white);border:1px solid var(--ink);padding:15px}
.issue-icon{display:grid;place-items:center;background:#ffe6df;border:1px solid var(--ink);height:38px;font-weight:bold;color:#bd4633}
.issue h3{font-size:13px;margin:0 0 4px}
.issue p{font-size:11px;color:var(--muted);margin:0}
.solution-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.solution{background:var(--white);border:1px solid var(--ink);padding:17px}
.solution h3{font-size:14px;margin:0 0 5px}
.solution p{font-size:12px;color:var(--muted);margin:0}
.impact{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
.metric{background:var(--purple);border:1px solid var(--ink);box-shadow:3px 3px var(--ink);padding:17px}
.metric:nth-child(even){background:var(--yellow)}
.metric b{display:block;font-size:30px;letter-spacing:-.06em}
.metric span{font-size:10px}
.caveat{font-size:10px;color:var(--muted);margin-top:16px}
.footer{padding:20px 0;color:var(--muted);font:10px monospace}
.footer .wrap{display:flex;justify-content:space-between;gap:14px;flex-wrap:wrap}

@media(max-width:760px){
  .wrap{width:calc(100% - 28px)}
  .nav{height:auto;min-height:62px}
  .nav a:not(.logo){margin-left:10px;font-size:10px}
  .hero{padding:38px 0}
  .hero-grid{grid-template-columns:1fr;gap:23px}
  .section-head{align-items:flex-start;flex-direction:column;gap:10px}
  .flow{grid-template-columns:repeat(2,1fr)}
  .screens{grid-template-columns:1fr;gap:13px}
  .arrow{transform:rotate(90deg);text-align:center}
  .phone{min-height:320px}
  .issues,.solution-grid{grid-template-columns:1fr}
  .impact{grid-template-columns:repeat(2,1fr)}
  section.block{padding:38px 0}
}
@media(max-width:420px){
  .nav a:not(.logo){margin-left:6px;font-size:9px}
  .nav a[href="#flow"]{display:none}
  .flow{grid-template-columns:1fr}
  .hero h1{font-size:44px}
}
</style>
</head>
<body>
<header class="top">
  <nav class="nav wrap">
    <a class="logo" href="#top"><i>UX</i> FIELD NOTES</a>
    <div>
      <a href="#problem">Problem</a>
      <a href="#redesign">Redesign</a>
      <a href="#impact">Impact</a>
    </div>
  </nav>
</header>

<main id="top">
  <section class="hero">
    <div class="wrap hero-grid">
      <div>
        <span class="badge">UX case study · Task 04</span>
        <h1>Making shopping feel <span style="background:var(--yellow)">simple.</span></h1>
        <p>A sample UX review of a small mobile shopping experience. We identify friction in discovery and navigation, then propose a clearer path from browsing to product selection.</p>
        <div class="meta">
          <span>Role: UX analysis</span>
          <span>Platform: Mobile</span>
          <span>Focus: Findability</span>
        </div>
      </div>
      <aside class="brief">
        <h2>THE DESIGN QUESTION</h2>
        <p>How might we help shoppers find a relevant product quickly, understand the offer, and take the next step with confidence?</p>
      </aside>
    </div>
  </section>

  <section class="block" id="flow">
    <div class="wrap">
      <div class="section-head">
        <div><div class="label">01 · User journey</div><h2>Where friction appears</h2></div>
        <p>The journey below is a sample scenario for the concept. Each step should make the next action clear.</p>
      </div>
      <div class="flow">
        <article class="step"><b>01 · ARRIVE</b><p>Shopper opens the home screen and scans the promotion.</p></article>
        <article class="step"><b>02 · DISCOVER</b><p>They look for a category or use search to narrow choices.</p></article>
        <article class="step"><b>03 · COMPARE</b><p>They review product details, price, and availability.</p></article>
        <article class="step"><b>04 · ACT</b><p>They add the product to a cart and continue checkout.</p></article>
      </div>
    </div>
  </section>

  <section class="block" id="problem">
    <div class="wrap">
      <div class="section-head">
        <div><div class="label">02 · Analyze the problem</div><h2>Current screen vs. proposed screen</h2></div>
        <p>Reduce competing elements, make categories recognizable, and give search and shopping actions stronger hierarchy.</p>
      </div>

      <div class="screens">
        <article class="screen-card">
          <h3>Before · crowded discovery</h3>
          <div class="phone">
            <div class="phone-top"><span>☰ &nbsp; SHOP EASY</span><span>♧</span></div>
            <div class="promo">BIG SALE<br>50% OFF<small>Shop the offer →</small></div>
            <div class="tilegrid">
              <div class="tile"><i>☆</i>Favorites</div>
              <div class="tile"><i>▧</i>Orders</div>
              <div class="tile"><i>⚙</i>Settings</div>
              <div class="tile"><i>♧</i>Account</div>
              <div class="tile"><i>✉</i>Messages</div>
              <div class="tile"><i>▣</i>Gifts</div>
              <div class="tile"><i>♧</i>Support</div>
              <div class="tile"><i>•••</i>More</div>
            </div>
            <div class="old-icons">⌂　▣　♧　☆　☰</div>
            <small style="color:#777">Many small icons compete with the main shopping action.</small>
          </div>
        </article>

        <div class="arrow" aria-hidden="true">→</div>

        <article class="screen-card" id="redesign">
          <h3>After · clearer shopping path</h3>
          <div class="phone">
            <div class="phone-top"><span>Find What<br>You Love</span><span>♧</span></div>
            <div class="search">⌕ &nbsp; Search products</div>
            <div class="clean-promo">Big Sale<br>50% Off<small style="display:block;font-size:9px;margin-top:8px">Selected items · Shop now →</small></div>
            <div style="font-size:10px;font-weight:bold;margin-top:12px">Categories</div>
            <div class="product">
              <div>♙<br>Fashion</div>
              <div>▧<br>Electronics</div>
              <div>⌂<br>Home</div>
              <div>♡<br>Beauty</div>
            </div>
            <a class="cta" href="#impact">Browse products →</a>
            <div class="new-nav"><span>⌂</span><span>⌕</span><span>♡</span><span>♧</span></div>
          </div>
        </article>
      </div>
    </div>
  </section>

  <section class="block">
    <div class="wrap">
      <div class="section-head">
        <div><div class="label">03 · Key findings</div><h2>What makes the experience harder</h2></div>
      </div>
      <div class="issues">
        <article class="issue"><div class="issue-icon">×</div><div><h3>Too many competing controls</h3><p>Small icons and shortcuts make it harder to spot the primary shopping path.</p></div></article>
        <article class="issue"><div class="issue-icon">×</div><div><h3>Unclear information hierarchy</h3><p>Promotions, categories, and account actions have similar visual weight.</p></div></article>
        <article class="issue"><div class="issue-icon">×</div><div><h3>Important actions are easy to miss</h3><p>The next step is not presented as a clear, high-visibility call to action.</p></div></article>
        <article class="issue"><div class="issue-icon">×</div><div><h3>Inconsistent icon meanings</h3><p>Unfamiliar icons can slow navigation, especially on a small screen.</p></div></article>
      </div>
    </div>
  </section>

  <section class="block">
    <div class="wrap">
      <div class="section-head">
        <div><div class="label">04 · Proposed solutions</div><h2>Make the next step obvious</h2></div>
      </div>
      <div class="solution-grid">
        <article class="solution"><h3>① Simplify navigation</h3><p>Keep a small set of predictable destinations in a persistent bottom bar.</p></article>
        <article class="solution"><h3>② Improve visual hierarchy</h3><p>Separate the offer, category shortcuts, and supporting actions with clear spacing.</p></article>
        <article class="solution"><h3>③ Make search easy to find</h3><p>Place a labeled search field near the top, where shoppers expect it.</p></article>
        <article class="solution"><h3>④ Use clear calls to action</h3><p>Use concise labels such as “Shop now” and “Browse products” to describe what happens next.</p></article>
      </div>
    </div>
  </section>

  <section class="block" id="impact">
    <div class="wrap">
      <div class="section-head">
        <div><div class="label">05 · Success measures</div><h2>How to evaluate the redesign</h2></div>
        <p>These are target measures for a usability test or product experiment, not results from a completed study.</p>
      </div>
      <div class="impact">
        <div class="metric"><b>↑</b><span>Product discovery completion</span></div>
        <div class="metric"><b>↑</b><span>Navigation confidence</span></div>
        <div class="metric"><b>↓</b><span>Time to find a product</span></div>
        <div class="metric"><b>↓</b><span>Mis-taps and backtracking</span></div>
      </div>
      <p class="caveat">Next step: test the prototype with shoppers, observe task completion, and compare results before and after the redesign.</p>
    </div>
  </section>
</main>

<footer class="footer">
  <div class="wrap">
    <span>UX CASE STUDY · SHOP EASY CONCEPT</span>
    <span>Research → Findings → Redesign → Test</span>
    <span>Task 04</span>
  </div>
</footer>
</body>
</html>
