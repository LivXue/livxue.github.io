<!-- ============================================================
     DIZHAN XUE — GitHub Profile README
     Design System: Aztec Network Official Brand Colors
     Parchment #F2EEE1 · Ink #1A1400 · Chartreuse #D4FF28
     ============================================================ -->

<style>
@import url('https://fonts.googleapis.com/css2?family=Martel:wght@300;400;600&family=Geist+Mono:wght@300;400;500;700&family=DM+Sans:wght@300;400;500;600&display=swap');

/* ═══════════════════════════════════════════════
   AZTEC OFFICIAL DESIGN TOKENS
   ═══════════════════════════════════════════════ */
:root {
  /* ── Official Aztec Brand Colors ── */
  --parchment:    #F2EEE1;
  --ink:          #1A1400;
  --chartreuse:   #D4FF28;
  --orchid:       #FF2DF4;
  --aqua:         #2BFAE9;
  --vermillion:   #FF1A1A;
  --malachite:    #001F18;
  --aubergine:    #2E0026;
  --lapis:        #00122E;
  --oxblood:      #2E0700;

  /* ── Nested Layer Hierarchy (page → deepest card) ── */
  --layer-0:  #F2EEE1;   /* Page bg: Parchment            */
  --layer-1:  #E8E3D2;   /* Section container: warm linen */
  --layer-2:  #DDD7C4;   /* Card: deeper parchment        */
  --layer-3:  #CFC8B2;   /* Inner / hover: warm tan       */

  /* ── Text ── */
  --text-primary:   #1A1400;
  --text-secondary: #3D3520;
  --text-tertiary:  #6B6040;
  --text-muted:     #9A9078;
  --text-on-dark:   #F2EEE1;

  /* ── Borders ── */
  --border-light:  rgba(26,20,0,0.10);
  --border-mid:    rgba(26,20,0,0.18);
  --border-strong: rgba(26,20,0,0.35);

  /* ── Typography ── */
  --font-serif: 'Martel', Georgia, serif;
  --font-mono:  'Geist Mono', 'Courier New', monospace;
  --font-sans:  'DM Sans', system-ui, sans-serif;
}

/* ═══════════════════════════════════════════════
   ANIMATIONS
   ═══════════════════════════════════════════════ */
@keyframes fadeUp {
  from { opacity:0; transform:translateY(18px); }
  to   { opacity:1; transform:translateY(0); }
}
@keyframes blink {
  0%,100% { opacity:1; } 50% { opacity:0; }
}
@keyframes glitchSlide {
  0%,100% { clip-path:inset(0 0 100% 0); transform:translateX(0); }
  20% { clip-path:inset(15% 0 60% 0); transform:translateX(-4px); }
  40% { clip-path:inset(40% 0 30% 0); transform:translateX(4px); }
  60% { clip-path:inset(60% 0 10% 0); transform:translateX(-3px); }
  80% { clip-path:inset(80% 0  0% 0); transform:translateX(2px); }
}
@keyframes glitchSlide2 {
  0%,100% { clip-path:inset(0 0 100% 0); transform:translateX(0); }
  20% { clip-path:inset(20% 0 55% 0); transform:translateX(5px); }
  40% { clip-path:inset(45% 0 25% 0); transform:translateX(-3px); }
  60% { clip-path:inset(65% 0 5%  0); transform:translateX(4px); }
  80% { clip-path:inset(85% 0  0% 0); transform:translateX(-2px); }
}

/* ═══════════════════════════════════════════════
   BASE RESET
   ═══════════════════════════════════════════════ */
body, .markdown-body {
  background: var(--layer-0) !important;
  color: var(--text-primary) !important;
  font-family: var(--font-sans) !important;
}
h1,h2,h3,h4,h5,h6 {
  text-decoration:none !important; border:none !important;
  border-bottom:none !important; box-shadow:none !important;
}
a { text-decoration: none; }

/* ═══════════════════════════════════════════════
   PAGE WRAPPER
   ═══════════════════════════════════════════════ */
.az-page {
  max-width: 860px;
  margin: 0 auto;
  padding: 0 20px 100px;
  background: var(--layer-0);
}

/* ═══════════════════════════════════════════════
   TOP BAR — Ink dark strip
   ═══════════════════════════════════════════════ */
