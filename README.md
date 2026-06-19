<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ashim C S — System Schematic</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&family=Newsreader:ital,wght@0,500;1,500&display=swap" rel="stylesheet"/>
<style>
:root{
  --paper:#0b1410;
  --paper-line:#16261d;
  --ink:#eef2ea;
  --ink-dim:#7d9485;
  --trace:#5dffb0;
  --trace-dim:#2e6b4c;
  --warn:#ff8a5c;
  --panel:#0e1a14;
  --panel-line:#22382c;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  background:var(--paper);
  color:var(--ink);
  font-family:'Space Grotesk',sans-serif;
  position:relative;
  overflow-x:hidden;
}

/* ───── BLUEPRINT GRID ───── */
.grid-bg{
  position:fixed; inset:0; z-index:0; pointer-events:none;
  background-image:
    linear-gradient(var(--paper-line) 1px, transparent 1px),
    linear-gradient(90deg, var(--paper-line) 1px, transparent 1px);
  background-size:48px 48px;
  opacity:0.5;
}
.grid-bg::after{
  content:'';
  position:absolute; inset:0;
  background:radial-gradient(ellipse 80% 50% at 50% 0%, rgba(93,255,176,0.06), transparent 60%);
}

/* ───── TRACE LINE — vertical circuit spine that grows on scroll ───── */
.spine{
  position:fixed; left:50%; top:0; bottom:0; width:1px;
  background:var(--panel-line);
  z-index:1; transform:translateX(-50%);
}
.spine-fill{
  position:absolute; top:0; left:0; width:100%; height:0%;
  background:linear-gradient(180deg, var(--trace), var(--trace-dim));
  box-shadow:0 0 12px var(--trace);
  transition:height 0.1s linear;
}

.wrap{ position:relative; z-index:2; max-width:980px; margin:0 auto; padding:0 32px; }

/* ───── CORNER COORDINATES (engineering drawing feel) ───── */
.coord{
  position:fixed; font-family:'IBM Plex Mono',monospace; font-size:10px;
  color:var(--ink-dim); letter-spacing:0.05em; z-index:50; opacity:0.6;
}
.coord.tl{ top:18px; left:18px; }
.coord.tr{ top:18px; right:18px; text-align:right; }
.coord.bl{ bottom:18px; left:18px; }
.coord.br{ bottom:18px; right:18px; text-align:right; }
@media(max-width:768px){ .coord{display:none;} }

/* ───── NAV ───── */
nav{
  position:fixed; top:0; left:0; right:0; z-index:40;
  border-bottom:1px solid var(--panel-line);
  background:rgba(11,20,16,0.85); backdrop-filter:blur(12px);
}
.nav-row{
  max-width:980px; margin:0 auto; padding:0 32px; height:56px;
  display:flex; align-items:center; justify-content:space-between;
}
.nav-mark{
  font-family:'IBM Plex Mono',monospace; font-size:13px; color:var(--trace);
  display:flex; align-items:center; gap:8px;
}
.nav-mark .dot{ width:6px; height:6px; border-radius:50%; background:var(--trace); animation:blink-dot 2.4s infinite; }
@keyframes blink-dot{0%,100%{opacity:1;}50%{opacity:0.25;}}
.nav-items{ display:flex; gap:28px; list-style:none; }
.nav-items a{
  font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--ink-dim);
  text-decoration:none; letter-spacing:0.08em; text-transform:uppercase;
  transition:color .2s;
}
.nav-items a:hover{ color:var(--trace); }
@media(max-width:700px){ .nav-items{display:none;} }

/* ───── HERO — schematic title block ───── */
.hero{ min-height:100vh; display:flex; flex-direction:column; justify-content:center; padding-top:70px; }
.title-block{
  border:1px solid var(--panel-line); background:rgba(14,26,20,0.5);
  position:relative;
}
.title-block::before, .title-block::after{
  content:''; position:absolute; width:14px; height:14px;
  border:1px solid var(--trace); opacity:0.7;
}
.title-block::before{ top:-1px; left:-1px; border-right:none; border-bottom:none; }
.title-block::after{ bottom:-1px; right:-1px; border-left:none; border-top:none; }

