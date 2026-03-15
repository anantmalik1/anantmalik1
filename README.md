<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>GitHub README Preview – Anant Raj Malik</title>
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700;800;900&display=swap');

    :root {
      --neon-blue: #00d4ff;
      --neon-purple: #b14fff;
      --neon-green: #00ff9d;
      --neon-pink: #ff006a;
      --dark-bg: #0a0a0f;
      --card-bg: rgba(255,255,255,0.04);
      --border: rgba(0,212,255,0.18);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--dark-bg);
      font-family: 'Inter', sans-serif;
      color: #e2e8f0;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ─── STAR FIELD ─── */
    #stars-canvas {
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
    }

    /* ─── SCROLLBAR ─── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #0a0a0f; }
    ::-webkit-scrollbar-thumb { background: linear-gradient(var(--neon-blue), var(--neon-purple)); border-radius: 3px; }

    /* ─── LAYOUT ─── */
    .page-wrapper {
      position: relative; z-index: 1;
      max-width: 900px; margin: 0 auto;
      padding: 20px 16px 60px;
    }

    /* ─── GLASS CARD ─── */
    .glass {
      background: rgba(10,10,20,0.72);
      backdrop-filter: blur(18px) saturate(160%);
      -webkit-backdrop-filter: blur(18px) saturate(160%);
      border: 1px solid var(--border);
      border-radius: 20px;
    }

    /* ─── GLOW UTILITIES ─── */
    .glow-blue  { text-shadow: 0 0 18px #00d4ff, 0 0 40px #00d4ff88; }
    .glow-purple{ text-shadow: 0 0 18px #b14fff, 0 0 40px #b14fff88; }
    .glow-green { text-shadow: 0 0 18px #00ff9d, 0 0 40px #00ff9d88; }
    .glow-pink  { text-shadow: 0 0 18px #ff006a, 0 0 40px #ff006a88; }

    .border-glow-blue   { box-shadow: 0 0 0 1px #00d4ff44, 0 0 24px #00d4ff22; }
    .border-glow-purple { box-shadow: 0 0 0 1px #b14fff44, 0 0 24px #b14fff22; }
    .border-glow-green  { box-shadow: 0 0 0 1px #00ff9d44, 0 0 24px #00ff9d22; }

    /* ─── ANIMATED GRADIENT TEXT ─── */
    .grad-text {
      background: linear-gradient(90deg, #00d4ff, #b14fff, #ff006a, #00ff9d, #00d4ff);
      background-size: 300% auto;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: grad-shift 4s linear infinite;
    }

    @keyframes grad-shift {
      0%   { background-position: 0% center; }
      100% { background-position: 300% center; }
    }

    /* ─── TYPING CURSOR ─── */
    .typing-cursor::after {
      content: '|';
      color: var(--neon-blue);
      animation: blink 0.75s step-end infinite;
      margin-left: 2px;
    }
    @keyframes blink { 50% { opacity: 0; } }

    /* ─── ANIMATED SEPARATOR ─── */
    .sep {
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--neon-blue), var(--neon-purple), var(--neon-pink), transparent);
      border-radius: 2px;
      margin: 28px 0;
      animation: sep-pulse 3s ease-in-out infinite;
    }
    @keyframes sep-pulse {
      0%,100% { opacity: 0.5; transform: scaleX(0.95); }
      50%      { opacity: 1;   transform: scaleX(1); }
    }

    /* ─── SECTION LABEL ─── */
    .section-label {
      display: inline-flex; align-items: center; gap: 10px;
      font-size: 0.7rem; font-weight: 700; letter-spacing: 0.2em;
      text-transform: uppercase; color: var(--neon-blue);
      background: rgba(0,212,255,0.08);
      border: 1px solid rgba(0,212,255,0.25);
      border-radius: 100px; padding: 4px 14px;
    }
    .section-title {
      font-size: clamp(1.4rem, 3vw, 2rem);
      font-weight: 800; line-height: 1.2;
      margin: 8px 0 4px;
    }

    /* ─── HERO BANNER ─── */
    #hero {
      position: relative; overflow: hidden;
      border-radius: 24px; padding: 48px 40px 40px;
      background: linear-gradient(135deg,#0d0d1a 0%,#0f0a1e 40%,#0a1020 100%);
      border: 1px solid rgba(0,212,255,0.22);
      box-shadow: 0 0 60px rgba(0,212,255,0.08), 0 0 120px rgba(177,79,255,0.06);
      margin-bottom: 24px;
    }
    #hero::before {
      content:''; position:absolute; inset:0;
      background: radial-gradient(ellipse 70% 60% at 80% 30%, rgba(0,212,255,0.12) 0%, transparent 65%),
                  radial-gradient(ellipse 50% 50% at 20% 80%, rgba(177,79,255,0.1) 0%, transparent 65%);
      pointer-events:none;
    }
    .hero-grid-lines {
      position:absolute; inset:0; pointer-events:none; overflow:hidden; border-radius:24px;
      background-image:
        linear-gradient(rgba(0,212,255,0.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,255,0.05) 1px, transparent 1px);
      background-size: 44px 44px;
      animation: grid-move 20s linear infinite;
    }
    @keyframes grid-move {
      0%   { background-position: 0 0; }
      100% { background-position: 44px 44px; }
    }

    .hero-avatar {
      width: 100px; height: 100px; border-radius: 50%;
      background: linear-gradient(135deg, #00d4ff33, #b14fff33);
      border: 2px solid rgba(0,212,255,0.5);
      box-shadow: 0 0 30px rgba(0,212,255,0.3), 0 0 60px rgba(177,79,255,0.2);
      display: flex; align-items: center; justify-content: center;
      font-size: 2.8rem; flex-shrink: 0;
      animation: avatar-float 4s ease-in-out infinite;
      position: relative;
    }
    @keyframes avatar-float {
      0%,100% { transform: translateY(0); }
      50%      { transform: translateY(-8px); }
    }
    .avatar-ring {
      position: absolute; inset: -6px; border-radius: 50%;
      border: 1.5px solid transparent;
      background: linear-gradient(#0d0d1a, #0d0d1a) padding-box,
                  linear-gradient(90deg, #00d4ff, #b14fff, #00ff9d) border-box;
      animation: ring-spin 4s linear infinite;
    }
    @keyframes ring-spin { to { transform: rotate(360deg); } }

    .status-dot {
      width: 10px; height: 10px; border-radius: 50%;
      background: var(--neon-green);
      box-shadow: 0 0 8px var(--neon-green);
      animation: pulse-dot 2s ease-in-out infinite;
    }
    @keyframes pulse-dot {
      0%,100% { transform:scale(1); opacity:1; }
      50%      { transform:scale(1.4); opacity:0.6; }
    }

    /* ─── SKILL ICON CHIP ─── */
    .skill-chip {
      display: inline-flex; align-items: center; gap: 6px;
      background: rgba(0,212,255,0.06);
      border: 1px solid rgba(0,212,255,0.18);
      border-radius: 8px; padding: 5px 10px;
      font-size: 0.72rem; font-weight: 500;
      transition: all 0.25s;
      white-space: nowrap;
      cursor: default;
    }
    .skill-chip:hover {
      background: rgba(0,212,255,0.14);
      border-color: rgba(0,212,255,0.45);
      transform: translateY(-2px);
      box-shadow: 0 4px 16px rgba(0,212,255,0.15);
    }
    .skill-chip .icon { font-size: 1rem; }

    /* ─── STAT CARD ─── */
    .stat-card {
      background: rgba(10,10,20,0.72);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 20px;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .stat-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 12px 40px rgba(0,212,255,0.15);
    }
    .stat-number {
      font-size: 2rem; font-weight: 800;
      background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    /* ─── PROJECT CARD ─── */
    .project-card {
      background: rgba(10,10,22,0.8);
      border-radius: 18px;
      border: 1px solid rgba(177,79,255,0.2);
      padding: 26px;
      position: relative; overflow: hidden;
      transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
    }
    .project-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
      border-radius: 18px 18px 0 0;
    }
    .project-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 16px 50px rgba(177,79,255,0.2);
      border-color: rgba(177,79,255,0.45);
    }
    .project-tag {
      display: inline-block;
      background: rgba(0,212,255,0.1);
      border: 1px solid rgba(0,212,255,0.25);
      border-radius: 100px; padding: 2px 10px;
      font-size: 0.66rem; font-weight: 600;
      color: var(--neon-blue); letter-spacing: 0.05em;
    }
    .project-tag.purple {
      background: rgba(177,79,255,0.1);
      border-color: rgba(177,79,255,0.25);
      color: #c77dff;
    }
    .project-tag.green {
      background: rgba(0,255,157,0.1);
      border-color: rgba(0,255,157,0.25);
      color: var(--neon-green);
    }

    /* ─── GITHUB WIDGET CARD ─── */
    .widget-card {
      border-radius: 16px;
      overflow: hidden;
      border: 1px solid var(--border);
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .widget-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 12px 40px rgba(0,212,255,0.12);
    }
    .widget-card img {
      width: 100%; display: block;
      border-radius: 15px;
    }

    /* ─── SNAKE SECTION ─── */
    #snake-section {
      position: relative; overflow: hidden;
      border-radius: 20px; padding: 30px;
      background: linear-gradient(135deg, rgba(0,212,255,0.05), rgba(177,79,255,0.05));
      border: 1px solid rgba(0,255,157,0.2);
    }

    /* ─── SNAKE CANVAS ─── */
    #snake-canvas {
      display: block; margin: 0 auto;
      border-radius: 12px;
      background: rgba(0,0,0,0.4);
      border: 1px solid rgba(0,255,157,0.2);
    }

    /* ─── QUOTE CARD ─── */
    .quote-card {
      background: linear-gradient(135deg, rgba(0,212,255,0.05), rgba(177,79,255,0.05));
      border: 1px solid rgba(177,79,255,0.25);
      border-radius: 16px; padding: 24px 30px;
      position: relative;
    }
    .quote-card::before {
      content: '"';
      position: absolute; top: -10px; left: 20px;
      font-size: 5rem; color: rgba(0,212,255,0.2);
      line-height: 1; font-family: serif;
    }

    /* ─── FOCUS ITEM ─── */
    .focus-item {
      display: flex; align-items: flex-start; gap: 14px;
      padding: 14px 16px;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(0,212,255,0.1);
      border-radius: 12px;
      transition: all 0.25s;
    }
    .focus-item:hover {
      background: rgba(0,212,255,0.06);
      border-color: rgba(0,212,255,0.25);
      transform: translateX(4px);
    }
    .focus-dot {
      width: 8px; height: 8px; border-radius: 50%;
      flex-shrink: 0; margin-top: 5px;
    }

    /* ─── ACHIEVEMENT BADGE ─── */
    .achieve-badge {
      display: flex; align-items: center; gap: 14px;
      padding: 14px 18px;
      background: rgba(10,10,22,0.7);
      border: 1px solid rgba(255,165,0,0.2);
      border-radius: 14px;
      transition: all 0.25s;
    }
    .achieve-badge:hover {
      border-color: rgba(255,165,0,0.45);
      background: rgba(255,165,0,0.06);
      transform: translateX(4px);
    }
    .achieve-icon {
      width: 42px; height: 42px; border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem; flex-shrink: 0;
    }

    /* ─── CONTACT CHIP ─── */
    .contact-chip {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 10px 18px;
      background: rgba(10,10,22,0.8);
      border: 1px solid var(--border);
      border-radius: 12px;
      font-size: 0.82rem; font-weight: 500;
      text-decoration: none; color: #c8d6e5;
      transition: all 0.25s;
      cursor: pointer;
    }
    .contact-chip:hover {
      background: rgba(0,212,255,0.1);
      border-color: var(--neon-blue);
      color: var(--neon-blue);
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(0,212,255,0.15);
    }

    /* ─── ACTIVITY GRAPH (fake) ─── */
    .contrib-cell {
      width: 11px; height: 11px; border-radius: 2px;
      flex-shrink: 0;
      transition: transform 0.2s;
    }
    .contrib-cell:hover { transform: scale(1.3); }

    /* ─── PROGRESS BAR ─── */
    .progress-bar-wrap {
      background: rgba(255,255,255,0.05);
      border-radius: 100px; overflow: hidden; height: 6px;
    }
    .progress-bar-fill {
      height: 100%; border-radius: 100px;
      animation: bar-load 1.5s ease-out forwards;
      transform-origin: left;
    }
    @keyframes bar-load {
      from { width: 0%; }
    }

    /* ─── FLOATING PARTICLES ─── */
    .particle {
      position: absolute; border-radius: 50%; pointer-events: none;
      animation: particle-drift linear infinite;
    }
    @keyframes particle-drift {
      0%   { transform: translateY(0) rotate(0deg); opacity: 0; }
      10%  { opacity: 1; }
      90%  { opacity: 1; }
      100% { transform: translateY(-300px) rotate(720deg); opacity: 0; }
    }

    /* ─── CODE RAIN ─── */
    #matrix-canvas {
      position: fixed; inset: 0; z-index: 0;
      opacity: 0.04; pointer-events: none;
    }

    /* ─── COPY BUTTON ─── */
    #copy-btn {
      position: fixed; bottom: 24px; right: 24px; z-index: 100;
      background: linear-gradient(135deg, #00d4ff, #b14fff);
      color: #fff; border: none; border-radius: 50px;
      padding: 12px 24px; font-size: 0.85rem; font-weight: 700;
      cursor: pointer; letter-spacing: 0.05em;
      box-shadow: 0 8px 30px rgba(0,212,255,0.35);
      transition: transform 0.2s, box-shadow 0.2s;
      display: flex; align-items: center; gap: 8px;
    }
    #copy-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 40px rgba(0,212,255,0.5);
    }
    #copy-btn:active { transform: scale(0.97); }

    /* ─── README MODAL ─── */
    #readme-modal {
      display: none; position: fixed; inset: 0; z-index: 200;
      background: rgba(0,0,0,0.88); backdrop-filter: blur(10px);
      align-items: center; justify-content: center;
    }
    #readme-modal.open { display: flex; }
    .modal-box {
      background: #0d0d1a; border: 1px solid var(--border);
      border-radius: 20px; padding: 30px;
      max-width: 820px; width: 95%; max-height: 85vh;
      display: flex; flex-direction: column; gap: 16px;
    }
    .modal-box pre {
      font-family: 'Fira Code', monospace;
      font-size: 0.72rem; line-height: 1.6;
      color: #a8d8ea; overflow: auto; flex: 1;
      background: rgba(0,0,0,0.4); border-radius: 10px;
      padding: 16px; max-height: 60vh;
      white-space: pre-wrap; word-break: break-all;
    }
    .modal-actions { display: flex; gap: 10px; justify-content: flex-end; }
    .btn-copy-md, .btn-close {
      padding: 8px 20px; border-radius: 8px; border: none;
      font-size: 0.82rem; font-weight: 700; cursor: pointer;
    }
    .btn-copy-md {
      background: linear-gradient(135deg, #00d4ff, #b14fff);
      color: #fff;
    }
    .btn-close {
      background: rgba(255,255,255,0.07);
      color: #cbd5e1; border: 1px solid rgba(255,255,255,0.1);
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 600px) {
      #hero { padding: 32px 20px 28px; }
      .hero-avatar { width: 76px; height: 76px; font-size: 2rem; }
    }
  </style>
</head>
<body>

<!-- Matrix rain -->
<canvas id="matrix-canvas"></canvas>
<!-- Stars -->
<canvas id="stars-canvas"></canvas>

<div class="page-wrapper">

  <!-- ════════════════════════ HERO ════════════════════════ -->
  <section id="hero">
    <div class="hero-grid-lines"></div>

    <!-- Top Row -->
    <div style="display:flex;align-items:flex-start;justify-content:space-between;flex-wrap:wrap;gap:20px;position:relative;z-index:1;">
      <!-- Avatar + Name -->
      <div style="display:flex;align-items:center;gap:22px;flex-wrap:wrap;">
        <div class="hero-avatar">
          🤖
          <div class="avatar-ring"></div>
        </div>
        <div>
          <div style="display:flex;align-items:center;gap:10px;margin-bottom:6px;">
            <div class="status-dot"></div>
            <span style="font-size:0.7rem;color:var(--neon-green);font-weight:600;letter-spacing:0.12em;">AVAILABLE FOR OPPORTUNITIES</span>
          </div>
          <h1 style="font-size:clamp(1.6rem,4vw,2.4rem);font-weight:900;line-height:1.1;" class="grad-text">Anant Raj Malik</h1>
          <div id="typing-title" style="font-family:'Fira Code',monospace;font-size:0.9rem;color:#94a3b8;margin-top:6px;" class="typing-cursor"></div>
        </div>
      </div>
      <!-- Badge stack -->
      <div style="display:flex;flex-direction:column;gap:8px;align-items:flex-end;">
        <span style="background:rgba(0,212,255,0.1);border:1px solid rgba(0,212,255,0.3);border-radius:8px;padding:4px 12px;font-size:0.7rem;font-weight:700;color:var(--neon-blue);letter-spacing:0.1em;">⚡ AI / ML</span>
        <span style="background:rgba(177,79,255,0.1);border:1px solid rgba(177,79,255,0.3);border-radius:8px;padding:4px 12px;font-size:0.7rem;font-weight:700;color:#c77dff;letter-spacing:0.1em;">🐍 PYTHON</span>
        <span style="background:rgba(0,255,157,0.1);border:1px solid rgba(0,255,157,0.3);border-radius:8px;padding:4px 12px;font-size:0.7rem;font-weight:700;color:var(--neon-green);letter-spacing:0.1em;">🎓 B.TECH CSE</span>
      </div>
    </div>

    <!-- About paragraph -->
    <p style="margin-top:24px;line-height:1.75;color:#94a3b8;font-size:0.9rem;max-width:640px;position:relative;z-index:1;border-left:3px solid var(--neon-blue);padding-left:14px;">
      Passionate AI developer focused on building <span style="color:var(--neon-blue);font-weight:600;">intelligent systems</span>, 
      <span style="color:#c77dff;font-weight:600;">machine learning models</span>, and 
      <span style="color:var(--neon-green);font-weight:600;">automation tools</span>. 
      Currently pursuing B.Tech CSE at Quantum University — turning data into decisions and ideas into intelligent products.
    </p>

    <!-- Quick-stat row -->
    <div style="display:flex;gap:28px;flex-wrap:wrap;margin-top:26px;position:relative;z-index:1;">
      <div style="text-align:center;">
        <div style="font-size:1.4rem;font-weight:800;color:var(--neon-blue);">2+</div>
        <div style="font-size:0.68rem;color:#64748b;text-transform:uppercase;letter-spacing:0.08em;">AI Projects</div>
      </div>
      <div style="width:1px;background:rgba(255,255,255,0.08);"></div>
      <div style="text-align:center;">
        <div style="font-size:1.4rem;font-weight:800;color:#c77dff;">16+</div>
        <div style="font-size:0.68rem;color:#64748b;text-transform:uppercase;letter-spacing:0.08em;">Technologies</div>
      </div>
      <div style="width:1px;background:rgba(255,255,255,0.08);"></div>
      <div style="text-align:center;">
        <div style="font-size:1.4rem;font-weight:800;color:var(--neon-green);">100%</div>
        <div style="font-size:0.68rem;color:#64748b;text-transform:uppercase;letter-spacing:0.08em;">Dedication</div>
      </div>
      <div style="width:1px;background:rgba(255,255,255,0.08);"></div>
      <div style="text-align:center;">
        <div style="font-size:1.4rem;font-weight:800;color:#ff006a;">∞</div>
        <div style="font-size:0.68rem;color:#64748b;text-transform:uppercase;letter-spacing:0.08em;">Curiosity</div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ ANIMATED HEADER (typing svg widget) ════════════════════════ -->
  <div style="text-align:center;margin-bottom:24px;">
    <div style="background:rgba(10,10,22,0.8);border:1px solid var(--border);border-radius:14px;padding:14px 20px;display:inline-block;">
      <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=22&pause=900&color=00D4FF&center=true&vCenter=true&multiline=false&width=600&lines=🤖+AI+%2F+ML+Engineer;🐍+Python+Developer;🧠+Building+Intelligent+Systems;📊+Data+Science+%26+Analytics;🚀+Quantum+University+%7C+CSE" alt="Typing SVG" style="border-radius:8px;max-width:100%;" />
    </div>
  </div>

  <div class="sep"></div>

  <!-- ════════════════════════ TECH STACK ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">⚙️ Tech Arsenal</span>
      <h2 class="section-title glow-blue">Skills & Technologies</h2>
      <p style="color:#64748b;font-size:0.82rem;">Tools and technologies I work with every day</p>
    </div>

    <!-- Skill icons via skillicons.dev -->
    <div class="glass" style="padding:24px;margin-bottom:18px;text-align:center;" >
      <p style="font-size:0.7rem;color:#64748b;text-transform:uppercase;letter-spacing:0.15em;margin-bottom:16px;">Core Stack</p>
      <img src="https://skillicons.dev/icons?i=python,tensorflow,sklearn,pytorch,pandas&theme=dark&perline=8" alt="Core Stack" style="max-width:100%;border-radius:8px;" />
    </div>

    <div class="glass" style="padding:24px;margin-bottom:18px;text-align:center;">
      <p style="font-size:0.7rem;color:#64748b;text-transform:uppercase;letter-spacing:0.15em;margin-bottom:16px;">Data & Visualization</p>
      <img src="https://skillicons.dev/icons?i=mysql,mongodb,js,git,github,jupyter,vscode,linux&theme=dark&perline=8" alt="Data Stack" style="max-width:100%;border-radius:8px;" />
    </div>

    <!-- Skill chips -->
    <div style="display:flex;flex-wrap:wrap;gap:8px;margin-top:16px;">
      <span class="skill-chip"><span class="icon">🐍</span> Python</span>
      <span class="skill-chip"><span class="icon">🧠</span> Machine Learning</span>
      <span class="skill-chip"><span class="icon">📊</span> Data Analysis</span>
      <span class="skill-chip"><span class="icon">🔬</span> Scikit-Learn</span>
      <span class="skill-chip"><span class="icon">🐼</span> Pandas</span>
      <span class="skill-chip"><span class="icon">🔢</span> NumPy</span>
      <span class="skill-chip"><span class="icon">🗄️</span> SQL</span>
      <span class="skill-chip"><span class="icon">⚡</span> JavaScript</span>
      <span class="skill-chip"><span class="icon">📈</span> Matplotlib</span>
      <span class="skill-chip"><span class="icon">🌊</span> Seaborn</span>
      <span class="skill-chip"><span class="icon">📉</span> Plotly</span>
      <span class="skill-chip"><span class="icon">🐬</span> MySQL</span>
      <span class="skill-chip"><span class="icon">🍃</span> MongoDB</span>
      <span class="skill-chip"><span class="icon">🌿</span> Git</span>
      <span class="skill-chip"><span class="icon">🐙</span> GitHub</span>
      <span class="skill-chip"><span class="icon">📓</span> Jupyter</span>
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ GITHUB STATS ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">📊 GitHub Analytics</span>
      <h2 class="section-title glow-purple">GitHub Stats</h2>
    </div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px;">
      <div class="widget-card">
        <img src="https://github-readme-stats.vercel.app/api?username=anantmalik1&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&icon_color=b14fff&text_color=94a3b8&border_radius=15&count_private=true" alt="GitHub Stats" />
      </div>
      <div class="widget-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=anantmalik1&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&text_color=94a3b8&border_radius=15&langs_count=8" alt="Top Languages" />
      </div>
    </div>

    <!-- Streak stats -->
    <div class="widget-card" style="margin-bottom:16px;">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=anantmalik1&theme=tokyonight&hide_border=true&background=0d0d1a&stroke=00d4ff&ring=b14fff&fire=ff006a&currStreakLabel=00d4ff&border_radius=15" alt="GitHub Streak" style="width:100%;border-radius:15px;display:block;" />
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ CONTRIBUTION GRAPH ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">📈 Activity</span>
      <h2 class="section-title glow-blue">Contribution Graph</h2>
    </div>
    <div class="widget-card">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=anantmalik1&bg_color=0d0d1a&color=00d4ff&line=b14fff&point=00ff9d&area=true&area_color=00d4ff&hide_border=true&border_radius=15&custom_title=Anant's%20Contribution%20Graph" alt="Contribution Graph" style="width:100%;border-radius:15px;display:block;" />
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ SNAKE ANIMATION ════════════════════════ -->
  <section id="snake-section" style="margin-bottom:28px;">
    <div style="margin-bottom:18px;position:relative;z-index:1;">
      <span class="section-label">🐍 Snake Game</span>
      <h2 class="section-title" style="color:#00ff9d;">Contribution Snake</h2>
      <p style="color:#64748b;font-size:0.82rem;">Watch the snake eat through my GitHub contributions!</p>
    </div>

    <!-- Live animated snake visual -->
    <canvas id="snake-canvas" width="820" height="120" style="max-width:100%;"></canvas>

    <!-- GitHub Actions snake widget note -->
    <div style="margin-top:14px;padding:12px 16px;background:rgba(0,255,157,0.06);border:1px solid rgba(0,255,157,0.2);border-radius:10px;font-size:0.75rem;color:#64748b;font-family:'Fira Code',monospace;">
      <span style="color:var(--neon-green);">▶</span> 
      In the real README, the snake animation is generated by GitHub Actions at:
      <span style="color:var(--neon-blue);">github.com/anantmalik1/anantmalik1/blob/output/github-contribution-grid-snake-dark.svg</span>
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ PROJECTS ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">🚀 Featured Work</span>
      <h2 class="section-title glow-purple">Project Showcase</h2>
      <p style="color:#64748b;font-size:0.82rem;">Handpicked projects that define my work</p>
    </div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:18px;">

      <!-- Project 1 – Sentra -->
      <div class="project-card" style="border-color:rgba(0,212,255,0.25);">
        <div style="display:flex;align-items:center;gap:12px;margin-bottom:14px;">
          <div style="width:46px;height:46px;border-radius:12px;background:linear-gradient(135deg,rgba(0,212,255,0.15),rgba(177,79,255,0.15));border:1px solid rgba(0,212,255,0.3);display:flex;align-items:center;justify-content:center;font-size:1.4rem;">🎙️</div>
          <div>
            <h3 style="font-size:1rem;font-weight:800;color:#e2e8f0;">Sentra</h3>
            <p style="font-size:0.7rem;color:var(--neon-blue);">Offline AI Voice Assistant</p>
          </div>
        </div>
        <p style="font-size:0.8rem;color:#94a3b8;line-height:1.65;margin-bottom:14px;">
          AI automation assistant using <strong style="color:#e2e8f0;">speech recognition</strong> and 
          <strong style="color:#e2e8f0;">NLP</strong>. Fully offline-capable, enabling voice-controlled 
          automation without cloud dependency.
        </p>
        <div style="display:flex;flex-wrap:wrap;gap:6px;margin-bottom:16px;">
          <span class="project-tag">Python</span>
          <span class="project-tag purple">NLP</span>
          <span class="project-tag green">Speech AI</span>
          <span class="project-tag">Offline</span>
        </div>
        <!-- Mini stat row -->
        <div style="display:flex;gap:16px;padding-top:12px;border-top:1px solid rgba(255,255,255,0.06);">
          <span style="font-size:0.72rem;color:#64748b;">⭐ AI Powered</span>
          <span style="font-size:0.72rem;color:#64748b;">🎙️ Voice NLP</span>
          <span style="font-size:0.72rem;color:#64748b;">🔒 Offline</span>
        </div>
      </div>

      <!-- Project 2 – Heart Disease -->
      <div class="project-card" style="border-color:rgba(255,0,106,0.25);">
        <div style="position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,#ff006a,#b14fff);border-radius:18px 18px 0 0;"></div>
        <div style="display:flex;align-items:center;gap:12px;margin-bottom:14px;">
          <div style="width:46px;height:46px;border-radius:12px;background:linear-gradient(135deg,rgba(255,0,106,0.15),rgba(177,79,255,0.15));border:1px solid rgba(255,0,106,0.3);display:flex;align-items:center;justify-content:center;font-size:1.4rem;">❤️‍🔥</div>
          <div>
            <h3 style="font-size:1rem;font-weight:800;color:#e2e8f0;">Heart Risk AI</h3>
            <p style="font-size:0.7rem;color:#ff6b9d;">Heart Disease Prediction</p>
          </div>
        </div>
        <p style="font-size:0.8rem;color:#94a3b8;line-height:1.65;margin-bottom:14px;">
          ML system predicting <strong style="color:#e2e8f0;">heart disease risk</strong> using 
          classification models with an interactive 
          <strong style="color:#e2e8f0;">Streamlit interface</strong> for real-time analysis.
        </p>
        <div style="display:flex;flex-wrap:wrap;gap:6px;margin-bottom:16px;">
          <span class="project-tag" style="color:#ff6b9d;border-color:rgba(255,106,157,0.3);background:rgba(255,106,157,0.08);">Scikit-Learn</span>
          <span class="project-tag purple">Streamlit</span>
          <span class="project-tag">Pandas</span>
          <span class="project-tag green">Healthcare AI</span>
        </div>
        <div style="display:flex;gap:16px;padding-top:12px;border-top:1px solid rgba(255,255,255,0.06);">
          <span style="font-size:0.72rem;color:#64748b;">🏥 Healthcare</span>
          <span style="font-size:0.72rem;color:#64748b;">📊 Streamlit</span>
          <span style="font-size:0.72rem;color:#64748b;">🎯 ML Model</span>
        </div>
      </div>

    </div>

    <!-- GitHub repo card widget -->
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:16px;">
      <div class="widget-card">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=sentra&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&icon_color=b14fff&text_color=94a3b8&border_radius=15" alt="Sentra Repo" />
      </div>
      <div class="widget-card">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=heart-disease-prediction&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=ff006a&icon_color=b14fff&text_color=94a3b8&border_radius=15" alt="Heart Disease Repo" />
      </div>
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ CURRENT FOCUS ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">🎯 Current Focus</span>
      <h2 class="section-title glow-green">What I'm Working On</h2>
    </div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
      <div class="focus-item">
        <div class="focus-dot" style="background:#00d4ff;box-shadow:0 0 8px #00d4ff;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">Deep Learning Models</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">Exploring neural architectures & transformers</div>
        </div>
      </div>
      <div class="focus-item">
        <div class="focus-dot" style="background:#b14fff;box-shadow:0 0 8px #b14fff;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">NLP & LLM Applications</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">Building language-aware AI systems</div>
        </div>
      </div>
      <div class="focus-item">
        <div class="focus-dot" style="background:#00ff9d;box-shadow:0 0 8px #00ff9d;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">Data Science Projects</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">End-to-end ML pipelines & analytics</div>
        </div>
      </div>
      <div class="focus-item">
        <div class="focus-dot" style="background:#ff006a;box-shadow:0 0 8px #ff006a;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">AI Voice Interfaces</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">Advancing Sentra's capabilities</div>
        </div>
      </div>
      <div class="focus-item">
        <div class="focus-dot" style="background:#ffd700;box-shadow:0 0 8px #ffd700;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">Open Source Contributions</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">Giving back to the ML community</div>
        </div>
      </div>
      <div class="focus-item">
        <div class="focus-dot" style="background:#00d4ff;box-shadow:0 0 8px #00d4ff;"></div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#e2e8f0;">B.Tech Final Year</div>
          <div style="font-size:0.75rem;color:#64748b;margin-top:3px;">CSE @ Quantum University</div>
        </div>
      </div>
    </div>

    <!-- Skill progress bars -->
    <div class="glass" style="padding:22px;margin-top:18px;">
      <p style="font-size:0.72rem;color:#64748b;text-transform:uppercase;letter-spacing:0.15em;margin-bottom:18px;">Proficiency Levels</p>
      <div style="display:flex;flex-direction:column;gap:14px;">
        <div>
          <div style="display:flex;justify-content:space-between;margin-bottom:6px;">
            <span style="font-size:0.8rem;color:#e2e8f0;">Python</span>
            <span style="font-size:0.75rem;color:var(--neon-blue);">90%</span>
          </div>
          <div class="progress-bar-wrap"><div class="progress-bar-fill" style="width:90%;background:linear-gradient(90deg,#00d4ff,#b14fff);"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;margin-bottom:6px;">
            <span style="font-size:0.8rem;color:#e2e8f0;">Machine Learning</span>
            <span style="font-size:0.75rem;color:#c77dff;">82%</span>
          </div>
          <div class="progress-bar-wrap"><div class="progress-bar-fill" style="width:82%;background:linear-gradient(90deg,#b14fff,#ff006a);"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;margin-bottom:6px;">
            <span style="font-size:0.8rem;color:#e2e8f0;">Data Analysis</span>
            <span style="font-size:0.75rem;color:var(--neon-green);">85%</span>
          </div>
          <div class="progress-bar-wrap"><div class="progress-bar-fill" style="width:85%;background:linear-gradient(90deg,#00ff9d,#00d4ff);"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;margin-bottom:6px;">
            <span style="font-size:0.8rem;color:#e2e8f0;">NLP / AI Systems</span>
            <span style="font-size:0.75rem;color:#ff6b9d;">75%</span>
          </div>
          <div class="progress-bar-wrap"><div class="progress-bar-fill" style="width:75%;background:linear-gradient(90deg,#ff006a,#b14fff);"></div></div>
        </div>
      </div>
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ ACHIEVEMENTS ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">🏆 Achievements</span>
      <h2 class="section-title" style="color:#ffd700;text-shadow:0 0 20px #ffd70088;">Milestones & Badges</h2>
    </div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:18px;">
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(255,215,0,0.1);border:1px solid rgba(255,215,0,0.25);">🤖</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#ffd700;">AI Project Builder</div>
          <div style="font-size:0.73rem;color:#64748b;">Built 2+ end-to-end AI systems</div>
        </div>
      </div>
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(0,212,255,0.1);border:1px solid rgba(0,212,255,0.25);">🐍</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:var(--neon-blue);">Python Enthusiast</div>
          <div style="font-size:0.73rem;color:#64748b;">Primary language for all projects</div>
        </div>
      </div>
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(0,255,157,0.1);border:1px solid rgba(0,255,157,0.25);">🧬</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:var(--neon-green);">Health AI Pioneer</div>
          <div style="font-size:0.73rem;color:#64748b;">ML model for medical prediction</div>
        </div>
      </div>
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(177,79,255,0.1);border:1px solid rgba(177,79,255,0.25);">🎙️</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#c77dff;">Voice AI Creator</div>
          <div style="font-size:0.73rem;color:#64748b;">Built offline voice assistant</div>
        </div>
      </div>
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(255,165,0,0.1);border:1px solid rgba(255,165,0,0.25);">🎓</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#ffa500;">CSE Scholar</div>
          <div style="font-size:0.73rem;color:#64748b;">B.Tech @ Quantum University</div>
        </div>
      </div>
      <div class="achieve-badge">
        <div class="achieve-icon" style="background:rgba(255,0,106,0.1);border:1px solid rgba(255,0,106,0.25);">🚀</div>
        <div>
          <div style="font-size:0.85rem;font-weight:700;color:#ff006a;">Open Source Contributor</div>
          <div style="font-size:0.73rem;color:#64748b;">Active GitHub presence</div>
        </div>
      </div>
    </div>

    <!-- GitHub trophies widget -->
    <div class="widget-card">
      <img src="https://github-profile-trophy.vercel.app/?username=anantmalik1&theme=tokyonight&no-frame=true&no-bg=true&column=6&margin-w=8&margin-h=8" alt="GitHub Trophies" style="width:100%;border-radius:15px;display:block;background:#0d0d1a;" />
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ DEV QUOTE ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">💬 Dev Quote</span>
      <h2 class="section-title glow-purple">Daily Inspiration</h2>
    </div>

    <div class="quote-card">
      <div id="quote-text" style="font-size:1.05rem;font-style:italic;color:#cbd5e1;line-height:1.8;margin-bottom:12px;padding-top:10px;">
        "The function of good software is to make the impossible merely difficult, and AI makes the difficult feel natural."
      </div>
      <div style="display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:8px;">
        <span id="quote-author" style="font-size:0.8rem;color:var(--neon-blue);font-weight:600;">— AI Philosophy</span>
        <button onclick="nextQuote()" style="background:rgba(0,212,255,0.1);border:1px solid rgba(0,212,255,0.25);border-radius:8px;padding:5px 14px;color:var(--neon-blue);font-size:0.75rem;cursor:pointer;font-weight:600;">Next Quote →</button>
      </div>
    </div>

    <!-- GitHub quote widget -->
    <div style="margin-top:14px;text-align:center;">
      <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight" alt="Dev Quote" style="max-width:100%;border-radius:15px;border:1px solid var(--border);" />
    </div>
  </section>

  <div class="sep"></div>

  <!-- ════════════════════════ CONTACT ════════════════════════ -->
  <section style="margin-bottom:28px;">
    <div style="margin-bottom:18px;">
      <span class="section-label">📬 Connect</span>
      <h2 class="section-title grad-text">Let's Build Together</h2>
      <p style="color:#64748b;font-size:0.82rem;max-width:520px;">
        I'm open to collaborations, AI projects, internships, and full-time opportunities. Let's create something intelligent!
      </p>
    </div>

    <div class="glass" style="padding:28px;text-align:center;">
      <div style="font-size:2rem;margin-bottom:12px;">🤝</div>
      <p style="color:#94a3b8;font-size:0.88rem;margin-bottom:20px;">
        <span style="color:var(--neon-green);font-weight:600;">Open to Work</span> — Looking for AI/ML roles, research positions, and exciting projects.
      </p>
      <div style="display:flex;flex-wrap:wrap;gap:10px;justify-content:center;">
        <a class="contact-chip" href="https://github.com/anantmalik1" target="_blank">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
          GitHub
        </a>
        <a class="contact-chip" href="https://linkedin.com/in/anantmalik1" target="_blank">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="contact-chip" href="mailto:anant@example.com">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Email Me
        </a>
        <a class="contact-chip" href="https://twitter.com/anantmalik1" target="_blank">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M23.953 4.57a10 10 0 0 1-2.825.775 4.958 4.958 0 0 0 2.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 0 0-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 0 0-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 0 1-2.228-.616v.06a4.923 4.923 0 0 0 3.946 4.827 4.996 4.996 0 0 1-2.212.085 4.936 4.936 0 0 0 4.604 3.417 9.867 9.867 0 0 1-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 0 0 7.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0 0 24 4.59z"/></svg>
          Twitter
        </a>
      </div>

      <!-- Profile views -->
      <div style="margin-top:22px;">
        <img src="https://komarev.com/ghpvc/?username=anantmalik1&style=for-the-badge&color=00d4ff&label=PROFILE+VIEWS" alt="Profile Views" style="border-radius:6px;" />
      </div>
    </div>
  </section>

  <!-- ════════════════════════ FOOTER ════════════════════════ -->
  <div style="text-align:center;padding-top:10px;">
    <div class="sep" style="margin-bottom:20px;"></div>
    <p style="font-family:'Fira Code',monospace;font-size:0.75rem;color:#334155;">
      <span style="color:var(--neon-blue);">print</span>(<span style="color:var(--neon-green);">"Thanks for visiting! Let's build the future with AI 🤖"</span>)
    </p>
    <p style="font-size:0.68rem;color:#1e293b;margin-top:8px;">
      ⚡ Crafted with passion by <span style="color:var(--neon-blue);">Anant Raj Malik</span> · AI/ML Engineer
    </p>
  </div>

</div><!-- end page-wrapper -->

<!-- Copy README Button -->
<button id="copy-btn" onclick="openModal()">
  📄 Get README.md
</button>

<!-- README Modal -->
<div id="readme-modal">
  <div class="modal-box">
    <div>
      <h3 style="font-size:1.1rem;font-weight:800;color:#e2e8f0;margin-bottom:4px;">📋 README.md — Copy & Paste into GitHub</h3>
      <p style="font-size:0.75rem;color:#64748b;">Create a repo named <code style="color:var(--neon-blue);">anantmalik1/anantmalik1</code> and paste this as <code style="color:var(--neon-blue);">README.md</code></p>
    </div>
    <pre id="readme-content"></pre>
    <div class="modal-actions">
      <button class="btn-close" onclick="closeModal()">✕ Close</button>
      <button class="btn-copy-md" onclick="copyReadme()">📋 Copy to Clipboard</button>
    </div>
  </div>
</div>

<script>
/* ═══════════════ MATRIX RAIN ═══════════════ */
(function(){
  const c = document.getElementById('matrix-canvas');
  const ctx = c.getContext('2d');
  function resize(){ c.width=window.innerWidth; c.height=window.innerHeight; }
  resize(); window.addEventListener('resize', resize);
  const chars='アイウエオカキクケコサシスセソタチツテトナニヌネノ01';
  let cols = Math.floor(c.width/16);
  let drops = Array(cols).fill(1);
  setInterval(()=>{
    cols = Math.floor(c.width/16);
    if(drops.length < cols) drops.push(1);
    ctx.fillStyle='rgba(0,0,0,0.04)';
    ctx.fillRect(0,0,c.width,c.height);
    ctx.fillStyle='#00ff9d';
    ctx.font='13px monospace';
    drops.forEach((y,i)=>{
      const ch=chars[Math.floor(Math.random()*chars.length)];
      ctx.fillText(ch,i*16,y*16);
      if(y*16>c.height && Math.random()>0.975) drops[i]=0;
      drops[i]++;
    });
  },50);
})();

/* ═══════════════ STAR FIELD ═══════════════ */
(function(){
  const c = document.getElementById('stars-canvas');
  const ctx = c.getContext('2d');
  function resize(){ c.width=window.innerWidth; c.height=window.innerHeight; }
  resize(); window.addEventListener('resize', resize);
  const stars=[];
  for(let i=0;i<160;i++){
    stars.push({
      x:Math.random()*window.innerWidth,
      y:Math.random()*window.innerHeight,
      r:Math.random()*1.5+0.3,
      a:Math.random(),
      da:(Math.random()-0.5)*0.008
    });
  }
  function draw(){
    ctx.clearRect(0,0,c.width,c.height);
    stars.forEach(s=>{
      s.a+=s.da;
      if(s.a<=0||s.a>=1) s.da*=-1;
      ctx.beginPath();
      ctx.arc(s.x,s.y,s.r,0,Math.PI*2);
      ctx.fillStyle=`rgba(200,220,255,${s.a})`;
      ctx.fill();
    });
    requestAnimationFrame(draw);
  }
  draw();
})();

/* ═══════════════ TYPING TITLE ═══════════════ */
(function(){
  const el = document.getElementById('typing-title');
  const texts = [
    'AI / ML Engineer',
    'Python Developer',
    'Building Intelligent Systems',
    'Data Science & Analytics',
    'Voice AI & NLP Builder'
  ];
  let ti=0, ci=0, del=false;
  function type(){
    const t=texts[ti];
    el.textContent = del ? t.slice(0,ci--) : t.slice(0,ci++);
    if(!del && ci===t.length+1){ del=true; setTimeout(type,1400); return; }
    if(del && ci===-1){ del=false; ti=(ti+1)%texts.length; ci=0; setTimeout(type,350); return; }
    setTimeout(type, del?50:85);
  }
  type();
})();

/* ═══════════════ SNAKE CANVAS ═══════════════ */
(function(){
  const c = document.getElementById('snake-canvas');
  const ctx = c.getContext('2d');
  const W = c.width, H = c.height;
  const CELL = 12, COLS = Math.floor(W/CELL), ROWS = Math.floor(H/CELL);

  // Build contribution grid (fake colored cells)
  const grid = [];
  const colors = ['#161b22','#0e4429','#006d32','#26a641','#39d353'];
  for(let r=0;r<ROWS;r++){
    grid[r]=[];
    for(let col=0;col<COLS;col++){
      const v = Math.random();
      grid[r][col] = v<0.5?0:v<0.7?1:v<0.85?2:v<0.95?3:4;
    }
  }

  // Snake
  let snake = [{x:3,y:1},{x:2,y:1},{x:1,y:1}];
  let dir = {x:1,y:0};
  let foods = [];
  function spawnFood(){
    for(let i=0;i<3;i++){
      foods.push({
        x:Math.floor(Math.random()*COLS),
        y:Math.floor(Math.random()*ROWS)
      });
    }
  }
  spawnFood();

  function drawGrid(){
    grid.forEach((row,r)=>{
      row.forEach((v,c2)=>{
        ctx.fillStyle = colors[v];
        ctx.beginPath();
        ctx.roundRect(c2*CELL+1, r*CELL+1, CELL-2, CELL-2, 2);
        ctx.fill();
      });
    });
  }

  function drawSnake(){
    snake.forEach((seg,i)=>{
      const prog = 1 - i/snake.length;
      ctx.fillStyle = `rgba(0,255,157,${0.3+prog*0.7})`;
      if(i===0){
        ctx.shadowColor='#00ff9d';
        ctx.shadowBlur=12;
      } else {
        ctx.shadowBlur=0;
      }
      ctx.beginPath();
      ctx.roundRect(seg.x*CELL+1, seg.y*CELL+1, CELL-2, CELL-2, 3);
      ctx.fill();
      ctx.shadowBlur=0;
    });
  }

  function drawFoods(){
    foods.forEach(f=>{
      ctx.fillStyle='#ffd700';
      ctx.shadowColor='#ffd700';
      ctx.shadowBlur=8;
      ctx.beginPath();
      ctx.arc(f.x*CELL+CELL/2, f.y*CELL+CELL/2, 3, 0, Math.PI*2);
      ctx.fill();
      ctx.shadowBlur=0;
    });
  }

  let frame=0;
  function update(){
    frame++;
    if(frame%6===0){
      const head=snake[0];
      const nx={(head.x+dir.x+COLS)%COLS};
      const ny={(head.y+dir.y+ROWS)%ROWS};
      const newHead={x:nx,y:ny};
      snake.unshift(newHead);

      // Eat food?
      const fi = foods.findIndex(f=>f.x===nx&&f.y===ny);
      if(fi>=0){
        foods.splice(fi,1);
        // "eat" contribution cell
        grid[ny][nx]=0;
        if(foods.length<3) spawnFood();
      } else {
        snake.pop();
      }

      // Steer toward food
      if(foods.length>0){
        const target=foods[0];
        const dx=target.x-head.x, dy=target.y-head.y;
        if(Math.abs(dx)>Math.abs(dy)){
          dir={x:dx>0?1:-1,y:0};
        } else if(dy!==0){
          dir={x:0,y:dy>0?1:-1};
        }
      }
    }

    ctx.clearRect(0,0,W,H);
    drawGrid();
    drawFoods();
    drawSnake();
    requestAnimationFrame(update);
  }
  update();
})();

/* ═══════════════ QUOTES ═══════════════ */
const quotes=[
  {q:'"The function of good software is to make the impossible merely difficult, and AI makes the difficult feel natural."', a:'— AI Philosophy'},
  {q:'"Machine learning is the field of study that gives computers the ability to learn without being explicitly programmed."', a:'— Arthur Samuel'},
  {q:'"Artificial intelligence is the new electricity."', a:'— Andrew Ng'},
  {q:'"Data is the new oil. But like oil, it has to be refined to be useful."', a:'— Clive Humby'},
  {q:'"The best way to predict the future is to invent it."', a:'— Alan Kay'},
  {q:'"Talk is cheap. Show me the code."', a:'— Linus Torvalds'},
  {q:'"In God we trust. All others must bring data."', a:'— W. Edwards Deming'},
];
let qi=0;
function nextQuote(){
  qi=(qi+1)%quotes.length;
  const qt=document.getElementById('quote-text');
  const qa=document.getElementById('quote-author');
  qt.style.opacity=0;
  qa.style.opacity=0;
  setTimeout(()=>{
    qt.textContent=quotes[qi].q;
    qa.textContent=quotes[qi].a;
    qt.style.transition='opacity 0.4s';
    qa.style.transition='opacity 0.4s';
    qt.style.opacity=1;
    qa.style.opacity=1;
  },300);
}

/* ═══════════════ README MODAL ═══════════════ */
const README_CONTENT = `<!-- 
  ╔══════════════════════════════════════════════════════════════╗
  ║     ANANT RAJ MALIK — AI/ML ENGINEER GITHUB PROFILE README  ║
  ║     Paste this file as README.md in repo: anantmalik1       ║
  ╚══════════════════════════════════════════════════════════════╝
-->

<div align="center">

<!-- ══════════════ ANIMATED BANNER ══════════════ -->

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Anant%20Raj%20Malik&fontSize=60&fontColor=fff&animation=twinkling&fontAlignY=35&desc=AI%20%2F%20ML%20Engineer%20%7C%20Python%20Developer&descAlignY=55&descSize=18" />

<!-- ══════════════ TYPING SVG ══════════════ -->

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=24&pause=900&color=00D4FF&center=true&vCenter=true&multiline=false&width=650&lines=🤖+AI+%2F+ML+Engineer;🐍+Python+Developer;🧠+Building+Intelligent+Systems;📊+Data+Science+%26+Analytics;🚀+Quantum+University+%7C+CSE)](https://git.io/typing-svg)

<!-- ══════════════ PROFILE VIEWS + BADGES ══════════════ -->

![Profile Views](https://komarev.com/ghpvc/?username=anantmalik1&style=for-the-badge&color=00d4ff&label=PROFILE+VIEWS)
[![GitHub followers](https://img.shields.io/github/followers/anantmalik1?style=for-the-badge&color=b14fff&labelColor=0d0d1a&label=FOLLOWERS)](https://github.com/anantmalik1)
[![GitHub stars](https://img.shields.io/github/stars/anantmalik1?style=for-the-badge&color=ffd700&labelColor=0d0d1a&label=STARS)](https://github.com/anantmalik1)

</div>

---

<!-- ══════════════ ABOUT ME ══════════════ -->

<img align="right" width="300" src="https://user-images.githubusercontent.com/74038190/229223263-cf2e4b07-2615-4f87-9c38-e37600f8381a.gif" />

## 🤖 About Me

\`\`\`python
class AnantRajMalik:
    name       = "Anant Raj Malik"
    role       = "AI / ML Engineer | Python Developer"
    university = "Quantum University"
    degree     = "B.Tech Computer Science Engineering"
    
    focus = [
        "Machine Learning",
        "NLP & Voice AI",
        "Data Science",
        "AI Automation",
    ]
    
    motto = "Turning data into decisions 🚀"
    status = "Open to opportunities ✅"
\`\`\`

> 🔭 Passionate AI developer focused on building **intelligent systems**, **machine learning models**, and **automation tools**.  
> 🎓 Currently pursuing B.Tech CSE at **Quantum University**  
> 🌱 Currently exploring **Deep Learning** and **LLM Applications**  
> 💡 Always learning, always building  

<br clear="right"/>

---

<!-- ══════════════ TECH STACK ══════════════ -->

## ⚡ Tech Stack & Tools

<div align="center">

**🧠 AI / Machine Learning**

[![My Skills](https://skillicons.dev/icons?i=python,tensorflow,sklearn,pytorch&theme=dark)](https://skillicons.dev)

**📊 Data & Visualization**

[![My Skills](https://skillicons.dev/icons?i=mysql,mongodb,js,git,github,jupyter,vscode,linux&theme=dark)](https://skillicons.dev)

</div>

<br>

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Scikit Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)

</div>

---

<!-- ══════════════ GITHUB STATS ══════════════ -->

## 📊 GitHub Analytics

<div align="center">

<img height="180" src="https://github-readme-stats.vercel.app/api?username=anantmalik1&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&icon_color=b14fff&text_color=94a3b8&border_radius=15&count_private=true" />
<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=anantmalik1&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&text_color=94a3b8&border_radius=15&langs_count=8" />

</div>

<div align="center">

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=anantmalik1&theme=tokyonight&hide_border=true&background=0d0d1a&stroke=00d4ff&ring=b14fff&fire=ff006a&currStreakLabel=00d4ff&border_radius=15)](https://git.io/streak-stats)

</div>

---

<!-- ══════════════ CONTRIBUTION GRAPH ══════════════ -->

## 📈 Contribution Graph

<div align="center">

[![Anant's github activity graph](https://github-readme-activity-graph.vercel.app/graph?username=anantmalik1&bg_color=0d0d1a&color=00d4ff&line=b14fff&point=00ff9d&area=true&area_color=00d4ff&hide_border=true&border_radius=15&custom_title=Anant's%20Contribution%20Graph)](https://github.com/ashutosh00710/github-readme-activity-graph)

</div>

---

<!-- ══════════════ SNAKE ANIMATION ══════════════ -->

## 🐍 Contribution Snake

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/anantmalik1/anantmalik1/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/anantmalik1/anantmalik1/output/github-contribution-grid-snake.svg" />
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/anantmalik1/anantmalik1/output/github-contribution-grid-snake-dark.svg" />
</picture>

> ⚙️ *To enable the snake animation, add this GitHub Actions workflow to your profile repo:*  
> `.github/workflows/snake.yml`

</div>

---

<!-- ══════════════ PROJECTS ══════════════ -->

## 🚀 Featured Projects

<div align="center">

<table>
<tr>
<td width="50%">

### 🎙️ Sentra — Offline AI Voice Assistant

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=sentra&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=00d4ff&icon_color=b14fff&text_color=94a3b8&border_radius=15)](https://github.com/anantmalik1/sentra)

> AI automation assistant using **speech recognition** and **NLP**. Fully offline-capable, enabling voice-controlled automation without cloud dependency.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-00D4FF?style=flat-square)
![Speech AI](https://img.shields.io/badge/Speech%20AI-B14FFF?style=flat-square)
![Offline](https://img.shields.io/badge/Offline-00FF9D?style=flat-square)

</td>
<td width="50%">

### ❤️ Heart Disease Risk Prediction

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=heart-disease-prediction&theme=tokyonight&hide_border=true&bg_color=0d0d1a&title_color=ff006a&icon_color=b14fff&text_color=94a3b8&border_radius=15)](https://github.com/anantmalik1/heart-disease-prediction)

> ML system predicting **heart disease risk** using classification models with an interactive **Streamlit interface** for real-time analysis.

![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

</td>
</tr>
</table>

</div>

---

<!-- ══════════════ CURRENT FOCUS ══════════════ -->

## 🎯 Current Focus

\`\`\`
🔵  Deep Learning Models     ████████████░░░  80%   Exploring neural architectures
🟣  NLP & LLM Applications   ██████████░░░░░  72%   Building language-aware AI systems  
🟢  Data Science Projects    ████████████░░░  82%   End-to-end ML pipelines & analytics
🔴  Voice AI (Sentra v2)     ███████████░░░░  75%   Advancing offline AI capabilities
🟡  Open Source              ████████░░░░░░░  55%   Contributing to ML community
🔵  B.Tech Final Year        ██████████████░  90%   CSE @ Quantum University
\`\`\`

---

<!-- ══════════════ ACHIEVEMENTS ══════════════ -->

## 🏆 GitHub Trophies

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=anantmalik1&theme=tokyonight&no-frame=true&no-bg=true&column=6&margin-w=8&margin-h=8)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

<!-- ══════════════ DEV QUOTE ══════════════ -->

## 💬 Dev Quote of the Day

<div align="center">

[![Readme Quotes](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight)](https://github.com/piyushsuthar/github-readme-quotes)

</div>

---

<!-- ══════════════ CONTACT ══════════════ -->

## 📬 Connect With Me

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-anantmalik1-181717?style=for-the-badge&logo=github)](https://github.com/anantmalik1)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/anantmalik1)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1DA1F2?style=for-the-badge&logo=twitter)](https://twitter.com/anantmalik1)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail)](mailto:anant@example.com)

</div>

---

<!-- ══════════════ FOOTER ══════════════ -->

<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer&animation=twinkling" />

\`\`\`python
print("Thanks for visiting! Let's build the future with AI 🤖")
# — Anant Raj Malik | AI/ML Engineer | Python Developer
\`\`\`

![Wave](https://raw.githubusercontent.com/mayhemantt/mayhemantt/Update/svg/Bottom.svg)

</div>

<!--
═══════════════════════════════════════════════════
  🐍 SNAKE SETUP — Add .github/workflows/snake.yml
═══════════════════════════════════════════════════
name: Generate Snake Animation
on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:
jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: anantmalik1
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: \${{ secrets.GITHUB_TOKEN }}
-->`;

document.getElementById('readme-content').textContent = README_CONTENT;

function openModal(){
  document.getElementById('readme-modal').classList.add('open');
}
function closeModal(){
  document.getElementById('readme-modal').classList.remove('open');
}
function copyReadme(){
  navigator.clipboard.writeText(README_CONTENT).then(()=>{
    const btn = document.querySelector('.btn-copy-md');
    btn.textContent = '✅ Copied!';
    setTimeout(()=>btn.textContent='📋 Copy to Clipboard',2500);
  });
}

// Close modal on backdrop click
document.getElementById('readme-modal').addEventListener('click', function(e){
  if(e.target===this) closeModal();
});
</script>
</body>
</html>