.az-topbar {
  background: var(--ink);
  margin: 0 -20px;
  padding: 11px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  flex-wrap: wrap;
}
.az-topbar-left {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: rgba(242,238,225,0.45);
}
.az-topbar-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--chartreuse);
  box-shadow: 0 0 7px var(--chartreuse);
  animation: blink 2s step-end infinite;
  display: inline-block;
  margin-right: 8px;
  vertical-align: middle;
}
.az-topbar-right {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 1.5px;
  color: var(--chartreuse);
  text-transform: uppercase;
}

/* ═══════════════════════════════════════════════
   HERO
   ═══════════════════════════════════════════════ */
.az-hero {
  padding: 68px 0 56px;
  border-bottom: 1px solid var(--border-light);
  animation: fadeUp 0.7s ease both;
}
.az-hero-eyebrow {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.az-hero-eyebrow::before {
  content: '';
  display: inline-block;
  width: 24px; height: 1px;
  background: var(--text-muted);
}
.az-hero-name {
  font-family: var(--font-serif);
  font-size: 52px;
  font-weight: 300;
  letter-spacing: -3px;
  line-height: 0.92;
  color: var(--ink);
  margin-bottom: 22px;
  position: relative;
  display: inline-block;
}
/* Glitch ghost layer 1 — Vermillion, terracotta */
.az-hero-name::before {
  content: attr(data-text);
  position: absolute; top: 0; left: 0;
  color: var(--vermillion);
  opacity: 0.28;
  pointer-events: none;
  animation: glitchSlide 6s ease-in-out infinite;
}
/* Glitch ghost layer 2 — Oxblood, opposite offset, delayed */
.az-hero-name::after {
  content: attr(data-text);
  position: absolute; top: 0; left: 0;
  color: var(--oxblood);
  opacity: 0.20;
  pointer-events: none;
  animation: glitchSlide2 6s 1.5s ease-in-out infinite;
}
/* Chartreuse underline on "Xue" */
.az-hero-name span {
  position: relative;
  display: inline-block;
}
.az-hero-name span::after {
  content: '';
  position: absolute;
  bottom: 4px; left: 0; right: 0;
  height: 5px;
  background: var(--chartreuse);
  opacity: 0.85;
}
.az-hero-role {
  font-family: var(--font-mono);
  font-size: 11px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: var(--text-tertiary);
  margin-bottom: 22px;
}
.az-hero-desc {
  font-size: 15px;
  line-height: 1.78;
  color: var(--text-secondary);
  max-width: 520px;
  margin-bottom: 36px;
}
.az-hero-desc strong { color: var(--ink); font-weight: 600; }

.az-social-row { display: flex; flex-wrap: wrap; gap: 8px; }
.az-social-btn {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: var(--ink);
  padding: 9px 18px;
  border: 1px solid var(--border-strong);
  background: transparent;
  border-radius: 3px;
  transition: all 0.15s ease;
  display: inline-block;
}
.az-social-btn:hover {
  background: var(--ink);
  color: var(--parchment);
  border-color: var(--ink);
}

/* ═══════════════════════════════════════════════
   STATS — Ink background, Chartreuse numbers
   ═══════════════════════════════════════════════ */
.az-stats {
  background: var(--ink);
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  margin: 40px 0;
  border-radius: 6px;
  overflow: hidden;
  animation: fadeUp 0.7s 0.12s ease both;
}
@media(max-width:580px){ .az-stats{grid-template-columns:repeat(2,1fr);} }

.az-stat {
  padding: 28px 20px;
  text-align: center;
  border-right: 1px solid rgba(242,238,225,0.06);
}
.az-stat:last-child { border-right: none; }
.az-stat-num {
  font-family: var(--font-serif);
  font-size: 38px;
  font-weight: 300;
  color: var(--chartreuse);
  display: block;
  letter-spacing: -1px;
  margin-bottom: 3px;
}
.az-stat-label {
  font-family: var(--font-mono);
  font-size: 14px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: rgba(242,238,225,0.3);
}

/* ═══════════════════════════════════════════════
   SECTION HEADER
   ═══════════════════════════════════════════════ */
.az-section-hd {
  display: flex;
  align-items: baseline;
  gap: 14px;
  margin: 52px 0 20px;
  padding-bottom: 12px;
  border-bottom: 1px solid var(--border-light);
}
.az-section-title {
  font-family: var(--font-serif);
  font-size: 22px;
  font-weight: 300;
  color: var(--ink);
  letter-spacing: -0.5px;
}
.az-section-title em { font-style: italic; color: var(--text-tertiary); }
.az-section-num {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 2px;
  color: var(--text-muted);
  margin-left: auto;
}

/* ═══════════════════════════════════════════════
   LAYERED CONTAINERS
   Layer 0 (page) → Layer 1 (section bg) → Layer 2 (card) → Layer 3 (inner/hover)
   ═══════════════════════════════════════════════ */

/* Layer 1 — section wrapper */
.az-section-bg {
  background: var(--layer-1);
  border-radius: 10px;
  padding: 20px;
  border: 1px solid var(--border-light);
  margin-bottom: 4px;
}

/* Layer 2 — card */
.az-card {
  background: var(--layer-2);
  border: 1px solid var(--border-mid);
  border-radius: 6px;
  padding: 20px 22px;
  transition: border-color 0.15s, background 0.15s;
  position: relative;
  overflow: hidden;
}
.az-card:hover {
  border-color: var(--border-strong);
  background: var(--layer-3);
}

/* ═══════════════════════════════════════════════
   ABOUT
   ═══════════════════════════════════════════════ */
.az-about-grid {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 10px;
}
@media(max-width:620px){ .az-about-grid{grid-template-columns:1fr;} }

.az-about-text {
  font-size: 14px;
  line-height: 1.78;
  color: var(--text-secondary);
}
.az-about-text strong { color: var(--ink); }
.az-about-text p { margin-bottom: 12px; }
.az-about-text p:last-child { margin-bottom: 0; }

.az-chip-label {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 10px;
  display: block;
}
.az-chips { display: flex; flex-wrap: wrap; gap: 6px; }
.az-chip {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 0.8px;
  text-transform: uppercase;
  padding: 5px 10px;
  background: var(--layer-0);
  border: 1px solid var(--border-mid);
  border-radius: 3px;
  color: var(--text-tertiary);
  transition: all 0.14s;
}
.az-chip:hover {
  background: var(--ink);
  color: var(--chartreuse);
  border-color: var(--ink);
}

/* ═══════════════════════════════════════════════
   PUBLICATION CARDS — Layer 2 inside Layer 1
   ═══════════════════════════════════════════════ */
.az-pub-list { display: flex; flex-direction: column; gap: 8px; }

.az-pub {
  background: var(--layer-2);
  border: 1px solid var(--border-mid);
  border-radius: 6px;
  display: flex;
  overflow: hidden;
  transition: border-color 0.15s, background 0.15s;
}
.az-pub:hover {
  border-color: var(--border-strong);
  background: var(--layer-3);
}

.az-pub-stripe { width: 3px; flex-shrink: 0; }
/* Stripe colors using Aztec brand palette */
.s-ch { background: var(--chartreuse); }
.s-aq { background: var(--aqua); }
.s-or { background: var(--orchid); }
.s-vr { background: var(--vermillion); }
.s-in { background: var(--ink); opacity: 0.4; }

.az-pub-body {
  flex: 1; padding: 17px 20px; min-width: 0;
}
.az-pub-title {
  font-size: 13.5px;
  font-weight: 500;
  color: var(--ink);
  line-height: 1.5;
  margin-bottom: 6px;
}
.az-pub-authors {
  font-family: var(--font-mono);
  font-size: 10.5px;
  color: var(--text-muted);
  margin-bottom: 12px;
  line-height: 1.5;
}
.az-pub-authors .me { color: var(--text-primary); font-weight: 700; }
.az-pub-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 8px;
}
.az-pub-tags { display: flex; flex-wrap: wrap; gap: 5px; }
.az-pub-tag {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  padding: 3px 9px;
  background: var(--layer-0);
  border: 1px solid var(--border-light);
  border-radius: 2px;
  color: var(--text-muted);
}