.tb-header{
  display:flex; justify-content:space-between; align-items:center;
  padding:14px 24px; border-bottom:1px solid var(--panel-line);
  font-family:'IBM Plex Mono',monospace; font-size:10px; color:var(--ink-dim);
  letter-spacing:0.1em; text-transform:uppercase;
}
.tb-header span.live{ color:var(--trace); }

.tb-body{ padding:48px 40px 56px; }

.eyebrow-tag{
  display:inline-flex; align-items:center; gap:8px;
  font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--trace);
  border:1px solid var(--trace-dim); padding:5px 12px; border-radius:3px;
  letter-spacing:0.08em; margin-bottom:28px;
  opacity:0; animation:rise .7s .15s forwards;
}

.name-display{
  font-size:clamp(48px,8vw,88px); font-weight:700; line-height:0.98; letter-spacing:-0.03em;
  margin-bottom:8px;
  opacity:0; animation:rise .7s .3s forwards;
}
.name-sub{
  font-family:'Newsreader', serif; font-style:italic; font-weight:500;
  font-size:clamp(18px,2.6vw,26px); color:var(--ink-dim); margin-bottom:32px;
  opacity:0; animation:rise .7s .45s forwards;
}
.name-sub b{ color:var(--trace); font-style:normal; font-weight:500; }

.role-line{
  font-family:'IBM Plex Mono',monospace; font-size:15px; color:var(--ink);
  margin-bottom:40px; min-height:24px;
  opacity:0; animation:rise .7s .6s forwards;
}
.role-line::before{ content:'$ '; color:var(--trace); }
.role-line .cursor{ display:inline-block; width:8px; height:16px; background:var(--trace); vertical-align:middle; margin-left:2px; animation:blink-dot 1s step-end infinite; }

.hero-actions{
  display:flex; gap:14px; flex-wrap:wrap;
  opacity:0; animation:rise .7s .75s forwards;
}
.action-btn{
  font-family:'IBM Plex Mono',monospace; font-size:12px; letter-spacing:0.04em;
  padding:13px 22px; border:1px solid var(--panel-line); background:transparent;
  color:var(--ink); text-decoration:none; display:inline-flex; align-items:center; gap:8px;
  transition:all .25s; position:relative; overflow:hidden;
}
.action-btn.primary{ border-color:var(--trace); color:var(--paper); background:var(--trace); font-weight:600; }
.action-btn.primary:hover{ box-shadow:0 0 28px rgba(93,255,176,0.5); transform:translateY(-2px); }
.action-btn:not(.primary):hover{ border-color:var(--trace); color:var(--trace); transform:translateY(-2px); }

@keyframes rise{ from{opacity:0; transform:translateY(18px);} to{opacity:1; transform:translateY(0);} }

/* readout strip under hero */
.readout-strip{
  display:grid; grid-template-columns:repeat(4,1fr);
  border:1px solid var(--panel-line); border-top:none;
  margin-top:-1px;
}
.readout{
  padding:18px 20px; border-right:1px solid var(--panel-line);
  font-family:'IBM Plex Mono',monospace;
}
.readout:last-child{ border-right:none; }
.readout-num{ font-size:24px; color:var(--trace); font-weight:600; line-height:1; }
.readout-label{ font-size:10px; color:var(--ink-dim); text-transform:uppercase; letter-spacing:0.08em; margin-top:6px; }
@media(max-width:700px){ .readout-strip{ grid-template-columns:repeat(2,1fr); } .readout{ border-bottom:1px solid var(--panel-line); } }

/* ───── SECTION FRAME ───── */
section{ padding:120px 0; }
.sec-tag{
  font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--trace);
  letter-spacing:0.15em; text-transform:uppercase; margin-bottom:18px;
  display:flex; align-items:center; gap:10px;
}
.sec-tag .idx{ color:var(--ink-dim); }
.sec-tag::after{ content:''; flex:1; height:1px; background:var(--panel-line); }
.sec-title{
  font-size:clamp(30px,4.5vw,46px); font-weight:700; letter-spacing:-0.025em;
  margin-bottom:56px; max-width:620px; line-height:1.08;
}
.sec-title em{ font-style:italic; font-family:'Newsreader',serif; color:var(--trace); font-weight:500; }

