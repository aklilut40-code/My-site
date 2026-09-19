<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Alex Rivera · beautiful portfolio</title>
  <!-- Font Awesome (icons) & Google Fonts -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #faf9ff;
      color: #1e1b2b;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* === GLOW & GRADIENTS === */
    .gradient-text {
      background: linear-gradient(135deg, #a855f7, #ec4899, #f97316);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    /* === HEADER / NAV === */
    header {
      padding: 20px 0;
      position: sticky;
      top: 0;
      backdrop-filter: blur(12px);
      background: rgba(250, 249, 255, 0.75);
      z-index: 100;
      border-bottom: 1px solid rgba(168, 85, 247, 0.1);
    }

    .nav-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-weight: 700;
      font-size: 1.8rem;
      letter-spacing: -0.03em;
    }

    .logo span {
      background: linear-gradient(135deg, #a855f7, #ec4899);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-weight: 500;
      color: #2d2640;
      transition: color 0.2s ease;
      font-size: 1rem;
    }

    .nav-links a:hover {
      color: #a855f7;
    }

    /* === HERO SECTION === */
    .hero {
      padding: 100px 0 80px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 40px;
    }

    .hero-content {
      flex: 1 1 350px;
    }

    .hero-badge {
      display: inline-block;
      background: rgba(168, 85, 247, 0.12);
      color: #8b5cf6;
      font-size: 0.85rem;
      font-weight: 600;
      padding: 6px 16px;
      border-radius: 40px;
      margin-bottom: 24px;
      letter-spacing: 0.3px;
      border: 1px solid rgba(168, 85, 247, 0.2);
    }

    .hero h1 {
      font-size: clamp(2.6rem, 8vw, 4.5rem);
      font-weight: 700;
      line-height: 1.1;
      letter-spacing: -0.03em;
      margin-bottom: 18px;
    }

    .hero p {
      font-size: 1.2rem;
      color: #4b445e;
      max-width: 550px;
      margin-bottom: 32px;
      font-weight: 400;
    }

    .hero-actions {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 14px 32px;
      border-radius: 60px;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.25s ease;
      font-size: 1rem;
      border: none;
      cursor: pointer;
    }

    .btn-primary {
      background: linear-gradient(135deg, #a855f7, #ec4899);
      color: white;
      box-shadow: 0 12px 24px -8px rgba(168, 85, 247, 0.4);
    }

    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 18px 30px -8px rgba(168, 85, 247, 0.6);
    }

    .btn-outline {
      background: transparent;
      border: 2px solid #e2d9f3;
      color: #2d2640;
    }

    .btn-outline:hover {
      border-color: #a855f7;
      background: rgba(168, 85, 247, 0.04);
      transform: translateY(-2px);
    }

    .hero-avatar {
      flex: 0 0 300px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    .avatar-blob {
      width: 300px;
      height: 300px;
      background: linear-gradient(135deg, #d8b4fe, #f9a8d4);
      border-radius: 62% 38% 46% 54% / 60% 54% 46% 40%;
      display: flex;
      justify-content: center;
      align-items: center;
      box-shadow: 0 30px 40px -20px rgba(168, 85, 247, 0.5);
      animation: blob-morph 8s infinite alternate ease-in-out;
    }

    .avatar-blob i {
      font-size: 9rem;
      color: white;
      filter: drop-shadow(0 12px 10px rgba(0, 0, 0, 0.1));
    }

    @keyframes blob-morph {
      0% { border-radius: 62% 38% 46% 54% / 60% 54% 46% 40%; }
      100% { border-radius: 46% 54% 40% 60% / 52% 46% 54% 48%; }
    }

    /* === SECTION TITLES === */
    .section-title {
      font-size: 2.2rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      margin-bottom: 16px;
    }

    .section-sub {
      color: #6b6280;
      font-size: 1.1rem;
      max-width: 600px;
      margin-bottom: 48px;
    }

    /* === PROJECTS GRID === */
    .projects {
      padding: 80px 0;
    }

    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 28px;
    }

    .project-card {
      background: white;
      border-radius: 32px;
      padding: 32px 28px;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.02);
      border: 1px solid rgba(168, 85, 247, 0.08);
      transition: all 0.3s cubic-bezier(0.2, 0, 0, 1);
      display: flex;
      flex-direction: column;
    }

    .project-card:hover {
      transform: translateY(-8px);
      border-color: rgba(168, 85, 247, 0.3);
      box-shadow: 0 30px 40px -20px rgba(168, 85, 247, 0.35);
    }

    .project-icon {
      width: 58px;
      height: 58px;
      background: rgba(168, 85, 247, 0.1);
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 24px;
      font-size: 1.8rem;
      color: #a855f7;
    }

    .project-card h3 {
      font-size: 1.5rem;
      font-weight: 600;
      margin-bottom: 10px;
      letter-spacing: -0.02em;
    }

    .project-card p {
      color: #5f5875;
      margin-bottom: 24px;
      flex: 1;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 24px;
    }

    .project-tags span {
      background: #f1ebff;
      padding: 6px 14px;
      border-radius: 40px;
      font-size: 0.8rem;
      font-weight: 500;
      color: #6d4fc9;
    }

    .project-link {
      text-decoration: none;
      font-weight: 600;
      color: #a855f7;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 0.95rem;
      transition: gap 0.2s;
    }

    .project-link:hover {
      gap: 14px;
    }

    /* === SKILLS SECTION (interactive) === */
    .skills {
      padding: 60px 0 80px;
    }

    .skills-wrapper {
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      margin-top: 20px;
    }

    .skill-pill {
      background: white;
      padding: 12px 26px;
      border-radius: 60px;
      font-weight: 500;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
      border: 1px solid #ede7ff;
      transition: all 0.2s ease;
      cursor: default;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .skill-pill i {
      color: #a855f7;
      font-size: 1rem;
    }

    .skill-pill:hover {
      border-color: #c4a0ff;
      background: #fcfaff;
      transform: scale(1.02);
    }

    /* === FOOTER === */
    footer {
      padding: 48px 0;
      border-top: 1px solid #ede7ff;
      margin-top: 40px;
      text-align: center;
      color: #6b6280;
    }

    .social-links {
      display: flex;
      justify-content: center;
      gap: 26px;
      margin-bottom: 24px;
    }

    .social-links a {
      color: #5b4e7a;
      font-size: 1.6rem;
      transition: all 0.2s;
    }

    .social-links a:hover {
      color: #a855f7;
      transform: translateY(-4px);
    }

    .footer-copy {
      font-size: 0.9rem;
    }

    /* === RESPONSIVE === */
    @media (max-width: 700px) {
      .hero {
        padding: 60px 0 40px;
        text-align: center;
        justify-content: center;
      }

      .hero p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-actions {
        justify-content: center;
      }

      .nav-links {
        display: none;
      }

      .avatar-blob {
        width: 240px;
        height: 240px;
      }

      .avatar-blob i {
        font-size: 7rem;
      }

      .section-title {
        font-size: 1.9rem;
      }

      .btn {
        padding: 12px 26px;
      }
    }
  </style>
</head>
<body>

  <!-- header / nav -->
  <header>
    <div class="container nav-bar">
      <div class="logo"><span>✦</span> alex.dev</div>
      <ul class="nav-links">
        <li><a href="#">Work</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </header>

  <main>
    <!-- HERO SECTION -->
    <div class="container hero">
      <div class="hero-content">
        <div class="hero-badge">
          <i class="fas fa-sparkles" style="margin-right: 6px;"></i> open to opportunities
        </div>
        <h1>
          Crafting <span class="gradient-text">digital</span><br>
          experiences with soul
        </h1>
        <p>
          I'm Alex Rivera — a designer & front‑end developer blending clean code with 
          beautiful, intuitive interfaces.
        </p>
        <div class="hero-actions">
          <a href="#" class="btn btn-primary">
            <i class="fas fa-arrow-down"></i> See my work
          </a>
          <a href="#" class="btn btn-outline">
            <i class="fas fa-paper-plane"></i> Let's talk
          </a>
        </div>
      </div>
      <div class="hero-avatar">
        <div class="avatar-blob">
          <i class="fas fa-code"></i>
        </div>
      </div>
    </div>

    <!-- PROJECTS SECTION -->
    <section class="projects">
      <div class="container">
        <h2 class="section-title">Featured <span class="gradient-text">projects</span></h2>
        <p class="section-sub">A curated selection of things I've built — from playful experiments to production apps.</p>

        <div class="project-grid">
          <!-- card 1 -->
          <div class="project-card">
            <div class="project-icon"><i class="fas fa-paint-brush"></i></div>
            <h3>Lumina UI</h3>
            <p>A light & airy design system with 40+ components, dark mode, and smooth micro-interactions.</p>
            <div class="project-tags">
              <span>React</span>
              <span>Figma</span>
              <span>Storybook</span>
            </div>
            <a href="#" class="project-link">Live demo <i class="fas fa-arrow-right"></i></a>
          </div>

          <!-- card 2 -->
          <div class="project-card">
            <div class="project-icon"><i class="fas fa-chart-line"></i></div>
            <h3>Flow Analytics</h3>
            <p>Minimal dashboard for tracking product metrics. Real‑time data with elegant charts and filters.</p>
            <div class="project-tags">
              <span>Vue</span>
              <span>D3.js</span>
              <span>Tailwind</span>
            </div>
            <a href="#" class="project-link">Live demo <i class="fas fa-arrow-right"></i></a>
          </div>

          <!-- card 3 -->
          <div class="project-card">
            <div class="project-icon"><i class="fas fa-mobile-alt"></i></div>
            <h3>EcoPulse</h3>
            <p>Mobile‑first concept for community climate action. Gamified challenges & local impact map.</p>
            <div class="project-tags">
              <span>React Native</span>
              <span>Firebase</span>
            </div>
            <a href="#" class="project-link">Case study <i class="fas fa-arrow-right"></i></a>
          </div>
        </div>
      </div>
    </section>

    <!-- SKILLS SECTION (interactive pills) -->
    <section class="skills">
      <div class="container">
        <h2 class="section-title">Toolbox & <span class="gradient-text">skills</span></h2>
        <p class="section-sub">Technologies I work with daily — always learning and adding more.</p>
        <div class="skills-wrapper" id="skillsContainer">
          <!-- dynamically populated? we'll use static + js interactive filtering, but let's keep static for simplicity -->
          <div class="skill-pill"><i class="fab fa-js"></i> JavaScript (ES6+)</div>
          <div class="skill-pill"><i class="fab fa-react"></i> React</div>
          <div class="skill-pill"><i class="fab fa-vuejs"></i> Vue</div>
          <div class="skill-pill"><i class="fab fa-html5"></i> HTML5</div>
          <div class="skill-pill"><i class="fab fa-css3-alt"></i> CSS3 / Sass</div>
          <div class="skill-pill"><i class="fas fa-mobile-alt"></i> Responsive Design</div>
          <div class="skill-pill"><i class="fas fa-pencil-ruler"></i> UI/UX</div>
          <div class="skill-pill"><i class="fas fa-code-branch"></i> Git & GitHub</div>
          <div class="skill-pill"><i class="fas fa-cloud"></i> Firebase</div>
          <div class="skill-pill"><i class="fas fa-database"></i> REST APIs</div>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer>
    <div class="container">
      <div class="social-links">
        <a href="#" aria-label="GitHub"><i class="fab fa-github"></i></a>
        <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
        <a href="#" aria-label="Dribbble"><i class="fab fa-dribbble"></i></a>
        <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
      </div>
      <div class="footer-copy">
        &copy; 2025 Alex Rivera · designed & built with <i class="fas fa-heart" style="color: #ec4899;"></i>
      </div>
    </div>
  </footer>

  <!-- simple interactive javascript: dynamic year, skill highlighting, and smooth scroll -->
  <script>
    (function() {
      // 1. update footer year automatically
      const footerCopy = document.querySelector('.footer-copy');
      if (footerCopy) {
        const currentYear = new Date().getFullYear();
        footerCopy.innerHTML = footerCopy.innerHTML.replace('2025', currentYear);
      }

      // 2. Interactive skill pills – subtle bounce on click & console greet (just for fun)
      const skills = document.querySelectorAll('.skill-pill');
      skills.forEach(skill => {
        skill.addEventListener('click', function(e) {
          // tiny visual pulse
          this.style.transform = 'scale(0.96)';
          setTimeout(() => { this.style.transform = ''; }, 120);
          // optional: log the skill text (clean & minimal)
          const skillName = this.innerText.trim();
          console.log(`✨ skill: ${skillName}`);
        });
      });

      // 3. Add a smooth scroll behavior to all anchor links with # (except dummy)
      document.querySelectorAll('a[href="#"]').forEach(link => {
        link.addEventListener('click', (e) => {
          e.preventDefault();  // prevent page jump for empty links
          // gentle nudge to show it's interactive: could scroll to top or not — but let's not
          // but we can add a small temporary toast? not needed.
          // just a friendly console note
          console.log('🔗 navigation link (demo)');
        });
      });

      // 4. Nav links that are #project etc — but we have no sections with ids, so we'll add ids for demo? 
      // Let's quickly assign IDs to sections for smoother nav (just for demonstration)
      // Actually we can set href="#work" to projects etc. but we didn't. Let's add IDs and update hrefs
      // But not required, portfolio is static. We'll just make the nav links smooth scroll to sections.
      // I'll assign ids to sections:
      const heroSection = document.querySelector('.hero');
      const projectsSection = document.querySelector('.projects');
      const skillsSection = document.querySelector('.skills');

      if (heroSection) heroSection.id = 'home';
      if (projectsSection) projectsSection.id = 'work';
      if (skillsSection) skillsSection.id = 'skills';

      // now update nav links hrefs dynamically (so they actually work)
      const navLinks = document.querySelectorAll('.nav-links a');
      if (navLinks.length >= 4) {
        navLinks[0].href = '#work';      // Work
        navLinks[1].href = '#work';      // Projects (same as work, fine)
        navLinks[2].href = '#skills';    // About? we use skills as about-ish
        navLinks[3].href = '#contact';   // Contact — but no contact section. let's create a dummy id on footer.
      }
      const footer = document.querySelector('footer');
      if (footer) footer.id = 'contact';

      // Also update the "See my work" button to point to #work
      const primaryBtn = document.querySelector('.btn-primary');
      if (primaryBtn) primaryBtn.href = '#work';

      // and outline button to #contact (footer)
      const outlineBtn = document.querySelector('.btn-outline');
      if (outlineBtn) outlineBtn.href = '#contact';

      // Also fix the "Let's talk" outline button
      // (already done above)

      // 5. (optional) add a simple scroll reveal animation for project cards — but keep it lightweight.
      // I'll add a subtle fade-in when they enter viewport using IntersectionObserver.
      const projectCards = document.querySelectorAll('.project-card');
      if (projectCards.length) {
        // initial style: slightly transparent & shifted
        projectCards.forEach(card => {
          card.style.opacity = '0';
          card.style.transform = 'translateY(20px)';
          card.style.transition = 'opacity 0.5s ease, transform 0.5s ease, box-shadow 0.3s, border-color 0.3s';
        });

        const observer = new IntersectionObserver((entries) => {
          entries.forEach(entry => {
            if (entry.isIntersecting) {
              entry.target.style.opacity = '1';
              entry.target.style.transform = 'translateY(0)';
              observer.unobserve(entry.target); // animate only once
            }

    
          });
        }, { threshold: 0.15 });

        projectCards.forEach(card => observer.observe(card));
      }

      // Also apply same to skills pills (staggered)
      const skillPills = document.querySelectorAll('.skill-pill');
      if (skillPills.length) {
        skillPills.forEach((pill, index) => {
          pill.style.opacity = '0';
          pill.style.transform = 'translateY(10px)';
          pill.style.transition = `opacity 0.4s ease ${index * 0.03}s, transform 0.4s ease ${index * 0.03}s, border-color 0.2s, background 0.2s`;
        });

        const skillObserver = new IntersectionObserver((entries) => {
          entries.forEach(entry => {
            if (entry.isIntersecting) {
              entry.target.style.opacity = '1';
              entry.target.style.transform = 'translateY(0)';
              skillObserver.unobserve(entry.target);
            }
          });
        }, { threshold: 0.1 });

        skillPills.forEach(pill => skillObserver.observe(pill));
      }

      // subtle hero blob animation already there.
      console.log('🌸 portfolio ready — enjoy!');
    })();
  </script>
</body>
</html>