/* Venue badges */
.az-venue {
  font-family: var(--font-mono);
  font-size: 9px;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  padding: 5px 12px;
  border-radius: 3px;
  white-space: nowrap;
  flex-shrink: 0;
}
.v-top  { background: var(--ink); color: var(--chartreuse); }
.v-conf { background: var(--layer-0); color: var(--text-secondary); border: 1px solid var(--border-mid); }
.v-acc  { background: var(--layer-3); color: var(--text-tertiary); border: 1px solid var(--border-mid); }
.v-arxiv{ background: var(--layer-1); color: var(--text-muted); border: 1px dashed var(--border-light); }

.az-pub.coauthor { opacity: 0.6; }
.az-pub.coauthor:hover { opacity: 1; }

/* ═══════════════════════════════════════════════
   HONORS
   ═══════════════════════════════════════════════ */
.az-honor-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
@media(max-width:580px){ .az-honor-grid{grid-template-columns:1fr;} }

.az-honor {
  background: var(--layer-2);
  border: 1px solid var(--border-mid);
  border-radius: 6px;
  padding: 22px;
  transition: all 0.15s;
}
.az-honor:hover { border-color: var(--border-strong); background: var(--layer-3); }
.az-honor-badge {
  display: inline-block;
  font-family: var(--font-mono);
  font-size: 8px;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 5px 11px;
  background: var(--ink);
  color: var(--chartreuse);
  border-radius: 2px;
  margin-bottom: 14px;
}
.az-honor-text {
  font-size: 13px;
  line-height: 1.68;
  color: var(--text-secondary);
}
.az-honor-text strong { color: var(--ink); font-weight: 600; }