/* ───── ABOUT — annotation style ───── */
.about-frame{
  display:grid; grid-template-columns:1fr 1.3fr; gap:56px;
}
.annotate-num{
  font-family:'IBM Plex Mono',monospace; color:var(--trace); font-size:13px;
  border-bottom:1px solid var(--trace-dim); padding-bottom:14px; margin-bottom:18px;
}
.about-prose p{ color:var(--ink-dim); line-height:1.85; margin-bottom:18px; font-size:15px; }
.about-prose strong{ color:var(--ink); font-weight:600; }
.spec-table{ border:1px solid var(--panel-line); font-family:'IBM Plex Mono',monospace; font-size:12.5px; }
.spec-row{ display:flex; border-bottom:1px solid var(--panel-line); }
.spec-row:last-child{ border-bottom:none; }
.spec-key{ width:130px; flex-shrink:0; padding:14px 16px; color:var(--ink-dim); background:var(--panel); border-right:1px solid var(--panel-line); }
.spec-val{ padding:14px 16px; color:var(--ink); }

/* ───── STACK — circuit board layout ───── */
.stack-board{ border:1px solid var(--panel-line); }
.stack-row{ display:grid; grid-template-columns:200px 1fr; border-bottom:1px solid var(--panel-line); }
.stack-row:last-child{ border-bottom:none; }
.stack-row-label{
  padding:22px 24px; border-right:1px solid var(--panel-line); background:var(--panel);
  display:flex; flex-direction:column; justify-content:center;
}
.stack-row-label .n{ font-family:'IBM Plex Mono',monospace; font-size:10px; color:var(--trace-dim); margin-bottom:4px; }
.stack-row-label .t{ font-weight:600; font-size:15px; }
.stack-row-items{ display:flex; flex-wrap:wrap; align-items:center; gap:0; padding:6px; }
.node{
  font-family:'IBM Plex Mono',monospace; font-size:12px; color:var(--ink-dim);
  padding:10px 16px; border-right:1px dashed var(--panel-line);
  transition:all .25s; cursor:default; position:relative;
}
.node:hover{ color:var(--trace); background:rgba(93,255,176,0.05); }
@media(max-width:700px){ .stack-row{ grid-template-columns:1fr; } .stack-row-label{ border-right:none; border-bottom:1px solid var(--panel-line); flex-direction:row; gap:10px; } }

/* ───── PROJECTS — schematic cards w/ scan-line reveal ───── */
.proj-list{ display:flex; flex-direction:column; gap:1px; background:var(--panel-line); border:1px solid var(--panel-line); }
.proj{
  background:var(--paper); padding:36px 40px; display:grid; grid-template-columns:64px 1fr; gap:28px;
  position:relative; overflow:hidden;
  transition:background .3s;
}
.proj:hover{ background:rgba(93,255,176,0.025); }
.proj-id{ font-family:'IBM Plex Mono',monospace; color:var(--trace-dim); font-size:13px; padding-top:4px; }
.proj:hover .proj-id{ color:var(--trace); }
.proj-content{ position:relative; }
.proj-flag{
  display:inline-block; font-family:'IBM Plex Mono',monospace; font-size:10px; color:var(--warn);
  border:1px solid rgba(255,138,92,0.4); padding:3px 9px; border-radius:2px; margin-bottom:14px; letter-spacing:0.05em;
}
.proj-title{ font-size:22px; font-weight:700; margin-bottom:6px; letter-spacing:-0.01em; }
.proj-sub{ font-family:'IBM Plex Mono',monospace; font-size:12px; color:var(--trace); margin-bottom:16px; letter-spacing:0.02em; }
.proj-desc{ color:var(--ink-dim); line-height:1.75; font-size:14.5px; max-width:620px; margin-bottom:20px; }
.proj-stack{ display:flex; flex-wrap:wrap; gap:8px; }
.proj-stack span{ font-family:'IBM Plex Mono',monospace; font-size:10.5px; color:var(--ink-dim); border:1px solid var(--panel-line); padding:4px 10px; }
@media(max-width:700px){ .proj{ grid-template-columns:1fr; gap:14px; padding:28px 24px; } }

