<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Rohit Jadhav — Backend-Focused Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --bg2: #161b22;
    --bg3: #21262d;
    --border: #30363d;
    --text: #e6edf3;
    --muted: #8b949e;
    --accent: #4FC3F7;
    --accent2: #79c0ff;
    --green: #3fb950;
    --orange: #f0883e;
    --purple: #a371f7;
    --pink: #f78166;
    --yellow: #e3b341;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    line-height: 1.6;
    min-height: 100vh;
  }

  /* NAV */
  nav {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(13,17,23,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    padding: 0 2rem;
    height: 56px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .nav-logo {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--accent);
    text-decoration: none;
  }
  .nav-links {
    display: flex;
    gap: 1.5rem;
    list-style: none;
  }
  .nav-links a {
    font-size: 13px;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
    font-family: 'JetBrains Mono', monospace;
  }
  .nav-links a:hover { color: var(--text); }
  .hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    padding: 4px;
  }
  .hamburger span {
    display: block;
    width: 22px;
    height: 2px;
    background: var(--muted);
    border-radius: 2px;
    transition: all 0.3s;
  }

  /* MOBILE NAV */
  .mobile-nav {
    display: none;
    position: fixed;
    top: 56px;
    left: 0; right: 0;
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
    padding: 1rem 2rem;
    z-index: 99;
    flex-direction: column;
    gap: 1rem;
  }
  .mobile-nav.open { display: flex; }
  .mobile-nav a {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--muted);
    text-decoration: none;
  }

  /* HERO */
  .hero {
    max-width: 900px;
    margin: 0 auto;
    padding: 5rem 2rem 4rem;
    position: relative;
  }
  .hero-eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--green);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 1.2rem;
  }
  .hero-eyebrow::before { content: '> '; color: var(--muted); }
  .hero h1 {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 700;
    line-height: 1.15;
    color: var(--text);
    margin-bottom: 0.5rem;
  }
  .hero h1 span { color: var(--accent); }
  .hero-subtitle {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(13px, 2vw, 15px);
    color: var(--muted);
    margin-bottom: 1.5rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    align-items: center;
  }
  .hero-subtitle .dot { color: var(--border); }
  .hero-bio {
    font-size: 15px;
    color: var(--muted);
    max-width: 620px;
    margin-bottom: 2.5rem;
    line-height: 1.8;
  }
  .hero-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 2.5rem;
  }
  .hero-meta span { display: flex; align-items: center; gap: 6px; }
  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border-radius: 6px;
    font-size: 13px;
    font-family: 'JetBrains Mono', monospace;
    text-decoration: none;
    border: 1px solid var(--border);
    transition: all 0.2s;
    cursor: pointer;
    background: var(--bg2);
    color: var(--text);
  }
  .badge:hover { border-color: var(--accent); color: var(--accent); }
  .badge.primary { background: var(--accent); color: #0d1117; border-color: var(--accent); font-weight: 600; }
  .badge.primary:hover { background: #81d4fa; border-color: #81d4fa; }

  /* SECTIONS */
  section { max-width: 900px; margin: 0 auto; padding: 3rem 2rem; }
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--green);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
  }
  .section-label::before { content: '// '; color: var(--border); }
  h2 {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(1.2rem, 3vw, 1.6rem);
    font-weight: 700;
    color: var(--text);
    margin-bottom: 2rem;
  }
  .divider { border: none; border-top: 1px solid var(--border); margin: 0 2rem; }

  /* PROJECT CARD */
  .project-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 2rem;
    margin-bottom: 1.5rem;
    transition: border-color 0.2s;
  }
  .project-card:hover { border-color: var(--accent2); }
  .project-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 1rem;
    flex-wrap: wrap;
    margin-bottom: 0.8rem;
  }
  .project-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--accent2);
  }
  .project-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 100px;
    border: 1px solid var(--border);
    color: var(--muted);
    white-space: nowrap;
  }
  .project-tag.featured { border-color: var(--orange); color: var(--orange); }
  .project-desc {
    font-size: 14px;
    color: var(--muted);
    margin-bottom: 1.2rem;
    line-height: 1.7;
  }

  /* TECH TABLE */
  .tech-table { width: 100%; border-collapse: collapse; margin-bottom: 1.5rem; font-size: 13px; }
  .tech-table th {
    text-align: left;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-weight: 500;
    font-size: 11px;
    padding: 6px 10px;
    border-bottom: 1px solid var(--border);
    letter-spacing: 0.05em;
  }
  .tech-table td {
    padding: 8px 10px;
    border-bottom: 1px solid #21262d;
    color: var(--text);
    font-size: 13px;
    vertical-align: top;
  }
  .tech-table td:first-child { color: var(--muted); font-family: 'JetBrains Mono', monospace; font-size: 12px; white-space: nowrap; }

  /* INFRA GRID */
  .infra-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
    margin-bottom: 1.5rem;
  }
  .infra-item {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }
  .infra-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    margin-top: 5px;
    flex-shrink: 0;
  }
  .infra-dot.green { background: var(--green); }
  .infra-dot.blue { background: var(--accent); }
  .infra-dot.orange { background: var(--orange); }
  .infra-dot.purple { background: var(--purple); }
  .infra-item p { font-size: 13px; color: var(--text); line-height: 1.4; }
  .infra-item span { font-size: 11px; color: var(--muted); display: block; margin-top: 2px; }

  /* ARCH DIAGRAM */
  .arch-block {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 1.5rem;
    margin-bottom: 1.5rem;
    overflow-x: auto;
  }
  .arch-block pre {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    line-height: 2;
    white-space: pre;
  }
  .arch-block pre .hl { color: var(--accent); }
  .arch-block pre .hl2 { color: var(--green); }
  .arch-block pre .hl3 { color: var(--orange); }
  .arch-block pre .hl4 { color: var(--purple); }

  /* PROJECT LINKS */
  .project-links { display: flex; flex-wrap: wrap; gap: 8px; }
  .plink {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    padding: 6px 14px;
    border-radius: 6px;
    border: 1px solid var(--border);
    color: var(--muted);
    text-decoration: none;
    background: var(--bg3);
    transition: all 0.2s;
  }
  .plink:hover { border-color: var(--accent); color: var(--accent); }

  /* TECH STACK */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 10px;
    margin-bottom: 1.5rem;
  }
  .stack-category { margin-bottom: 2rem; }
  .stack-cat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.8rem;
    padding-left: 2px;
  }
  .pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 7px 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--text);
    margin: 4px 4px 4px 0;
    transition: border-color 0.2s;
  }
  .pill:hover { border-color: var(--accent2); }
  .pill .dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }

  /* DSA SECTION */
  .dsa-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.5rem 2rem;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: center;
  }
  .dsa-stat { text-align: center; }
  .dsa-stat .num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2rem;
    font-weight: 700;
    color: var(--accent);
    display: block;
  }
  .dsa-stat .label { font-size: 12px; color: var(--muted); }
  .dsa-tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .dsa-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    border: 1px solid var(--border);
    color: var(--muted);
  }

  /* BLOG CARD */
  .blog-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.5rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
    text-decoration: none;
    transition: border-color 0.2s;
  }
  .blog-card:hover { border-color: var(--orange); }
  .blog-card-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--text);
    margin-bottom: 4px;
  }
  .blog-card-sub { font-size: 13px; color: var(--muted); }
  .blog-arrow { font-size: 1.5rem; color: var(--orange); }

  /* CONNECT */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }
  .connect-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 1rem 1.2rem;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: all 0.2s;
  }
  .connect-item:hover { border-color: var(--accent); transform: translateY(-2px); }
  .connect-icon { font-size: 1.2rem; }
  .connect-label { font-size: 13px; color: var(--text); font-weight: 500; }
  .connect-sub { font-size: 11px; color: var(--muted); font-family: 'JetBrains Mono', monospace; }

  /* STATS */
  .stats-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 1.5rem;
  }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 1rem 1.5rem;
    text-align: center;
    flex: 1;
    min-width: 120px;
  }
  .stat-card .n {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--accent);
    display: block;
  }
  .stat-card .l { font-size: 11px; color: var(--muted); margin-top: 2px; }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem;
    text-align: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
  footer span { color: var(--accent); }

  /* RESULTS LIST */
  .results-list { list-style: none; display: flex; flex-direction: column; gap: 8px; }
  .results-list li {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 14px;
    color: var(--muted);
  }
  .results-list li::before {
    content: '→';
    color: var(--green);
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  /* RESPONSIVE */
  @media (max-width: 640px) {
    nav { padding: 0 1.2rem; }
    .nav-links { display: none; }
    .hamburger { display: flex; }
    .hero { padding: 3rem 1.2rem 2.5rem; }
    section { padding: 2.5rem 1.2rem; }
    .divider { margin: 0 1.2rem; }
    .hero-meta { gap: 1rem; }
    .project-card { padding: 1.4rem; }
    .dsa-card { gap: 1.2rem; padding: 1.2rem; }
    .arch-block { padding: 1rem; }
    .arch-block pre { font-size: 11px; }
    .tech-table { font-size: 12px; }
    .badge { font-size: 12px; padding: 7px 13px; }
  }
  @media (max-width: 480px) {
    .hero h1 { font-size: 1.7rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">rohitjadhav8849</a>
  <ul class="nav-links">
    <li><a href="#projects">projects</a></li>
    <li><a href="#stack">stack</a></li>
    <li><a href="#dsa">dsa</a></li>
    <li><a href="#connect">connect</a></li>
  </ul>
  <div class="hamburger" onclick="toggleNav()" aria-label="Menu">
    <span></span><span></span><span></span>
  </div>
</nav>
<div class="mobile-nav" id="mobileNav">
  <a href="#projects" onclick="toggleNav()">projects</a>
  <a href="#stack" onclick="toggleNav()">stack</a>
  <a href="#dsa" onclick="toggleNav()">dsa</a>
  <a href="#connect" onclick="toggleNav()">connect</a>
</div>

<!-- HERO -->
<div class="hero">
  <p class="hero-eyebrow">4th Year · NIT Silchar · India</p>
  <h1>Hi, I'm <span>Rohit Jadhav</span> 👋</h1>
  <div class="hero-subtitle">
    <span>Backend-Focused Full Stack Developer</span>
    <span class="dot">•</span>
    <span>React Native · Node.js · AWS · Docker · K8s</span>
  </div>
  <p class="hero-bio">
    I build production-style applications and explore scalable backend systems, cloud infrastructure, and distributed architectures. I don't clone tutorials — I ship real products.
  </p>
  <div class="hero-meta">
    <span>📍 India — Open to Remote & Relocation</span>
    <span>🚀 Open to Backend, Full Stack & SWE Roles</span>
    <span>🎓 NIT Silchar · ECE</span>
  </div>
  <div class="badge-row">
    <a href="https://linkedin.com/in/rohit-jadhav-8bb77127a" class="badge primary" target="_blank">LinkedIn ↗</a>
    <a href="https://github.com/rohitjadhav8849" class="badge" target="_blank">GitHub</a>
    <a href="https://llm-deployment.hashnode.dev" class="badge" target="_blank">Blog</a>
    <a href="https://youtu.be/pbej5XLWinA" class="badge" target="_blank">YouTube</a>
    <a href="YOUR_RESUME_LINK_HERE" class="badge" target="_blank">Resume PDF</a>
  </div>
</div>

<hr class="divider"/>

<!-- PROJECTS -->
<section id="projects">
  <p class="section-label">featured work</p>
  <h2>What I've Built</h2>

  <!-- SOCIETYPAY -->
  <div class="project-card">
    <div class="project-header">
      <span class="project-title">🏢 SocietyPay</span>
      <span class="project-tag featured">Production-Grade</span>
    </div>
    <p class="project-desc">
      AI-powered society management platform — automates complaints, payment risk, and visitor security using ML and NLP. Built end-to-end with a full backend infrastructure stack.
    </p>

    <table class="tech-table">
      <thead>
        <tr><th>Layer</th><th>Technology</th></tr>
      </thead>
      <tbody>
        <tr><td>📱 Mobile App</td><td>React Native + TypeScript</td></tr>
        <tr><td>⚙️ Backend API</td><td>Node.js + Express + JWT</td></tr>
        <tr><td>🗄️ Database</td><td>MongoDB Atlas + Mongoose</td></tr>
        <tr><td>🧠 NLP Routing</td><td>Python + Naive Bayes + CountVectorizer</td></tr>
        <tr><td>💰 Payment Risk</td><td>Scikit-learn + FastAPI</td></tr>
        <tr><td>💳 Payments</td><td>Razorpay + signature verification</td></tr>
        <tr><td>🛡️ Anomaly Detection</td><td>Isolation Forest</td></tr>
      </tbody>
    </table>

    <p style="font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--accent);letter-spacing:0.1em;text-transform:uppercase;margin-bottom:0.8rem;">Infrastructure & Scalability</p>
    <div class="infra-grid">
      <div class="infra-item">
        <div class="infra-dot green"></div>
        <div><p>Redis Caching</p><span>Faster API responses</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot blue"></div>
        <div><p>API Rate Limiting</p><span>Abuse prevention</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot orange"></div>
        <div><p>BullMQ Jobs</p><span>Background processing</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot purple"></div>
        <div><p>AWS EC2 + Nginx</p><span>Production deployment</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot green"></div>
        <div><p>Docker</p><span>Containerized backend</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot blue"></div>
        <div><p>GitHub Actions CI/CD</p><span>Automated workflows</span></div>
      </div>
    </div>

    <p style="font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--accent);letter-spacing:0.1em;text-transform:uppercase;margin-bottom:0.8rem;">Architecture</p>
    <div class="arch-block">
      <pre>
  <span class="hl">User Request</span>
       ↓
     <span class="hl2">DNS</span>
       ↓
     <span class="hl2">CDN</span>
       ↓
  <span class="hl2">Load Balancer</span>
       ↓
  <span class="hl3">Nginx</span>  (reverse proxy)
       ↓
  <span class="hl">Node.js API</span>
    ↙         ↘
<span class="hl2">Redis</span>     <span class="hl3">BullMQ</span>
    ↘         ↙
  <span class="hl4">MongoDB Atlas</span></pre>
    </div>

    <p style="font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--green);letter-spacing:0.1em;text-transform:uppercase;margin-bottom:0.8rem;">Results</p>
    <ul class="results-list" style="margin-bottom:1.5rem;">
      <li>Complaints auto-categorized and routed instantly via NLP</li>
      <li>Payment defaulters flagged before they miss payment</li>
      <li>Visitor behavior analyzed in real time with Isolation Forest</li>
    </ul>

    <div class="project-links">
      <a href="https://github.com/rohitjadhav8849/SocietyPay" class="plink" target="_blank">⭐ View on GitHub</a>
    </div>
  </div>

  <!-- LLM K8S -->
  <div class="project-card">
    <div class="project-header">
      <span class="project-title">☸️ Open Source LLM on Kubernetes</span>
      <span class="project-tag">DevRel · DrDroid (YC)</span>
    </div>
    <p class="project-desc">
      Got a 2–3 hour assignment. Spent 3 days doing it properly. Deployed Mistral 7B on Kubernetes with Grafana monitoring, a FastAPI backend, React chatbot UI, and a full Mistral vs GPT-4 comparative analysis.
    </p>
    <blockquote style="border-left:2px solid var(--border);padding-left:1rem;color:var(--muted);font-size:13px;font-style:italic;margin-bottom:1.5rem;">
      "The best LLM stack is not the smartest one. It's the one that fits your use case, your budget, and your infrastructure."
    </blockquote>

    <div class="infra-grid">
      <div class="infra-item">
        <div class="infra-dot purple"></div>
        <div><p>Mistral 7B via Ollama</p><span>Running locally</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot blue"></div>
        <div><p>FastAPI Backend</p><span>Containerized with Docker</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot orange"></div>
        <div><p>Kubernetes</p><span>Health checks + scaling</span></div>
      </div>
      <div class="infra-item">
        <div class="infra-dot green"></div>
        <div><p>Prometheus + Grafana</p><span>Live monitoring</span></div>
      </div>
    </div>

    <div class="project-links">
      <a href="https://github.com/rohitjadhav8849/llm-k8s-project" class="plink" target="_blank">💻 View Code</a>
      <a href="https://youtu.be/pbej5XLWinA" class="plink" target="_blank">▶ Watch Demo</a>
      <a href="https://llm-deployment.hashnode.dev" class="plink" target="_blank">📝 Read Blog</a>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- TECH STACK -->
<section id="stack">
  <p class="section-label">tools & technologies</p>
  <h2>Tech Stack</h2>

  <div class="stack-category">
    <p class="stack-cat-label">Languages</p>
    <span class="pill"><span class="dot" style="background:#f7df1e"></span>JavaScript</span>
    <span class="pill"><span class="dot" style="background:#3178c6"></span>TypeScript</span>
    <span class="pill"><span class="dot" style="background:#3776ab"></span>Python</span>
    <span class="pill"><span class="dot" style="background:#00599c"></span>C++</span>
    <span class="pill"><span class="dot" style="background:#a8b9cc"></span>C</span>
  </div>

  <div class="stack-category">
    <p class="stack-cat-label">Mobile & Web</p>
    <span class="pill"><span class="dot" style="background:#61dafb"></span>React Native</span>
    <span class="pill"><span class="dot" style="background:#61dafb"></span>React</span>
    <span class="pill"><span class="dot" style="background:#6da55f"></span>Node.js</span>
    <span class="pill"><span class="dot" style="background:#404d59"></span>Express</span>
    <span class="pill"><span class="dot" style="background:#005571"></span>FastAPI</span>
  </div>

  <div class="stack-category">
    <p class="stack-cat-label">Backend & Infrastructure</p>
    <span class="pill"><span class="dot" style="background:#dc382d"></span>Redis</span>
    <span class="pill"><span class="dot" style="background:#ff6b6b"></span>BullMQ</span>
    <span class="pill"><span class="dot" style="background:#ff9900"></span>AWS EC2</span>
    <span class="pill"><span class="dot" style="background:#009639"></span>Nginx</span>
    <span class="pill"><span class="dot" style="background:#2088ff"></span>GitHub Actions</span>
    <span class="pill"><span class="dot" style="background:#dc382d"></span>Redis Cloud</span>
  </div>

  <div class="stack-category">
    <p class="stack-cat-label">ML & AI</p>
    <span class="pill"><span class="dot" style="background:#f7931e"></span>Scikit-learn</span>
    <span class="pill"><span class="dot" style="background:#000"></span>Ollama</span>
    <span class="pill"><span class="dot" style="background:#ff6b35"></span>Mistral 7B</span>
    <span class="pill"><span class="dot" style="background:#4fc3f7"></span>Naive Bayes</span>
    <span class="pill"><span class="dot" style="background:#a371f7"></span>Isolation Forest</span>
  </div>

  <div class="stack-category">
    <p class="stack-cat-label">DevOps & Cloud</p>
    <span class="pill"><span class="dot" style="background:#326ce5"></span>Kubernetes</span>
    <span class="pill"><span class="dot" style="background:#2496ed"></span>Docker</span>
    <span class="pill"><span class="dot" style="background:#f46800"></span>Grafana</span>
    <span class="pill"><span class="dot" style="background:#e6522c"></span>Prometheus</span>
  </div>

  <div class="stack-category">
    <p class="stack-cat-label">Database & Tools</p>
    <span class="pill"><span class="dot" style="background:#4ea94b"></span>MongoDB</span>
    <span class="pill"><span class="dot" style="background:#47a248"></span>MongoDB Atlas</span>
    <span class="pill"><span class="dot" style="background:#f05033"></span>Git</span>
    <span class="pill"><span class="dot" style="background:#fcc624"></span>Linux</span>
    <span class="pill"><span class="dot" style="background:#3395ff"></span>Razorpay</span>
  </div>
</section>

<hr class="divider"/>

<!-- DSA -->
<section id="dsa">
  <p class="section-label">problem solving</p>
  <h2>DSA & System Design</h2>
  <div class="dsa-card">
    <div>
      <div class="dsa-stat">
        <span class="num">200+</span>
        <span class="label">LeetCode problems solved</span>
      </div>
    </div>
    <div style="flex:1;">
      <p style="font-size:13px;color:var(--muted);margin-bottom:0.8rem;">Strong focus on:</p>
      <div class="dsa-tags">
        <span class="dsa-tag">Graphs</span>
        <span class="dsa-tag">Trees</span>
        <span class="dsa-tag">Dynamic Programming</span>
        <span class="dsa-tag">Sliding Window</span>
        <span class="dsa-tag">System Design</span>
        <span class="dsa-tag">Rate Limiters</span>
        <span class="dsa-tag">Job Queues</span>
        <span class="dsa-tag">Caching</span>
      </div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- BLOG -->
<section>
  <p class="section-label">writing</p>
  <h2>Latest Blog</h2>
  <a href="https://llm-deployment.hashnode.dev" class="blog-card" target="_blank">
    <div>
      <p class="blog-card-title">🔥 I Had 3 Days to Deploy an Open Source LLM on Kubernetes.</p>
      <p class="blog-card-sub">Here's what actually happened.</p>
    </div>
    <span class="blog-arrow">→</span>
  </a>
</section>

<hr class="divider"/>

<!-- CONNECT -->
<section id="connect">
  <p class="section-label">get in touch</p>
  <h2>Let's Connect</h2>
  <p style="font-size:15px;color:var(--muted);margin-bottom:1.5rem;">
    Actively looking for <strong style="color:var(--text)">backend, full stack, and software engineering roles</strong> where I can ship fast and own systems end to end. Remote / relocation / hybrid — open to all.
  </p>
  <div class="connect-grid">
    <a href="https://linkedin.com/in/rohit-jadhav-8bb77127a" class="connect-item" target="_blank">
      <span class="connect-icon">💼</span>
      <div>
        <p class="connect-label">LinkedIn</p>
        <p class="connect-sub">rohit-jadhav-8bb77127a</p>
      </div>
    </a>
    <a href="https://github.com/rohitjadhav8849" class="connect-item" target="_blank">
      <span class="connect-icon">🐙</span>
      <div>
        <p class="connect-label">GitHub</p>
        <p class="connect-sub">rohitjadhav8849</p>
      </div>
    </a>
    <a href="mailto:your@email.com" class="connect-item" target="_blank">
      <span class="connect-icon">📧</span>
      <div>
        <p class="connect-label">Email</p>
        <p class="connect-sub">your@email.com</p>
      </div>
    </a>
    <a href="YOUR_RESUME_LINK_HERE" class="connect-item" target="_blank">
      <span class="connect-icon">📄</span>
      <div>
        <p class="connect-label">Resume</p>
        <p class="connect-sub">View PDF</p>
      </div>
    </a>
  </div>
</section>

<footer>
  <p>4th Year · NIT Silchar · <span>Backend Engineering</span> · Full Stack Development · Cloud Infrastructure</p>
  <p style="margin-top:8px;">⭐ If any of my projects helped you — a star means a lot!</p>
</footer>

<script>
function toggleNav() {
  document.getElementById('mobileNav').classList.toggle('open');
}
document.querySelectorAll('.mobile-nav a, a[href^="#"]').forEach(a => {
  a.addEventListener('click', function(e) {
    const href = this.getAttribute('href');
    if (href && href.startsWith('#') && href.length > 1) {
      e.preventDefault();
      const target = document.querySelector(href);
      if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});
</script>
</body>
</html>
