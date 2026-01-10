<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Utkarsh Rishi | AI Developer & Founder</title>
    
    <!-- Fonts: 'Inter' for clean readability, 'Space Grotesk' for futuristic headings -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
    
    <!-- Icons: FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-dark: #0a0a0f;
            --bg-card: rgba(20, 20, 35, 0.6);
            --primary: #8b5cf6; /* Violet */
            --primary-glow: #8b5cf688;
            --accent: #d946ef; /* Fuchsia */
            --text-main: #ffffff;
            --text-muted: #94a3b8;
            --border-light: rgba(255, 255, 255, 0.1);
            --gradient-main: linear-gradient(135deg, #8b5cf6 0%, #d946ef 100%);
            --font-heading: 'Space Grotesk', sans-serif;
            --font-body: 'Inter', sans-serif;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: var(--font-body);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* --- Ambient Background Effects --- */
        .ambient-glow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            overflow: hidden;
        }

        .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.4;
            animation: float 20s infinite ease-in-out;
        }

        .orb-1 {
            width: 400px;
            height: 400px;
            background: var(--primary);
            top: -100px;
            left: -100px;
        }

        .orb-2 {
            width: 500px;
            height: 500px;
            background: var(--accent);
            bottom: -150px;
            right: -150px;
            animation-delay: -5s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(30px, 50px); }
        }

        /* --- Layout & Typography --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        section {
            padding: 5rem 0;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        h1, h2, h3 {
            font-family: var(--font-heading);
            font-weight: 700;
        }

        .gradient-text {
            background: var(--gradient-main);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* --- Header --- */
        header {
            padding: 2rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            background: rgba(10, 10, 15, 0.7);
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: -1px;
            color: var(--text-main);
            text-decoration: none;
        }

        .logo span { color: var(--primary); }

        .cta-btn {
            padding: 0.6rem 1.5rem;
            background: var(--gradient-main);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.9rem;
            transition: var(--transition);
            box-shadow: 0 4px 15px var(--primary-glow);
        }

        .cta-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px var(--primary-glow);
        }

        /* --- Hero Section --- */
        .hero {
            min-height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content h1 {
            font-size: 4rem;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            letter-spacing: -2px;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto 2.5rem;
        }

        .status-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 0.5rem 1rem;
            background: rgba(139, 92, 246, 0.1);
            border: 1px solid var(--primary);
            border-radius: 50px;
            color: var(--primary);
            font-size: 0.85rem;
            margin-bottom: 2rem;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            background: var(--primary);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--primary);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.5); opacity: 0.5; }
            100% { transform: scale(1); opacity: 1; }
        }

        /* --- About Me --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1.5fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            color: var(--text-muted);
        }

        .highlight-box {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: 1rem;
            padding: 2rem;
            backdrop-filter: blur(10px);
        }

        .highlight-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .highlight-item i {
            color: var(--accent);
        }

        /* --- Projects --- */
        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: 1.5rem;
            padding: 2rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--gradient-main);
            transform: scaleX(0);
            transform-origin: left;
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
            border-color: rgba(139, 92, 246, 0.3);
            box-shadow: 0 10px 40px -10px rgba(0,0,0,0.5);
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-icon {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            background: rgba(255,255,255,0.05);
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            color: var(--text-main);
        }

        .project-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .project-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
            flex-grow: 1;
            margin-bottom: 1.5rem;
        }

        .tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .tag {
            font-size: 0.75rem;
            padding: 0.25rem 0.75rem;
            background: rgba(255,255,255,0.05);
            border-radius: 20px;
            color: var(--text-muted);
            border: 1px solid rgba(255,255,255,0.05);
        }

        /* --- Tech Stack --- */
        .stack-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 1.5rem;
        }

        .tech-item {
            background: rgba(255,255,255,0.03);
            border: 1px solid var(--border-light);
            padding: 1.5rem;
            border-radius: 1rem;
            text-align: center;
            transition: var(--transition);
        }

        .tech-item:hover {
            background: rgba(139, 92, 246, 0.1);
            border-color: var(--primary);
            transform: translateY(-3px);
        }

        .tech-item i {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--text-main);
        }
        
        .tech-item p {
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        /* --- GitHub Stats Placeholder (Styled) --- */
        .stats-container {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: 1.5rem;
            padding: 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .stat-box h3 {
            font-size: 2.5rem;
            color: var(--primary);
        }
        
        .stat-box p {
            color: var(--text-muted);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* --- Philosophy --- */
        .philosophy-card {
            background: linear-gradient(135deg, rgba(139, 92, 246, 0.1), rgba(217, 70, 239, 0.05));
            border: 1px solid rgba(139, 92, 246, 0.2);
            border-radius: 1.5rem;
            padding: 4rem 2rem;
            text-align: center;
            position: relative;
        }

        .quote-icon {
            font-size: 3rem;
            color: var(--primary);
            opacity: 0.3;
            margin-bottom: 1.5rem;
        }

        .quote-text {
            font-size: 1.5rem;
            font-family: var(--font-heading);
            max-width: 700px;
            margin: 0 auto;
            font-style: italic;
        }

        /* --- Fun Fact --- */
        .fun-fact {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2rem;
            margin-top: 4rem;
            padding: 2rem;
            background: rgba(255,255,255,0.03);
            border-radius: 1rem;
            border: 1px dashed var(--border-light);
        }
        
        .fun-fact i {
            color: var(--accent);
            font-size: 1.5rem;
        }

        /* --- Connect --- */
        .connect-section {
            text-align: center;
            padding-bottom: 8rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .social-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255,255,255,0.05);
            border: 1px solid var(--border-light);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-main);
            font-size: 1.2rem;
            transition: var(--transition);
            text-decoration: none;
        }

        .social-btn:hover {
            background: var(--primary);
            border-color: var(--primary);
            transform: translateY(-5px);
            box-shadow: 0 5px 15px var(--primary-glow);
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 2rem;
            border-top: 1px solid var(--border-light);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .nav-content {
                flex-direction: column;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- Ambient Background -->
    <div class="ambient-glow">
        <div class="orb orb-1"></div>
        <div class="orb orb-2"></div>
    </div>

    <!-- Navigation -->
    <header>
        <div class="container nav-content">
            <a href="#" class="logo">Arc<span>Devs</span></a>
            <a href="#contact" class="cta-btn">Let's Connect</a>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container">
        
        <!-- Hero Section -->
        <section class="hero visible">
            <div class="hero-content">
                <div class="status-badge">
                    <span class="status-dot"></span>
                    Open to Opportunities & Collabs
                </div>
                <h1>Building the <br><span class="gradient-text">Future of Intelligence</span></h1>
                <p class="hero-subtitle">
                    I’m Utkarsh Rishi. A 16-year-old AI Developer & Founder of ArcDevs. 
                    I don’t just use AI — I engineer intelligence from the ground up.
                </p>
                <div style="display: flex; gap: 1rem; justify-content: center;">
                    <a href="#projects" class="cta-btn">View Projects</a>
                    <a href="#about" style="padding: 0.6rem 1.5rem; border: 1px solid var(--border-light); border-radius: 50px; text-decoration: none; color: var(--text-main); transition: var(--transition);">About Me</a>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about">
            <div class="section-header">
                <h2>About <span class="gradient-text">Me</span></h2>
            </div>
            <div class="about-grid">
                <div class="about-text">
                    <p>
                        I’m a 16 y/o AI developer from India 🇮🇳 obsessed with <strong>system-level AI assistants, LLMs, and AI ecosystems</strong>. While many are simply prompting models, I’m focused on the architecture that makes them truly autonomous.
                    </p>
                    <p>
                        My vision is simple: <em>AI that feels alive, fast, and personal.</em> I treat AI development not just as coding, but as a craft of engineering digital cognition.
                    </p>
                </div>
                <div class="highlight-box">
                    <div class="highlight-item">
                        <i class="fa-solid fa-brain"></i>
                        <span>Building Custom AI Assistants</span>
                    </div>
                    <div class="highlight-item">
                        <i class="fa-solid fa-microchip"></i>
                        <span>Working on LLMs & AI Frameworks</span>
                    </div>
                    <div class="highlight-item">
                        <i class="fa-solid fa-microphone-lines"></i>
                        <span>Exploring Voice-based AI Systems</span>
                    </div>
                    <div class="highlight-item">
                        <i class="fa-solid fa-network-wired"></i>
                        <span>Creating End-to-end AI Ecosystems</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects">
            <div class="section-header">
                <h2>Current <span class="gradient-text">Projects</span></h2>
                <p style="color: var(--text-muted);">Where intelligence meets application.</p>
            </div>
            
            <div class="projects-grid">
                <!-- Falcon AI -->
                <div class="project-card">
                    <div class="project-icon">
                        <i class="fa-solid fa-bolt"></i>
                    </div>
                    <h3 class="project-title">FALCON AI</h3>
                    <p class="project-desc">
                        A powerful AI assistant designed for speed, reasoning, and real-world usage. Built for performance when it matters most.
                    </p>
                    <div class="tags">
                        <span class="tag">Speed</span>
                        <span class="tag">Reasoning</span>
                        <span class="tag">Assistant</span>
                    </div>
                </div>

                <!-- ArcMind LLM -->
                <div class="project-card">
                    <div class="project-icon">
                        <i class="fa-solid fa-cube"></i>
                    </div>
                    <h3 class="project-title">ArcMind LLM</h3>
                    <p class="project-desc">
                        A custom large language model focused on intelligence, memory retention, and autonomy. Moving beyond simple response generation.
                    </p>
                    <div class="tags">
                        <span class="tag">LLM</span>
                        <span class="tag">Memory</span>
                        <span class="tag">Autonomy</span>
                    </div>
                </div>

                <!-- RishiAI -->
                <div class="project-card">
                    <div class="project-icon">
                        <i class="fa-solid fa-robot"></i>
                    </div>
                    <h3 class="project-title">RishiAI</h3>
                    <p class="project-desc">
                        My personal AI assistant — minimal, smart, and system-aware. A showcase of what a personalized digital companion looks like.
                    </p>
                    <div class="tags">
                        <span class="tag">Personal</span>
                        <span class="tag">System-Aware</span>
                        <span class="tag">Minimal</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tech Stack -->
        <section>
            <div class="section-header">
                <h2>The <span class="gradient-text">Arsenal</span></h2>
                <p style="color: var(--text-muted);">Languages, frameworks, and tools I use to engineer intelligence.</p>
            </div>
            
            <div class="stack-grid">
                <!-- Languages -->
                <div class="tech-item">
                    <i class="fa-brands fa-python" style="color: #3776ab;"></i>
                    <p>Python</p>
                </div>
                <div class="tech-item">
                    <i class="fa-brands fa-js" style="color: #f7df1e;"></i>
                    <p>JavaScript</p>
                </div>
                <div class="tech-item">
                    <i class="fa-solid fa-code" style="color: #00599C;"></i>
                    <p>C / C++</p>
                </div>
                
                <!-- AI/ML -->
                <div class="tech-item">
                    <i class="fa-solid fa-brain" style="color: #FF6F00;"></i>
                    <p>Transformers</p>
                </div>
                <div class="tech-item">
                    <i class="fa-solid fa-wand-magic-sparkles"></i>
                    <p>Prompt Eng</p>
                </div>
                <div class="tech-item">
                    <i class="fa-solid fa-gauge-high"></i>
                    <p>Optimization</p>
                </div>

                <!-- Tools -->
                <div class="tech-item">
                    <i class="fa-solid fa-server"></i>
                    <p>APIs</p>
                </div>
                <div class="tech-item">
                    <i class="fa-solid fa-microphone"></i>
                    <p>Voice AI</p>
                </div>
            </div>
        </section>

        <!-- GitHub Stats Section (Simulated) -->
        <section>
            <div class="section-header">
                <h2><span class="gradient-text">Impact</span></h2>
            </div>
            <div class="stats-container">
                <div class="stats-grid">
                    <div class="stat-box">
                        <h3>150k+</h3>
                        <p>Lines of Code</p>
                    </div>
                    <div class="stat-box">
                        <h3>10+</h3>
                        <p>AI Models</p>
                    </div>
                    <div class="stat-box">
                        <h3>100%</h3>
                        <p>Obsession</p>
                    </div>
                </div>
            </div>
            
            <div class="fun-fact">
                <i class="fa-solid fa-rocket"></i>
                <p>I build AI the way others build startups — <strong>fast, obsessed, and future-first.</strong></p>
            </div>
        </section>

        <!-- Philosophy -->
        <section>
            <div class="philosophy-card">
                <i class="fa-solid fa-quote-left quote-icon"></i>
                <p class="quote-text">
                    “AI shouldn’t feel artificial. It should feel inevitable.”
                </p>
            </div>
        </section>

        <!-- Connect -->
        <section id="contact" class="connect-section">
            <h2>Ready to build the <span class="gradient-text">Future?</span></h2>
            <p style="color: var(--text-muted); margin-top: 1rem;">
                ⭐ If you like what I’m building, star the repos and follow the journey.
            </p>
            <div class="social-links">
                <a href="#" class="social-btn" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="#" class="social-btn" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="#" class="social-btn" title="Twitter / X"><i class="fa-brands fa-x-twitter"></i></a>
                <a href="#" class="social-btn" title="Email"><i class="fa-solid fa-envelope"></i></a>
            </div>
        </section>

    </main>

    <footer>
        <p>© 2024 Utkarsh Rishi • ArcDevs. Engineered with Intelligence.</p>
    </footer>

    <script>
        // Simple Intersection Observer for scroll animations
        document.addEventListener('DOMContentLoaded', () => {
            const observerOptions = {
                threshold: 0.1,
                rootMargin: "0px 0px -50px 0px"
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            document.querySelectorAll('section').forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
