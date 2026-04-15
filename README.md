
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Cyrus Maina — Data Analyst & AI Specialist</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0e1a;
    --bg2: #0f1525;
    --surface: #141c30;
    --border: #1e2a45;
    --accent: #3b82f6;
    --accent2: #06b6d4;
    --gold: #f59e0b;
    --text: #e8edf5;
    --muted: #6b7fa3;
    --faint: #1a2540;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Mono', monospace;
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    position: fixed;
    width: 12px; height: 12px;
    background: var(--accent);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s, width 0.2s, height 0.2s, background 0.2s;
  }
  .cursor-ring {
    position: fixed;
    width: 36px; height: 36px;
    border: 1.5px solid rgba(59,130,246,0.5);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: transform 0.15s ease-out, width 0.3s, height 0.3s;
  }
  body:has(a:hover) .cursor, body:has(button:hover) .cursor { width: 20px; height: 20px; background: var(--gold); }
  body:has(a:hover) .cursor-ring, body:has(button:hover) .cursor-ring { width: 56px; height: 56px; }

  /* Noise overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1;
    opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 1.25rem 3rem;
    display: flex; justify-content: space-between; align-items: center;
    border-bottom: 1px solid transparent;
    transition: all 0.3s;
    backdrop-filter: blur(0px);
  }
  nav.scrolled {
    background: rgba(10,14,26,0.92);
    border-color: var(--border);
    backdrop-filter: blur(16px);
  }
  .nav-logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    letter-spacing: 0.08em;
    color: var(--text);
    text-decoration: none;
  }
  .nav-logo span { color: var(--accent); }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    font-size: 0.72rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 8rem 4rem 6rem 5rem;
    position: relative;
    z-index: 2;
  }

  .hero-tag {
    font-size: 0.68rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1.5rem;
    display: flex; align-items: center; gap: 0.75rem;
  }
  .hero-tag::before {
    content: '';
    display: block;
    width: 2rem; height: 1px;
    background: var(--accent);
  }

  .hero-name {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(3.5rem, 6vw, 6rem);
    line-height: 1.0;
    color: var(--text);
    margin-bottom: 0.5rem;
  }
  .hero-name em {
    font-style: italic;
    color: var(--accent2);
  }

  .hero-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 2rem;
    margin-top: 0.5rem;
  }

  .hero-bio {
    font-size: 0.82rem;
    line-height: 1.9;
    color: var(--muted);
    max-width: 400px;
    margin-bottom: 3rem;
  }

  .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }

  .btn-primary {
    display: inline-block;
    padding: 0.75rem 2rem;
    background: var(--accent);
    color: #fff;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    border: none;
    cursor: pointer;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
    transition: background 0.2s, transform 0.2s;
  }
  .btn-primary:hover { background: var(--accent2); transform: translateY(-2px); }

  .btn-ghost {
    display: inline-block;
    padding: 0.75rem 2rem;
    border: 1px solid var(--border);
    color: var(--muted);
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    cursor: pointer;
    background: transparent;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
    transition: border-color 0.2s, color 0.2s;
  }
  .btn-ghost:hover { border-color: var(--accent); color: var(--text); }

  /* Hero right — data viz decoration */
  .hero-right {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
  }

  .data-orb {
    position: absolute;
    width: 420px; height: 420px;
    border-radius: 50%;
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
  }
  .data-orb::before, .data-orb::after {
    content: '';
    position: absolute;
    border-radius: 50%;
    border: 1px solid var(--faint);
  }
  .data-orb::before { inset: -40px; }
  .data-orb::after { inset: -80px; border-color: rgba(30,42,69,0.5); }

  .orb-inner {
    width: 280px; height: 280px;
    border-radius: 50%;
    background: radial-gradient(circle at 40% 40%, rgba(59,130,246,0.15), rgba(6,182,212,0.05), transparent 70%);
    border: 1px solid rgba(59,130,246,0.2);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    gap: 0.4rem;
  }

  .orb-stat { text-align: center; }
  .orb-stat .num {
    font-family: 'Syne', sans-serif;
    font-size: 2.2rem;
    font-weight: 800;
    color: var(--text);
    line-height: 1;
  }
  .orb-stat .label {
    font-size: 0.62rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
  }
  .orb-divider {
    width: 1px; height: 24px;
    background: var(--border);
    margin: 0.2rem auto;
  }

  /* Floating tags */
  .float-tag {
    position: absolute;
    padding: 0.4rem 0.9rem;
    background: var(--surface);
    border: 1px solid var(--border);
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    color: var(--accent);
    text-transform: uppercase;
    animation: floatTag 4s ease-in-out infinite;
    clip-path: polygon(0 0, calc(100% - 6px) 0, 100% 6px, 100% 100%, 6px 100%, 0 calc(100% - 6px));
  }
  .float-tag:nth-child(1) { top: 20%; left: -5%; animation-delay: 0s; }
  .float-tag:nth-child(2) { top: 65%; right: 0%; animation-delay: 1.3s; }
  .float-tag:nth-child(3) { bottom: 18%; left: 5%; animation-delay: 2.6s; }

  @keyframes floatTag {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
  }

  /* Connecting dots */
  .hero-grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      radial-gradient(circle at 70% 50%, rgba(59,130,246,0.06) 0%, transparent 60%),
      radial-gradient(circle at 30% 30%, rgba(6,182,212,0.04) 0%, transparent 50%);
  }

  /* SECTION BASE */
  section {
    padding: 7rem 5rem;
    position: relative;
    z-index: 2;
  }

  .section-header {
    display: flex; align-items: flex-end; gap: 2rem;
    margin-bottom: 4rem;
  }
  .section-num {
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    color: var(--accent);
    text-transform: uppercase;
    padding-bottom: 0.15rem;
  }
  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2rem, 3.5vw, 3rem);
    line-height: 1;
    color: var(--text);
  }
  .section-title em { font-style: italic; color: var(--accent2); }
  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
    margin-bottom: 0.4rem;
  }

  /* ABOUT */
  #about { background: var(--bg2); }
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }
  .about-text p {
    font-size: 0.82rem;
    line-height: 1.95;
    color: var(--muted);
    margin-bottom: 1.25rem;
  }
  .about-text p strong { color: var(--text); font-weight: 500; }
  .about-highlights {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }
  .highlight-card {
    padding: 1.5rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: 2px solid var(--accent);
    transition: border-color 0.2s, transform 0.2s;
  }
  .highlight-card:hover { border-color: var(--accent2); transform: translateY(-3px); }
  .highlight-card .hc-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 0.4rem;
  }
  .highlight-card .hc-label {
    font-size: 0.68rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* EXPERIENCE */
  #experience { background: var(--bg); }
  .timeline { position: relative; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 8px; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent), var(--border), transparent);
  }
  .timeline-item {
    padding-left: 2.5rem;
    padding-bottom: 3rem;
    position: relative;
  }
  .timeline-item::before {
    content: '';
    position: absolute;
    left: -4px; top: 8px;
    width: 9px; height: 9px;
    border-radius: 50%;
    background: var(--accent);
    border: 2px solid var(--bg);
    box-shadow: 0 0 12px rgba(59,130,246,0.5);
  }
  .timeline-item.current::before {
    background: var(--gold);
    box-shadow: 0 0 12px rgba(245,158,11,0.5);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 12px rgba(245,158,11,0.5); }
    50% { box-shadow: 0 0 24px rgba(245,158,11,0.8); }
  }
  .ti-meta {
    display: flex; align-items: baseline; gap: 1rem;
    margin-bottom: 0.4rem; flex-wrap: wrap;
  }
  .ti-company {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--text);
  }
  .ti-date {
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    padding: 0.2rem 0.6rem;
    border: 1px solid rgba(59,130,246,0.3);
    background: rgba(59,130,246,0.05);
  }
  .ti-date.active {
    color: var(--gold);
    border-color: rgba(245,158,11,0.3);
    background: rgba(245,158,11,0.05);
  }
  .ti-role {
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.8rem;
  }
  .ti-bullets { list-style: none; }
  .ti-bullets li {
    font-size: 0.78rem;
    line-height: 1.8;
    color: var(--muted);
    padding-left: 1rem;
    position: relative;
    margin-bottom: 0.25rem;
  }
  .ti-bullets li::before {
    content: '→';
    position: absolute; left: 0;
    color: var(--accent);
    font-size: 0.65rem;
  }

  /* SKILLS */
  #skills { background: var(--bg2); }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  .skill-card {
    padding: 2rem;
    background: var(--surface);
    border: 1px solid var(--border);
    position: relative;
    overflow: hidden;
    transition: transform 0.2s, border-color 0.2s;
  }
  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }
  .skill-card:hover::before { transform: scaleX(1); }
  .skill-card:hover { transform: translateY(-4px); border-color: rgba(59,130,246,0.3); }
  .skill-card-icon {
    font-size: 1.4rem;
    margin-bottom: 1rem;
  }
  .skill-card-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--text);
    margin-bottom: 1rem;
  }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .skill-tag {
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.25rem 0.6rem;
    background: var(--faint);
    border: 1px solid var(--border);
    color: var(--muted);
    transition: color 0.2s, border-color 0.2s;
  }
  .skill-card:hover .skill-tag {
    border-color: rgba(59,130,246,0.25);
    color: var(--text);
  }

  /* EDUCATION */
  #education { background: var(--bg); }
  .edu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
  .edu-card {
    padding: 2.5rem;
    background: var(--surface);
    border: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }
  .edu-card::after {
    content: '';
    position: absolute;
    top: -30px; right: -30px;
    width: 80px; height: 80px;
    border-radius: 50%;
    border: 1px solid var(--border);
    opacity: 0.5;
  }
  .edu-deg {
    font-family: 'DM Serif Display', serif;
    font-size: 1.3rem;
    color: var(--text);
    margin-bottom: 0.4rem;
    line-height: 1.2;
  }
  .edu-school {
    font-family: 'Syne', sans-serif;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.5rem;
  }
  .edu-meta {
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    color: var(--muted);
    margin-bottom: 1rem;
  }
  .edu-badge {
    display: inline-block;
    padding: 0.25rem 0.7rem;
    background: rgba(245,158,11,0.1);
    border: 1px solid rgba(245,158,11,0.3);
    color: var(--gold);
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* CONTACT */
  #contact {
    background: var(--bg2);
    text-align: center;
  }
  .contact-inner {
    max-width: 600px;
    margin: 0 auto;
  }
  .contact-big {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    line-height: 1.05;
    color: var(--text);
    margin-bottom: 1rem;
  }
  .contact-big em { font-style: italic; color: var(--accent2); }
  .contact-sub {
    font-size: 0.78rem;
    line-height: 1.8;
    color: var(--muted);
    margin-bottom: 3rem;
  }
  .contact-links {
    display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;
    margin-bottom: 3rem;
  }
  .contact-pill {
    display: flex; align-items: center; gap: 0.5rem;
    padding: 0.6rem 1.2rem;
    border: 1px solid var(--border);
    color: var(--muted);
    text-decoration: none;
    font-size: 0.72rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: all 0.2s;
  }
  .contact-pill:hover {
    background: var(--surface);
    color: var(--text);
    border-color: var(--accent);
  }

  /* FOOTER */
  footer {
    padding: 2rem 5rem;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    color: var(--muted);
    text-transform: uppercase;
    position: relative;
    z-index: 2;
  }

  /* ANIMATIONS */
  .fade-up {
    opacity: 0;
    transform: translateY(28px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-up.visible { opacity: 1; transform: translateY(0); }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    section { padding: 5rem 2rem; }
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    #hero { grid-template-columns: 1fr; }
    .hero-left { padding: 7rem 2rem 4rem; }
    .hero-right { display: none; }
    .about-grid, .edu-grid, .skills-grid { grid-template-columns: 1fr; }
    footer { padding: 1.5rem 2rem; flex-direction: column; gap: 0.5rem; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav id="nav">
  <a class="nav-logo" href="#hero">CM<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-left">
    <div class="hero-tag">Data Analyst &amp; AI Specialist</div>
    <h1 class="hero-name">Cyrus<br><em>Maina</em></h1>
    <div class="hero-title">BSc Statistics · University of Nairobi</div>
    <p class="hero-bio">
      Turning raw data into actionable intelligence. Specialising in data annotation,
      AI model development support, and statistical analysis—with tools like Python,
      R, and SQL powering every insight.
    </p>
    <div class="hero-btns">
      <a class="btn-primary" href="#contact">Get in Touch</a>
      <a class="btn-ghost" href="#experience">View Work</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="float-tag">Python · R · SQL</div>
    <div class="float-tag">Machine Learning</div>
    <div class="float-tag">Data Annotation</div>
    <div class="data-orb">
      <div class="orb-inner">
        <div class="orb-stat">
          <div class="num">2+</div>
          <div class="label">Years Experience</div>
        </div>
        <div class="orb-divider"></div>
        <div class="orb-stat">
          <div class="num">3</div>
          <div class="label">AI Platforms</div>
        </div>
        <div class="orb-divider"></div>
        <div class="orb-stat">
          <div class="num">∞</div>
          <div class="label">Data Points</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-header fade-up">
    <span class="section-num">01</span>
    <h2 class="section-title">About <em>Me</em></h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="about-text fade-up">
      <p>
        I'm a <strong>Statistics student at the University of Nairobi</strong> with a strong passion
        for extracting meaning from data. My academic foundation in probability, inference,
        and statistical modelling complements my hands-on industry experience.
      </p>
      <p>
        Over the past two years I've worked with globally recognised AI companies—
        <strong>Atlas Capture, Telus International AI, and TransPerfect</strong>—contributing
        to machine learning pipelines through high-quality data labelling, annotation,
        and collection.
      </p>
      <p>
        Beyond technical work, I serve as <strong>Vice Chairperson of the Mathematics
        Association of Nairobi University</strong>, leading academic initiatives and
        community events for 200+ students.
      </p>
      <p>
        I'm bilingual in <strong>English and Swahili</strong> and open to remote and
        on-site opportunities in data science, analytics, and AI.
      </p>
    </div>
    <div class="about-highlights fade-up">
      <div class="highlight-card">
        <div class="hc-num">2+</div>
        <div class="hc-label">Years in AI & Data</div>
      </div>
      <div class="highlight-card">
        <div class="hc-num">3</div>
        <div class="hc-label">Global AI Firms</div>
      </div>
      <div class="highlight-card">
        <div class="hc-num">200+</div>
        <div class="hc-label">Students Led (MANU)</div>
      </div>
      <div class="highlight-card">
        <div class="hc-num">B+</div>
        <div class="hc-label">Academic Grade</div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header fade-up">
    <span class="section-num">02</span>
    <h2 class="section-title">Experi<em>ence</em></h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline">

    <div class="timeline-item current fade-up">
      <div class="ti-meta">
        <span class="ti-company">Atlas Capture</span>
        <span class="ti-date active">Dec 2025 — Present</span>
      </div>
      <div class="ti-role">Data Labeler · Remote</div>
      <ul class="ti-bullets">
        <li>Label and annotate diverse datasets to support ML model training and validation.</li>
        <li>Maintain strict quality assurance protocols ensuring data accuracy and consistency.</li>
        <li>Collaborate cross-functionally to meet project deadlines and volume targets.</li>
      </ul>
    </div>

    <div class="timeline-item current fade-up">
      <div class="ti-meta">
        <span class="ti-company">Telus International AI</span>
        <span class="ti-date active">Jan 2024 — Present</span>
      </div>
      <div class="ti-role">AI Data Rater · Remote (USA)</div>
      <ul class="ti-bullets">
        <li>Evaluate and rate AI-generated content to improve model accuracy and relevance.</li>
        <li>Perform data annotation and collection for NLP and computer vision pipelines.</li>
        <li>Consistently maintain high accuracy rates and meet daily throughput targets.</li>
      </ul>
    </div>

    <div class="timeline-item fade-up">
      <div class="ti-meta">
        <span class="ti-company">TransPerfect</span>
        <span class="ti-date">Jan 2024 — Aug 2024</span>
      </div>
      <div class="ti-role">Data Contributor · Remote (USA)</div>
      <ul class="ti-bullets">
        <li>Collected, processed, and uploaded structured datasets into AI/ML pipelines.</li>
        <li>Followed precise contribution protocols to ensure data integrity and usability.</li>
      </ul>
    </div>

    <div class="timeline-item fade-up">
      <div class="ti-meta">
        <span class="ti-company">Mathematics Association of Nairobi University</span>
        <span class="ti-date active">Jun 2024 — Present</span>
      </div>
      <div class="ti-role">Vice Chairperson · Nairobi, Kenya</div>
      <ul class="ti-bullets">
        <li>Elected to co-lead a 200+ member academic association focused on mathematics.</li>
        <li>Organise workshops, academic events, and peer mentorship programmes.</li>
        <li>Advocate for student resources and liaise between students and faculty.</li>
      </ul>
    </div>

  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header fade-up">
    <span class="section-num">03</span>
    <h2 class="section-title">Tech <em>Stack</em></h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-card fade-up">
      <div class="skill-card-icon">📊</div>
      <div class="skill-card-title">Data Analysis</div>
      <div class="skill-tags">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">R</span>
        <span class="skill-tag">Excel</span>
        <span class="skill-tag">SQL</span>
        <span class="skill-tag">Statistical Inference</span>
      </div>
    </div>
    <div class="skill-card fade-up">
      <div class="skill-card-icon">🏷️</div>
      <div class="skill-card-title">Data Annotation</div>
      <div class="skill-tags">
        <span class="skill-tag">Image Labeling</span>
        <span class="skill-tag">NLP Annotation</span>
        <span class="skill-tag">QA Protocols</span>
        <span class="skill-tag">RLHF</span>
      </div>
    </div>
    <div class="skill-card fade-up">
      <div class="skill-card-icon">🤖</div>
      <div class="skill-card-title">Machine Learning</div>
      <div class="skill-tags">
        <span class="skill-tag">Supervised Learning</span>
        <span class="skill-tag">Model Evaluation</span>
        <span class="skill-tag">NLP Basics</span>
        <span class="skill-tag">Feature Engineering</span>
      </div>
    </div>
    <div class="skill-card fade-up">
      <div class="skill-card-icon">📈</div>
      <div class="skill-card-title">Visualisation</div>
      <div class="skill-tags">
        <span class="skill-tag">Tableau</span>
        <span class="skill-tag">Matplotlib</span>
        <span class="skill-tag">ggplot2</span>
        <span class="skill-tag">Seaborn</span>
      </div>
    </div>
    <div class="skill-card fade-up">
      <div class="skill-card-icon">🗄️</div>
      <div class="skill-card-title">Databases</div>
      <div class="skill-tags">
        <span class="skill-tag">SQL</span>
        <span class="skill-tag">Data Cleaning</span>
        <span class="skill-tag">Data Manipulation</span>
        <span class="skill-tag">ETL Basics</span>
      </div>
    </div>
    <div class="skill-card fade-up">
      <div class="skill-card-icon">🧩</div>
      <div class="skill-card-title">Soft Skills</div>
      <div class="skill-tags">
        <span class="skill-tag">Attention to Detail</span>
        <span class="skill-tag">Leadership</span>
        <span class="skill-tag">Communication</span>
        <span class="skill-tag">Problem Solving</span>
      </div>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header fade-up">
    <span class="section-num">04</span>
    <h2 class="section-title">Educa<em>tion</em></h2>
    <div class="section-line"></div>
  </div>
  <div class="edu-grid">
    <div class="edu-card fade-up">
      <div class="edu-school">University of Nairobi</div>
      <div class="edu-deg">BSc Statistics<br>(In Progress)</div>
      <div class="edu-meta">Nairobi, Kenya · Sept 2022 – Present</div>
      <p style="font-size:0.75rem;color:var(--muted);line-height:1.8;margin-bottom:1rem;">
        Core modules include Statistical Inference, Probability Theory, Data Analysis,
        Machine Learning, and Database Systems.
      </p>
      <span class="edu-badge">Currently Enrolled</span>
    </div>
    <div class="edu-card fade-up">
      <div class="edu-school">Kangema High School</div>
      <div class="edu-deg">Kenya Certificate of Secondary Education</div>
      <div class="edu-meta">Muranga, Kenya · Jan 2018 – Jul 2021</div>
      <p style="font-size:0.75rem;color:var(--muted);line-height:1.8;margin-bottom:1rem;">
        Strong performance in Mathematics and Sciences.
        Developed analytical foundations that underpin current technical work.
      </p>
      <span class="edu-badge">Grade: B+</span>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div class="section-header fade-up" style="justify-content:center;margin-bottom:2rem;">
      <span class="section-num">05</span>
      <h2 class="section-title">Let's <em>Connect</em></h2>
    </div>
    <h2 class="contact-big fade-up">Open to <em>new</em><br>opportunities</h2>
    <p class="contact-sub fade-up">
      Whether you have a project in mind, a role to fill, or just want to talk data —
      I'd love to hear from you. Based in Nairobi, available globally.
    </p>
    <div class="contact-links fade-up">
      <a class="contact-pill" href="mailto:cyrusmaina628@gmail.com">
        ✉ cyrusmaina628@gmail.com
      </a>
      <a class="contact-pill" href="tel:+254769648365">
        📞 (+254) 769-648-365
      </a>
      <a class="contact-pill" href="https://linkedin.com/in/cyrusmaina" target="_blank">
        in LinkedIn
      </a>
    </div>
    <a class="btn-primary" href="mailto:cyrusmaina628@gmail.com" style="font-size:0.75rem;">
      Send a Message →
    </a>
  </div>
</section>

<footer>
  <span>© 2026 Cyrus Maina</span>
  <span>Nairobi, Kenya</span>
  <span>Built with ♥ &amp; data</span>
</footer>

<script>
  // Cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });
  function animateCursor() {
    cursor.style.left = mx + 'px'; cursor.style.top = my + 'px';
    rx += (mx - rx) * 0.12; ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px'; ring.style.top = ry + 'px';
    requestAnimationFrame(animateCursor);
  }
  animateCursor();

  // Nav scroll
  window.addEventListener('scroll', () => {
    document.getElementById('nav').classList.toggle('scrolled', window.scrollY > 40);
  });

  // Fade-up observer
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Stagger children
  document.querySelectorAll('.skills-grid, .about-highlights, .edu-grid').forEach(parent => {
    [...parent.querySelectorAll('.fade-up')].forEach((el, i) => {
      el.style.transitionDelay = (i * 0.1) + 's';
    });
  });
</script>
</body>
</html>