/* ═══════════════════════════════════════════════
   PROJECTS
   ═══════════════════════════════════════════════ */
.az-proj-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
@media(max-width:580px){ .az-proj-grid{grid-template-columns:1fr;} }

.az-proj {
  background: var(--layer-2);
  border: 1px solid var(--border-mid);
  border-radius: 6px;
  padding: 24px;
  transition: all 0.15s;
}
.az-proj:hover { border-color: var(--border-strong); background: var(--layer-3); }
.az-proj-icon { font-size: 26px; margin-bottom: 12px; display: block; }
.az-proj-name {
  font-family: var(--font-serif);
  font-size: 18px;
  font-weight: 400;
  color: var(--ink);
  margin-bottom: 3px;
}
.az-proj-type {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 12px;
}
.az-proj-desc {
  font-size: 12.5px;
  color: var(--text-secondary);
  line-height: 1.65;
  margin-bottom: 18px;
}
.az-proj-link {
  font-family: var(--font-mono);
  font-size: 9px;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: var(--ink);
  padding: 6px 14px;
  border: 1px solid var(--border-strong);
  border-radius: 2px;
  display: inline-block;
  transition: all 0.15s;
}
.az-proj-link:hover {
  background: var(--ink);
  color: var(--chartreuse);
}

/* ═══════════════════════════════════════════════
   CONTACT
   ═══════════════════════════════════════════════ */
.az-contact-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
@media(max-width:540px){ .az-contact-grid{grid-template-columns:1fr;} }

.az-contact-card {
  background: var(--layer-2);
  border: 1px solid var(--border-mid);
  border-radius: 6px;
  padding: 20px;
  text-align: center;
  transition: all 0.15s;
}
.az-contact-card:hover { border-color: var(--border-strong); background: var(--layer-3); }
.az-contact-icon { font-size: 22px; display: block; margin-bottom: 8px; }
.az-contact-val {
  font-family: var(--font-mono);
  font-size: 10px;
  color: var(--text-secondary);
  word-break: break-all;
}

/* ═══════════════════════════════════════════════
   FOOTER — Ink dark
   ═══════════════════════════════════════════════ */
.az-footer {
  background: var(--ink);
  margin: 60px -20px 0;
  padding: 26px 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px;
}
.az-footer-l {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 0.8px;
  color: rgba(242,238,225,0.35);
}
.az-footer-r {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--chartreuse);
  opacity: 0.75;
}

/* Scroll reveal */
.rv { animation: fadeUp 0.55s ease both; }
.d1 { animation-delay: 0.08s; }
.d2 { animation-delay: 0.16s; }
</style>

<!-- ══════════════════════════════════════════════
     PAGE MARKUP
     ══════════════════════════════════════════════ -->

