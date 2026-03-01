<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>XonKiv — Innovate Your Workflow</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,700;1,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --dark: #151515;
    --mid-dark: #2a2a2a;
    --mid: #555;
    --mid-light: #888;
    --light: #c8c8c8;
    --lighter: #e8e8e8;
    --white: #f7f7f7;
    --accent: #ffffff;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--black);
    color: var(--lighter);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 3rem;
    background: rgba(10,10,10,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--mid-dark);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem; letter-spacing: .12em;
    color: var(--white); text-decoration: none;
  }
  .nav-logo span { color: var(--mid-light); }
  .nav-links { display: flex; gap: 2.2rem; list-style: none; }
  .nav-links a {
    font-family: 'DM Mono', monospace; font-size: .78rem; letter-spacing: .1em;
    color: var(--mid-light); text-decoration: none; text-transform: uppercase;
    transition: color .25s;
  }
  .nav-links a:hover { color: var(--white); }
  .nav-cta {
    font-family: 'DM Mono', monospace; font-size: .78rem; letter-spacing: .1em;
    text-transform: uppercase; text-decoration: none;
    padding: .6rem 1.4rem; border: 1px solid var(--mid);
    color: var(--lighter); transition: all .25s;
  }
  .nav-cta:hover { background: var(--white); color: var(--black); border-color: var(--white); }

  /* ── SECTIONS ── */
  section { padding: 7rem 3rem; }

  .section-label {
    font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .25em;
    text-transform: uppercase; color: var(--mid-light); margin-bottom: 1rem;
    display: flex; align-items: center; gap: .8rem;
  }
  .section-label::before { content: ''; display: block; width: 2rem; height: 1px; background: var(--mid); }

  h1, h2, h3 { font-family: 'Bebas Neue', sans-serif; letter-spacing: .06em; line-height: 1; }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: 0 3rem 6rem;
    position: relative;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0; z-index: 0;
    background: radial-gradient(ellipse 80% 60% at 70% 30%, #2a2a2a 0%, #0a0a0a 70%);
  }
  .hero-grid {
    position: absolute; inset: 0; z-index: 1;
    background-image: linear-gradient(rgba(255,255,255,.03) 1px, transparent 1px),
                      linear-gradient(90deg, rgba(255,255,255,.03) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 100% 100% at 50% 0%, black 0%, transparent 80%);
  }
  .hero-content { position: relative; z-index: 2; max-width: 900px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: .6rem;
    font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .18em; text-transform: uppercase;
    color: var(--mid-light); border: 1px solid var(--mid-dark);
    padding: .4rem 1rem; margin-bottom: 2.5rem;
  }
  .hero-badge::before { content: '●'; font-size: .5rem; color: var(--mid-light); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }

  .hero-title {
    font-size: clamp(5rem, 14vw, 13rem);
    color: var(--white); line-height: .92;
    margin-bottom: 2rem;
  }
  .hero-title .hollow {
    -webkit-text-stroke: 1px var(--mid);
    color: transparent;
  }
  .hero-sub {
    font-size: 1.1rem; font-weight: 300; color: var(--mid-light);
    max-width: 480px; line-height: 1.7; margin-bottom: 3rem;
  }
  .hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; }
  .btn-primary {
    font-family: 'DM Mono', monospace; font-size: .82rem; letter-spacing: .1em; text-transform: uppercase;
    text-decoration: none; padding: 1rem 2.5rem;
    background: var(--white); color: var(--black);
    transition: all .25s;
  }
  .btn-primary:hover { background: var(--lighter); }
  .btn-ghost {
    font-family: 'DM Mono', monospace; font-size: .82rem; letter-spacing: .1em; text-transform: uppercase;
    text-decoration: none; padding: 1rem 2.5rem;
    border: 1px solid var(--mid); color: var(--lighter);
    transition: all .25s;
  }
  .btn-ghost:hover { border-color: var(--white); color: var(--white); }

  .hero-scroll {
    position: absolute; bottom: 2.5rem; right: 3rem; z-index: 2;
    font-family: 'DM Mono', monospace; font-size: .65rem; letter-spacing: .2em; text-transform: uppercase;
    color: var(--mid); writing-mode: vertical-rl;
    display: flex; align-items: center; gap: .8rem;
  }
  .hero-scroll::after { content: ''; width: 1px; height: 3rem; background: var(--mid); }

  /* ── ABOUT ── */
  #about { background: var(--dark); }
  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center;
    margin-top: 4rem;
  }
  .about-title { font-size: clamp(3rem, 6vw, 6rem); color: var(--white); margin-bottom: 2rem; }
  .about-body { font-weight: 300; line-height: 1.8; color: var(--mid-light); font-size: 1.05rem; }
  .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 3rem; }
  .stat-card {
    padding: 1.5rem; border: 1px solid var(--mid-dark);
    background: var(--black);
  }
  .stat-number { font-family: 'Bebas Neue', sans-serif; font-size: 3rem; color: var(--white); line-height: 1; }
  .stat-label { font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .15em; text-transform: uppercase; color: var(--mid); margin-top: .4rem; }
  .values-list { margin-top: 2rem; display: flex; flex-direction: column; gap: 1rem; }
  .value-item {
    display: flex; align-items: flex-start; gap: 1rem;
    padding: 1.2rem; border-left: 2px solid var(--mid-dark);
    transition: border-color .25s;
  }
  .value-item:hover { border-left-color: var(--white); }
  .value-icon { font-size: 1.4rem; min-width: 2rem; }
  .value-title { font-family: 'DM Mono', monospace; font-size: .8rem; letter-spacing: .1em; text-transform: uppercase; color: var(--lighter); margin-bottom: .3rem; }
  .value-desc { font-size: .9rem; color: var(--mid-light); font-weight: 300; line-height: 1.6; }

  /* ── SERVICES ── */
  #services { background: var(--black); }
  .services-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 4rem; flex-wrap: wrap; gap: 2rem; }
  .services-title { font-size: clamp(3rem, 7vw, 7rem); color: var(--white); }
  .services-desc { max-width: 380px; color: var(--mid-light); font-weight: 300; line-height: 1.7; }
  .services-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.5rem; }
  .service-card {
    border: 1px solid var(--mid-dark); padding: 2.5rem;
    background: var(--dark); position: relative; overflow: hidden;
    transition: border-color .3s, transform .3s;
    cursor: default;
  }
  .service-card::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(255,255,255,.03) 0%, transparent 60%);
    opacity: 0; transition: opacity .3s;
  }
  .service-card:hover { border-color: var(--mid); transform: translateY(-2px); }
  .service-card:hover::before { opacity: 1; }
  .service-num {
    font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .2em;
    color: var(--mid); margin-bottom: 1.5rem;
  }
  .service-icon { font-size: 2.5rem; margin-bottom: 1.2rem; }
  .service-name { font-family: 'Bebas Neue', sans-serif; font-size: 2rem; color: var(--white); letter-spacing: .08em; margin-bottom: .8rem; }
  .service-alt { font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .12em; text-transform: uppercase; color: var(--mid); margin-bottom: 1rem; }
  .service-desc { color: var(--mid-light); font-size: .95rem; font-weight: 300; line-height: 1.7; }
  .service-tag {
    display: inline-block; margin-top: 1.2rem;
    font-family: 'DM Mono', monospace; font-size: .68rem; letter-spacing: .15em; text-transform: uppercase;
    padding: .35rem .8rem; border: 1px solid var(--mid-dark); color: var(--mid-light);
  }

  /* ── PRICES ── */
  #prices { background: var(--dark); }
  .prices-title { font-size: clamp(3rem, 7vw, 7rem); color: var(--white); margin-bottom: 1rem; }
  .prices-sub { color: var(--mid-light); font-weight: 300; font-size: 1.05rem; margin-bottom: 4rem; max-width: 520px; line-height: 1.7; }
  .pricing-tabs { display: flex; gap: 0; margin-bottom: 3rem; border: 1px solid var(--mid-dark); width: fit-content; }
  .tab {
    font-family: 'DM Mono', monospace; font-size: .75rem; letter-spacing: .15em; text-transform: uppercase;
    padding: .8rem 2rem; cursor: pointer; color: var(--mid-light);
    background: transparent; border: none; transition: all .25s;
  }
  .tab.active { background: var(--white); color: var(--black); }
  .pricing-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
  .price-card {
    border: 1px solid var(--mid-dark); padding: 2.5rem;
    position: relative; background: var(--black);
    transition: border-color .3s;
  }
  .price-card.featured {
    border-color: var(--mid); background: var(--mid-dark);
  }
  .price-card.featured::before {
    content: 'MOST POPULAR';
    position: absolute; top: -1px; left: 50%; transform: translateX(-50%);
    font-family: 'DM Mono', monospace; font-size: .62rem; letter-spacing: .2em;
    background: var(--white); color: var(--black); padding: .3rem .8rem;
  }
  .price-card:hover { border-color: var(--mid-light); }
  .price-plan { font-family: 'DM Mono', monospace; font-size: .75rem; letter-spacing: .18em; text-transform: uppercase; color: var(--mid-light); margin-bottom: 1.5rem; }
  .price-amount {
    font-family: 'Bebas Neue', sans-serif; font-size: 4.5rem; color: var(--white);
    letter-spacing: .04em; line-height: 1; margin-bottom: .3rem;
  }
  .price-amount sup { font-size: 2rem; vertical-align: super; }
  .price-period { font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .12em; color: var(--mid); margin-bottom: 2rem; }
  .price-divider { border: none; border-top: 1px solid var(--mid-dark); margin-bottom: 2rem; }
  .price-features { list-style: none; display: flex; flex-direction: column; gap: .8rem; margin-bottom: 2.5rem; }
  .price-features li {
    font-size: .9rem; color: var(--mid-light); font-weight: 300;
    display: flex; align-items: center; gap: .7rem;
  }
  .price-features li::before { content: '—'; color: var(--mid); font-family: 'DM Mono', monospace; }
  .price-features li.highlight { color: var(--lighter); }
  .price-features li.highlight::before { content: '✓'; color: var(--white); }
  .btn-plan {
    display: block; text-align: center; text-decoration: none; width: 100%;
    font-family: 'DM Mono', monospace; font-size: .78rem; letter-spacing: .12em; text-transform: uppercase;
    padding: 1rem; border: 1px solid var(--mid); color: var(--lighter);
    transition: all .25s;
  }
  .btn-plan:hover { background: var(--white); color: var(--black); border-color: var(--white); }
  .btn-plan.featured-btn { background: var(--white); color: var(--black); border-color: var(--white); }
  .btn-plan.featured-btn:hover { background: var(--lighter); }
  .pricing-note { margin-top: 2rem; font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .1em; color: var(--mid); text-align: center; }

  /* toggle panels */
  .plan-panel { display: none; }
  .plan-panel.active { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }

  /* ── CONTACT ── */
  #contact { background: var(--black); }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; margin-top: 4rem; }
  .contact-title { font-size: clamp(3rem, 6vw, 6rem); color: var(--white); margin-bottom: 1.5rem; }
  .contact-info { display: flex; flex-direction: column; gap: 1.5rem; }
  .contact-item { display: flex; gap: 1.2rem; align-items: flex-start; }
  .contact-icon { font-size: 1.2rem; min-width: 2rem; padding-top: .1rem; }
  .contact-label { font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .15em; text-transform: uppercase; color: var(--mid); margin-bottom: .3rem; }
  .contact-value { color: var(--lighter); font-size: .95rem; line-height: 1.6; }
  .contact-form { display: flex; flex-direction: column; gap: 1.2rem; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
  .form-group { display: flex; flex-direction: column; gap: .5rem; }
  .form-label { font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .15em; text-transform: uppercase; color: var(--mid); }
  .form-input, .form-textarea {
    background: var(--dark); border: 1px solid var(--mid-dark);
    color: var(--lighter); font-family: 'DM Sans', sans-serif; font-size: .95rem; font-weight: 300;
    padding: .9rem 1rem; outline: none; transition: border-color .25s; resize: none;
  }
  .form-input:focus, .form-textarea:focus { border-color: var(--mid); }
  .form-textarea { height: 120px; }
  .form-submit {
    font-family: 'DM Mono', monospace; font-size: .82rem; letter-spacing: .12em; text-transform: uppercase;
    padding: 1rem 2.5rem; background: var(--white); color: var(--black); border: none;
    cursor: pointer; transition: background .25s; align-self: flex-start;
  }
  .form-submit:hover { background: var(--lighter); }
  .social-links { display: flex; gap: 1rem; margin-top: 2rem; }
  .social-link {
    font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .12em; text-transform: uppercase;
    padding: .6rem 1rem; border: 1px solid var(--mid-dark); color: var(--mid-light); text-decoration: none;
    transition: all .25s;
  }
  .social-link:hover { border-color: var(--white); color: var(--white); }

  /* ── FAQ ── */
  #faq { background: var(--dark); }
  .faq-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 5rem; margin-top: 4rem; }
  .faq-title { font-size: clamp(3rem, 6vw, 6rem); color: var(--white); position: sticky; top: 6rem; align-self: start; }
  .faq-list { display: flex; flex-direction: column; }
  .faq-item { border-bottom: 1px solid var(--mid-dark); }
  .faq-question {
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.8rem 0; cursor: pointer; gap: 1rem;
  }
  .faq-q-text { font-family: 'DM Sans', sans-serif; font-size: 1.05rem; font-weight: 500; color: var(--lighter); }
  .faq-toggle { font-family: 'DM Mono', monospace; font-size: 1.2rem; color: var(--mid); transition: transform .3s; min-width: 1.5rem; text-align: center; }
  .faq-item.open .faq-toggle { transform: rotate(45deg); color: var(--white); }
  .faq-answer { max-height: 0; overflow: hidden; transition: max-height .4s ease, padding .4s; }
  .faq-item.open .faq-answer { max-height: 300px; padding-bottom: 1.5rem; }
  .faq-answer p { color: var(--mid-light); font-weight: 300; line-height: 1.8; font-size: .97rem; }

  /* ── FOOTER ── */
  footer {
    background: var(--black); border-top: 1px solid var(--mid-dark);
    padding: 3rem;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1.5rem;
  }
  .footer-logo { font-family: 'Bebas Neue', sans-serif; font-size: 1.8rem; color: var(--white); letter-spacing: .12em; }
  .footer-copy { font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .1em; color: var(--mid); }
  .footer-links { display: flex; gap: 1.5rem; }
  .footer-links a { font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .12em; text-transform: uppercase; color: var(--mid); text-decoration: none; transition: color .2s; }
  .footer-links a:hover { color: var(--lighter); }

  /* ── DIVIDERS ── */
  .ticker {
    background: var(--mid-dark); padding: .8rem 0; overflow: hidden; white-space: nowrap;
    border-top: 1px solid var(--mid-dark); border-bottom: 1px solid var(--mid-dark);
  }
  .ticker-inner { display: inline-flex; animation: scroll 18s linear infinite; }
  .ticker-inner span {
    font-family: 'DM Mono', monospace; font-size: .7rem; letter-spacing: .2em; text-transform: uppercase;
    color: var(--mid-light); padding: 0 3rem;
  }
  .ticker-inner span::before { content: '◆ '; }
  @keyframes scroll { from{transform:translateX(0)} to{transform:translateX(-50%)} }

  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 5rem 1.5rem; }
    .about-grid, .contact-grid, .faq-grid { grid-template-columns: 1fr; gap: 3rem; }
    .services-grid { grid-template-columns: 1fr; }
    .pricing-grid, .plan-panel.active { grid-template-columns: 1fr; }
    .services-header { flex-direction: column; }
    .form-row { grid-template-columns: 1fr; }
    footer { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#home" class="nav-logo">Xon<span>Kiv</span></a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#prices">Prices</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#faq">FAQ</a></li>
  </ul>
  <a href="#prices" class="nav-cta">Get Started</a>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-badge">Mérida, Spain — Est. 2024</div>
    <h1 class="hero-title">
      INNOVATE<br>
      YOUR <span class="hollow">WORKFLOW</span>
    </h1>
    <p class="hero-sub">From concept to creation — everything your digital workspace needs, in one powerful subscription. Built for students and creators starting their journey.</p>
    <div class="hero-actions">
      <a href="#prices" class="btn-primary">See Plans</a>
      <a href="#services" class="btn-ghost">Explore Apps</a>
    </div>
  </div>
  <div class="hero-scroll">Scroll</div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span>Text Processor</span><span>Video Editor</span><span>Image Studio</span><span>Spreadsheets</span>
    <span>Student Plans</span><span>Permanent License</span><span>Made for Beginners</span><span>Mérida, Spain</span>
    <span>Text Processor</span><span>Video Editor</span><span>Image Studio</span><span>Spreadsheets</span>
    <span>Student Plans</span><span>Permanent License</span><span>Made for Beginners</span><span>Mérida, Spain</span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="section-label">About Us</div>
  <div class="about-grid">
    <div>
      <h2 class="about-title">YOUR VISION,<br>OUR CODE.</h2>
      <p class="about-body">XonKiv was founded to create special tools for learning professional and digital work. We specialize in software for Windows — and are now expanding into hardware — with one clear goal: make digital creativity and productivity accessible for everyone, especially those just starting out.</p>
      <p class="about-body" style="margin-top:1.2rem;">Our central office is in Mérida, Spain, with additional offices across the country. We're available <strong style="color:var(--lighter);font-weight:500;">08:00 — 23:00</strong>, every day.</p>
      <div class="about-stats">
        <div class="stat-card"><div class="stat-number">4</div><div class="stat-label">Core Applications</div></div>
        <div class="stat-card"><div class="stat-number">7.5€</div><div class="stat-label">Student Monthly</div></div>
        <div class="stat-card"><div class="stat-number">100%</div><div class="stat-label">Beginner Friendly</div></div>
        <div class="stat-card"><div class="stat-number">∞</div><div class="stat-label">Permanent Licenses</div></div>
      </div>
    </div>
    <div>
      <div class="values-list">
        <div class="value-item">
          <div class="value-icon">🎯</div>
          <div>
            <div class="value-title">Mission</div>
            <div class="value-desc">Bring the easiest way to learn and use digital technology for work or creativity — in an interactive way — to every user, regardless of their starting level.</div>
          </div>
        </div>
        <div class="value-item">
          <div class="value-icon">🔭</div>
          <div>
            <div class="value-title">Vision</div>
            <div class="value-desc">To grow into a global reference — a standard that students, schools, and small businesses look to when they need powerful yet accessible digital tools.</div>
          </div>
        </div>
        <div class="value-item">
          <div class="value-icon">🔧</div>
          <div>
            <div class="value-title">Innovation</div>
            <div class="value-desc">Continuously improving our software while racing to bring dedicated XonKiv hardware to market — purpose-built for digital work areas.</div>
          </div>
        </div>
        <div class="value-item">
          <div class="value-icon">⭐</div>
          <div>
            <div class="value-title">Reliability</div>
            <div class="value-desc">Backed by reviews from schools, small companies, and individual users — visible on our official website for full transparency.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="services-header">
    <div>
      <div class="section-label">Services</div>
      <h2 class="services-title">FOUR<br>POWERFUL<br>TOOLS.</h2>
    </div>
    <p class="services-desc">Everything you need to work, study, and create — designed from the ground up for people who are just beginning their digital journey.</p>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-num">01 / 04</div>
      <div class="service-icon">📝</div>
      <div class="service-name">KivWriter</div>
      <div class="service-alt">Similar to Microsoft Word / LibreOffice</div>
      <p class="service-desc">A full-featured word processor built for clarity. Write reports, essays, and professional documents with an intuitive interface that gets out of your way.</p>
      <span class="service-tag">Documents</span>
    </div>
    <div class="service-card">
      <div class="service-num">02 / 04</div>
      <div class="service-icon">🎬</div>
      <div class="service-name">KivCut</div>
      <div class="service-alt">Similar to Premiere Pro / DaVinci Resolve</div>
      <p class="service-desc">A powerful yet approachable video editor. Cut, color-grade, and export your videos without the steep learning curve of industry-standard tools.</p>
      <span class="service-tag">Video Editing</span>
    </div>
    <div class="service-card">
      <div class="service-num">03 / 04</div>
      <div class="service-icon">🖼️</div>
      <div class="service-name">KivPixel</div>
      <div class="service-alt">Similar to Adobe Photoshop</div>
      <p class="service-desc">Design marketing visuals, edit photos, and craft graphics with professional results. Perfect for students learning design fundamentals.</p>
      <span class="service-tag">Image Design</span>
    </div>
    <div class="service-card">
      <div class="service-num">04 / 04</div>
      <div class="service-icon">📊</div>
      <div class="service-name">KivSheet</div>
      <div class="service-alt">Similar to Microsoft Excel</div>
      <p class="service-desc">Organize data, build budgets, and create charts and reports. Formulas made simple — learn the logic of spreadsheets without the frustration.</p>
      <span class="service-tag">Spreadsheets</span>
    </div>
  </div>
</section>

<!-- TICKER 2 -->
<div class="ticker">
  <div class="ticker-inner">
    <span>Solutions in Every Byte</span><span>Your Vision, Our Code</span><span>Innovate Your Workflow</span><span>Built for Starters</span><span>Windows Native</span><span>Made in Spain</span>
    <span>Solutions in Every Byte</span><span>Your Vision, Our Code</span><span>Innovate Your Workflow</span><span>Built for Starters</span><span>Windows Native</span><span>Made in Spain</span>
  </div>
</div>

<!-- PRICES -->
<section id="prices">
  <div class="section-label">Pricing</div>
  <h2 class="prices-title">CLEAR,<br>FAIR PRICES.</h2>
  <p class="prices-sub">Discover software at half price for students. Choose between a monthly subscription or a one-time permanent license — no hidden fees, ever.</p>

  <div class="pricing-tabs">
    <button class="tab active" onclick="showPlans('monthly', this)">Monthly</button>
    <button class="tab" onclick="showPlans('onetime', this)">One-Time</button>
  </div>

  <!-- MONTHLY -->
  <div id="plan-monthly" class="plan-panel active">
    <div class="price-card">
      <div class="price-plan">Single App</div>
      <div class="price-amount"><sup>€</sup>—</div>
      <div class="price-period">Not available for single apps on monthly</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li>Choose one application</li>
        <li>See one-time license below</li>
        <li>Best for focused learners</li>
      </ul>
      <a href="#contact" class="btn-plan">Contact Us</a>
    </div>
    <div class="price-card featured">
      <div class="price-plan">All Apps — Pro</div>
      <div class="price-amount"><sup>€</sup>15</div>
      <div class="price-period">/ month — Full access</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li class="highlight">KivWriter included</li>
        <li class="highlight">KivCut included</li>
        <li class="highlight">KivPixel included</li>
        <li class="highlight">KivSheet included</li>
        <li>Cancel anytime</li>
      </ul>
      <a href="#contact" class="btn-plan featured-btn">Get Started</a>
    </div>
    <div class="price-card">
      <div class="price-plan">All Apps — Student</div>
      <div class="price-amount"><sup>€</sup>7.5</div>
      <div class="price-period">/ month — Valid until graduation</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li class="highlight">All 4 apps included</li>
        <li class="highlight">50% student discount</li>
        <li>Valid student ID required</li>
        <li>License active during studies</li>
      </ul>
      <a href="#contact" class="btn-plan">Get Student Plan</a>
    </div>
  </div>

  <!-- ONE-TIME -->
  <div id="plan-onetime" class="plan-panel">
    <div class="price-card">
      <div class="price-plan">Single App — Pro</div>
      <div class="price-amount"><sup>€</sup>60</div>
      <div class="price-period">one-time — Permanent license</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li class="highlight">1 app of your choice</li>
        <li class="highlight">Permanent license</li>
        <li>All future updates</li>
        <li>No recurring charges</li>
      </ul>
      <a href="#contact" class="btn-plan">Buy License</a>
    </div>
    <div class="price-card featured">
      <div class="price-plan">All Apps — Pro</div>
      <div class="price-amount"><sup>€</sup>60<span style="font-size:1.5rem"> × 4</span></div>
      <div class="price-period">per app — Permanent, all apps</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li class="highlight">All 4 apps included</li>
        <li class="highlight">Permanent licenses</li>
        <li class="highlight">Pay once, own forever</li>
        <li>Full suite access</li>
      </ul>
      <a href="#contact" class="btn-plan featured-btn">Buy Full Suite</a>
    </div>
    <div class="price-card">
      <div class="price-plan">Single App — Student</div>
      <div class="price-amount"><sup>€</sup>30</div>
      <div class="price-period">one-time — Valid until graduation</div>
      <hr class="price-divider">
      <ul class="price-features">
        <li class="highlight">1 app of your choice</li>
        <li class="highlight">50% student discount</li>
        <li>Valid student ID required</li>
        <li>License active during studies</li>
      </ul>
      <a href="#contact" class="btn-plan">Buy Student License</a>
    </div>
  </div>

  <p class="pricing-note">★ Student discount requires valid student ID verification — contact us to apply</p>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-label">Contact</div>
  <div class="contact-grid">
    <div>
      <h2 class="contact-title">LET'S<br>TALK.</h2>
      <div class="contact-info">
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div>
            <div class="contact-label">HQ Location</div>
            <div class="contact-value">Mérida, Spain<br>Additional offices across the country</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">🕐</div>
          <div>
            <div class="contact-label">Business Hours</div>
            <div class="contact-value">08:00 — 23:00, every day</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">🌐</div>
          <div>
            <div class="contact-label">Social Media</div>
            <div class="contact-value">Follow us on YouTube, TikTok & Instagram for tutorials, news, and updates.</div>
          </div>
        </div>
      </div>
      <div class="social-links">
        <a href="#" class="social-link">YouTube</a>
        <a href="#" class="social-link">TikTok</a>
        <a href="#" class="social-link">Instagram</a>
      </div>
    </div>
    <div>
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">First Name</label>
            <input class="form-input" type="text" placeholder="John">
          </div>
          <div class="form-group">
            <label class="form-label">Last Name</label>
            <input class="form-input" type="text" placeholder="Doe">
          </div>
        </div>
        <div class="form-group">
          <label class="form-label">Email</label>
          <input class="form-input" type="email" placeholder="john@example.com">
        </div>
        <div class="form-group">
          <label class="form-label">Subject</label>
          <input class="form-input" type="text" placeholder="Pricing inquiry / Student discount / Support...">
        </div>
        <div class="form-group">
          <label class="form-label">Message</label>
          <textarea class="form-textarea" placeholder="Tell us what you need..."></textarea>
        </div>
        <button type="submit" class="form-submit">Send Message →</button>
      </form>
    </div>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <div class="section-label">FAQ</div>
  <div class="faq-grid">
    <h2 class="faq-title">COMMON<br>QUESTIONS.</h2>
    <div class="faq-list">

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">Who are XonKiv products designed for?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>XonKiv is primarily built for students and people starting out in the digital workspace — whether that's writing, design, video editing, or data management. That said, our tools are powerful enough for professionals who want a more accessible, streamlined experience.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">What's the difference between the student and pro plans?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>Student plans offer a 50% discount — monthly access to all apps at €7.50, or individual one-time licenses at €30 each. The student license remains valid until you finish your current educational program. Verification with a valid student ID is required.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">Are licenses permanent? What happens after I stop paying?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>One-time license purchases give you permanent ownership of the software — no subscription needed, no expiry. Monthly subscriptions remain active as long as you continue paying, and you can cancel anytime. Student licenses are tied to your graduation date.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">Is XonKiv software available on Mac or mobile?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>Currently, all XonKiv applications are native to Windows. We are actively working on expanding compatibility to other platforms in future releases. Stay tuned to our social media channels for announcements.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">How do competitors like Adobe or Microsoft compare?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>Tools like Adobe and Microsoft are powerful, but they're primarily built with experienced professionals in mind. XonKiv is designed from day one for people learning the ropes — simpler interfaces, accessible pricing, and educational focus — without sacrificing real functionality.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">Where can I read reviews from other users?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>We have an official reviews section on our website where schools, small companies, and individual users post their experiences. We believe in full transparency — every review, positive or constructive, is visible to everyone.</p></div>
      </div>

      <div class="faq-item">
        <div class="faq-question" onclick="toggleFaq(this)">
          <span class="faq-q-text">Is XonKiv working on hardware products?</span>
          <span class="faq-toggle">+</span>
        </div>
        <div class="faq-answer"><p>Yes! XonKiv started with software, but we're actively developing hardware designed specifically for people working in digital areas. Our goal is to create an end-to-end ecosystem — devices that pair seamlessly with our software for an optimized learning and working experience.</p></div>
      </div>

    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">XonKiv</div>
  <div class="footer-copy">© 2024 XonKiv. All rights reserved. Mérida, Spain.</div>
  <div class="footer-links">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#prices">Prices</a>
    <a href="#contact">Contact</a>
    <a href="#faq">FAQ</a>
  </div>
</footer>

<script>
  function toggleFaq(el) {
    const item = el.closest('.faq-item');
    item.classList.toggle('open');
  }

  function showPlans(type, btn) {
    document.querySelectorAll('.plan-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById('plan-' + type).classList.add('active');
    btn.classList.add('active');
  }

  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.form-submit');
    btn.textContent = 'Message Sent ✓';
    btn.style.background = '#555';
    btn.style.color = '#f7f7f7';
    setTimeout(() => {
      btn.textContent = 'Send Message →';
      btn.style.background = '';
      btn.style.color = '';
      e.target.reset();
    }, 3000);
  }

  // Animate elements on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) e.target.style.opacity = '1';
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.service-card, .price-card, .value-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transition = 'opacity .6s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
