<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bittu Kumar — Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
  :root {
    --bg: #0a0c10;
    --bg2: #0f1117;
    --bg3: #161b22;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.12);
    --text: #e6edf3;
    --muted: #7d8590;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --accent3: #f78166;
    --accent4: #d2a8ff;
    --glow: rgba(88,166,255,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* animated grid bg */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(88,166,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(88,166,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    z-index: 0;
    pointer-events: none;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 3rem 1.5rem 5rem;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 2rem;
    align-items: center;
    margin-bottom: 4rem;
    animation: fadeUp 0.6s ease both;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(63,185,80,0.1);
    border: 1px solid rgba(63,185,80,0.3);
    color: var(--accent2);
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    padding: 4px 12px;
    border-radius: 100px;
    margin-bottom: 1.25rem;
    letter-spacing: 0.05em;
  }

  .hero-badge::before {
    content: '';
    width: 6px;
    height: 6px;
    background: var(--accent2);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  .hero h1 {
    font-family: 'Space Mono', monospace;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 700;
    line-height: 1.1;
    letter-spacing: -0.02em;
    margin-bottom: 0.75rem;
  }

  .hero h1 span {
    color: var(--accent);
    display: block;
  }

  .hero p {
    font-size: 1rem;
    color: var(--muted);
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 1.75rem;
  }

  .hero-links {
    display: flex;
    gap: 0.75rem;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 0.6rem 1.25rem;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
  }

  .btn-primary {
    background: var(--accent);
    color: #0a0c10;
    border: none;
  }
  .btn-primary:hover { background: #79c0ff; transform: translateY(-1px); }

  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border2);
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-1px); }

  .avatar-wrap {
    position: relative;
    width: 160px;
    height: 160px;
    flex-shrink: 0;
  }

  .avatar-ring {
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent4), var(--accent2), var(--accent));
    animation: spin 6s linear infinite;
  }

  .avatar-inner {
    position: absolute;
    inset: 3px;
    border-radius: 50%;
    background: var(--bg3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Space Mono', monospace;
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--accent);
    overflow: hidden;
  }

  /* ── SECTION TITLE ── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 1.25rem;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── CARDS GRID ── */
  .grid-2 { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; }
  .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 1rem; }
  .grid-4 { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 0.75rem; }

  .card {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.25rem;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }
  .card:hover {
    border-color: var(--border2);
    transform: translateY(-2px);
    background: #1c2128;
  }
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(88,166,255,0.4), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .card:hover::before { opacity: 1; }

  .card-icon {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    margin-bottom: 0.9rem;
  }
  .icon-blue { background: rgba(88,166,255,0.1); color: var(--accent); }
  .icon-green { background: rgba(63,185,80,0.1); color: var(--accent2); }
  .icon-purple { background: rgba(210,168,255,0.1); color: var(--accent4); }
  .icon-orange { background: rgba(247,129,102,0.1); color: var(--accent3); }

  .card h3 {
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 0.4rem;
    color: var(--text);
  }
  .card p {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ── TECH STACK ── */
  .tech-section { margin-bottom: 3rem; }

  .tech-category {
    margin-bottom: 1.5rem;
  }

  .tech-category-title {
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    letter-spacing: 0.08em;
    margin-bottom: 0.75rem;
    text-transform: uppercase;
  }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .pill {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 6px 14px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    background: var(--bg3);
    border: 1px solid var(--border);
    color: var(--text);
    transition: all 0.2s;
    cursor: default;
  }
  .pill:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(88,166,255,0.05);
  }
  .pill i { font-size: 16px; }

  /* ── STATS ── */
  .stat-card {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.5rem;
    text-align: center;
  }
  .stat-number {
    font-family: 'Space Mono', monospace;
    font-size: 2rem;
    font-weight: 700;
    color: var(--accent);
    display: block;
    margin-bottom: 0.25rem;
  }
  .stat-label {
    font-size: 12px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  /* ── QUOTE ── */
  .quote-block {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: 0 12px 12px 0;
    padding: 1.5rem 1.75rem;
    margin: 3rem 0;
    position: relative;
  }
  .quote-block p {
    font-size: 1.05rem;
    font-style: italic;
    color: var(--text);
    line-height: 1.7;
  }
  .quote-block::before {
    content: '"';
    font-family: 'Space Mono', monospace;
    font-size: 4rem;
    color: var(--accent);
    opacity: 0.2;
    position: absolute;
    top: -0.5rem;
    left: 1rem;
    line-height: 1;
  }

  /* ── SOCIAL ── */
  .social-strip {
    display: flex;
    gap: 0.75rem;
    flex-wrap: wrap;
    margin-top: 1rem;
  }
  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 0.65rem 1.1rem;
    border-radius: 10px;
    border: 1px solid var(--border);
    background: var(--bg3);
    color: var(--text);
    text-decoration: none;
    font-size: 14px;
    font-weight: 500;
    transition: all 0.2s;
  }
  .social-btn:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }
  .social-btn i { font-size: 18px; }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }
  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .section { margin-bottom: 3.5rem; animation: fadeUp 0.6s ease both; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }

  /* ── MOBILE ── */
  @media (max-width: 600px) {
    .hero { grid-template-columns: 1fr; }
    .avatar-wrap { width: 100px; height: 100px; margin: 0 auto; order: -1; }
    .hero-links { flex-direction: column; }
    .btn { justify-content: center; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-text">
      <div class="hero-badge">
        <span>Available for opportunities</span>
      </div>
      <h1>Hey, I'm<span>Bittu Kumar 👋</span></h1>
      <p>Full Stack MERN Developer building scalable web and mobile applications. Passionate about crafting responsive UIs, robust REST APIs, and production-ready SaaS products. Currently exploring React Native and advanced system design.</p>
      <div class="hero-links">
        <a href="mailto:bk7355583@gmail.com" class="btn btn-primary">
          <i class="ti ti-mail"></i> Get in Touch
        </a>
        <a href="https://github.com/B2Kumar03" class="btn btn-outline">
          <i class="ti ti-brand-github"></i> GitHub
        </a>
        <a href="https://www.linkedin.com/in/bittu-kumar-2b54b0267/" class="btn btn-outline">
          <i class="ti ti-brand-linkedin"></i> LinkedIn
        </a>
      </div>
    </div>
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <div class="avatar-inner">BK</div>
    </div>
  </div>

  <!-- FOCUS -->
  <div class="section">
    <div class="section-label"><i class="ti ti-bolt"></i> Current Focus</div>
    <div class="grid-2">
      <div class="card">
        <div class="card-icon icon-blue"><i class="ti ti-world"></i></div>
        <h3>Web Applications & SaaS</h3>
        <p>Building scalable full-stack products with modern architecture and clean deployment pipelines.</p>
      </div>
      <div class="card">
        <div class="card-icon icon-green"><i class="ti ti-device-mobile"></i></div>
        <h3>React Native & Mobile</h3>
        <p>Expanding into cross-platform mobile development with Expo and React Native.</p>
      </div>
      <div class="card">
        <div class="card-icon icon-purple"><i class="ti ti-layout-dashboard"></i></div>
        <h3>Landing Pages & Platforms</h3>
        <p>Crafting high-converting interfaces with pixel-perfect responsive design.</p>
      </div>
      <div class="card">
        <div class="card-icon icon-orange"><i class="ti ti-topology-star-ring"></i></div>
        <h3>DSA & System Design</h3>
        <p>Sharpening problem-solving skills and designing scalable, fault-tolerant systems.</p>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-label"><i class="ti ti-stack-2"></i> Tech Stack</div>

    <div class="tech-category">
      <div class="tech-category-title">Languages</div>
      <div class="tech-pills">
        <div class="pill"><i class="ti ti-brand-javascript"></i> JavaScript</div>
        <div class="pill"><i class="ti ti-brand-typescript"></i> TypeScript</div>
        <div class="pill"><i class="ti ti-brand-python"></i> Python</div>
        <div class="pill"><i class="ti ti-code"></i> C / C++</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="tech-category-title">Frontend</div>
      <div class="tech-pills">
        <div class="pill"><i class="ti ti-brand-react"></i> React.js</div>
        <div class="pill"><i class="ti ti-device-mobile-code"></i> React Native</div>
        <div class="pill"><i class="ti ti-brand-html5"></i> HTML5</div>
        <div class="pill"><i class="ti ti-brand-css3"></i> CSS3</div>
        <div class="pill"><i class="ti ti-wind"></i> Tailwind CSS</div>
        <div class="pill"><i class="ti ti-arrows-shuffle"></i> Redux</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="tech-category-title">Backend</div>
      <div class="tech-pills">
        <div class="pill"><i class="ti ti-brand-nodejs"></i> Node.js</div>
        <div class="pill"><i class="ti ti-server"></i> Express.js</div>
        <div class="pill"><i class="ti ti-lock"></i> JWT Auth</div>
        <div class="pill"><i class="ti ti-api"></i> REST APIs</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="tech-category-title">Tools & Database</div>
      <div class="tech-pills">
        <div class="pill"><i class="ti ti-leaf"></i> MongoDB</div>
        <div class="pill"><i class="ti ti-brand-git"></i> Git</div>
        <div class="pill"><i class="ti ti-brand-github"></i> GitHub</div>
        <div class="pill"><i class="ti ti-api-app"></i> Postman</div>
        <div class="pill"><i class="ti ti-brand-vercel"></i> Vercel</div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-label"><i class="ti ti-chart-bar"></i> GitHub Activity</div>
    <div class="grid-4">
      <div class="stat-card">
        <span class="stat-number">20+</span>
        <span class="stat-label">Repositories</span>
      </div>
      <div class="stat-card">
        <span class="stat-number">MERN</span>
        <span class="stat-label">Primary Stack</span>
      </div>
      <div class="stat-card">
        <span class="stat-number">2+</span>
        <span class="stat-label">Years Coding</span>
      </div>
      <div class="stat-card">
        <span class="stat-number">∞</span>
        <span class="stat-label">Problems Solved</span>
      </div>
    </div>
    <br>
    <div style="background: var(--bg3); border: 1px solid var(--border); border-radius: 12px; padding: 1rem; text-align: center;">
      <img src="https://github-readme-stats.vercel.app/api?username=B2Kumar03&show_icons=true&theme=github_dark&hide_border=true&bg_color=00000000&title_color=58a6ff&icon_color=58a6ff&text_color=7d8590" alt="GitHub Stats" style="max-width: 100%; height: auto; border-radius: 8px;" />
    </div>
  </div>

  <!-- HOBBIES -->
  <div class="section">
    <div class="section-label"><i class="ti ti-heart"></i> Interests & Hobbies</div>
    <div class="grid-4">
      <div class="card" style="text-align: center;">
        <div class="card-icon icon-blue" style="margin: 0 auto 0.75rem;"><i class="ti ti-code"></i></div>
        <h3 style="font-size:13px;">Building Projects</h3>
      </div>
      <div class="card" style="text-align: center;">
        <div class="card-icon icon-green" style="margin: 0 auto 0.75rem;"><i class="ti ti-book"></i></div>
        <h3 style="font-size:13px;">Tech & Startups</h3>
      </div>
      <div class="card" style="text-align: center;">
        <div class="card-icon icon-purple" style="margin: 0 auto 0.75rem;"><i class="ti ti-puzzle"></i></div>
        <h3 style="font-size:13px;">Coding Challenges</h3>
      </div>
      <div class="card" style="text-align: center;">
        <div class="card-icon icon-orange" style="margin: 0 auto 0.75rem;"><i class="ti ti-rocket"></i></div>
        <h3 style="font-size:13px;">Product Ideas</h3>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="quote-block">
    <p>I don't just write code — I build products that solve real problems.</p>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-label"><i class="ti ti-at"></i> Connect with me</div>
    <div class="social-strip">
      <a href="https://www.linkedin.com/in/bittu-kumar-2b54b0267/" class="social-btn">
        <i class="ti ti-brand-linkedin"></i> LinkedIn
      </a>
      <a href="https://github.com/B2Kumar03" class="social-btn">
        <i class="ti ti-brand-github"></i> GitHub
      </a>
      <a href="mailto:bk7355583@gmail.com" class="social-btn">
        <i class="ti ti-mail"></i> bk7355583@gmail.com
      </a>
    </div>
  </div>

</div>
</body>
</html>
