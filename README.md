<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>imad_ahnich — GitHub README</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@300;400;600;700&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050508;
    --bg2: #0a0a10;
    --bg3: #0d0d16;
    --surface: #0f0f1a;
    --surface2: #141420;
    --lain-blue: #4169e1;
    --lain-purple: #6a0dad;
    --lain-cyan: #00e5ff;
    --lain-pink: #ff006e;
    --lain-glow: #7b2fff;
    --wire: #1a1a30;
    --text: #c8d8f0;
    --text-dim: #6070a0;
    --text-muted: #3a4060;
    --accent: #00e5ff;
    --accent2: #7b2fff;
    --green: #00ff88;
    --amber: #ffaa00;
    --red: #ff3355;
    --mono: 'Share Tech Mono', monospace;
    --head: 'Rajdhani', sans-serif;
    --display: 'Orbitron', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Scanline overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }

  /* Circuit board bg */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(65,105,225,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(65,105,225,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 20px 60px;
    position: relative;
    z-index: 1;
  }

  /* ========== BANNER ========== */
  .banner {
    width: 100%;
    height: 280px;
    position: relative;
    overflow: hidden;
    margin-bottom: -1px;
    border-bottom: 1px solid rgba(0,229,255,0.15);
  }

  .banner-bg {
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at 30% 60%, rgba(106,13,173,0.5) 0%, transparent 55%),
                radial-gradient(ellipse at 70% 40%, rgba(65,105,225,0.4) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 100%, rgba(0,229,255,0.15) 0%, transparent 40%),
                #050510;
  }

  /* Lain face - SVG-drawn eyes that "watch" */
  .lain-face {
    position: absolute;
    right: 80px;
    bottom: 0;
    width: 220px;
    height: 260px;
    opacity: 0.85;
  }

  .banner-code {
    position: absolute;
    inset: 0;
    font-size: 9px;
    color: rgba(65,105,225,0.18);
    line-height: 1.4;
    padding: 10px;
    overflow: hidden;
    white-space: pre;
    pointer-events: none;
    font-family: var(--mono);
  }

  /* Circuit lines on banner */
  .circuit-svg {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
  }

  .banner-content {
    position: absolute;
    bottom: 30px;
    left: 40px;
  }

  .banner-name {
    font-family: var(--display);
    font-size: 52px;
    font-weight: 900;
    color: #fff;
    text-shadow: 0 0 30px rgba(0,229,255,0.6), 0 0 60px rgba(123,47,255,0.4);
    letter-spacing: 2px;
    animation: flicker 8s infinite;
  }

  .banner-sub {
    font-family: var(--head);
    font-size: 14px;
    color: var(--accent);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-top: 4px;
    opacity: 0.9;
  }

  @keyframes flicker {
    0%,100%{opacity:1} 92%{opacity:1} 93%{opacity:0.6} 94%{opacity:1} 97%{opacity:1} 98%{opacity:0.7} 99%{opacity:1}
  }

  /* Status bar */
  .status-bar {
    background: rgba(0,0,0,0.8);
    border-bottom: 1px solid rgba(0,229,255,0.2);
    padding: 8px 40px;
    display: flex;
    gap: 30px;
    font-size: 11px;
    color: var(--text-dim);
    font-family: var(--mono);
    position: relative;
    z-index: 1;
  }
  .status-item { display: flex; align-items: center; gap: 6px; }
  .status-dot { width: 6px; height: 6px; border-radius: 50%; }
  .status-dot.online { background: var(--green); box-shadow: 0 0 6px var(--green); animation: pulse 2s infinite; }
  .status-dot.building { background: var(--amber); box-shadow: 0 0 6px var(--amber); animation: pulse 1.2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }

  /* ========== SECTIONS ========== */
  section {
    margin-top: 50px;
  }

  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 6px;
    opacity: 0.7;
  }

  .section-title {
    font-family: var(--head);
    font-size: 28px;
    font-weight: 700;
    color: #fff;
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,229,255,0.4), transparent);
  }

  /* ========== TERMINAL WHOAMI ========== */
  .terminal {
    background: rgba(5,5,15,0.95);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 4px;
    overflow: hidden;
    box-shadow: 0 0 40px rgba(0,0,0,0.8), inset 0 0 60px rgba(65,105,225,0.03);
    position: relative;
  }

  .terminal::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 4px;
    box-shadow: 0 0 1px rgba(0,229,255,0.3) inset;
    pointer-events: none;
  }

  .terminal-bar {
    background: rgba(15,15,28,0.95);
    border-bottom: 1px solid rgba(0,229,255,0.12);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    color: var(--text-dim);
  }
  .t-dot { width: 10px; height: 10px; border-radius: 50%; }
  .t-dot.r { background: #ff5f57; }
  .t-dot.y { background: #febc2e; }
  .t-dot.g { background: #28c840; }
  .t-path { margin-left: 10px; color: var(--text-muted); font-size: 11px; }

  .terminal-body {
    padding: 24px 28px 28px;
    font-size: 13px;
    line-height: 2;
  }

  .t-prompt { color: var(--accent); }
  .t-cmd { color: #fff; }
  .t-comment { color: var(--text-muted); }
  .t-key { color: var(--lain-cyan); padding-left: 20px; }
  .t-val { color: #a8d8ff; }
  .t-str { color: var(--green); }
  .t-num { color: var(--amber); }
  .t-bracket { color: var(--text-dim); }
  .t-fn { color: var(--accent2); }
  .t-quote { color: var(--amber); opacity: 0.8; font-style: italic; }
  .t-indent1 { padding-left: 20px; }
  .t-indent2 { padding-left: 40px; }
  .t-indent3 { padding-left: 60px; }

  .cursor {
    display: inline-block;
    width: 8px;
    height: 14px;
    background: var(--accent);
    vertical-align: middle;
    animation: blink 1.1s step-end infinite;
    margin-left: 2px;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ========== SKILLS ========== */
  .skills-grid {
    display: flex;
    flex-direction: column;
    gap: 18px;
  }

  .skill-row {
    display: flex;
    align-items: flex-start;
    gap: 16px;
  }

  .skill-label {
    font-size: 11px;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    min-width: 130px;
    padding-top: 4px;
    font-family: var(--mono);
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .skill-tag {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 4px 12px;
    border-radius: 3px;
    font-size: 12px;
    font-family: var(--head);
    font-weight: 600;
    letter-spacing: 0.5px;
    border: 1px solid transparent;
    transition: all 0.2s;
    cursor: default;
    white-space: nowrap;
  }

  .skill-tag:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 15px rgba(0,0,0,0.4);
  }

  .skill-icon { width: 14px; height: 14px; border-radius: 2px; flex-shrink: 0; }

  /* Language/library colors matching real logos */
  .tag-python  { background: rgba(55,118,171,0.2); border-color: rgba(55,118,171,0.5); color: #4da6ff; }
  .tag-python  .skill-icon { background: linear-gradient(135deg, #3776ab, #ffd343); }
  .tag-r       { background: rgba(39,109,195,0.2); border-color: rgba(39,109,195,0.4); color: #7ab3f0; }
  .tag-r       .skill-icon { background: #276dc3; }
  .tag-c       { background: rgba(0,89,156,0.2);   border-color: rgba(0,89,156,0.4);   color: #6aabf7; }
  .tag-cpp     { background: rgba(0,89,156,0.2);   border-color: rgba(0,89,156,0.4);   color: #6aabf7; }
  .tag-js      { background: rgba(247,223,30,0.12); border-color: rgba(247,223,30,0.3);color: #f7df1e; }
  .tag-js      .skill-icon { background: #f7df1e; }
  .tag-numpy   { background: rgba(77,171,207,0.15); border-color: rgba(77,171,207,0.35);color: #4dabcf; }
  .tag-pandas  { background: rgba(22,75,115,0.25); border-color: rgba(22,75,115,0.5); color: #5a9fd4; }
  .tag-sklearn { background: rgba(242,107,52,0.15); border-color: rgba(242,107,52,0.35);color: #f26734; }
  .tag-tf      { background: rgba(255,111,0,0.15);  border-color: rgba(255,111,0,0.35); color: #ff6f00; }
  .tag-tf      .skill-icon { background: #ff6f00; }
  .tag-torch   { background: rgba(238,76,44,0.15);  border-color: rgba(238,76,44,0.35); color: #ee4c2c; }
  .tag-keras   { background: rgba(210,35,52,0.15);  border-color: rgba(210,35,52,0.35); color: #d22334; }
  .tag-hf      { background: rgba(255,204,0,0.1);   border-color: rgba(255,204,0,0.3);  color: #ffcc00; }
  .tag-spark   { background: rgba(228,68,6,0.15);   border-color: rgba(228,68,6,0.35);  color: #e44406; }
  .tag-postgres { background: rgba(51,103,145,0.2); border-color: rgba(51,103,145,0.4); color: #336791; color: #5ba8d4; }
  .tag-mongo   { background: rgba(71,162,72,0.15);  border-color: rgba(71,162,72,0.35); color: #47a248; }
  .tag-mysql   { background: rgba(0,116,170,0.15);  border-color: rgba(0,116,170,0.35); color: #00749b; color: #4aafd4; }
  .tag-redis   { background: rgba(220,38,38,0.15);  border-color: rgba(220,38,38,0.35); color: #dc2626; color: #f07070; }
  .tag-powerbi { background: rgba(243,164,42,0.12); border-color: rgba(243,164,42,0.3); color: #f3a42a; }
  .tag-flask   { background: rgba(255,255,255,0.05);border-color: rgba(255,255,255,0.15);color: #ccc; }
  .tag-fastapi { background: rgba(0,150,136,0.15);  border-color: rgba(0,150,136,0.35); color: #009688; }
  .tag-react   { background: rgba(97,218,251,0.1);  border-color: rgba(97,218,251,0.3); color: #61dafb; }
  .tag-django  { background: rgba(9,77,54,0.25);    border-color: rgba(9,77,54,0.5);    color: #44b78b; }
  .tag-linux   { background: rgba(255,204,0,0.1);   border-color: rgba(255,204,0,0.25); color: #ffcc00; }
  .tag-git     { background: rgba(240,80,51,0.15);  border-color: rgba(240,80,51,0.35); color: #f05033; }
  .tag-docker  { background: rgba(35,155,214,0.15); border-color: rgba(35,155,214,0.35);color: #23abf0; }
  .tag-vscode  { background: rgba(0,122,204,0.15);  border-color: rgba(0,122,204,0.35); color: #007acc; }
  .tag-colab   { background: rgba(246,130,3,0.15);  border-color: rgba(246,130,3,0.35); color: #f68203; }

  .skill-divider {
    width: 1px;
    background: rgba(0,229,255,0.1);
    align-self: stretch;
    min-height: 30px;
    margin: 0 4px;
  }

  /* ========== PROJECTS ========== */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }

  @media (max-width: 650px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--surface);
    border: 1px solid rgba(0,229,255,0.12);
    border-radius: 4px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
    cursor: default;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--card-accent, var(--accent)), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: rgba(0,229,255,0.3);
    transform: translateY(-2px);
  }

  .project-card:hover::before { opacity: 1; }

  .project-icon {
    font-size: 28px;
    margin-bottom: 12px;
    display: block;
    filter: drop-shadow(0 0 8px var(--card-accent, var(--accent)));
  }

  .project-name {
    font-family: var(--head);
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
    letter-spacing: 0.5px;
  }

  .project-desc {
    font-size: 11.5px;
    color: var(--text-dim);
    line-height: 1.7;
    margin-bottom: 14px;
  }

  .project-tree {
    font-size: 11px;
    color: var(--text-muted);
    line-height: 1.8;
    border-left: 1px solid rgba(0,229,255,0.1);
    padding-left: 12px;
    margin-bottom: 14px;
  }

  .project-tree .leaf { color: var(--text-dim); }
  .project-tree .val  { color: var(--accent); }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .p-tag {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 2px;
    font-family: var(--head);
    font-weight: 600;
    letter-spacing: 0.5px;
    border: 1px solid currentColor;
    opacity: 0.7;
  }

  /* WIP badge */
  .wip-badge {
    position: absolute;
    top: 12px;
    right: 12px;
    font-size: 9px;
    padding: 2px 7px;
    border-radius: 2px;
    background: rgba(255,170,0,0.15);
    border: 1px solid rgba(255,170,0,0.4);
    color: var(--amber);
    letter-spacing: 1px;
    font-family: var(--head);
    font-weight: 700;
  }

  /* ========== STATS ========== */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
    margin-bottom: 24px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid rgba(65,105,225,0.15);
    border-radius: 4px;
    padding: 18px 22px;
  }

  .stat-card-title {
    font-size: 10px;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .stat-card-title::before {
    content: '';
    width: 20px;
    height: 1px;
    background: var(--accent);
  }

  .lang-bar {
    display: flex;
    height: 5px;
    border-radius: 3px;
    overflow: hidden;
    margin-bottom: 12px;
    gap: 1px;
  }

  .lang-seg { height: 100%; transition: width 0.5s; }
  .lang-seg.py  { background: #3776ab; }
  .lang-seg.js  { background: #f7df1e; }
  .lang-seg.nb  { background: #f37626; }
  .lang-seg.sh  { background: #4eaa25; }
  .lang-seg.ot  { background: #555; }

  .lang-legend {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .lang-item {
    display: flex;
    align-items: center;
    gap: 5px;
    font-size: 11px;
    color: var(--text-dim);
  }

  .lang-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }

  /* Contribution graph */
  .contrib-graph {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    grid-template-rows: repeat(7, 1fr);
    gap: 2px;
    direction: ltr;
  }

  .contrib-cell {
    width: 100%;
    aspect-ratio: 1;
    border-radius: 1px;
    background: var(--surface2);
    transition: transform 0.1s;
  }

  .contrib-cell:hover { transform: scale(1.3); }
  .contrib-cell.l1 { background: rgba(0,229,255,0.2); }
  .contrib-cell.l2 { background: rgba(0,229,255,0.45); }
  .contrib-cell.l3 { background: rgba(0,229,255,0.7); }
  .contrib-cell.l4 { background: rgba(0,229,255,0.95); box-shadow: 0 0 4px rgba(0,229,255,0.5); }

  .stats-meta {
    font-size: 11px;
    color: var(--text-muted);
    margin-top: 10px;
    display: flex;
    gap: 20px;
  }

  .stats-meta span { color: var(--text-dim); }

  /* Quote */
  .quote-block {
    border-left: 2px solid rgba(0,229,255,0.3);
    padding: 16px 24px;
    margin-top: 40px;
    color: var(--text-dim);
    font-style: italic;
    font-size: 13px;
    position: relative;
  }

  .quote-block::before {
    content: '"';
    font-family: var(--display);
    font-size: 48px;
    color: rgba(0,229,255,0.15);
    position: absolute;
    top: -10px;
    left: 10px;
    line-height: 1;
  }

  .quote-author {
    font-style: normal;
    font-size: 11px;
    color: var(--text-muted);
    margin-top: 6px;
    letter-spacing: 1px;
  }

  /* Connect */
  .connect-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .connect-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 18px;
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 3px;
    font-family: var(--head);
    font-size: 13px;
    font-weight: 600;
    color: var(--text-dim);
    text-decoration: none;
    letter-spacing: 0.5px;
    transition: all 0.25s;
    background: rgba(0,229,255,0.03);
  }

  .connect-btn:hover {
    border-color: rgba(0,229,255,0.5);
    color: var(--accent);
    background: rgba(0,229,255,0.06);
    box-shadow: 0 0 20px rgba(0,229,255,0.1);
    transform: translateY(-1px);
  }

  .connect-icon { font-size: 16px; }

  /* Open to work */
  .open-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    background: rgba(0,255,136,0.07);
    border: 1px solid rgba(0,255,136,0.3);
    border-radius: 3px;
    font-size: 12px;
    color: var(--green);
    margin-top: 20px;
    font-family: var(--head);
    font-weight: 600;
    letter-spacing: 0.5px;
  }

  .open-badge::before {
    content: '';
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 8px var(--green);
    animation: pulse 1.5s infinite;
  }

  /* Footer */
  .footer {
    margin-top: 60px;
    padding-top: 20px;
    border-top: 1px solid rgba(65,105,225,0.1);
    font-size: 10px;
    color: var(--text-muted);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  /* ── Lain Portrait (pure CSS/SVG) ── */
  .lain-portrait {
    position: absolute;
    right: 40px;
    bottom: 0;
    width: 200px;
    height: 255px;
    opacity: 0.88;
  }
</style>
</head>
<body>

<!-- BANNER -->
<div class="banner">
  <!-- Lain image as full background -->
  <img src="data:image/jpeg;base64,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" alt="banner" style="position:absolute;inset:0;width:100%;height:100%;object-fit:cover;object-position:center top;opacity:0.92;"/>
  <!-- Purple overlay to blend with theme -->
  <div style="position:absolute;inset:0;background:linear-gradient(90deg,rgba(5,0,20,0.55) 0%,rgba(60,0,120,0.25) 40%,rgba(5,0,20,0.5) 100%),linear-gradient(0deg,rgba(5,0,15,0.7) 0%,transparent 60%);"></div>
  <!-- Code rain background -->
  <div class="banner-code" id="codeRain"></div>


  <div class="banner-content">
    <div class="banner-name">imad_ahnich</div>
    <div class="banner-sub">Data Science · Machine Learning · AI — in training</div>
  </div>
</div>

<!-- STATUS BAR -->
<div class="status-bar">
  <div class="status-item"><div class="status-dot online"></div> IDS Student @ EST Fkih Ben Salah</div>
  <div class="status-item"><div class="status-dot building"></div> Building: spam-detection-system</div>
  <div class="status-item" style="margin-left:auto; color: rgba(0,229,255,0.5);">Morocco · he/him</div>
</div>

<div class="container">

  <!-- ========== WHOAMI ========== -->
  <section>
    <div class="section-label">> whoami</div>
    <div class="section-title">About</div>
    <div class="terminal">
      <div class="terminal-bar">
        <div class="t-dot r"></div>
        <div class="t-dot y"></div>
        <div class="t-dot g"></div>
        <span class="t-path">~/imad_ahnich/README.md — bash</span>
      </div>
      <div class="terminal-body">
<div><span class="t-prompt">$ </span><span class="t-cmd">cat profile.json</span></div>
<br>
<div class="t-bracket">{</div>
<div><span class="t-key">"name"</span><span class="t-bracket">:</span> <span class="t-str">"Imad Ahnich"</span><span class="t-bracket">,</span></div>
<div><span class="t-key">"role"</span><span class="t-bracket">:</span> <span class="t-str">"IDS Student @ EST Fkih Ben Salah"</span><span class="t-bracket">,</span></div>
<div><span class="t-key">"layer"</span><span class="t-bracket">:</span> <span class="t-str">"Data · Intelligence · Systems"</span><span class="t-bracket">,</span></div>
<div><span class="t-key">"location"</span><span class="t-bracket">:</span> <span class="t-str">"Morocco / Wired"</span><span class="t-bracket">,</span></div>
<div><span class="t-key">"status"</span><span class="t-bracket">:</span> <span class="t-str">"[ ■ online ]"</span><span class="t-bracket">,</span></div>
<br>
<div><span class="t-key">"interests"</span><span class="t-bracket">: [</span></div>
<div class="t-indent2"><span class="t-str">"Machine Learning"</span><span class="t-bracket">,</span></div>
<div class="t-indent2"><span class="t-str">"Big Data"</span><span class="t-bracket">,</span></div>
<div class="t-indent2"><span class="t-str">"AI Systems"</span></div>
<div class="t-indent1"><span class="t-bracket">],</span></div>
<br>
<div><span class="t-key">"currently"</span><span class="t-bracket">: {</span></div>
<div class="t-indent2"><span class="t-key">"building"</span><span class="t-bracket">:</span> <span class="t-str">"Spam Detection System (Naïve Bayes + SVM + CNN+LSTM)"</span><span class="t-bracket">,</span></div>
<div class="t-indent2"><span class="t-key">"learning"</span><span class="t-bracket">: [</span><span class="t-str">"Transformers"</span><span class="t-bracket">,</span> <span class="t-str">"FastAPI deployment"</span><span class="t-bracket">],</span></div>
<div class="t-indent2"><span class="t-key">"seeking"</span><span class="t-bracket">:</span> <span class="t-str">"PFE Internship — Data Science / AI / ML"</span></div>
<div class="t-indent1"><span class="t-bracket">},</span></div>
<br>
<div><span class="t-key">"quote"</span><span class="t-bracket">:</span> <span class="t-quote">"Present Day. Present Time — Let's build."</span></div>
<div class="t-bracket">}</div>
<br>
<div><span class="t-prompt">$ </span><span class="cursor"></span></div>
      </div>
    </div>
  </section>

  <!-- ========== SKILLS ========== -->
  <section>
    <div class="section-label">> skills --list</div>
    <div class="section-title">Skills</div>
    <div class="skills-grid">
      <div class="skill-row">
        <div class="skill-label">Languages</div>
        <div class="skill-tags">
          <span class="skill-tag tag-python"><span class="skill-icon" style="background:linear-gradient(135deg,#3776ab,#ffd343)"></span>Python</span>
          <span class="skill-tag tag-r"><span class="skill-icon" style="background:#276dc3;display:flex;align-items:center;justify-content:center;font-size:9px;font-weight:900;color:#fff;">R</span>R</span>
          <span class="skill-tag tag-c">C</span>
          <span class="skill-tag tag-cpp">C++</span>
          <span class="skill-tag tag-js"><span class="skill-icon" style="background:#f7df1e;display:flex;align-items:center;justify-content:center;font-size:8px;font-weight:900;color:#000;">JS</span>JavaScript</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-label">ML / DL</div>
        <div class="skill-tags">
          <span class="skill-tag tag-sklearn">Scikit-learn</span>
          <span class="skill-tag tag-tf"><span class="skill-icon" style="background:#ff6f00"></span>TensorFlow</span>
          <span class="skill-tag tag-torch">PyTorch</span>
          <span class="skill-tag tag-keras">Keras</span>
          <span class="skill-tag tag-hf">🤗 HuggingFace</span>
          <span class="skill-tag tag-numpy">NumPy</span>
          <span class="skill-tag tag-pandas">Pandas</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-label">Models known</div>
        <div style="font-size:11px; color:var(--text-muted); padding-top:4px; line-height:2; font-family:var(--mono);">
          <span style="color:var(--text-dim)">Classical ML ·</span> LR · NB · SVM · KNN · RF · XGBoost<br>
          <span style="color:var(--text-dim)">Deep Learning ·</span> ANN · CNN · LSTM · Transformers<br>
          <span style="color:var(--text-dim)">NLP ·</span> TF-IDF · Tokenization · Text Classification
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-label">Big Data & DB</div>
        <div class="skill-tags">
          <span class="skill-tag tag-spark">Apache Spark</span>
          <span class="skill-tag tag-postgres">PostgreSQL</span>
          <span class="skill-tag tag-mongo">MongoDB</span>
          <span class="skill-tag tag-mysql">MySQL</span>
          <span class="skill-tag tag-powerbi">Power BI</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-label">Web & Deploy</div>
        <div class="skill-tags">
          <span class="skill-tag tag-flask">Flask</span>
          <span class="skill-tag tag-fastapi">FastAPI</span>
          <span class="skill-tag tag-react">React</span>
          <span class="skill-tag tag-django">Django</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-label">System & Tools</div>
        <div class="skill-tags">
          <span class="skill-tag tag-linux">Linux (Nobara)</span>
          <span class="skill-tag tag-git">Git</span>
          <span class="skill-tag tag-docker">Docker</span>
          <span class="skill-tag tag-vscode">VS Code</span>
          <span class="skill-tag tag-colab">Colab</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ========== PROJECTS ========== -->
  <section>
    <div class="section-label">> ls projects/</div>
    <div class="section-title">Projects</div>
    <div class="projects-grid">

      <!-- Spam Detection -->
      <div class="project-card" style="--card-accent: #00ff88;">
        <span class="project-icon">📡</span>
        <div class="project-name">[spam-detection-system]</div>
        <div class="project-desc">
          Comparaison ML & Deep Learning pour détecter le spam SMS/Email. Multiple models, multiple metrics.
        </div>
        <div class="project-tree">
          <div>├── <span class="leaf">models/</span> <span class="val">NB · SVM · RF · LR · CNN+LSTM</span></div>
          <div>├── <span class="leaf">nlp/</span> <span class="val">TF-IDF vectorization</span></div>
          <div>├── <span class="leaf">eval/</span> <span class="val">Accuracy · Precision · Recall · F1</span></div>
          <div>└── <span class="leaf">api/</span> <span class="val">FastAPI deployment</span></div>
        </div>
        <div class="project-tags">
          <span class="p-tag" style="color:#3776ab;">Python</span>
          <span class="p-tag" style="color:#f26734;">Sklearn</span>
          <span class="p-tag" style="color:#ee4c2c;">PyTorch</span>
          <span class="p-tag" style="color:#009688;">FastAPI</span>
        </div>
      </div>

      <!-- AI vs Human Text -->
      <div class="project-card" style="--card-accent: #7b2fff;">
        <span class="project-icon">🧠</span>
        <div class="project-name">[ai-vs-human-txt]</div>
        <div class="project-desc">
          Détecteur de texte généré par IA vs humain. Classification binaire avec features linguistiques + deep NLP.
        </div>
        <div class="project-tree">
          <div>├── <span class="leaf">features/</span> <span class="val">perplexity · burstiness · entropy</span></div>
          <div>├── <span class="leaf">models/</span> <span class="val">SVM · BERT fine-tune</span></div>
          <div>├── <span class="leaf">data/</span> <span class="val">custom dataset mixing</span></div>
          <div>└── <span class="leaf">ui/</span> <span class="val">Flask interface</span></div>
        </div>
        <div class="project-tags">
          <span class="p-tag" style="color:#3776ab;">Python</span>
          <span class="p-tag" style="color:#ffcc00;">HuggingFace</span>
          <span class="p-tag" style="color:#ffffff;">Flask</span>
        </div>
        <div class="wip-badge">WIP</div>
      </div>

      <!-- Clothes Store Chatbot -->
      <div class="project-card" style="--card-accent: #ff006e;">
        <span class="project-icon">👗</span>
        <div class="project-name">[style-advisor-bot]</div>
        <div class="project-desc">
          E-commerce clothes store + AI chatbot qui t'aide à choisir ton style selon tes préférences, météo & budget.
        </div>
        <div class="project-tree">
          <div>├── <span class="leaf">store/</span> <span class="val">Django e-commerce backend</span></div>
          <div>├── <span class="leaf">bot/</span> <span class="val">NLP intent classification</span></div>
          <div>├── <span class="leaf">rec/</span> <span class="val">collaborative filtering</span></div>
          <div>└── <span class="leaf">ui/</span> <span class="val">React frontend</span></div>
        </div>
        <div class="project-tags">
          <span class="p-tag" style="color:#44b78b;">Django</span>
          <span class="p-tag" style="color:#61dafb;">React</span>
          <span class="p-tag" style="color:#3776ab;">Python</span>
          <span class="p-tag" style="color:#009688;">FastAPI</span>
        </div>
        <div class="wip-badge">WIP</div>
      </div>

      <!-- LSTM Stock -->
      <div class="project-card" style="--card-accent: #ffaa00;">
        <span class="project-icon">📈</span>
        <div class="project-name">[lstm-stock-prediction]</div>
        <div class="project-desc">
          Prédiction de cours boursier avec LSTM bi-couche. EarlyStopping, MinMaxScaler, MSE/RMSE evaluation.
        </div>
        <div class="project-tree">
          <div>├── <span class="leaf">preprocessing/</span> <span class="val">MinMaxScaler · séquences</span></div>
          <div>├── <span class="leaf">model/</span> <span class="val">LSTM 2 couches · EarlyStopping</span></div>
          <div>└── <span class="leaf">eval/</span> <span class="val">MSE · RMSE · charts</span></div>
        </div>
        <div class="project-tags">
          <span class="p-tag" style="color:#3776ab;">Python</span>
          <span class="p-tag" style="color:#ff6f00;">TensorFlow</span>
          <span class="p-tag" style="color:#4dabcf;">NumPy</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ========== STATS ========== -->
  <section>
    <div class="section-label">> stats</div>
    <div class="section-title">Statistics</div>
    <div class="stats-grid">
      <!-- Language stats -->
      <div class="stat-card">
        <div class="stat-card-title">Top Languages</div>
        <div class="lang-bar">
          <div class="lang-seg py" style="width:55%"></div>
          <div class="lang-seg js" style="width:18%"></div>
          <div class="lang-seg nb" style="width:15%"></div>
          <div class="lang-seg sh" style="width:7%"></div>
          <div class="lang-seg ot" style="width:5%"></div>
        </div>
        <div class="lang-legend">
          <div class="lang-item"><div class="lang-dot" style="background:#3776ab"></div>Python 55%</div>
          <div class="lang-item"><div class="lang-dot" style="background:#f7df1e"></div>JS 18%</div>
          <div class="lang-item"><div class="lang-dot" style="background:#f37626"></div>Jupyter 15%</div>
          <div class="lang-item"><div class="lang-dot" style="background:#4eaa25"></div>Shell 7%</div>
          <div class="lang-item"><div class="lang-dot" style="background:#555"></div>Other 5%</div>
        </div>
      </div>
      <!-- Contribution graph -->
      <div class="stat-card" style="grid-column: span 1;">
        <div class="stat-card-title">Contribution Activity</div>
        <div class="contrib-graph" id="contribGraph"></div>
        <div class="stats-meta">
          <div>Total commits: <span id="totalCommits">47</span></div>
          <div>This year: <span id="yearCommits">2025–2026</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ========== CONNECT ========== -->
  <section>
    <div class="section-label">> connect</div>
    <div class="section-title">Connect</div>
    <div class="connect-row">
      <a href="https://github.com/imad-ah" class="connect-btn" target="_blank">
        <span class="connect-icon">⌥</span> GitHub
      </a>
      <a href="https://linkedin.com/in/imad-ahnich" class="connect-btn" target="_blank">
        <span class="connect-icon">◈</span> LinkedIn
      </a>
      <a href="mailto:imadahnich320@gmail.com" class="connect-btn">
        <span class="connect-icon">◉</span> Gmail
      </a>
    </div>
    <div class="open-badge">
      Open to internship opportunities in Data Science & AI — Morocco
    </div>
  </section>

  <!-- Quote -->
  <div class="quote-block">
    Present Day. Present Time — Let's build.
    <div class="quote-author">— Lain Iwakura</div>
  </div>

  <!-- Footer -->
  <div class="footer">
    <span>imad_ahnich · EST Fkih Ben Salah · IDS 2024–2025</span>
    <span style="color:rgba(0,229,255,0.3)">[ wired ]</span>
  </div>

</div>

<script>
// ─── CODE RAIN ───────────────────────────────────────────
const codeLines = [
  'import numpy as np','import pandas as pd','from sklearn.svm import SVC',
  'from tensorflow.keras.models import Sequential','from sklearn.naive_bayes import MultinomialNB',
  'model.fit(X_train, y_train)','accuracy = model.score(X_test, y_test)',
  'X = TfidfVectorizer().fit_transform(corpus)','lstm = LSTM(128, return_sequences=True)',
  'optimizer = Adam(lr=0.001)','loss: categorical_crossentropy','epochs=50, batch_size=32',
  'f1_score(y_true, y_pred, average="weighted")','confusion_matrix(y_test, y_pred)',
  'app = FastAPI()','@app.post("/predict")','class SpamRequest(BaseModel):',
  'return {"label": prediction, "confidence": prob}','from transformers import BertTokenizer',
  'model.compile(loss="binary_crossentropy")','EarlyStopping(patience=5)',
  'train_test_split(X, y, test_size=0.2)','MinMaxScaler().fit_transform(data)',
];
const rainEl = document.getElementById('codeRain');
let rainContent = '';
for(let i=0;i<18;i++) rainContent += codeLines[Math.floor(Math.random()*codeLines.length)] + '\n';
rainEl.textContent = rainContent;

// ─── CONTRIBUTION GRAPH ──────────────────────────────────
const graph = document.getElementById('contribGraph');
const levels = ['','l1','l2','l3','l4'];
let cells = [];
for(let w=0;w<52;w++){
  for(let d=0;d<7;d++){
    const cell = document.createElement('div');
    const r = Math.random();
    let cls = '';
    if(r > 0.65) cls = levels[Math.floor(Math.random()*4)+1];
    // Recent weeks more active
    if(w > 46) {
      const r2 = Math.random();
      cls = r2 > 0.3 ? levels[Math.floor(Math.random()*3)+2] : levels[1];
    }
    cell.className = 'contrib-cell ' + cls;
    cell.title = `${cls ? cls.replace('l','') + ' contributions' : '0 contributions'}`;
    graph.appendChild(cell);
    cells.push(cell);
  }
}

</script>

</body>
</html>
