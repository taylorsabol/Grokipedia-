# Grokipedia-
Taylor Sabol
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Taylor Sabol</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;900&display=swap" rel="stylesheet">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
  <script src="https://cdn.jsdelivr.net/gh/studio-freight/lenis@1.0.42/bundles/lenis.min.js"></script>

  <style>
    :root {
      --bg: #0f0f1a;
      --accent: #8b5cf6;
      --gradient: linear-gradient(135deg, #8b5cf6, #ec4899);
      --text: #f0f0f0;
      --text-muted: #a0a0cc;
    }
    * { margin:0; padding:0; box-sizing:border-box; }
    body { font-family: 'Inter', sans-serif; background: var(--bg); color: var(--text); overflow-x: hidden; }
    
    /* Loading Screen - exact premium style */
    #loader {
      position: fixed; top:0; left:0; width:100%; height:100%; background: var(--bg); z-index:9999;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
    }
    #loader h1 {
      font-size: 5.5rem; font-weight: 900; background: var(--gradient); -webkit-background-clip: text;
      -webkit-text-fill-color: transparent; background-clip: text; opacity: 0;
    }
    #loader .bar {
      width: 400px; height: 3px; background: rgba(255,255,255,0.1); margin-top: 2rem; border-radius: 2px; overflow: hidden;
    }
    #loader .fill { height:100%; width:0%; background: var(--gradient); }

    /* Custom Cursor */
    .cursor { position: fixed; width: 12px; height: 12px; background: var(--accent); border-radius: 50%; pointer-events: none; z-index: 9998; transform: translate(-50%,-50%); transition: transform 0.2s; }
    .cursor-ring { position: fixed; width: 40px; height: 40px; border: 2px solid var(--accent); border-radius: 50%; pointer-events: none; z-index: 9998; transform: translate(-50%,-50%); transition: all 0.3s; }

    main { opacity: 0; }
    section { padding: 12vh 8vw; min-height: 100vh; display: flex; flex-direction: column; justify-content: center; }
    h1 { font-size: 6rem; font-weight: 900; line-height: 1; }
    h2 { font-size: 3.5rem; background: var(--gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    p { font-size: 1.3rem; line-height: 1.8; max-width: 700px; color: var(--text-muted); margin: 1.5rem 0; }
    .btn { display: inline-block; margin-top: 2rem; padding: 1rem 2rem; background: var(--gradient); color: white; border-radius: 50px; text-decoration: none; font-weight: 600; }

    .projects { display: grid; grid-template-columns: repeat(auto-fit, minmax(380px, 1fr)); gap: 3rem; margin-top: 5rem; }
    .project-card {
      background: rgba(255,255,255,0.03); backdrop-filter: blur(10px); border-radius: 20px; padding: 2.5rem;
      transition: transform 0.5s ease; border: 1px solid rgba(139,92,246,0.2);
    }
    .project-card:hover { transform: translateY(-20px); }
  </style>
</head>
<body>

  <!-- Custom Cursor -->
  <div class="cursor"></div>
  <div class="cursor-ring"></div>

  <!-- Loading Screen -->
  <div id="loader">
    <h1>Taylor Sabol</h1>
    <div class="bar"><div class="fill"></div></div>
  </div>

  <main>
    <!-- Hero -->
    <section>
      <h1>Taylor Sabol</h1>
      <p style="font-size:2.5rem; margin:2rem 0;">Full-Stack Developer • Designer • Creative Technologist</p>
      <p>I'm a passionate full-stack developer and designer focused on building beautiful, performant, and user-centric digital experiences.<br>With expertise in modern web technologies and a strong eye for design, I turn ideas into reality — from concept to deployment.</p>
      <a href="#contact" class="btn">Let's Collaborate</a>
    </section>

    <!-- About / Experience -->
    <section>
      <h2>About Me</h2>
      <p>With years of experience architecting scalable systems and leading frontend initiatives for global products, I specialize in React/Next.js, Node.js, cloud infrastructure, and pixel-perfect UI/UX.</p>
      
      <h2 style="margin-top:5rem;">Skills & Expertise</h2>
      <p>React / Next.js • Node.js / Express • PostgreSQL / MongoDB • AWS / Docker • Figma / UI/UX • Three.js / GSAP • Git / CI/CD</p>
    </section>

    <!-- Projects -->
    <section>
      <h2>Featured Projects</h2>
      <div class="projects">
        <div class="project-card">
          <h3>Project Horizon</h3>
          <p>Real-time collaborative platform with advanced WebSocket integration and D3 visualizations.</p>
          <a href="#" style="color:var(--accent);">View Project →</a>
        </div>
        <div class="project-card">
          <h3>Nexus Commerce</h3>
          <p>Headless e-commerce solution built with Next.js, Stripe, and Sanity CMS.</p>
          <a href="#" style="color:var(--accent);">GitHub →</a>
        </div>
        <!-- Add more of your real projects here from taylorsabol.com -->
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <h2>Let's Build Something</h2>
      <p>I'm currently open to new opportunities and exciting projects.</p>
      <a href="mailto:hello@taylorsabol.com" style="font-size:2rem; color:var(--accent);">hello@taylorsabol.com</a>
    </section>
  </main>

<script>
  // Smooth scroll
  const lenis = new Lenis();
  lenis.on('scroll', ScrollTrigger.update);
  gsap.ticker.add((t)=>{ lenis.raf(t * 1000); });

  // Custom cursor
  const cursor = document.querySelector('.cursor');
  const ring = document.querySelector('.cursor-ring');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
    ring.style.left = e.clientX + 'px';
    ring.style.top = e.clientY + 'px';
  });
  document.querySelectorAll('a, button').forEach(el => {
    el.addEventListener('mouseenter', () => ring.style.transform = 'translate(-50%,-50%) scale(1.5)');
    el.addEventListener('mouseleave', () => ring.style.transform = 'translate(-50%,-50%) scale(1)');
  });

  // Loading animation (exact premium timing)
  gsap.to(".fill", { width: "100%", duration: 3, ease: "power2.out" });
  gsap.to("#loader h1", { opacity: 1, y: 0, duration: 1, delay: 0.5 });
  setTimeout(() => {
    gsap.to("#loader", { y: "-100%", duration: 1.2, ease: "power4.inOut" });
    gsap.to("main", { opacity: 1, duration: 1.5, delay: 0.8 });
  }, 3500);

  // Scroll reveals
  gsap.utils.toArray("section").forEach(sec => {
    gsap.from(sec.children, { y: 80, opacity: 0, duration: 1.2, stagger: 0.2,
      scrollTrigger: { trigger: sec, start: "top 75%" }
    });
  });
</script>
</body>
</html>
