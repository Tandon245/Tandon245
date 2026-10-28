<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#0b0f14" />
  <meta name="description" content="Abhishek Tandon — Android Developer specializing in Kotlin, Jetpack Compose, MVVM, Clean Architecture, and BLE integrations." />
  <title>Abhishek Tandon | Android Developer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      color-scheme: dark;
      --bg: #0b0f14;
      --panel: #111821;
      --panel-2: #151e29;
      --text: #e8eef7;
      --muted: #a5b1c2;
      --line: #273241;
      --cyan: #00d9ff;
      --blue: #4776e6;
      --purple: #9b5de5;
      --green: #3ddc84;
      --orange: #ff9f43;
      --radius: 18px;
      --max-width: 1080px;
      --shadow: 0 18px 48px rgba(0, 0, 0, .24);
    }

    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 90px; }
    body {
      margin: 0;
      background:
        radial-gradient(ellipse at 12% 0%, rgba(71, 118, 230, .13), transparent 34rem),
        radial-gradient(ellipse at 92% 10%, rgba(155, 93, 229, .10), transparent 32rem),
        var(--bg);
      color: var(--text);
      font: 16px/1.7 Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      overflow-x: hidden;
    }
    a { color: inherit; text-decoration: none; }
    img { max-width: 100%; display: block; }
    button, a { -webkit-tap-highlight-color: transparent; }
    .container { width: min(var(--max-width), calc(100% - 40px)); margin-inline: auto; }
    .mono { font-family: "JetBrains Mono", monospace; }
    .muted { color: var(--muted); }
    .eyebrow {
      display: inline-flex; align-items: center; gap: 9px;
      color: var(--cyan); font: 600 .78rem "JetBrains Mono", monospace;
      letter-spacing: .12em; text-transform: uppercase;
    }
    .eyebrow::before { content: ""; width: 25px; height: 2px; background: var(--cyan); }
    h1, h2, h3, p { margin-top: 0; }
    h1 { font-size: clamp(2.6rem, 7vw, 5.3rem); line-height: 1.04; letter-spacing: -.065em; margin: 20px 0; }
    h2 { font-size: clamp(1.8rem, 4vw, 2.65rem); line-height: 1.15; letter-spacing: -.045em; margin-bottom: 14px; }
    h3 { line-height: 1.3; }
    .gradient-text {
      background: linear-gradient(100deg, var(--cyan), #8a8cff 58%, #c77dff);
      -webkit-background-clip: text; background-clip: text; color: transparent;
    }

    /* Header and navigation */
    .site-header {
      position: sticky; top: 0; z-index: 50;
      background: rgba(11, 15, 20, .82); backdrop-filter: blur(18px);
      border-bottom: 1px solid rgba(165, 177, 194, .14);
    }
    .nav {
      min-height: 70px; display: flex; align-items: center;
      justify-content: space-between; gap: 24px;
    }
    .brand { display: inline-flex; align-items: center; gap: 11px; font-weight: 800; letter-spacing: -.03em; white-space: nowrap; }
    .brand-mark {
      display: grid; place-items: center; width: 38px; height: 38px; border-radius: 12px;
      color: #061017; background: linear-gradient(135deg, var(--cyan), #8a8cff);
      font: 800 1rem "JetBrains Mono", monospace; box-shadow: 0 0 25px rgba(0, 217, 255, .18);
    }
    .nav-links { display: flex; align-items: center; gap: 5px; list-style: none; margin: 0; padding: 0; }
    .nav-links a { display: block; padding: 10px 12px; border-radius: 10px; color: var(--muted); font-size: .88rem; transition: color .2s, background .2s; }
    .nav-links a:hover, .nav-links a:focus-visible { color: var(--text); background: var(--panel-2); outline: none; }
    .nav-cta { border: 1px solid rgba(0, 217, 255, .42); color: var(--cyan) !important; }
    .menu-toggle {
      display: none; width: 42px; height: 42px; border: 1px solid var(--line);
      border-radius: 12px; background: var(--panel); color: var(--text); cursor: pointer; font-size: 1.2rem;
    }

    /* Hero */
    .hero { padding: 92px 0 66px; }
    .hero-grid { display: grid; grid-template-columns: minmax(0, 1.35fr) minmax(260px, .65fr); align-items: center; gap: 52px; }
    .availability { display: inline-flex; align-items: center; gap: 9px; padding: 8px 12px; border: 1px solid rgba(61, 220, 132, .24); background: rgba(61, 220, 132, .07); border-radius: 999px; color: #9af0bc; font-size: .82rem; }
    .status-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--green); box-shadow: 0 0 0 5px rgba(61, 220, 132, .12); }
    .hero-copy { max-width: 720px; color: var(--muted); font-size: 1.08rem; }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 28px; }
    .btn {
      display: inline-flex; justify-content: center; align-items: center; gap: 10px;
      min-height: 46px; padding: 0 18px; border: 1px solid var(--line); border-radius: 12px;
      font-weight: 700; font-size: .9rem; transition: transform .2s, border-color .2s, background .2s;
    }
    .btn:hover { transform: translateY(-3px); border-color: var(--cyan); }
    .btn-primary { background: linear-gradient(100deg, var(--cyan), #8a8cff); border-color: transparent; color: #061017; }
    .btn-secondary { background: var(--panel); }
    .hero-card {
      position: relative; overflow: hidden; padding: 28px; border: 1px solid var(--line);
      border-radius: 24px; background: linear-gradient(150deg, rgba(21, 30, 41, .96), rgba(12, 18, 26, .96)); box-shadow: var(--shadow);
    }
    .hero-card::before { content: ""; position: absolute; width: 180px; height: 180px; right: -80px; top: -90px; background: var(--purple); filter: blur(85px); opacity: .28; }
    .code-window { position: relative; font: .82rem/1.9 "JetBrains Mono", monospace; color: var(--muted); }
    .window-dots { display: flex; gap: 7px; margin-bottom: 22px; }
    .window-dots span { width: 9px; height: 9px; border-radius: 50%; background: #ff6b6b; }
    .window-dots span:nth-child(2) { background: #ffd166; }
    .window-dots span:nth-child(3) { background: #3ddc84; }
    .code-key { color: #c792ea; }
    .code-value { color: #c3e88d; }
    .code-string { color: #f78c6c; }
    .hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin-top: 24px; }
    .stat { padding: 14px 10px; border-radius: 13px; background: rgba(255, 255, 255, .035); border: 1px solid rgba(255, 255, 255, .06); }
    .stat strong { display: block; font-size: 1.2rem; }
    .stat span { display: block; color: var(--muted); font-size: .72rem; }

    /* Shared sections */
    section { padding: 76px 0; }
    .section-heading { display: flex; justify-content: space-between; align-items: end; gap: 20px; margin-bottom: 30px; }
    .section-heading p { max-width: 570px; margin-bottom: 0; color: var(--muted); }
    .panel { background: rgba(17, 24, 33, .8); border: 1px solid var(--line); border-radius: var(--radius); }
    .about-grid { display: grid; grid-template-columns: 1.1fr .9fr; gap: 20px; }
    .about-card { padding: 28px; }
    .about-card p { color: var(--muted); }
    .check-list { list-style: none; margin: 18px 0 0; padding: 0; display: grid; gap: 12px; }
    .check-list li { display: flex; gap: 11px; align-items: flex-start; color: var(--muted); }
    .check-list li::before { content: "✓"; color: var(--green); font-weight: 800; }
    .focus-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 12px; }
    .focus-item { padding: 18px; background: var(--panel-2); border-radius: 14px; border: 1px solid rgba(255,255,255,.045); }
    .focus-item strong { display: block; margin-bottom: 5px; }
    .focus-item span { color: var(--muted); font-size: .86rem; }

    /* Skills */
    .skill-groups { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 16px; }
    .skill-card { padding: 24px; }
    .skill-card h3 { margin: 0 0 16px; }
    .chips { display: flex; flex-wrap: wrap; gap: 9px; }
    .chip { display: inline-flex; padding: 8px 11px; border: 1px solid #2b394a; border-radius: 9px; background: #141d27; color: #cbd5e1; font-size: .82rem; }

    /* Projects */
    .project-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 18px; }
    .project-card { overflow: hidden; display: flex; flex-direction: column; padding: 25px; transition: transform .22s, border-color .22s; }
    .project-card:hover { transform: translateY(-5px); border-color: rgba(0, 217, 255, .45); }
    .project-top { display: flex; align-items: center; justify-content: space-between; gap: 12px; margin-bottom: 15px; }
    .project-icon { display: grid; place-items: center; width: 48px; height: 48px; border-radius: 14px; background: linear-gradient(135deg, rgba(0,217,255,.18), rgba(155,93,229,.18)); font-size: 1.45rem; }
    .project-type { color: var(--cyan); font: .72rem "JetBrains Mono", monospace; text-transform: uppercase; letter-spacing: .08em; }
    .project-card h3 { margin-bottom: 9px; font-size: 1.25rem; }
    .project-card p { color: var(--muted); font-size: .92rem; }
    .project-card .chips { margin: 5px 0 22px; }
    .project-card .chip { font-size: .73rem; padding: 6px 8px; }
    .project-links { display: flex; flex-wrap: wrap; gap: 10px; margin-top: auto; }
    .text-link { color: var(--cyan); font-size: .86rem; font-weight: 700; }
    .text-link:hover { text-decoration: underline; }

    /* Experience and education */
    .timeline { display: grid; gap: 16px; }
    .timeline-item { position: relative; padding: 25px 27px 25px 32px; }
    .timeline-item::before { content: ""; position: absolute; left: 0; top: 27px; bottom: 27px; width: 3px; border-radius: 4px; background: linear-gradient(var(--cyan), var(--purple)); }
    .timeline-top { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; }
    .timeline-top h3 { margin: 0 0 5px; }
    .timeline-date { color: var(--cyan); font: .78rem "JetBrains Mono", monospace; white-space: nowrap; }
    .timeline-item p { margin: 8px 0 0; color: var(--muted); }
    .timeline-item ul { margin-bottom: 0; color: var(--muted); padding-left: 20px; }

    /* Connect and footer */
    .contact-panel { padding: clamp(25px, 5vw, 48px); text-align: center; background: radial-gradient(ellipse at top, rgba(71,118,230,.16), transparent 65%), var(--panel); }
    .contact-panel p { max-width: 590px; margin: 0 auto 24px; color: var(--muted); }
    .social-links { display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; }
    footer { padding: 28px 0 38px; border-top: 1px solid var(--line); color: var(--muted); font-size: .82rem; }
    .footer-inner { display: flex; justify-content: space-between; gap: 15px; flex-wrap: wrap; }
    .back-top { color: var(--cyan); }

    @media (max-width: 900px) {
      .nav-links { gap: 0; }
      .nav-links a { padding-inline: 8px; font-size: .82rem; }
      .hero-grid { grid-template-columns: 1fr; gap: 30px; }
      .hero-card { max-width: 560px; }
      .about-grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 700px) {
      .container { width: min(100% - 28px, var(--max-width)); }
      .nav { min-height: 64px; }
      .menu-toggle { display: inline-grid; place-items: center; }
      .nav-links {
        display: none; position: absolute; top: 64px; left: 14px; right: 14px;
        padding: 10px; border: 1px solid var(--line); border-radius: 15px;
        background: rgba(17, 24, 33, .98); box-shadow: var(--shadow);
        align-items: stretch; flex-direction: column;
      }
      .nav-links.open { display: flex; }
      .nav-links a { padding: 12px; font-size: .92rem; }
      .hero { padding: 65px 0 38px; }
      section { padding: 55px 0; }
      .section-heading { display: block; }
      .section-heading p { margin-top: 12px; }
      .skill-groups, .project-grid { grid-template-columns: 1fr; }
      .timeline-top { display: block; }
      .timeline-date { display: inline-block; margin-top: 7px; }
      .hero-stats { gap: 7px; }
      .stat strong { font-size: 1.05rem; }
    }
    @media (max-width: 390px) {
      .brand { font-size: .9rem; }
      .brand-mark { width: 34px; height: 34px; }
      .hero-stats { grid-template-columns: 1fr; }
      .focus-grid { grid-template-columns: 1fr; }
      .btn { width: 100%; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { scroll-behavior: auto !important; animation-duration: .01ms !important; transition-duration: .01ms !important; }
    }
  </style>
</head>
<body>
  <header class="site-header">
    <nav class="nav container" aria-label="Main navigation">
      <a class="brand" href="#home" aria-label="Abhishek Tandon home">
        <span class="brand-mark">AT</span>
        <span>Abhishek <span class="gradient-text">Tandon</span></span>
      </a>
      <button class="menu-toggle" id="menuToggle" aria-label="Open navigation menu" aria-expanded="false" aria-controls="navLinks">☰</button>
      <ul class="nav-links" id="navLinks">
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Tech Stack</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#education">Education</a></li>
        <li><a class="nav-cta" href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="container hero-grid">
        <div>
          <span class="availability"><span class="status-dot"></span> Open to new opportunities</span>
          <p class="eyebrow" style="margin-top:26px">Android Developer · Noida, India</p>
          <h1>Building Android apps that feel <span class="gradient-text">fast, useful & reliable.</span></h1>
          <p class="hero-copy">I'm Abhishek Tandon, an Android Developer focused on Kotlin, Jetpack Compose, MVVM, and Clean Architecture. I build maintainable production apps and enjoy solving challenging integration problems across APIs, Firebase, and Bluetooth-connected devices.</p>
          <div class="hero-actions">
            <a class="btn btn-primary" href="#projects">Explore my work <span aria-hidden="true">↗</span></a>
            <a class="btn btn-secondary" href="https://www.linkedin.com/in/er-abhishek-tandon-3120a1220/" target="_blank" rel="noopener noreferrer">Connect on LinkedIn</a>
            <a class="btn btn-secondary" href="mailto:tandonabhishek245@gmail.com">Email me</a>
          </div>
          <div class="hero-stats">
            <div class="stat"><strong>3+ years</strong><span>Development experience</span></div>
            <div class="stat"><strong>Android</strong><span>Primary specialization</span></div>
            <div class="stat"><strong>Production</strong><span>Real-world applications</span></div>
          </div>
        </div>

        <aside class="hero-card" aria-label="Developer profile card">
          <div class="code-window">
            <div class="window-dots"><span></span><span></span><span></span></div>
            <div><span class="code-key">class</span> <span class="code-value">AndroidDeveloper</span> {</div>
            <div>&nbsp;&nbsp;<span class="code-key">val</span> name = <span class="code-string">"Abhishek"</span></div>
            <div>&nbsp;&nbsp;<span class="code-key">val</span> language = <span class="code-string">"Kotlin"</span></div>
            <div>&nbsp;&nbsp;<span class="code-key">val</span> UI = <span class="code-string">"Jetpack Compose"</span></div>
            <div>&nbsp;&nbsp;<span class="code-key">val</span> architecture = <span class="code-string">"Clean + MVVM"</span></div>
            <div>&nbsp;&nbsp;<span class="code-key">val</span> mindset = <span class="code-string">"Build. Improve. Repeat."</span></div>
            <div>}</div>
            <br />
            <div><span class="code-key">// Turning ideas into dependable apps.</span></div>
          </div>
        </aside>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-heading">
          <div><span class="eyebrow">A little about me</span><h2>Engineering with <span class="gradient-text">purpose.</span></h2></div>
          <p>I care about the details behind a good app: clear architecture, responsive UI, dependable data flows, and code that's easy to maintain.</p>
        </div>
        <div class="about-grid">
          <article class="panel about-card">
            <h3>👋 Hello, I'm Abhishek</h3>
            <p>I develop Android applications with a focus on clean structure and practical user experiences. My day-to-day work includes building UI, connecting APIs, managing asynchronous tasks, debugging production issues, and integrating third-party SDKs.</p>
            <p>My preferred approach is to keep responsibilities separated, make state predictable, and write code that another developer can understand and extend.</p>
            <ul class="check-list">
              <li>Kotlin, Java, and Jetpack Compose</li>
              <li>MVVM, Clean Architecture, and Repository Pattern</li>
              <li>REST APIs, Firebase, and local persistence</li>
              <li>BLE device integration and release support</li>
            </ul>
          </article>
          <div class="focus-grid">
            <div class="focus-item"><strong>📐 Architecture</strong><span>Maintainable, testable, scalable app structure.</span></div>
            <div class="focus-item"><strong>🎨 UI Engineering</strong><span>Compose interfaces with thoughtful state handling.</span></div>
            <div class="focus-item"><strong>🔌 Integrations</strong><span>APIs, Firebase, BLE, and third-party SDKs.</span></div>
            <div class="focus-item"><strong>🛠️ Reliability</strong><span>Debugging, edge cases, and production readiness.</span></div>
          </div>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-heading">
          <div><span class="eyebrow">Tools of the trade</span><h2>Tech <span class="gradient-text">stack.</span></h2></div>
          <p>Technologies and patterns I use to build and support mobile applications.</p>
        </div>
        <div class="skill-groups">
          <article class="panel skill-card">
            <h3>📱 Android & UI</h3>
            <div class="chips"><span class="chip">Kotlin</span><span class="chip">Java</span><span class="chip">Android SDK</span><span class="chip">Jetpack Compose</span><span class="chip">XML Views</span><span class="chip">Material Design</span></div>
          </article>
          <article class="panel skill-card">
            <h3>🏗️ Architecture & Libraries</h3>
            <div class="chips"><span class="chip">MVVM</span><span class="chip">Clean Architecture</span><span class="chip">Repository Pattern</span><span class="chip">Coroutines</span><span class="chip">Flow</span><span class="chip">Retrofit</span><span class="chip">Room</span></div>
          </article>
          <article class="panel skill-card">
            <h3>☁️ Backend & Cloud</h3>
            <div class="chips"><span class="chip">REST APIs</span><span class="chip">Firebase Auth</span><span class="chip">Firestore</span><span class="chip">FCM</span><span class="chip">Crashlytics</span><span class="chip">Spring Boot</span><span class="chip">MySQL</span></div>
          </article>
          <article class="panel skill-card">
            <h3>🧰 Tools & Other</h3>
            <div class="chips"><span class="chip">Android Studio</span><span class="chip">Git</span><span class="chip">GitHub</span><span class="chip">Postman</span><span class="chip">BLE</span><span class="chip">Flutter</span><span class="chip">Google Play Console</span></div>
          </article>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <div class="section-heading">
          <div><span class="eyebrow">Selected work</span><h2>Projects in the <span class="gradient-text">real world.</span></h2></div>
          <p>A selection of applications and domains I've worked on. Open the app links to verify current public listings.</p>
        </div>
        <div class="project-grid">
          <article class="panel project-card">
            <div class="project-top"><span class="project-icon">🏃</span><span class="project-type">Health-tech · BLE</span></div>
            <h3>Brio — Smart Fitness</h3>
            <p>A fitness application connecting with Bluetooth-enabled smart devices and supporting fitness data workflows.</p>
            <div class="chips"><span class="chip">Kotlin</span><span class="chip">Jetpack Compose</span><span class="chip">BLE SDK</span><span class="chip">MVVM</span></div>
            <div class="project-links"><a class="text-link" href="https://play.google.com/store/apps/details?id=sa.com.brio.android" target="_blank" rel="noopener noreferrer">View on Google Play ↗</a></div>
          </article>
          <article class="panel project-card">
            <div class="project-top"><span class="project-icon">💳</span><span class="project-type">Fintech · Payments</span></div>
            <h3>MoConnect</h3>
            <p>A fintech mobile experience for airtime top-ups, international recharges, utility payments, and wallet-related workflows.</p>
            <div class="chips"><span class="chip">Kotlin</span><span class="chip">Retrofit</span><span class="chip">Coroutines</span><span class="chip">Firebase</span></div>
            <div class="project-links"><a class="text-link" href="https://play.google.com/store/apps/details?id=za.co.moconnect.android.customer" target="_blank" rel="noopener noreferrer">View on Google Play ↗</a></div>
          </article>
          <article class="panel project-card">
            <div class="project-top"><span class="project-icon">📲</span><span class="project-type">Telecom · Mobile</span></div>
            <h3>EasiApp</h3>
            <p>A telecom application supporting SIM registration workflows and mobile utility services.</p>
            <div class="chips"><span class="chip">Android SDK</span><span class="chip">Kotlin</span><span class="chip">REST APIs</span><span class="chip">Integrations</span></div>
            <div class="project-links"><a class="text-link" href="https://play.google.com/store/apps/details?id=za.co.easicall.rica" target="_blank" rel="noopener noreferrer">View on Google Play ↗</a></div>
          </article>
          <article class="panel project-card">
            <div class="project-top"><span class="project-icon">💙</span><span class="project-type">Social · Android</span></div>
            <h3>Selective Matchmaker</h3>
            <p>A matchmaking application with authentication, search, filtering, and user-focused application flows.</p>
            <div class="chips"><span class="chip">Kotlin</span><span class="chip">MVVM</span><span class="chip">Firebase Auth</span><span class="chip">REST APIs</span></div>
            <div class="project-links"><a class="text-link" href="https://play.google.com/store/apps/details?id=com.selectivematchmaker.android" target="_blank" rel="noopener noreferrer">View on Google Play ↗</a></div>
          </article>
        </div>
      </div>
    </section>

    <section id="experience">
      <div class="container">
        <div class="section-heading">
          <div><span class="eyebrow">Career journey</span><h2>Professional <span class="gradient-text">experience.</span></h2></div>
          <p>Experience building, integrating, and maintaining mobile applications across different product domains.</p>
        </div>
        <div class="timeline">
          <article class="panel timeline-item">
            <div class="timeline-top"><div><h3>Android Developer · Vidursoft</h3><span class="muted">Android development and production support</span></div><span class="timeline-date">Oct 2024 — Present</span></div>
            <ul>
              <li>Develop and maintain Android application features using Kotlin and Jetpack Compose.</li>
              <li>Apply MVVM and Clean Architecture to keep application code modular and maintainable.</li>
              <li>Integrate REST APIs, Firebase services, and Bluetooth-enabled hardware SDKs.</li>
              <li>Investigate issues, improve reliability, and support release workflows.</li>
            </ul>
          </article>
          <article class="panel timeline-item">
            <div class="timeline-top"><div><h3>Java / Android Developer · Monoprabal Engineering</h3><span class="muted">Mobile development and backend integration</span></div><span class="timeline-date">Mar 2023 — Sep 2024</span></div>
            <ul>
              <li>Built and maintained Android features using Kotlin and Java.</li>
              <li>Integrated REST APIs and worked with Spring Boot services and MySQL-backed systems.</li>
              <li>Implemented Firebase Realtime Database and Firebase Cloud Messaging workflows.</li>
              <li>Contributed to UI development, debugging, and application maintenance.</li>
            </ul>
          </article>
        </div>
      </div>
    </section>

    <section id="education">
      <div class="container">
        <div class="section-heading">
          <div><span class="eyebrow">Learning foundation</span><h2>Education.</h2></div>
        </div>
        <article class="panel timeline-item">
          <div class="timeline-top"><div><h3>Bachelor of Technology (B.Tech)</h3><span class="muted">Rajiv Gandhi Proudyogiki Vishwavidyalaya (RGPV), Bhopal</span></div><span class="timeline-date">2017 — 2021</span></div>
          <p>CGPA: 7.24</p>
        </article>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="panel contact-panel">
          <span class="eyebrow">Have a project in mind?</span>
          <h2>Let's build something <span class="gradient-text">great.</span></h2>
          <p>I'm always interested in connecting with developers, teams, and people building useful products. Reach out through any of the links below.</p>
          <div class="social-links">
            <a class="btn btn-primary" href="mailto:tandonabhishek245@gmail.com">✉ Email me</a>
            <a class="btn btn-secondary" href="https://www.linkedin.com/in/er-abhishek-tandon-3120a1220/" target="_blank" rel="noopener noreferrer">LinkedIn ↗</a>
            <a class="btn btn-secondary" href="https://github.com/Tandon245" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
            <a class="btn btn-secondary" href="https://portfolioabhishektandon.netlify.app/" target="_blank" rel="noopener noreferrer">Portfolio ↗</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <span>© <span id="year"></span> Abhishek Tandon. Built with care.</span>
      <a class="back-top" href="#home">Back to top ↑</a>
    </div>
  </footer>

  <script>
    const menuToggle = document.getElementById("menuToggle");
    const navLinks = document.getElementById("navLinks");

    menuToggle.addEventListener("click", () => {
      const isOpen = navLinks.classList.toggle("open");
      menuToggle.setAttribute("aria-expanded", String(isOpen));
      menuToggle.setAttribute("aria-label", isOpen ? "Close navigation menu" : "Open navigation menu");
      menuToggle.textContent = isOpen ? "×" : "☰";
    });

    navLinks.querySelectorAll("a").forEach((link) => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("open");
        menuToggle.setAttribute("aria-expanded", "false");
        menuToggle.setAttribute("aria-label", "Open navigation menu");
        menuToggle.textContent = "☰";
      });
    });

    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
