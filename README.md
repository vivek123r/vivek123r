<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vivek R — Portfolio</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;color:#111;background:#fff}
@media(prefers-color-scheme:dark){body{color:#f0f0f0;background:#111}}

.hero{padding:2rem 1.5rem 1.5rem;border-bottom:1px solid #e5e5e5}
@media(prefers-color-scheme:dark){.hero{border-color:#2a2a2a}}
.hero-top{display:flex;align-items:center;gap:16px;margin-bottom:1rem}
.avatar{width:64px;height:64px;border-radius:50%;background:#0891b2;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:500;color:#fff;flex-shrink:0}
.hero h1{font-size:22px;font-weight:500;margin-bottom:2px}
.hero-sub{font-size:13px;color:#666;margin-bottom:8px}
@media(prefers-color-scheme:dark){.hero-sub{color:#999}}
.hero-badges{display:flex;flex-wrap:wrap;gap:6px}
.hb{font-size:11px;padding:3px 10px;border-radius:99px;font-weight:500;border:1px solid transparent}
.hb-teal{background:#E1F5EE;color:#0F6E56;border-color:#5DCAA5}
.hb-purple{background:#EEEDFE;color:#3C3489;border-color:#AFA9EC}
.hb-amber{background:#FAEEDA;color:#633806;border-color:#EF9F27}
.hb-green{background:#EAF3DE;color:#27500A;border-color:#97C459}
@media(prefers-color-scheme:dark){
  .hb-teal{background:#085041;color:#9FE1CB;border-color:#0F6E56}
  .hb-purple{background:#26215C;color:#CECBF6;border-color:#534AB7}
  .hb-amber{background:#412402;color:#FAC775;border-color:#854F0B}
  .hb-green{background:#173404;color:#C0DD97;border-color:#3B6D11}
}

.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;padding:1rem 1.5rem;border-bottom:1px solid #e5e5e5}
@media(prefers-color-scheme:dark){.stats-row{border-color:#2a2a2a}}
.stat{background:#f5f5f5;border-radius:8px;padding:10px 12px;text-align:center}
@media(prefers-color-scheme:dark){.stat{background:#1e1e1e}}
.stat-num{font-size:20px;font-weight:500}
.stat-lbl{font-size:11px;color:#666;margin-top:2px}
@media(prefers-color-scheme:dark){.stat-lbl{color:#888}}

.tabs{display:flex;border-bottom:1px solid #e5e5e5;overflow-x:auto;padding:0 1.5rem}
@media(prefers-color-scheme:dark){.tabs{border-color:#2a2a2a}}
.tab{padding:10px 14px;font-size:13px;cursor:pointer;border:none;background:none;color:#666;white-space:nowrap;border-bottom:2px solid transparent;transition:color 0.15s}
@media(prefers-color-scheme:dark){.tab{color:#888}}
.tab.active{color:#0891b2;border-bottom-color:#0891b2;font-weight:500}
.tab:hover:not(.active){color:#111}
@media(prefers-color-scheme:dark){.tab:hover:not(.active){color:#f0f0f0}}

.panel{display:none;padding:1.25rem 1.5rem}
.panel.active{display:block}

.section-label{font-size:11px;font-weight:500;color:#888;text-transform:uppercase;letter-spacing:0.06em;margin-bottom:12px}

.about-bio{font-size:13px;line-height:1.7;color:#555;margin-bottom:1.25rem}
@media(prefers-color-scheme:dark){.about-bio{color:#aaa}}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:1.25rem}
.about-card{background:#f5f5f5;border-radius:8px;padding:12px 14px}
@media(prefers-color-scheme:dark){.about-card{background:#1e1e1e}}
.about-card .lbl{font-size:11px;color:#888;margin-bottom:3px;text-transform:uppercase;letter-spacing:0.05em}
.about-card .val{font-size:13px;font-weight:500}
.currently-row{display:flex;flex-direction:column;gap:6px}
.currently-item{display:flex;align-items:center;gap:10px;font-size:13px;color:#555}
@media(prefers-color-scheme:dark){.currently-item{color:#aaa}}
.currently-item i{font-size:16px;color:#0891b2}

.skill-group{margin-bottom:1rem}
.skill-group h3{font-size:11px;font-weight:500;color:#888;text-transform:uppercase;letter-spacing:0.06em;margin-bottom:8px}
.pills{display:flex;flex-wrap:wrap;gap:6px}
.pill{font-size:12px;padding:4px 10px;background:#f5f5f5;border:1px solid #e5e5e5;border-radius:99px;color:#111}
@media(prefers-color-scheme:dark){.pill{background:#1e1e1e;border-color:#333;color:#f0f0f0}}
.pill-hot{background:#E1F5EE;border-color:#5DCAA5;color:#0F6E56}
@media(prefers-color-scheme:dark){.pill-hot{background:#085041;border-color:#0F6E56;color:#9FE1CB}}

.proj-card{border:1px solid #e5e5e5;border-radius:12px;padding:14px 16px;margin-bottom:10px;background:#fff;cursor:pointer;transition:border-color 0.15s}
@media(prefers-color-scheme:dark){.proj-card{border-color:#2a2a2a;background:#111}}
.proj-card:hover{border-color:#aaa}
@media(prefers-color-scheme:dark){.proj-card:hover{border-color:#555}}
.proj-card.open{border-color:#0891b2}
.proj-top{display:flex;align-items:flex-start;justify-content:space-between;gap:8px;margin-bottom:6px}
.proj-title{font-size:14px;font-weight:500}
.proj-stack{font-size:11px;color:#888;margin-bottom:6px}
.proj-desc{font-size:13px;color:#555;line-height:1.5}
@media(prefers-color-scheme:dark){.proj-desc{color:#aaa}}
.proj-stats{display:flex;flex-wrap:wrap;gap:6px;margin-top:10px}
.proj-stat{font-size:11px;background:#f5f5f5;padding:3px 8px;border-radius:99px;color:#666}
@media(prefers-color-scheme:dark){.proj-stat{background:#1e1e1e;color:#888}}
.proj-detail{overflow:hidden;max-height:0;transition:max-height 0.3s ease}
.proj-detail.open{max-height:300px}
.proj-detail ul{padding:10px 0 2px 1rem;display:flex;flex-direction:column;gap:4px}
.proj-detail li{font-size:12px;color:#555;line-height:1.5}
@media(prefers-color-scheme:dark){.proj-detail li{color:#aaa}}
.chevron{font-size:16px;color:#888;transition:transform 0.2s;flex-shrink:0}
.chevron.open{transform:rotate(180deg)}

.timeline{position:relative;padding-left:20px}
.timeline::before{content:'';position:absolute;left:6px;top:6px;bottom:6px;width:1px;background:#e5e5e5}
@media(prefers-color-scheme:dark){.timeline::before{background:#2a2a2a}}
.tl-item{position:relative;margin-bottom:1.25rem}
.tl-dot{position:absolute;left:-17px;top:4px;width:8px;height:8px;border-radius:50%;border:1px solid #aaa;background:#fff}
@media(prefers-color-scheme:dark){.tl-dot{background:#111;border-color:#555}}
.tl-dot.active{background:#0891b2;border-color:#0891b2}
.tl-title{font-size:14px;font-weight:500;margin-bottom:2px}
.tl-meta{font-size:12px;color:#888;margin-bottom:6px}
.tl-item ul{padding-left:1rem}
.tl-item li{font-size:12px;color:#555;line-height:1.6}
@media(prefers-color-scheme:dark){.tl-item li{color:#aaa}}

.cert-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin-bottom:1.25rem}
.cert-card{background:#f5f5f5;border-radius:8px;padding:14px 12px;text-align:center}
@media(prefers-color-scheme:dark){.cert-card{background:#1e1e1e}}
.cert-icon{font-size:22px;margin-bottom:6px;color:#888}
.cert-name{font-size:12px;font-weight:500;line-height:1.4;margin-bottom:2px}
.cert-by{font-size:11px;color:#888}

.connect-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:1.25rem}
.connect-btn{display:flex;align-items:center;gap:10px;padding:12px 14px;border:1px solid #e5e5e5;border-radius:8px;text-decoration:none;color:#111;background:#fff;cursor:pointer;transition:background 0.15s}
@media(prefers-color-scheme:dark){.connect-btn{border-color:#2a2a2a;background:#111;color:#f0f0f0}}
.connect-btn:hover{background:#f5f5f5}
@media(prefers-color-scheme:dark){.connect-btn:hover{background:#1e1e1e}}
.cb-icon{width:34px;height:34px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:17px;flex-shrink:0}
.cb-label{font-size:11px;color:#888}
.cb-val{font-size:12px;font-weight:500}
.cb-mail .cb-icon{background:#FAECE7;color:#993C1D}
.cb-li .cb-icon{background:#E6F1FB;color:#185FA5}
.cb-gh .cb-icon{background:#EEEDFE;color:#3C3489}
.cb-web .cb-icon{background:#EAF3DE;color:#27500A}
@media(prefers-color-scheme:dark){
  .cb-mail .cb-icon{background:#4A1B0C;color:#F5C4B3}
  .cb-li .cb-icon{background:#042C53;color:#B5D4F4}
  .cb-gh .cb-icon{background:#26215C;color:#CECBF6}
  .cb-web .cb-icon{background:#173404;color:#C0DD97}
}
.status-row{display:flex;align-items:center;gap:8px;padding:10px 14px;background:#f5f5f5;border-radius:8px;font-size:13px;color:#555;margin-bottom:1rem}
@media(prefers-color-scheme:dark){.status-row{background:#1e1e1e;color:#aaa}}
.status-dot{width:8px;height:8px;border-radius:50%;background:#22c55e;flex-shrink:0}
.quote-block{border-left:2px solid #0891b2;padding:10px 14px;font-size:13px;font-style:italic;color:#666;border-radius:0}
@media(prefers-color-scheme:dark){.quote-block{color:#aaa}}
</style>
</head>
<body>

<div class="hero">
  <div class="hero-top">
    <div class="avatar">VR</div>
    <div>
      <h1>Vivek R</h1>
      <p class="hero-sub">Full-stack engineer · AI agents · Kerala, India</p>
      <div class="hero-badges">
        <span class="hb hb-teal">LangGraph</span>
        <span class="hb hb-purple">React · Flutter</span>
        <span class="hb hb-amber">AWS · Docker</span>
        <span class="hb hb-green">Open to work</span>
      </div>
    </div>
  </div>
</div>

<div class="stats-row">
  <div class="stat"><div class="stat-num">4</div><div class="stat-lbl">Projects shipped</div></div>
  <div class="stat"><div class="stat-num">8</div><div class="stat-lbl">AI agents built</div></div>
  <div class="stat"><div class="stat-num">3</div><div class="stat-lbl">Certifications</div></div>
  <div class="stat"><div class="stat-num">20%</div><div class="stat-lbl">Deploy time saved</div></div>
</div>

<div class="tabs">
  <button class="tab active" onclick="showTab('about',this)"><i class="ti ti-user" style="font-size:14px;margin-right:4px"></i>About</button>
  <button class="tab" onclick="showTab('stack',this)"><i class="ti ti-code" style="font-size:14px;margin-right:4px"></i>Stack</button>
  <button class="tab" onclick="showTab('projects',this)"><i class="ti ti-rocket" style="font-size:14px;margin-right:4px"></i>Projects</button>
  <button class="tab" onclick="showTab('exp',this)"><i class="ti ti-briefcase" style="font-size:14px;margin-right:4px"></i>Experience</button>
  <button class="tab" onclick="showTab('certs',this)"><i class="ti ti-certificate" style="font-size:14px;margin-right:4px"></i>Certs</button>
  <button class="tab" onclick="showTab('connect',this)"><i class="ti ti-at" style="font-size:14px;margin-right:4px"></i>Connect</button>
</div>

<div id="about" class="panel active">
  <p class="about-bio">Full-stack engineer specializing in AI-powered systems, automation pipelines, and cross-platform apps. Final-year IT student shipping production-grade LLM integrations and multi-agent orchestration at scale.</p>
  <div class="about-grid">
    <div class="about-card"><div class="lbl">Specialization</div><div class="val">AI agents · LangGraph</div></div>
    <div class="about-card"><div class="lbl">Full-stack</div><div class="val">React · Node.js · Flutter</div></div>
    <div class="about-card"><div class="lbl">Cloud</div><div class="val">AWS · Docker · K8s</div></div>
    <div class="about-card"><div class="lbl">Automation</div><div class="val">n8n · API pipelines</div></div>
  </div>
  <div class="section-label">Currently working on</div>
  <div class="currently-row">
    <div class="currently-item"><i class="ti ti-brain"></i>Advanced multi-agent systems and LLM reasoning</div>
    <div class="currently-item"><i class="ti ti-cloud"></i>Cloud-native architecture and serverless patterns</div>
    <div class="currently-item"><i class="ti ti-device-mobile"></i>Cross-platform mobile apps with Flutter</div>
    <div class="currently-item"><i class="ti ti-settings-automation"></i>Automation workflows and low-code platforms</div>
  </div>
</div>

<div id="stack" class="panel">
  <div class="skill-group">
    <h3>Languages</h3>
    <div class="pills">
      <span class="pill">Python</span><span class="pill">JavaScript</span><span class="pill">Dart</span><span class="pill">SQL</span><span class="pill">HTML5</span><span class="pill">CSS3</span>
    </div>
  </div>
  <div class="skill-group">
    <h3>Frontend & mobile</h3>
    <div class="pills">
      <span class="pill pill-hot">React</span><span class="pill">Next.js</span><span class="pill pill-hot">Flutter</span><span class="pill">Tailwind CSS</span><span class="pill">Bootstrap</span>
    </div>
  </div>
  <div class="skill-group">
    <h3>Backend & APIs</h3>
    <div class="pills">
      <span class="pill pill-hot">Node.js</span><span class="pill">REST APIs</span><span class="pill">WebSockets</span><span class="pill">JWT</span><span class="pill">Jest</span>
    </div>
  </div>
  <div class="skill-group">
    <h3>AI & automation</h3>
    <div class="pills">
      <span class="pill pill-hot">LangGraph</span><span class="pill pill-hot">LLM APIs</span><span class="pill">Prompt engineering</span><span class="pill">Vector DBs</span><span class="pill">n8n</span><span class="pill">Semantic search</span>
    </div>
  </div>
  <div class="skill-group">
    <h3>Cloud & DevOps</h3>
    <div class="pills">
      <span class="pill pill-hot">AWS EC2</span><span class="pill">AWS S3</span><span class="pill">IAM</span><span class="pill">CloudWatch</span><span class="pill">Docker</span><span class="pill">Kubernetes</span><span class="pill">GitHub CI/CD</span>
    </div>
  </div>
  <div class="skill-group">
    <h3>Databases</h3>
    <div class="pills">
      <span class="pill">PostgreSQL</span><span class="pill">MongoDB</span><span class="pill">MySQL</span><span class="pill">SQLite</span><span class="pill">Firebase</span>
    </div>
  </div>
</div>

<div id="projects" class="panel">
  <div class="proj-card" onclick="toggleProj(this)">
    <div class="proj-top">
      <span class="proj-title">Multi-agent recommendation engine</span>
      <i class="ti ti-chevron-down chevron"></i>
    </div>
    <div class="proj-stack">LangGraph · LLM APIs · Node.js · React · AWS</div>
    <div class="proj-desc">8-agent pipeline across Amazon, YouTube & web. Ranked results in 15–20s via 5 concurrent analyzers.</div>
    <div class="proj-stats">
      <span class="proj-stat">100+ SSE events/search</span>
      <span class="proj-stat">8 agents</span>
      <span class="proj-stat">3 LLM calls/query</span>
    </div>
    <div class="proj-detail">
      <ul>
        <li>Engineered 5 concurrent specialized analyzers delivering ranked results in 15–20 seconds per query</li>
        <li>Implemented 100+ SSE streaming events per search with adaptive confidence scoring</li>
        <li>Optimized agent orchestration using LangGraph for seamless inter-agent communication</li>
        <li>Deployed on AWS with real-time monitoring and error recovery</li>
      </ul>
    </div>
  </div>
  <div class="proj-card" onclick="toggleProj(this)">
    <div class="proj-top">
      <span class="proj-title">AI-extension builder</span>
      <i class="ti ti-chevron-down chevron"></i>
    </div>
    <div class="proj-stack">LangGraph · LLM APIs · JavaScript · React</div>
    <div class="proj-desc">Natural-language → production Chrome extension in under 30 seconds with self-correction loops.</div>
    <div class="proj-stats">
      <span class="proj-stat">&lt;30s generation</span>
      <span class="proj-stat">Zero manual scaffolding</span>
    </div>
    <div class="proj-detail">
      <ul>
        <li>Designed a parse→plan→generate→validate pipeline with self-correction loops</li>
        <li>Eliminated manual scaffolding entirely through intelligent code generation</li>
        <li>Integrated semantic validation for generated code ensuring quality and compatibility</li>
      </ul>
    </div>
  </div>
  <div class="proj-card" onclick="toggleProj(this)">
    <div class="proj-top">
      <span class="proj-title">AI-powered email automation</span>
      <i class="ti ti-chevron-down chevron"></i>
    </div>
    <div class="proj-stack">n8n · LLMs · Gmail API · WhatsApp API · Google Calendar</div>
    <div class="proj-desc">Intelligent automation across email, messaging and calendar. Zero data loss in production.</div>
    <div class="proj-stats">
      <span class="proj-stat">5+ hrs saved/week</span>
      <span class="proj-stat">Zero data loss</span>
    </div>
    <div class="proj-detail">
      <ul>
        <li>Saved 5+ hours of manual work per week through intelligent scheduling</li>
        <li>Achieved zero data loss over weeks of unattended production operation via retry logic</li>
        <li>Integrated Gmail, WhatsApp, and Google Calendar with LLM-powered smart responses</li>
      </ul>
    </div>
  </div>
  <div class="proj-card" onclick="toggleProj(this)">
    <div class="proj-top">
      <span class="proj-title">Real-time system monitor</span>
      <i class="ti ti-chevron-down chevron"></i>
    </div>
    <div class="proj-stack">Python · Flutter · WebSockets</div>
    <div class="proj-desc">Cross-platform CPU/RAM/network telemetry streaming at sub-200ms latency. Zero cloud dependencies.</div>
    <div class="proj-stats">
      <span class="proj-stat">&lt;200ms latency</span>
      <span class="proj-stat">iOS & Android</span>
      <span class="proj-stat">No cloud</span>
    </div>
    <div class="proj-detail">
      <ul>
        <li>Engineered real-time streaming of CPU, RAM, and network metrics via WebSockets</li>
        <li>Implemented remote command execution with on-device privacy</li>
        <li>Delivered native mobile experience on iOS & Android</li>
      </ul>
    </div>
  </div>
</div>

<div id="exp" class="panel">
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-dot active"></div>
      <div class="tl-title">AWS Intern</div>
      <div class="tl-meta">Cydez Technologies · 2024</div>
      <ul>
        <li>Provisioned EC2 & S3 with Python/Bash automation → 20% faster deployments</li>
        <li>Implemented IAM least-privilege roles and CloudWatch dashboards</li>
        <li>Maintained 99.9% system uptime with real-time monitoring and alerting</li>
      </ul>
    </div>
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-title">B.Tech in Information Technology</div>
      <div class="tl-meta">Viswajyothi College of Engineering & Technology · Oct 2022 – May 2026 · GPA 7.36</div>
    </div>
  </div>
</div>

<div id="certs" class="panel">
  <div class="cert-grid">
    <div class="cert-card">
      <div class="cert-icon"><i class="ti ti-brand-meta"></i></div>
      <div class="cert-name">Meta Front-End Developer</div>
      <div class="cert-by">Meta · Coursera</div>
    </div>
    <div class="cert-card">
      <div class="cert-icon"><i class="ti ti-brand-google"></i></div>
      <div class="cert-name">IT Automation with Python</div>
      <div class="cert-by">Google · Coursera</div>
    </div>
    <div class="cert-card">
      <div class="cert-icon"><i class="ti ti-cloud"></i></div>
      <div class="cert-name">AWS Cloud Technical Essentials</div>
      <div class="cert-by">AWS · Coursera</div>
    </div>
  </div>
  <div class="section-label">Education</div>
  <div class="about-card">
    <div class="lbl">Bachelor of Technology · Information Technology</div>
    <div class="val" style="margin-top:4px">Viswajyothi College of Engineering and Technology</div>
    <div style="font-size:12px;color:#888;margin-top:4px">Vazhakulam, Kerala · Expected May 2026 · GPA 7.36 / 10</div>
  </div>
</div>

<div id="connect" class="panel">
  <div class="status-row">
    <div class="status-dot"></div>
    <span>Open to full-stack, AI/backend roles and startup collaboration</span>
  </div>
  <div class="connect-grid">
    <a class="connect-btn cb-mail" href="mailto:vivek987pm@gmail.com">
      <div class="cb-icon"><i class="ti ti-mail"></i></div>
      <div><div class="cb-label">Email</div><div class="cb-val">vivek987pm@gmail.com</div></div>
    </a>
    <a class="connect-btn cb-li" href="https://www.linkedin.com/in/vivek-r-015008188">
      <div class="cb-icon"><i class="ti ti-brand-linkedin"></i></div>
      <div><div class="cb-label">LinkedIn</div><div class="cb-val">vivek-r-015008188</div></div>
    </a>
    <a class="connect-btn cb-gh" href="https://github.com/vivek123r">
      <div class="cb-icon"><i class="ti ti-brand-github"></i></div>
      <div><div class="cb-label">GitHub</div><div class="cb-val">vivek123r</div></div>
    </a>
    <a class="connect-btn cb-web" href="https://vivek123r.github.io/Portfolio/#/">
      <div class="cb-icon"><i class="ti ti-world"></i></div>
      <div><div class="cb-label">Portfolio</div><div class="cb-val">vivek123r.github.io</div></div>
    </a>
  </div>
  <div class="quote-block">"The best code is the one that solves real problems at scale."</div>
</div>

<script>
function showTab(id, el) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  el.classList.add('active');
}
function toggleProj(card) {
  const detail = card.querySelector('.proj-detail');
  const chevron = card.querySelector('.chevron');
  const isOpen = detail.classList.contains('open');
  document.querySelectorAll('.proj-detail').forEach(d => d.classList.remove('open'));
  document.querySelectorAll('.chevron').forEach(c => c.classList.remove('open'));
  document.querySelectorAll('.proj-card').forEach(c => c.classList.remove('open'));
  if (!isOpen) {
    detail.classList.add('open');
    chevron.classList.add('open');
    card.classList.add('open');
  }
}
</script>
</body>
</html>
