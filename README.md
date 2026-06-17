<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ashim C S | Full-Stack & AI Engineer</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@500;600;700&display=swap" rel="stylesheet">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@500;600;700&display=swap');
    
    :root {
      --primary: 59 130 246;
    }
    
    body {
      font-family: 'Inter', system-ui, sans-serif;
    }
    
    .heading-font {
      font-family: 'Space Grotesk', sans-serif;
    }

    .hero-bg {
      background: radial-gradient(at center bottom, rgba(59, 130, 246, 0.15), transparent 70%);
    }

    .glass {
      background: rgba(15, 23, 42, 0.75);
      backdrop-filter: blur(16px);
    }

    .card-hover {
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .card-hover:hover {
      transform: translateY(-12px) scale(1.02);
      box-shadow: 0 25px 50px -12px rgb(0 0 0 / 0.4);
    }

    .skill-bar {
      height: 6px;
      background: linear-gradient(90deg, rgb(59 130 246), rgb(147 51 234));
      transition: width 1.5s cubic-bezier(0.34, 1.56, 0.64, 1);
    }

    .nav-link {
      position: relative;
    }
    
    .nav-link:after {
      content: '';
      position: absolute;
      width: 0;
      height: 2px;
      bottom: -2px;
      left: 0;
      background: rgb(59 130 246);
      transition: width 0.3s ease;
    }
    
    .nav-link:hover:after {
      width: 100%;
    }

    .glow-text {
      text-shadow: 0 0 20px rgb(59 130 246 / 0.5),
                   0 0 40px rgb(59 130 246 / 0.3);
    }

    .floating {
      animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-20px); }
    }

    .section-title {
      position: relative;
      display: inline-block;
    }
    
    .section-title:after {
      content: '';
      position: absolute;
      width: 60px;
      height: 3px;
      background: linear-gradient(to right, rgb(59 130 246), transparent);
      bottom: -8px;
      left: 0;
    }
  </style>
