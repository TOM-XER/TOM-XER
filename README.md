<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Muhammad Parvez | Portfolio</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', 'Segoe UI', system-ui, -apple-system, BlinkMacSystemFont, 'Roboto', sans-serif;
      background: #0a0f1e;
      color: #eef5ff;
      line-height: 1.5;
      padding: 2rem 1rem;
    }

    /* animated background gradient aura */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 30%, rgba(0, 255, 255, 0.08), rgba(10, 15, 30, 0.95));
      z-index: -2;
      pointer-events: none;
    }

    /* floating particles animation */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
      overflow: hidden;
    }

    .particle {
      position: absolute;
      background: rgba(0, 255, 255, 0.4);
      border-radius: 50%;
      animation: floatParticle 12s infinite ease-in-out;
      opacity: 0;
    }

    @keyframes floatParticle {
      0% {
        transform: translateY(0) translateX(0) scale(0);
        opacity: 0;
      }
      20% {
        opacity: 0.6;
      }
      80% {
        opacity: 0.3;
      }
      100% {
        transform: translateY(-100vh) translateX(40px) scale(1.2);
        opacity: 0;
      }
    }

    /* main container */
    .portfolio-container {
      max-width: 1200px;
      margin: 0 auto;
      backdrop-filter: blur(2px);
    }

    /* animated gradient border card */
    .glass-card {
      background: rgba(15, 25, 45, 0.6);
      backdrop-filter: blur(12px);
      border-radius: 2rem;
      border: 1px solid rgba(0, 255, 255, 0.2);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
    }

    .glass-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 40px rgba(0, 255, 255, 0.15);
      border-color: rgba(0, 255, 255, 0.6);
    }

    /* header section with animated text */
    .hero {
      text-align: center;
      padding: 2.5rem 1rem;
      margin-bottom: 2rem;
      position: relative;
      overflow: hidden;
    }

    .hero::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 10%;
      width: 80%;
      height: 3px;
      background: linear-gradient(90deg, transparent, cyan, #ff66cc, cyan, transparent);
      animation: borderGlow 3s infinite linear;
      border-radius: 4px;
    }

    @keyframes borderGlow {
      0% { background-position: -200%; }
      100% { background-position: 200%; }
      background-size: 200% auto;
    }

    .avatar-wrapper {
      display: inline-block;
      margin-bottom: 1rem;
      position: relative;
    }

    .avatar {
      width: 130px;
      height: 130px;
      background: linear-gradient(135deg, #00c6ff, #0072ff);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3.5rem;
      font-weight: bold;
      color: white;
      box-shadow: 0 0 0 4px rgba(0, 255, 255, 0.5), 0 0 0 8px rgba(0, 200, 255, 0.2);
      animation: pulseRing 2s infinite;
      transition: all 0.3s;
    }

    @keyframes pulseRing {
      0% { box-shadow: 0 0 0 0px rgba(0, 255, 255, 0.7), 0 0 0 5px rgba(0, 200, 255, 0.3);}
      70% { box-shadow: 0 0 0 12px rgba(0, 255, 255, 0), 0 0 0 12px rgba(0, 200, 255, 0);}
      100% { box-shadow: 0 0 0 0px rgba(0, 255, 255, 0), 0 0 0 0px rgba(0, 200, 255, 0);}
    }

    .name {
      font-size: 3rem;
      font-weight: 800;
      background: linear-gradient(135deg, #FFFFFF, #00ffff, #ff66cc, #ffcc33);
      background-size: 300% 300%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: gradientShift 4s ease infinite;
      margin-bottom: 0.5rem;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .username {
      font-size: 1.3rem;
      background: rgba(0, 255, 255, 0.2);
      display: inline-block;
      padding: 0.3rem 1.2rem;
      border-radius: 40px;
      backdrop-filter: blur(4px);
      letter-spacing: 1px;
      font-family: monospace;
      border: 1px solid cyan;
      animation: blinkBorder 1.8s infinite;
    }

    @keyframes blinkBorder {
      0%, 100% { border-color: cyan; box-shadow: 0 0 3px cyan;}
      50% { border-color: #ff66cc; box-shadow: 0 0 8px #ff66cc;}
    }

    .tagline {
      font-size: 1.2rem;
      margin-top: 1rem;
      color: #b0e0ff;
      display: flex;
      justify-content: center;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .typed-text {
      background: linear-gradient(90deg, #0ff, #f0f);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-weight: 600;
      animation: flicker 2s infinite;
    }

    @keyframes flicker {
      0%, 100% { opacity: 1; text-shadow: 0 0 2px cyan;}
      50% { opacity: 0.8; text-shadow: 0 0 8px magenta;}
    }

    /* contact row */
    .contact-bar {
      display: flex;
      justify-content: center;
      gap: 2rem;
      margin: 1.5rem 0 2rem;
      flex-wrap: wrap;
    }

    .contact-btn {
      background: rgba(0, 20, 40, 0.7);
      backdrop-filter: blur(8px);
      padding: 0.7rem 1.8rem;
      border-radius: 50px;
      text-decoration: none;
      font-weight: bold;
      color: white;
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
      border: 1px solid rgba(0, 255, 255, 0.5);
      font-size: 1.1rem;
    }

    .contact-btn:hover {
      transform: scale(1.08);
      background: rgba(0, 255, 255, 0.2);
      border-color: #0ff;
      box-shadow: 0 0 15px cyan;
      letter-spacing: 1px;
    }

    .contact-icon {
      font-size: 1.4rem;
      animation: bounceIcon 0.8s infinite alternate;
    }

    @keyframes bounceIcon {
      0% { transform: translateY(0px);}
      100% { transform: translateY(-4px);}
    }

    /* section titles with animated underline */
    .section-title {
      font-size: 2rem;
      margin: 2rem 0 1.5rem 0;
      position: relative;
      display: inline-block;
    }

    .section-title::after {
      content: '';
      position: absolute;
      bottom: -8px;
      left: 0;
      width: 60%;
      height: 3px;
      background: linear-gradient(90deg, cyan, #ff44cc);
      animation: slideWidth 2s infinite alternate;
    }

    @keyframes slideWidth {
      0% { width: 30%; opacity: 0.6; }
      100% { width: 100%; opacity: 1; }
    }

    /* project grid */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.8rem;
      margin-top: 1rem;
    }

    .project-card {
      background: rgba(10, 20, 35, 0.7);
      backdrop-filter: blur(10px);
      border-radius: 1.5rem;
      padding: 1.5rem;
      transition: all 0.4s ease;
      border-left: 4px solid cyan;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(0, 255, 255, 0.1), transparent);
      transition: left 0.6s;
    }

    .project-card:hover::before {
      left: 100%;
    }

    .project-card:hover {
      transform: translateY(-8px) scale(1.01);
      box-shadow: 0 20px 30px -10px rgba(0, 255, 255, 0.3);
      border-left-color: #ff66cc;
    }

    .project-title {
      font-size: 1.6rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      background: linear-gradient(120deg, #fff, #aaffff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .project-tech {
      display: inline-block;
      background: rgba(0, 255, 255, 0.2);
      padding: 0.2rem 0.8rem;
      border-radius: 20px;
      font-size: 0.75rem;
      margin: 0.5rem 0;
      font-weight: 600;
    }

    .project-desc {
      margin: 0.8rem 0;
      color: #cbd5ff;
    }

    .project-link {
      display: inline-block;
      margin-top: 0.8rem;
      text-decoration: none;
      color: cyan;
      font-weight: bold;
      transition: 0.2s;
      border-bottom: 1px dashed cyan;
    }

    .project-link:hover {
      color: #ff88dd;
      border-bottom-color: #ff88dd;
      letter-spacing: 1px;
    }

    /* stats row */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.8rem;
      margin: 2rem 0;
    }

    .stats-card {
      background: rgba(10, 25, 45, 0.6);
      border-radius: 1.2rem;
      padding: 0.6rem;
      transition: 0.3s;
      border: 1px solid rgba(0, 255, 255, 0.3);
    }

    .stats-card:hover {
      transform: scale(1.02);
      border-color: cyan;
    }

    /* animated skill badges */
    .skills {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin: 1.5rem 0;
      justify-content: center;
    }

    .skill-badge {
      background: linear-gradient(145deg, #1e2a47, #0f172a);
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      font-weight: 500;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
      transition: all 0.2s;
      animation: softGlow 2s infinite alternate;
      border: 1px solid rgba(0, 255, 255, 0.4);
    }

    @keyframes softGlow {
      0% { text-shadow: 0 0 0px cyan; border-color: rgba(0,255,255,0.3);}
      100% { text-shadow: 0 0 2px cyan; border-color: cyan; box-shadow: 0 0 6px rgba(0,255,255,0.5);}
    }

    .skill-badge:hover {
      transform: translateY(-3px);
    }

    /* animated footer */
    .footer {
      text-align: center;
      margin-top: 3rem;
      padding: 1.5rem;
      border-radius: 2rem;
      background: rgba(0, 0, 0, 0.3);
      backdrop-filter: blur(4px);
      animation: fadeSlide 1.2s;
    }

    @keyframes fadeSlide {
      from { opacity: 0; transform: translateY(20px);}
      to { opacity: 1; transform: translateY(0);}
    }

    .glow-text {
      animation: pulseText 1.8s infinite;
    }

    @keyframes pulseText {
      0%, 100% { opacity: 0.8; text-shadow: 0 0 2px cyan;}
      50% { opacity: 1; text-shadow: 0 0 8px #ff44cc;}
    }

    hr {
      border: none;
      height: 2px;
      background: linear-gradient(90deg, transparent, cyan, #ff66cc, transparent);
      margin: 1rem 0;
    }
  </style>
</head>
<body>
<div class="particles" id="particles"></div>
<div class="portfolio-container">

  <!-- Hero section with animated gradient and pulse avatar -->
  <div class="glass-card hero">
    <div class="avatar-wrapper">
      <div class="avatar">👨‍💻</div>
    </div>
    <h1 class="name">MUHAMMAD PARVEZ</h1>
    <div class="username">@TOM-XER</div>
    <div class="tagline">
      <span>🚀 Full‑Stack Developer</span>
      <span>⚡ Python & Web Expert</span>
      <span class="typed-text">✦ Automation Enthusiast ✦</span>
    </div>
    <div class="tagline" style="font-size:0.9rem; margin-top:0.5rem;">
      <span>💻 15+ Web Projects</span>
      <span>🐍 12+ Python Tools</span>
      <span>✨ AI & Bots</span>
    </div>
  </div>

  <!-- Contact animated links -->
  <div class="contact-bar">
    <a href="https://facebook.com/parvez.0142" target="_blank" class="contact-btn">
      <span class="contact-icon">📘</span> Facebook
    </a>
    <a href="https://instagram.com/parvez.0142" target="_blank" class="contact-btn">
      <span class="contact-icon">📷</span> Instagram
    </a>
    <a href="https://github.com/TOM-XER" target="_blank" class="contact-btn">
      <span class="contact-icon">🐙</span> GitHub
    </a>
  </div>

  <!-- about & automation motion text -->
  <div class="glass-card" style="padding: 1.5rem; margin-bottom: 1.5rem; text-align: center;">
    <p style="font-size: 1.1rem;">⚙️ <strong>Automotion Portfolio</strong> — fully animated, interactive showcase of my <strong>Web & Python universe</strong>. Every element breathes with motion, reflecting modern development craft.</p>
    <p style="margin-top: 0.8rem;">🔥 <strong>“Code that moves, designs that inspire”</strong> — Muhammad Parvez</p>
  </div>

  <!-- Skills section with animated badges -->
  <h2 class="section-title">🛠️ Tech Arsenal (animated)</h2>
  <div class="skills">
    <span class="skill-badge">Python 🐍</span>
    <span class="skill-badge">Django ⚡</span>
    <span class="skill-badge">Flask 🌶️</span>
    <span class="skill-badge">React ⚛️</span>
    <span class="skill-badge">JavaScript 💛</span>
    <span class="skill-badge">HTML5/CSS3 🎨</span>
    <span class="skill-badge">FastAPI 🚀</span>
    <span class="skill-badge">PostgreSQL 🐘</span>
    <span class="skill-badge">Docker 🐳</span>
    <span class="skill-badge">Selenium 🤖</span>
  </div>

  <!-- Projects Section: ALL WEB & PYTHON PROJECTS -->
  <h2 class="section-title">🌐 Web Development Projects</h2>
  <div class="projects-grid">
    <div class="project-card">
      <div class="project-title">AI Content Hub</div>
      <div class="project-tech">React + Django + GPT API</div>
      <div class="project-desc">Intelligent blog platform with AI summarizer, realtime editor, and user dashboard. Fully responsive & animated UI.</div>
      <a href="#" class="project-link">🔗 Live Demo →</a>
    </div>
    <div class="project-card">
      <div class="project-title">EcoCart Marketplace</div>
      <div class="project-tech">MERN Stack</div>
      <div class="project-desc">Full e-commerce with payment, admin panel, product filters, and dynamic order tracking.</div>
      <a href="#" class="project-link">🔗 Source Code →</a>
    </div>
    <div class="project-card">
      <div class="project-title">Portfolio 4D</div>
      <div class="project-tech">Three.js + GSAP</div>
      <div class="project-desc">3D interactive portfolio with WebGL, particle system, and smooth scroll animations.</div>
      <a href="#" class="project-link">🔗 Explore →</a>
    </div>
    <div class="project-card">
      <div class="project-title">DevCollab Hub</div>
      <div class="project-tech">Flask + Socket.io</div>
      <div class="project-desc">Real-time collaborative code editor with chat, syntax highlighting, and room sharing.</div>
      <a href="#" class="project-link">🔗 Join Beta →</a>
    </div>
  </div>

  <h2 class="section-title">🐍 Python Projects (Automation & AI)</h2>
  <div class="projects-grid">
    <div class="project-card">
      <div class="project-title">AutoML Pipeline</div>
      <div class="project-tech">Python, Scikit-learn, Pandas</div>
      <div class="project-desc">Automated machine learning tool that preprocesses, trains, and evaluates models with one CLI command.</div>
      <a href="#" class="project-link">🔗 View Repo →</a>
    </div>
    <div class="project-card">
      <div class="project-title">Smart Instagram Bot</div>
      <div class="project-tech">InstaPy + Selenium</div>
      <div class="project-desc">Automation bot for engagement, smart comments, and AI-powered content analysis.</div>
      <a href="#" class="project-link">🔗 Bot Demo →</a>
    </div>
    <div class="project-card">
      <div class="project-title">Web Scraper Studio</div>
      <div class="project-tech">BeautifulSoup, Scrapy, FastAPI</div>
      <div class="project-desc">Enterprise-grade scraping framework with proxy rotation, data export, and dashboard.</div>
      <a href="#" class="project-link">🔗 Scraper API →</a>
    </div>
    <div class="project-card">
      <div class="project-title">TaskFlow CLI</div>
      <div class="project-tech">Python, Click, SQLite</div>
      <div class="project-desc">Terminal productivity tool with animated progress bars, reminders, and time tracking.</div>
      <a href="#" class="project-link">🔗 Install Now →</a>
    </div>
  </div>

  <!-- GitHub Stats with animated hover cards (dynamic images) -->
  <h2 class="section-title">📊 GitHub Analytics (live)</h2>
  <div class="stats-row">
    <div class="stats-card">
      <img src="https://github-readme-stats.vercel.app/api?username=TOM-XER&show_icons=true&count_private=true&hide_border=true&bg_color=0a0f1e&title_color=00ffff&text_color=ccd6f6&icon_color=ff66cc" alt="GitHub Stats" style="border-radius: 1rem; max-width: 100%;">
    </div>
    <div class="stats-card">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=TOM-XER&theme=radical&hide_border=true&background=0a0f1e&ring=00ffff&fire=ff66cc&currStreakLabel=00ffff" alt="GitHub Streak" style="border-radius: 1rem;">
    </div>
    <div class="stats-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=TOM-XER&layout=compact&theme=radical&hide_border=true&bg_color=0a0f1e&title_color=00ffff" alt="Top Languages" style="border-radius: 1rem;">
    </div>
  </div>

  <!-- animated activity graph with motion blur? Contribution graph style -->
  <div style="margin: 2rem 0; text-align: center;">
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=TOM-XER&theme=react-dark&bg_color=0a0f1e&color=00ffff&line=ff66cc&point=ffffff&area=true&hide_border=true" width="100%" alt="contribution graph" style="border-radius: 20px;">
  </div>

  <!-- Automation Feature Highlights (Animated Showcase) -->
  <div class="glass-card" style="padding: 1.8rem; margin: 2rem 0; text-align: center;">
    <h3 style="font-size: 1.8rem; margin-bottom: 1rem;">✨ <span class="glow-text">AUTOMOTION FEATURES</span> ✨</h3>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 1.5rem;">
      <div style="background: rgba(0,255,255,0.1); border-radius: 50px; padding: 0.5rem 1.5rem;">⚡ Live CSS Animations</div>
      <div style="background: rgba(0,255,255,0.1); border-radius: 50px; padding: 0.5rem 1.5rem;">🌀 Floating Particles</div>
      <div style="background: rgba(0,255,255,0.1); border-radius: 50px; padding: 0.5rem 1.5rem;">🎭 Hover 3D Cards</div>
      <div style="background: rgba(0,255,255,0.1); border-radius: 50px; padding: 0.5rem 1.5rem;">🌈 Gradient Motion Shift</div>
      <div style="background: rgba(0,255,255,0.1); border-radius: 50px; padding: 0.5rem 1.5rem;">🔁 Infinite Border Pulse</div>
    </div>
    <p style="margin-top: 1.5rem;">⚙️ <strong>“All Web + Python projects”</strong> are crafted with love, automation scripts, and cutting-edge motion. <br> Developed by Muhammad Parvez (TOM-XER). Every line pulses with energy.</p>
  </div>

  <!-- Footer with contact again -->
  <div class="footer">
    <p>🚀 <strong>MUHAMMAD PARVEZ</strong> | Portfolio 2025 — Fully Automotion Animated</p>
    <p style="margin-top: 0.5rem;">📧 Reach out for collab | 🌟 <a href="https://facebook.com/parvez.0142" style="color: cyan; text-decoration: none;">Facebook</a> | 📸 <a href="https://instagram.com/parvez.0142" style="color: #ff66cc;">Instagram</a></p>
    <hr>
    <p class="glow-text" style="font-size: 0.85rem;">💫 “Automation meets art — interactive portfolio in motion” 💫</p>
  </div>
</div>

<script>
  // generate floating particles dynamically for extra motion feel (CSS only but we can add random particles)
  (function createParticles() {
    const container = document.getElementById('particles');
    const particleCount = 45;
    for (let i = 0; i < particleCount; i++) {
      const particle = document.createElement('div');
      particle.classList.add('particle');
      const size = Math.random() * 6 + 2;
      particle.style.width = size + 'px';
      particle.style.height = size + 'px';
      particle.style.left = Math.random() * 100 + '%';
      particle.style.animationDelay = Math.random() * 12 + 's';
      particle.style.animationDuration = 8 + Math.random() * 10 + 's';
      particle.style.opacity = Math.random() * 0.5;
      particle.style.background = `radial-gradient(circle, cyan, rgba(0,255,255,0.2))`;
      container.appendChild(particle);
    }
  })();
</script>
</body>
</html>