<div class="az-page">

<!-- TOP BAR -->
<div class="az-topbar">
  <div class="az-topbar-left"><span class="az-topbar-dot"></span>NODE ACTIVE · CASIA · BEIJING</div>
  <div class="az-topbar-right">Multimodal AI</div>
</div>

<!-- ════ HERO ════ -->
<div class="az-hero">
  <div class="az-hero-eyebrow">PhD Candidate · Institute of Automation · Chinese Academy of Sciences</div>
  <h1 class="az-hero-name" data-text="Dizhan Xue">Dizhan <span>Xue</span></h1>
  <p class="az-hero-role">State Key Laboratory of Multimodal Artificial Intelligence Systems</p>
  <p class="az-hero-desc">
    Researcher at <strong>CASIA</strong>, advised by Prof. Changsheng Xu.<br>
    Building toward <strong>AGI through multimodal reasoning</strong> — with a current focus on <strong>LLM Agents</strong> and their capacity for open-world intelligence.
  </p>
  <div class="az-social-row">
    <a href="mailto:xuedizhan17@mails.ucas.ac.cn" class="az-social-btn">Email</a>
    <a href="https://scholar.google.com/citations?user=V5Aeh_oAAAAJ" class="az-social-btn">Scholar</a>
    <a href="https://dblp.org/pid/293/9621" class="az-social-btn">DBLP</a>
    <a href="https://github.com/LivXue" class="az-social-btn">GitHub</a>
  </div>
</div>

<!-- ════ STATS (Ink bg, Chartreuse numbers) ════ -->
<div class="az-stats rv">
  <div class="az-stat"><span class="az-stat-num">20+</span><span class="az-stat-label">Publications</span></div>
  <div class="az-stat"><span class="az-stat-num">9</span><span class="az-stat-label">First-author Papers</span></div>
  <div class="az-stat"><span class="az-stat-num">4</span><span class="az-stat-label">Top Conferences</span></div>
  <div class="az-stat"><span class="az-stat-num">5</span><span class="az-stat-label">Top Journals</span></div>
</div>

<!-- ════ ABOUT ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">About</div>
  <div class="az-section-num">01 / 05</div>
</div>

<!-- Layer 1 section bg → Layer 2 cards inside -->
<div class="az-section-bg rv d1">
  <div style="display: grid; grid-template-columns: 1fr; gap: 10px;">
    <div class="az-card">
      <div class="az-about-text">
        <p>I'm a PhD candidate at <strong>State Key Laboratory of Multimodal Artificial Intelligence Systems</strong>, Institute of Automation, Chinese Academy of Sciences (CASIA), advised by <strong>Prof. Changsheng Xu</strong>.</p>
        <p>My core research focuses on enabling AI to understand and reason across complex multimodal information. I believe that <strong>multimodal intelligence is the essential pathway to AGI</strong>. Recently, I've been particularly interested in <strong>LLM Agents</strong> and their capabilities in sophisticated reasoning tasks.</p>
      </div>
    </div>
    <div class="az-card">
      <span class="az-chip-label">Research Interests</span>
      <div class="az-chips">
        <span class="az-chip">Multimodal Reasoning</span>
        <span class="az-chip">LLM Agents</span>
        <span class="az-chip">Explainable AI</span>
        <span class="az-chip">Vision-Language Models</span>
        <span class="az-chip">Social Media Analysis</span>
      </div>
    </div>
  </div>
</div>

<!-- ════ EDUCATION ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">Education</div>
  <div class="az-section-num">01.5 / 05</div>
</div>