</head>
<body class="bg-zinc-950 text-zinc-200 overflow-x-hidden">

  <!-- HERO -->
  <header class="hero-bg min-h-screen flex items-center relative">
    <div class="absolute inset-0 bg-[radial-gradient(#27272a_1px,transparent_1px)] [background-size:50px_50px] opacity-20"></div>
    
    <div class="max-w-7xl mx-auto px-6 pt-20 pb-16 relative z-10">
      <div class="flex flex-col lg:flex-row items-center gap-16">
        <!-- Left Content -->
        <div class="lg:w-3/5 space-y-8">
          <div class="inline-flex items-center gap-2 px-5 py-2 bg-white/5 border border-white/10 rounded-3xl text-sm backdrop-blur-md">
            <div class="w-2 h-2 bg-emerald-400 rounded-full animate-pulse"></div>
            Available for Freelance Opportunities
          </div>

          <h1 class="text-7xl lg:text-8xl font-bold heading-font tracking-tighter glow-text">
            ASHIM C S
          </h1>
          
          <p class="text-3xl lg:text-4xl text-zinc-400 font-light">
            Full-Stack Engineer &nbsp;•&nbsp; AI Vision Architect
          </p>

          <p class="max-w-lg text-lg text-zinc-400 leading-relaxed">
            Building intelligent, scalable digital experiences at the intersection of 
            <span class="text-blue-400 font-medium">software engineering</span> and 
            <span class="text-purple-400 font-medium">artificial intelligence</span>.
          </p>

          <div class="flex flex-wrap gap-4">
            <a href="mailto:ashimcs23@gmail.com" 
               class="px-8 py-4 bg-blue-600 hover:bg-blue-500 transition-all rounded-2xl flex items-center gap-3 font-semibold text-lg shadow-lg shadow-blue-500/30">
              <i class="fa-solid fa-envelope"></i>
              Get In Touch
            </a>
            
            <a href="https://github.com/ashimcs" target="_blank"
               class="px-8 py-4 border border-white/30 hover:border-white/60 transition-all rounded-2xl flex items-center gap-3 font-semibold">
              <i class="fa-brands fa-github text-2xl"></i>
              View GitHub
            </a>
          </div>

          <div class="flex items-center gap-8 pt-8">
            <a href="https://linkedin.com/in/ashim-cs-4b7569397" target="_blank" class="flex items-center gap-3 hover:text-blue-400 transition-colors">
              <i class="fa-brands fa-linkedin text-3xl"></i>
              <span class="text-sm">LinkedIn</span>
            </a>
            <a href="https://github.com/ashimcs" target="_blank" class="flex items-center gap-3 hover:text-blue-400 transition-colors">
              <i class="fa-brands fa-github text-3xl"></i>
              <span class="text-sm">GitHub</span>
            </a>
          </div>
        </div>

        <!-- Right Visual -->
        <div class="lg:w-2/5 relative">
          <div class="relative">
            <img src="https://github.com/ashimcs.png" 
                 alt="Ashim C S"
                 class="w-80 h-80 lg:w-96 lg:h-96 rounded-[4rem] object-cover border-8 border-zinc-800 shadow-2xl floating">
            
            <div class="absolute -top-6 -right-6 bg-zinc-900 border border-blue-500/30 rounded-3xl px-6 py-4 glass shadow-xl">
              <div class="flex items-center gap-4">
                <div class="text-4xl">🚀</div>
                <div>
                  <div class="text-sm text-zinc-400">Current Focus</div>
                  <div class="font-semibold">Edge AI + Vision Systems</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-12 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 text-zinc-500">
      <div class="text-xs tracking-widest">SCROLL TO EXPLORE</div>
      <i class="fa-solid fa-chevron-down animate-bounce text-xl"></i>
    </div>
  </header>

  <!-- NAV -->
  <nav class="sticky top-0 z-50 bg-zinc-950/80 backdrop-blur-lg border-b border-white/10">
    <div class="max-w-7xl mx-auto px-6 py-5 flex justify-between items-center">
      <div class="font-bold text-2xl heading-font tracking-tighter">ASHIM<span class="text-blue-500">.</span></div>
      
      <div class="hidden md:flex items-center gap-10 text-sm font-medium">
        <a href="#about" class="nav-link">About</a>
        <a href="#skills" class="nav-link">Expertise</a>
        <a href="#projects" class="nav-link">Projects</a>
        <a href="#stats" class="nav-link">Analytics</a>
      </div>

      <a href="mailto:ashimcs23@gmail.com" 
         class="px-6 py-3 bg-white text-zinc-900 hover:bg-amber-300 rounded-2xl text-sm font-semibold flex items-center gap-2 transition-all">
        <i class="fa-solid fa-paper-plane"></i>
        <span>Contact</span>
      </a>
    </div>
  </nav>

  <!-- ABOUT -->
  <section id="about" class="py-24 border-b border-white/5">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid lg:grid-cols-12 gap-16 items-center">
        <div class="lg:col-span-5">
          <div class="sticky top-28">
            <span class="px-4 py-2 bg-purple-500/10 text-purple-400 text-sm rounded-full">CHAPTER 01</span>
            <h2 class="text-6xl heading-font font-semibold mt-6 leading-none">Beyond<br>Code</h2>
            <p class="mt-8 text-zinc-400 text-lg">
              I architect systems that don't just work — they anticipate, adapt, and evolve.
            </p>
          </div>
        </div>

        <div class="lg:col-span-7 space-y-8 text-zinc-300">
          <p class="text-xl leading-relaxed">
            I'm an analytical, business-oriented Full-Stack Engineer and AI Consultant with a passion for building 
            production-grade applications that merge beautiful interfaces with powerful intelligence.
          </p>
          
          <div class="grid md:grid-cols-3 gap-6 pt-8">
            <div class="glass border border-white/10 rounded-3xl p-8 card-hover">
              <div class="text-blue-400 text-4xl mb-6">🧠</div>
              <h4 class="font-semibold text-xl mb-2">AI & Vision</h4>
              <p class="text-zinc-400">Gemini, Llama-3-Vision, Groq, face-api.js</p>
            </div>
            <div class="glass border border-white/10 rounded-3xl p-8 card-hover">
              <div class="text-emerald-400 text-4xl mb-6">📱</div>
              <h4 class="font-semibold text-xl mb-2">Mobile First</h4>
              <p class="text-zinc-400">Flutter, Dart, Cross-platform Architecture</p>
            </div>
            <div class="glass border border-white/10 rounded-3xl p-8 card-hover">
              <div class="text-amber-400 text-4xl mb-6">⚡</div>
              <h4 class="font-semibold text-xl mb-2">Scalable Backend</h4>
              <p class="text-zinc-400">Django • DRF • PostgreSQL • Multi-tenant</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills" class="py-24 bg-black/40">
    <div class="max-w-7xl mx-auto px-6">
      <h2 class="section-title text-5xl heading-font font-semibold mb-16">Technical Arsenal</h2>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Column 1 -->
        <div class="space-y-10">
          <div>
            <h3 class="uppercase text-xs tracking-widest text-zinc-500 mb-6">Frontend & Mobile</h3>
            <div class="flex flex-wrap gap-3">
              <div class="px-6 py-3 bg-white/5 rounded-2xl text-sm flex items-center gap-3">Flutter</div>
              <div class="px-6 py-3 bg-white/5 rounded-2xl text-sm flex items-center gap-3">Dart</div>
              <div class="px-6 py-3 bg-white/5 rounded-2xl text-sm flex items-center gap-3">React</div>
              <div class="px-6 py-3 bg-white/5 rounded-2xl text-sm flex items-center gap-3">Tailwind</div>
            </div>
          </div>
          
          <div>
            <h3 class="uppercase text-xs tracking-widest text-zinc-500 mb-6">Backend & Cloud</h3>
            <div class="space-y-6">
              <div>
                <div class="flex justify-between text-sm mb-2">
                  <span>Django / DRF</span>
                  <span class="text-emerald-400">95%</span>
                </div>
                <div class="h-1.5 bg-zinc-800 rounded-full overflow-hidden"><div class="skill-bar w-[95%]"></div></div>
              </div>
              <div>
                <div class="flex justify-between text-sm mb-2">
                  <span>PostgreSQL</span>
                  <span class="text-emerald-400">90%</span>
                </div>
                <div class="h-1.5 bg-zinc-800 rounded-full overflow-hidden"><div class="skill-bar w-[90%]"></div></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Column 2 -->
        <div class="space-y-10">
          <div>
            <h3 class="uppercase text-xs tracking-widest text-zinc-500 mb-6">AI & Computer Vision</h3>
            <div class="flex flex-wrap gap-3">
              <div class="px-5 py-3 bg-gradient-to-r from-blue-500/10 to-purple-500/10 border border-blue-500/30 rounded-3xl text-sm">Google Gemini</div>
              <div class="px-5 py-3 bg-gradient-to-r from-blue-500/10 to-purple-500/10 border border-blue-500/30 rounded-3xl text-sm">Llama 3 Vision</div>
              <div class="px-5 py-3 bg-gradient-to-r from-blue-500/10 to-purple-500/10 border border-blue-500/30 rounded-3xl text-sm">Groq NLP</div>
              <div class="px-5 py-3 bg-gradient-to-r from-blue-500/10 to-purple-500/10 border border-blue-500/30 rounded-3xl text-sm">face-api.js</div>
            </div>
          </div>
        </div>

        <!-- Column 3 -->
        <div>
          <h3 class="uppercase text-xs tracking-widest text-zinc-500 mb-6">Core Strengths</h3>
          <ul class="space-y-6 text-lg">
            <li class="flex items-start gap-4"><span class="text-blue-400 mt-1">→</span> Scalable System Architecture</li>
            <li class="flex items-start gap-4"><span class="text-blue-400 mt-1">→</span> Real-time AI Pipelines</li>
            <li class="flex items-start gap-4"><span class="text-blue-400 mt-1">→</span> Edge Computing & Mesh Networks</li>
            <li class="flex items-start gap-4"><span class="text-blue-400 mt-1">→</span> Secure Multi-tenant Systems</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects" class="py-24">
    <div class="max-w-7xl mx-auto px-6">
      <h2 class="section-title text-5xl heading-font font-semibold mb-16">Featured Deployments</h2>
      
      <div class="grid md:grid-cols-2 gap-8">
        <div class="glass border border-white/10 rounded-3xl p-8 card-hover group">
          <div class="h-2 w-16 bg-gradient-to-r from-blue-400 to-purple-500 rounded mb-8"></div>
          <h3 class="text-3xl font-semibold heading-font mb-2">Smart Voyage</h3>
          <p class="text-zinc-400">AI-Powered Autonomous Travel Planner</p>
          <ul class="mt-8 space-y-4 text-sm">
            <li class="flex gap-3"><span class="text-emerald-400">•</span> 40% reduction in manual planning</li>
            <li class="flex gap-3"><span class="text-emerald-400">•</span> JWT + OTP Security Layer</li>
            <li class="flex gap-3"><span class="text-emerald-400">•</span> Gemini + Groq Intelligence</li>
          </ul>
          <div class="mt-10 pt-6 border-t border-white/10 flex justify-between text-xs uppercase tracking-widest">
            <span>Flutter • Django • PostgreSQL</span>
          </div>
        </div>

        <div class="glass border border-white/10 rounded-3xl p-8 card-hover group">
          <div class="h-2 w-16 bg-gradient-to-r from-purple-400 to-pink-500 rounded mb-8"></div>
          <h3 class="text-3xl font-semibold heading-font mb-2">MindSpace</h3>
          <p class="text-zinc-400">Real-time Emotional Intelligence Platform</p>
          <ul class="mt-8 space-y-4 text-sm">
            <li class="flex gap-3"><span class="text-emerald-400">•</span> Client-side face-api.js tracking</li>
            <li class="flex gap-3"><span class="text-emerald-400">•</span> 7 Emotional States Mapping</li>
            <li class="flex gap-3"><span class="text-emerald-400">•</span> Live Analytics Dashboard</li>
          </ul>
          <div class="mt-10 pt-6 border-t border-white/10 flex justify-between text-xs uppercase tracking-widest">
            <span>HTML5 • Django • MongoDB</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- STATS -->
  <section id="stats" class="py-20 bg-zinc-900">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
        <div>
          <div class="text-6xl font-bold text-blue-400">15+</div>
          <div class="text-zinc-400 mt-2">Projects Delivered</div>
        </div>
        <div>
          <div class="text-6xl font-bold text-purple-400">98%</div>
          <div class="text-zinc-400 mt-2">Client Satisfaction</div>
        </div>
        <div>
          <div class="text-6xl font-bold text-emerald-400">4</div>
          <div class="text-zinc-400 mt-2">Production Apps</div>
        </div>
        <div>
          <div class="text-6xl font-bold text-amber-400">∞</div>
          <div class="text-zinc-400 mt-2">Learning Velocity</div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER / CONTACT -->
  <footer class="py-20 border-t border-white/10">
    <div class="max-w-7xl mx-auto px-6 text-center">
      <p class="text-zinc-400">Let's build something extraordinary together.</p>
      <a href="mailto:ashimcs23@gmail.com" class="inline-block mt-8 px-10 py-6 bg-white text-zinc-900 rounded-3xl font-semibold text-xl hover:scale-105 transition-transform">
        Start a Conversation →
      </a>
      
      <div class="mt-20 text-xs text-zinc-500 flex flex-col md:flex-row justify-center gap-6">
        <p>© 2026 Ashim C S. All rights reserved.</p>
        <p>Made with precision and passion</p>
      </div>
    </div>
  </footer>

  <script>
    // Tailwind script already included via CDN
    
    // Animate skill bars when in view
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const bars = entry.target.querySelectorAll('.skill-bar');
          bars.forEach(bar => {
            bar.style.width = bar.style.width || '0%';
          });
        }
      });
    }, { threshold: 0.5 });

    document.querySelectorAll('section').forEach(section => {
      observer.observe(section);
    });

    // Smooth scroll for nav
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        if (this.getAttribute('href') !== '#') {
          e.preventDefault();
          document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
          });
        }
      });
    });
  </script>
</body>
</html>