/* ───── CERTS — punch-card row ───── */
.cert-row{
  display:grid; grid-template-columns:36px 1fr auto; align-items:center; gap:18px;
  padding:18px 22px; border:1px solid var(--panel-line); margin-bottom:-1px;
  font-family:'IBM Plex Mono',monospace;
  transition:all .25s;
}
.cert-row:hover{ border-color:var(--trace-dim); background:rgba(93,255,176,0.03); }
.cert-check{ width:18px; height:18px; border:1px solid var(--trace); display:flex; align-items:center; justify-content:center; color:var(--trace); font-size:11px; }
.cert-title{ font-family:'Space Grotesk',sans-serif; font-weight:500; font-size:14.5px; }
.cert-issuer{ color:var(--ink-dim); font-size:11px; text-align:right; white-space:nowrap; }

/* ───── CONTACT — terminal close ───── */
.terminal{
  border:1px solid var(--panel-line); background:var(--panel);
}
.terminal-bar{
  padding:10px 18px; border-bottom:1px solid var(--panel-line);
  display:flex; gap:7px; align-items:center;
}
.terminal-bar span{ width:9px; height:9px; border-radius:50%; background:var(--panel-line); }
.terminal-body{ padding:36px 40px; font-family:'IBM Plex Mono',monospace; font-size:13.5px; line-height:2; }
.terminal-body .ln{ color:var(--ink-dim); }
.terminal-body .ln .k{ color:var(--trace); }
.terminal-body a{ color:var(--ink); text-decoration:none; border-bottom:1px dotted var(--ink-dim); transition:all .2s; }
.terminal-body a:hover{ color:var(--trace); border-color:var(--trace); }

footer{ padding:36px 0 60px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--ink-dim); }
footer b{ color:var(--trace); }

/* ───── reveal-on-scroll ───── */
.rv{ opacity:0; transform:translateY(24px); transition:opacity .6s ease, transform .6s ease; }
.rv.in{ opacity:1; transform:translateY(0); }

@media(prefers-reduced-motion:reduce){ *{animation-duration:.01ms!important; transition-duration:.01ms!important;} }
</style>
</head>
<body>

<div class="grid-bg"></div>
<div class="spine"><div class="spine-fill" id="spineFill"></div></div>

<span class="coord tl">N 08°31' KERALA / IND</span>
<span class="coord tr">REV 2026.06 — BUILD/STABLE</span>
<span class="coord bl">SHEET 01 OF 01</span>
<span class="coord br">SCALE — N/A</span>

<nav>
  <div class="nav-row">
    <div class="nav-mark"><span class="dot"></span>ASHIM·CS</div>
    <ul class="nav-items">
      <li><a href="#about">01 / About</a></li>
      <li><a href="#stack">02 / Stack</a></li>
      <li><a href="#work">03 / Work</a></li>
      <li><a href="#certs">04 / Certs</a></li>
      <li><a href="#contact">05 / Contact</a></li>
    </ul>
  </div>
</nav>