<div class="az-section-bg rv d1">
  <div style="display: grid; grid-template-columns: 1fr; gap: 10px;">
    <!-- PhD -->
    <div class="az-card">
      <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 12px;">
        <span style="font-size: 24px;">🔬</span>
        <div style="flex: 1;">
          <div style="font-family: var(--font-serif); font-size: 15px; font-weight: 500; color: var(--ink); margin-bottom: 4px;">PhD in Pattern Recognition and Intelligent Systems</div>
          <div style="font-size: 12px; color: var(--text-tertiary);">Institute of Automation, Chinese Academy of Sciences (CASIA)</div>
        </div>
      </div>
      <div style="font-size: 11px; color: var(--text-secondary); line-height: 1.8;">
        <strong>📅</strong> Sep 2021 - Jun 2026<br>
        <strong>👨‍🏫</strong> Advisor: <span style="color: var(--text-primary);">Prof. Changsheng Xu</span><br>
        <strong>📝</strong> Thesis: <span style="color: var(--text-primary);">Reliable Multimodal Reasoning in Complicated Scenarios</span>
      </div>
    </div>

    <!-- Bachelor -->
    <div class="az-card">
      <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 12px;">
        <span style="font-size: 24px;">🎓</span>
        <div style="flex: 1;">
          <div style="font-family: var(--font-serif); font-size: 15px; font-weight: 500; color: var(--ink); margin-bottom: 4px;">Bachelor of Computer Science and Technology</div>
          <div style="font-size: 12px; color: var(--text-tertiary);">University of Chinese Academy of Sciences (UCAS) (\#3 in China by national avg. admission score)</div>
        </div>
      </div>
      <div style="font-size: 11px; color: var(--text-secondary); line-height: 1.8;">
        <strong>📅</strong> Sep 2017 - Jun 2021<br>
        <strong>👨‍🏫</strong> Advisor: <span style="color: var(--text-primary);">Prof. Changsheng Xu</span><br>
        <strong>📝</strong> Thesis: <span style="color: var(--text-primary);">Debiased Short Video Recommendation Based on Counterfactual Reasoning</span>
      </div>
    </div>
  </div>
</div>

<!-- ════ FIRST-AUTHOR PUBLICATIONS ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">First-<em>author</em> Publications</div>
  <div class="az-section-num">02 / 05</div>
</div>

<!-- Layer 1 → Layer 2 pub cards inside -->
<div class="az-section-bg rv">
  <div class="az-pub-list">

    <div class="az-pub">
      <div class="az-pub-stripe s-ch"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Integrating Neural-Symbolic Reasoning With Variational Causal Inference Network for Explanatory Visual Question Answering</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">VQA</span><span class="az-pub-tag">Causal Inference</span><span class="az-pub-tag">Neural-Symbolic</span><span class="az-pub-tag">Explainable AI</span></div>
          <span class="az-venue v-top">IEEE TPAMI 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-aq"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Variational Causal Inference Network for Explanatory Visual Question Answering</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">VQA</span><span class="az-pub-tag">Causal Inference</span><span class="az-pub-tag">Explainable AI</span></div>
          <span class="az-venue v-top">ICCV 2023</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-or"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">SoMe: A Realistic Benchmark for LLM-based Social Media Agents</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Jing Cui, Shengsheng Qian, Chuanrui Hu, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">LLM Agents</span><span class="az-pub-tag">Social Media</span><span class="az-pub-tag">Benchmark</span></div>
          <span class="az-venue v-top">AAAI 2026</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-vr"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Few-Shot Multimodal Explanation for Visual Question Answering</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">VQA</span><span class="az-pub-tag">Few-Shot</span><span class="az-pub-tag">Explainable AI</span><span class="az-pub-tag">LLM Agents</span></div>
          <span class="az-venue v-conf">ACM MM 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-ch"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">MMT: Image-guided Story Ending Generation with Multimodal Memory Transformer</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Cross-Modal Generation</span><span class="az-pub-tag">Vision-Language</span><span class="az-pub-tag">Memory</span></div>
          <span class="az-venue v-conf">ACM MM 2022</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-aq"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">LININ: Logic Integrated Neural Inference Network for Explanatory Visual Question Answering</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">VQA</span><span class="az-pub-tag">Neural-Symbolic</span><span class="az-pub-tag">Explainable AI</span></div>
          <span class="az-venue v-conf">IEEE TMM 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-in"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Vision-Controllable Language Model for Image-guided Story Ending Generation</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Controllable Generation</span><span class="az-pub-tag">Vision-Language</span></div>
          <span class="az-venue v-acc">IEEE TMM (accepted)</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-ch"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Short-video Propagation Influence Rating: A New Real-world Dataset and A New Large Graph Model</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Chuanrui Hu, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Short Video</span><span class="az-pub-tag">Large Graph Model</span><span class="az-pub-tag">Dataset</span></div>
          <span class="az-venue v-acc">IEEE TKDE (accepted)</span>
        </div>
      </div>
    </div>

    <div class="az-pub">
      <div class="az-pub-stripe s-or"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">A Unified Framework for Backdoor Trigger Segmentation</div>
        <div class="az-pub-authors"><span class="me">Dizhan Xue</span>, Shengsheng Qian, Xueshan Deng, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Backdoor Attack</span><span class="az-pub-tag">AI Security</span></div>
          <span class="az-venue v-acc">IEEE TIP 2026</span>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- ════ CO-AUTHOR PAPERS ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">Co-<em>authored</em> Papers</div>
  <div class="az-section-num">03 / 05</div>
</div>

<div class="az-section-bg rv">
  <div class="az-pub-list">

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-in"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Integrating Multi-Label Contrastive Learning with Dual Adversarial Graph Neural Networks for Cross-Modal Retrieval</div>
        <div class="az-pub-authors">Shengsheng Qian, <span class="me">Dizhan Xue</span>, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Cross-Modal Retrieval</span><span class="az-pub-tag">Contrastive Learning</span><span class="az-pub-tag">Graph Neural Networks</span></div>
          <span class="az-venue v-top">IEEE TPAMI 2022</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-ch"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval</div>
        <div class="az-pub-authors">Zhenyu Yang, <span class="me">Dizhan Xue</span>, Shengsheng Qian, Weiming Dong, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Composed Retrieval</span><span class="az-pub-tag">Zero-Shot</span><span class="az-pub-tag">LLM</span></div>
          <span class="az-venue v-top">ACM SIGIR 2024 🏆</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-aq"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">BadAgent: Inserting and Activating Backdoor Attacks in LLM Agents</div>
        <div class="az-pub-authors">Yifei Wang, <span class="me">Dizhan Xue</span>, Shengjie Zhang, Shengsheng Qian</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Backdoor Attack</span><span class="az-pub-tag">LLM Agents</span><span class="az-pub-tag">AI Security</span></div>
          <span class="az-venue v-top">ACL 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-vr"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Dual Adversarial Graph Neural Networks for Multi-Label Cross-Modal Retrieval</div>
        <div class="az-pub-authors">Shengsheng Qian, <span class="me">Dizhan Xue</span>, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Cross-Modal Retrieval</span><span class="az-pub-tag">Adversarial Learning</span><span class="az-pub-tag">Graph Neural Networks</span></div>
          <span class="az-venue v-top">AAAI 2021</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-or"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Nonparametric Clustering-Guided Cross-View Contrastive Learning for Partially View-Aligned Representation Learning</div>
        <div class="az-pub-authors">Shengsheng Qian, <span class="me">Dizhan Xue</span>, Jun Hu, Huaiwen Zhang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Contrastive Learning</span><span class="az-pub-tag">Partially Aligned</span><span class="az-pub-tag">Clustering</span></div>
          <span class="az-venue v-top">IEEE TIP 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-in"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Adaptive Label-Aware Graph Convolutional Networks for Cross-Modal Retrieval</div>
        <div class="az-pub-authors">Shengsheng Qian, <span class="me">Dizhan Xue</span>, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Cross-Modal Retrieval</span><span class="az-pub-tag">Graph Convolutional Networks</span><span class="az-pub-tag">Label-Aware</span></div>
          <span class="az-venue v-top">IEEE TMM 2021</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-ch"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Open-World Social Event Classification</div>
        <div class="az-pub-authors">Shengsheng Qian, Hong Chen, <span class="me">Dizhan Xue</span>, Quan Fang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Social Event</span><span class="az-pub-tag">Open-World</span><span class="az-pub-tag">Classification</span></div>
          <span class="az-venue v-top">WWW 2023</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-aq"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Semantic Editing Increment Benefits Zero-Shot Composed Image Retrieval</div>
        <div class="az-pub-authors">Zhenyu Yang, Shengsheng Qian, <span class="me">Dizhan Xue</span>, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Composed Retrieval</span><span class="az-pub-tag">Zero-Shot</span><span class="az-pub-tag">Semantic Editing</span></div>
          <span class="az-venue v-top">ACM MM 2024</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-vr"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">Learning Temporal Event Knowledge for Continual Social Event Classification</div>
        <div class="az-pub-authors">Shengsheng Qian, Shengjie Zhang, <span class="me">Dizhan Xue</span>, Huaiwen Zhang, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Temporal Knowledge</span><span class="az-pub-tag">Continual Learning</span><span class="az-pub-tag">Social Event</span></div>
          <span class="az-venue v-top">IEEE TKDE 2025</span>
        </div>
      </div>
    </div>

    <div class="az-pub coauthor">
      <div class="az-pub-stripe s-or"></div>
      <div class="az-pub-body">
        <div class="az-pub-title">SVBench: A Benchmark with Temporal Multi-Turn Dialogues for Streaming Video Understanding</div>
        <div class="az-pub-authors">Zhenyu Yang, Yuhang Hu, Zemin Du, <span class="me">Dizhan Xue</span>, Shengsheng Qian, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu</div>
        <div class="az-pub-footer">
          <div class="az-pub-tags"><span class="az-pub-tag">Streaming Video</span><span class="az-pub-tag">Multi-Turn Dialogue</span><span class="az-pub-tag">Benchmark</span></div>
          <span class="az-venue v-top">ICLR 2025</span>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- ════ HONORS ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">Select<em>ed</em> Honors</div>
  <div class="az-section-num">04 / 05</div>
</div>

<div class="az-section-bg rv">
  <div class="az-honor-grid">
    <div class="az-honor">
      <span class="az-honor-badge">Best Paper Honorable Mention</span>
      <div class="az-honor-text"><strong>ACM SIGIR 2024</strong> — LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval. Co-authored with Zhenyu Yang et al.</div>
    </div>
    <div class="az-honor">
      <span class="az-honor-badge" style="background:var(--ink); color:var(--aqua);">First-Class Scholarship</span>
      <div class="az-honor-text"><strong>UCAS 2018</strong> — First-Class Academic Scholarship of the University of Chinese Academy of Sciences. Awarded to the top 5% of students.</div>
    </div>
  </div>
</div>

<!-- ════ PROJECTS ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">Open <em>Source</em></div>
  <div class="az-section-num">05 / 05</div>
</div>

<div class="az-section-bg rv">
  <div class="az-proj-grid">
    <div class="az-proj">
      <span class="az-proj-icon">📧</span>
      <div class="az-proj-name">MailMind</div>
      <div class="az-proj-type">Email Agent</div>
      <div class="az-proj-desc">LLM-powered multi-step email assistant for intelligent email management.</div>
      <a href="https://github.com/LivXue/open-email-agent" class="az-proj-link">View on GitHub →</a>
    </div>
    <div class="az-proj">
      <span class="az-proj-icon">🔗</span>
      <div class="az-proj-name">GNN4CMR</div>
      <div class="az-proj-type">Cross-modal Retrieval</div>
      <div class="az-proj-desc">Graph Neural Network and Toolkits for Cross-modal Retrieval tasks.</div>
      <a href="https://github.com/LivXue/GNN4CMR" class="az-proj-link">View on GitHub →</a>
    </div>
  </div>
</div>

<!-- ════ CONTACT ════ -->
<div class="az-section-hd rv">
  <div class="az-section-title">Con<em>tact</em></div>
</div>

<div class="az-section-bg rv">
  <div class="az-contact-grid">
    <div class="az-contact-card">
      <span class="az-contact-icon">📧</span>
      <div class="az-contact-val">xuedizhan17@mails.ucas.ac.cn</div>
    </div>
    <div class="az-contact-card">
      <span class="az-contact-icon">🌐</span>
      <div class="az-contact-val">dblp.org/pid/293/9621</div>
    </div>
    <div class="az-contact-card">
      <span class="az-contact-icon">💻</span>
      <div class="az-contact-val">github.com/LivXue</div>
    </div>
  </div>
</div>

<!-- ════ FOOTER (Ink dark) ════ -->
<div class="az-footer">
  <div class="az-footer-l">© 2025 Dizhan Xue · State Key Laboratory of Multimodal Artificial Intelligence Systems</div>
  <div class="az-footer-r">Built with passion for multimodal AI & intelligent systems</div>
</div>

</div>