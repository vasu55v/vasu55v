<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vasu Virani - Futuristic Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(0, 255, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(255, 0, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 40% 80%, rgba(0, 255, 127, 0.1) 0%, transparent 50%);
            animation: bgPulse 8s ease-in-out infinite alternate;
        }

        @keyframes bgPulse {
            0% { opacity: 0.3; }
            100% { opacity: 0.8; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 3rem;
            animation: slideDown 1s ease-out;
        }

        .header h1 {
            font-size: 3.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: textGlow 3s ease-in-out infinite alternate;
            margin-bottom: 1rem;
        }

        .header h3 {
            font-size: 1.5rem;
            color: #a0a0a0;
            animation: fadeIn 2s ease-out 0.5s both;
        }

        @keyframes slideDown {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes textGlow {
            0% { filter: drop-shadow(0 0 10px rgba(0, 255, 255, 0.5)); }
            100% { filter: drop-shadow(0 0 20px rgba(255, 0, 255, 0.8)); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Cards */
        .card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            margin: 2rem 0;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            animation: slideUp 0.8s ease-out;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 255, 255, 0.1), transparent);
            animation: rotate 4s linear infinite;
            z-index: -1;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.2);
            border-color: rgba(0, 255, 255, 0.3);
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Section titles */
        .section-title {
            font-size: 2rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            background: linear-gradient(45deg, #00ffff, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        /* Experience section */
        .experience {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(255, 0, 255, 0.1));
            animation-delay: 0.2s;
        }

        /* About section */
        .about {
            background: linear-gradient(135deg, rgba(255, 0, 255, 0.1), rgba(0, 255, 127, 0.1));
            animation-delay: 0.4s;
        }

        .about-list {
            list-style: none;
            padding: 0;
        }

        .about-list li {
            padding: 0.5rem 0;
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        .about-list li:hover {
            transform: translateX(10px);
            color: #00ffff;
        }

        /* Tech stack */
        .tech-stack {
            background: linear-gradient(135deg, rgba(0, 255, 127, 0.1), rgba(255, 255, 0, 0.1));
            animation-delay: 0.6s;
        }

        .tech-category {
            margin-bottom: 2rem;
        }

        .tech-category h4 {
            font-size: 1.2rem;
            color: #00ffff;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-badge {
            background: linear-gradient(45deg, #1a1a2e, #16213e);
            border: 1px solid rgba(0, 255, 255, 0.3);
            color: #ffffff;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .tech-badge:hover::before {
            left: 100%;
        }

        .tech-badge:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 255, 255, 0.3);
            border-color: #00ffff;
        }

        /* Connect section */
        .connect {
            background: linear-gradient(135deg, rgba(255, 255, 0, 0.1), rgba(0, 255, 255, 0.1));
            animation-delay: 0.8s;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 1rem;
        }

        .social-link {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #0077B5, #00A0DC);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link.twitter {
            background: linear-gradient(45deg, #1DA1F2, #0d8bd9);
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .social-link:hover::before {
            left: 100%;
        }

        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        /* Stats section */
        .stats {
            background: linear-gradient(135deg, rgba(255, 0, 255, 0.1), rgba(0, 255, 255, 0.1));
            animation-delay: 1s;
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-card {
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 15px;
            padding: 1.5rem;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
            border-color: #00ffff;
        }

        .stat-card img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            filter: drop-shadow(0 4px 8px rgba(0, 255, 255, 0.3));
        }

        /* Visitor count */
        .visitor-count {
            text-align: center;
            margin-top: 3rem;
            animation: fadeIn 2s ease-out 1.5s both;
        }

        .visitor-count img {
            filter: drop-shadow(0 4px 8px rgba(0, 255, 255, 0.5));
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
            
            .social-links {
                flex-direction: column;
                align-items: center;
            }
            
            .tech-badges {
                justify-content: center;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(0, 0, 0, 0.1);
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(180deg, #00ffff, #ff00ff);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(180deg, #ff00ff, #00ffff);
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    
    <div class="container">
        <div class="header">
            <h1>Hey 👋, I'm Vasu Virani</h1>
            <h3>A passionate Full-Stack Python Developer from India</h3>
        </div>

        <div class="card experience">
            <h2 class="section-title">💼 Experience</h2>
            <div>
                <h3 style="color: #00ffff; margin-bottom: 0.5rem;">🧠 Backend Developer Intern @ WhatBytes</h3>
                <p style="color: #a0a0a0; font-style: italic; margin-bottom: 1rem;">May 2025 – Present</p>
                <p>Worked on Django REST APIs, PostgreSQL integration, email services, and real-time data processing.</p>
            </div>
        </div>

        <div class="card about">
            <h2 class="section-title">💫 About Me</h2>
            <ul class="about-list">
                <li>🔭 I'm currently working on a product price comparison platform for Zepto, Blinkit, and Swiggy.</li>
                <li>🌱 I'm diving deeper into <strong>Celery, Redis, PostgreSQL, FastAPI</strong>, and <strong>Selenium/Playwright</strong> for automation & scraping.</li>
                <li>💬 Ask me about <strong>Django, Python, React, JWT, PostgreSQL, REST APIs, Web scraping</strong>, and <strong>deployment</strong>.</li>
                <li>🤝 Open to collaborate on any open-source or full-stack projects.</li>
                <li>📫 Reach me: <strong>vasuvirani55@gmail.com</strong></li>
            </ul>
        </div>

        <div class="card connect">
            <h2 class="section-title">🌐 Connect with Me</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/virani-vasu-9a0a6224a" class="social-link" target="_blank">
                    LinkedIn
                </a>
                <a href="https://x.com/VasuVirani" class="social-link twitter" target="_blank">
                    X (Twitter)
                </a>
            </div>
        </div>

        <div class="card tech-stack">
            <h2 class="section-title">🧰 Tech Stack</h2>
            
            <div class="tech-category">
                <h4>Languages:</h4>
                <div class="tech-badges">
                    <span class="tech-badge">Python</span>
                    <span class="tech-badge">JavaScript</span>
                    <span class="tech-badge">TypeScript</span>
                    <span class="tech-badge">C</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>Frontend:</h4>
                <div class="tech-badges">
                    <span class="tech-badge">React</span>
                    <span class="tech-badge">Vite</span>
                    <span class="tech-badge">HTML5</span>
                    <span class="tech-badge">CSS3</span>
                    <span class="tech-badge">Bootstrap</span>
                    <span class="tech-badge">React Hook Form</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>Backend:</h4>
                <div class="tech-badges">
                    <span class="tech-badge">Django</span>
                    <span class="tech-badge">Django REST</span>
                    <span class="tech-badge">JWT</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>Database & DevOps:</h4>
                <div class="tech-badges">
                    <span class="tech-badge">PostgreSQL</span>
                    <span class="tech-badge">SQLite</span>
                    <span class="tech-badge">Git</span>
                    <span class="tech-badge">GitHub</span>
                    <span class="tech-badge">Vercel</span>
                    <span class="tech-badge">Netlify</span>
                    <span class="tech-badge">GitHub Pages</span>
                </div>
            </div>
        </div>

        <div class="card stats">
            <h2 class="section-title">📊 GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=vasu55v&theme=dark&hide_border=false&include_all_commits=true&count_private=true" alt="GitHub Stats" />
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=vasu55v&theme=dark&hide_border=false" alt="GitHub Streak" />
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=vasu55v&theme=dark&hide_border=false&layout=compact&langs_count=10" alt="Top Languages" />
                </div>
            </div>
        </div>

        <div class="visitor-count">
            <h2 class="section-title">🧮 Visitor Count</h2>
            <img src="https://visitcount.itsvg.in/api?id=vasu55v&icon=0&color=0" alt="Visitor Count" />
        </div>
    </div>
</body>
</html>