<div class="wrap">

  <!-- ═══ HERO ═══ -->
  <section class="hero" id="top">
    <div class="title-block">
      <div class="tb-header">
        <span>DOC — IDENTITY_SCHEMATIC.SYS</span>
        <span class="live">● STATUS: AVAILABLE</span>
      </div>
      <div class="tb-body">
        <div class="eyebrow-tag">◎ Open for freelance & full-time roles</div>
        <h1 class="name-display">ASHIM&nbsp;C&nbsp;S</h1>
        <p class="name-sub">A full-stack engineer who builds <b>AI-native</b> systems —<br/>from mobile mesh networks to LLM-backed pipelines.</p>
        <p class="role-line"><span id="typed"></span><span class="cursor"></span></p>
        <div class="hero-actions">
          <a href="mailto:ashimcs23@gmail.com" class="action-btn primary">Initiate Contact →</a>
          <a href="https://github.com/ashimcs" target="_blank" class="action-btn">View Source Repos</a>
          <a href="https://www.linkedin.com/in/ashim-cs-4b7569397" target="_blank" class="action-btn">LinkedIn ↗</a>
        </div>
      </div>
      <div class="readout-strip">
        <div class="readout"><div class="readout-num">07</div><div class="readout-label">Systems Shipped</div></div>
        <div class="readout"><div class="readout-num">05</div><div class="readout-label">AI Models Wired</div></div>
        <div class="readout"><div class="readout-num">04</div><div class="readout-label">Languages Spoken</div></div>
        <div class="readout"><div class="readout-num">∞</div><div class="readout-label">Coffee Consumed</div></div>
      </div>
    </div>
  </section>

  <!-- ═══ ABOUT ═══ -->
  <section id="about">
    <div class="sec-tag"><span class="idx">01</span> Profile</div>
    <h2 class="sec-title rv">The engineer behind the <em>schematic</em></h2>
    <div class="about-frame">
      <div class="rv">
        <div class="annotate-num">FIG. 1 — CORE SPECS</div>
        <div class="spec-table">
          <div class="spec-row"><div class="spec-key">EDUCATION</div><div class="spec-val">MCA, APJ Abdul Kalam<br/>Technological University<br/>2024 — 2026</div></div>
          <div class="spec-row"><div class="spec-key">PRIOR DEG.</div><div class="spec-val">BCA, MG University<br/>Kottayam, 2020 — 2023</div></div>
          <div class="spec-row"><div class="spec-key">LOCATION</div><div class="spec-val">Kerala, India</div></div>
          <div class="spec-row"><div class="spec-key">LANGUAGES</div><div class="spec-val">EN · HI · ML · TA</div></div>
          <div class="spec-row"><div class="spec-key">STATUS</div><div class="spec-val">Freelance + Full-time<br/>open</div></div>
        </div>
      </div>
      <div class="about-prose rv">
        <p>I work across the full delivery cycle — architecture, API design, database modeling, and client-facing demos. Most of my recent builds sit at the seam between <strong>mobile engineering and applied AI</strong>: wiring LLMs, computer vision models, and NLP pipelines into systems people actually use.</p>
        <p>My core stack is <strong>Flutter on the front, Django REST on the back</strong>. I've shipped production integrations with Google Gemini Vision, Groq, LLaMA 3 Vision, and the Google GenAI SDK — alongside more foundational work in JWT auth, OTP flows, and multi-tenant database sync.</p>
        <p>My MCA thesis project, <strong>Sentinel AI</strong>, pushes furthest into systems territory: a mesh-networked, offline-capable disaster response app that doesn't depend on internet infrastructure to function.</p>
        <p>Outside of code: I run client walkthroughs, lead code reviews, and translate dense technical architecture into language non-engineers can act on.</p>
      </div>
    </div>
  </section>

  <!-- ═══ STACK ═══ -->
  <section id="stack">
    <div class="sec-tag"><span class="idx">02</span> Architecture</div>
    <h2 class="sec-title rv">The <em>stack</em>, wired end to end</h2>
    <div class="stack-board rv">
      <div class="stack-row">
        <div class="stack-row-label"><div class="n">LAYER / 01</div><div class="t">Mobile & Frontend</div></div>
        <div class="stack-row-items">
          <span class="node">Flutter</span><span class="node">Dart</span><span class="node">JavaScript</span>
          <span class="node">HTML5</span><span class="node">CSS3</span><span class="node">Bootstrap 5</span><span class="node">Android SDK</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label"><div class="n">LAYER / 02</div><div class="t">Backend & APIs</div></div>
        <div class="stack-row-items">
          <span class="node">Python</span><span class="node">Django</span><span class="node">Django REST</span>
          <span class="node">JWT Auth</span><span class="node">OTP Verify</span><span class="node">SMTP</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label"><div class="n">LAYER / 03</div><div class="t">Data Persistence</div></div>
        <div class="stack-row-items">
          <span class="node">PostgreSQL</span><span class="node">MySQL</span><span class="node">MongoDB</span><span class="node">SQLite</span>
        </div>
      </div>
      <div class="stack-row">
        <div class="stack-row-label"><div class="n">LAYER / 04</div><div class="t">AI / ML Integration</div></div>
        <div class="stack-row-items">
          <span class="node">Gemini Vision</span><span class="node">Groq NLP</span><span class="node">LLaMA 3 Vision</span>
          <span class="node">Google GenAI SDK</span><span class="node">face-api.js</span><span class="node">Chart.js</span><span class="node">Pillow</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ═══ PROJECTS ═══ -->
  <section id="work">
    <div class="sec-tag"><span class="idx">03</span> Deployments</div>
    <h2 class="sec-title rv">Six systems, <em>shipped</em></h2>
    <div class="proj-list">

      <div class="proj rv">
        <div class="proj-id">P‑01</div>
        <div class="proj-content">
          <span class="proj-flag">⚠ FLAGSHIP — MCA FINAL YEAR</span>
          <div class="proj-title">Sentinel AI</div>
          <div class="proj-sub">Autonomous Disaster Intelligence Ecosystem</div>
          <p class="proj-desc">A decentralized mobile platform that forms star-topology BLE/Wi-Fi mesh networks via Google Nearby Connections — keeping devices talking when internet infrastructure goes down. LLaMA 3 Vision runs on-device for situational intelligence in zero-connectivity zones.</p>
          <div class="proj-stack"><span>Flutter</span><span>Django REST</span><span>LLaMA 3 Vision</span><span>Nearby Connections API</span><span>SQLite</span><span>MySQL</span></div>
        </div>
      </div>

      <div class="proj rv">
        <div class="proj-id">P‑02</div>
        <div class="proj-content">
          <div class="proj-title">Smart Voyage</div>
          <div class="proj-sub">AI-Powered Autonomous Travel Planner</div>
          <p class="proj-desc">Generates multi-day travel itineraries via Gemini Vision + Groq API, rendered asynchronously across a cross-platform Flutter shell. JWT-secured endpoints with a structured OTP verification matrix protect every session.</p>
          <div class="proj-stack"><span>Flutter</span><span>Django REST</span><span>PostgreSQL</span><span>Gemini Vision</span><span>Groq API</span></div>
        </div>
      </div>

      <div class="proj rv">
        <div class="proj-id">P‑03</div>
        <div class="proj-content">
          <div class="proj-title">MindSpace</div>
          <div class="proj-sub">Computer Vision Emotional Tracking Platform</div>
          <p class="proj-desc">Browser-based biometric workflow mapping live webcam landmarks to emotional-state metrics via face-api.js, with historical analytics surfaced through a Django + Chart.js dashboard.</p>
          <div class="proj-stack"><span>face-api.js</span><span>Django</span><span>MongoDB</span><span>Chart.js</span></div>
        </div>
      </div>

      <div class="proj rv">
        <div class="proj-id">P‑04</div>
        <div class="proj-content">
          <div class="proj-title">VoxMark AI</div>
          <div class="proj-sub">Cross-Platform Content Generation Suite</div>
          <p class="proj-desc">A decoupled mobile app built around an interactive drag-and-drop canvas, with backend image rendering through the Google GenAI SDK and Pillow. Presented data-flow architecture directly to client stakeholders.</p>
          <div class="proj-stack"><span>Flutter</span><span>Django REST</span><span>Google GenAI SDK</span><span>Pillow</span><span>MySQL</span></div>
        </div>
      </div>

      <div class="proj rv">
        <div class="proj-id">P‑05</div>
        <div class="proj-content">
          <div class="proj-title">AI Career Guidance Suite</div>
          <div class="proj-sub">NLP-Powered Job Matching Engine</div>
          <p class="proj-desc">Parses user profiles against raw job listings via Groq's NLP engine, scoring exact keyword overlap and rendering localized career roadmaps as live Chart.js visualizations.</p>
          <div class="proj-stack"><span>Python</span><span>Django</span><span>Groq NLP API</span><span>MySQL</span><span>Chart.js</span></div>
        </div>
      </div>

      <div class="proj rv">
        <div class="proj-id">P‑06</div>
        <div class="proj-content">
          <div class="proj-title">CarCare SOS</div>
          <div class="proj-sub">On-Demand Vehicle Assistance Dispatch</div>
          <p class="proj-desc">Routes emergency SOS calls to the nearest available technician via Leaflet.js maps, while logging every transaction and dispatching SMTP alerts in real time.</p>
          <div class="proj-stack"><span>Django</span><span>Leaflet.js</span><span>MySQL</span><span>SMTP</span><span>Glassmorphism CSS</span></div>
        </div>
      </div>

    </div>
  </section>

  <!-- ═══ CERTS ═══ -->
  <section id="certs">
    <div class="sec-tag"><span class="idx">04</span> Verification</div>
    <h2 class="sec-title rv">Credentials on <em>record</em></h2>
    <div class="rv">
      <div class="cert-row"><div class="cert-check">✓</div><div class="cert-title">Generative AI Advanced Fine-Tuning for LLMs</div><div class="cert-issuer">IBM · COURSERA</div></div>
      <div class="cert-row"><div class="cert-check">✓</div><div class="cert-title">Generative AI & LLMs: Architecture and Data Preparation</div><div class="cert-issuer">IBM · COURSERA</div></div>
      <div class="cert-row"><div class="cert-check">✓</div><div class="cert-title">Introduction to Artificial Intelligence</div><div class="cert-issuer">IBM · COURSERA</div></div>
      <div class="cert-row"><div class="cert-check">✓</div><div class="cert-title">Accelerate Your Job Search with AI</div><div class="cert-issuer">GOOGLE · COURSERA</div></div>
      <div class="cert-row"><div class="cert-check">✓</div><div class="cert-title">Flutter & Mobile App Architectures — 6 Month Intensive</div><div class="cert-issuer">SANS BORNE WEB SOLUTIONS</div></div>
    </div>
  </section>

  <!-- ═══ CONTACT ═══ -->
  <section id="contact">
    <div class="sec-tag"><span class="idx">05</span> Connection</div>
    <h2 class="sec-title rv">Let's <em>compile</em> something</h2>
    <div class="terminal rv">
      <div class="terminal-bar"><span></span><span></span><span></span></div>
      <div class="terminal-body">
        <div class="ln"><span class="k">$</span> whoami</div>
        <div class="ln">&gt; Ashim C S — Full-Stack Engineer, Kerala IN</div>
        <div class="ln"><span class="k">$</span> contact --email</div>
        <div class="ln">&gt; <a href="mailto:ashimcs23@gmail.com">ashimcs23@gmail.com</a></div>
        <div class="ln"><span class="k">$</span> contact --phone</div>
        <div class="ln">&gt; <a href="tel:+917025096864">+91 7025096864</a></div>
        <div class="ln"><span class="k">$</span> contact --linkedin</div>
        <div class="ln">&gt; <a href="https://www.linkedin.com/in/ashim-cs-4b7569397" target="_blank">linkedin.com/in/ashim-cs-4b7569397</a></div>
        <div class="ln"><span class="k">$</span> contact --github</div>
        <div class="ln">&gt; <a href="https://github.com/ashimcs" target="_blank">github.com/ashimcs</a></div>
        <div class="ln"><span class="k">$</span> status</div>
        <div class="ln">&gt; Open to freelance contracts & full-time roles. Reply &lt;24h.</div>
      </div>
    </div>
  </section>

</div>

<footer>BUILT BY <b>ASHIM C S</b> — KERALA, INDIA — 2026 — END OF SHEET</footer>

<script>
// typing line
const roles = [
  "role: full-stack-engineer --primary",
  "role: flutter-developer --mobile",
  "role: django-rest-architect --backend",
  "role: ai-integration-specialist --llm",
  "role: computer-vision-engineer --cv",
];
let ri=0, ci=0, del=false;
const el = document.getElementById('typed');
function tick(){
  const w = roles[ri];
  if(!del){ el.textContent = w.slice(0, ++ci); if(ci===w.length){ del=true; setTimeout(tick,1600); return; } }
  else { el.textContent = w.slice(0, --ci); if(ci===0){ del=false; ri=(ri+1)%roles.length; } }
  setTimeout(tick, del?35:65);
}
tick();

// spine fill on scroll
const spineFill = document.getElementById('spineFill');
function updateSpine(){
  const h = document.documentElement;
  const pct = (h.scrollTop) / (h.scrollHeight - h.clientHeight) * 100;
  spineFill.style.height = pct + '%';
}
document.addEventListener('scroll', updateSpine);
updateSpine();

// reveal on scroll
const obs = new IntersectionObserver(es=>{
  es.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('in'); } });
},{threshold:0.1});
document.querySelectorAll('.rv').forEach(el=>obs.observe(el));
</script>
</body>
</html>
