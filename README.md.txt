<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aarav Gupta - Portfolio</title>
    <link rel="icon" href="logo.png" type="image/png">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
        }

        h1, h2, h3 {
            font-family: 'Montserrat', sans-serif;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navbar */
        .navbar {
            position: sticky;
            top: 0;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            z-index: 1000;
        }

        .navbar .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #007bff;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links a {
            margin-left: 2rem;
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #007bff;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background-color: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Mobile Styles */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 60px;
                left: -100%;
                width: 100%;
                height: 100vh;
                background-color: #fff;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                transition: left 0.3s;
            }

            .nav-links.active {
                left: 0;
            }

            .hamburger {
                display: flex;
            }

            .hamburger.active span:nth-child(1) {
                transform: rotate(-45deg) translate(-5px, 6px);
            }

            .hamburger.active span:nth-child(2) {
                opacity: 0;
            }

            .hamburger.active span:nth-child(3) {
                transform: rotate(45deg) translate(-5px, -6px);
            }
        }

        /* Hero */
        .hero {
            background: linear-gradient(135deg, #007bff, #0056b3);
            color: #fff;
            text-align: center;
            padding: 100px 20px;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .cta-btn {
            background-color: #fff;
            color: #007bff;
            border: none;
            padding: 0.75rem 1.5rem;
            font-size: 1rem;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .cta-btn:hover {
            background-color: #e9ecef;
        }

        /* Sections */
        section {
            padding: 60px 0;
        }

        h2 {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 2rem;
            color: #007bff;
        }

        /* About */
        .about p {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s, transform 0.6s;
        }

        .about p.fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background-color: #fff;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            text-align: center;
        }

        .progress-bar {
            background-color: #e9ecef;
            border-radius: 5px;
            height: 10px;
            margin-top: 1rem;
            overflow: hidden;
        }

        .progress {
            height: 100%;
            background-color: #007bff;
            width: 0;
            transition: width 1s;
        }

        /* Projects */
        .filter-buttons {
            text-align: center;
            margin-bottom: 2rem;
        }

        .filter-btn {
            background-color: #e9ecef;
            border: none;
            padding: 0.5rem 1rem;
            margin: 0 0.5rem;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .filter-btn.active {
            background-color: #007bff;
            color: #fff;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: #fff;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        /* Certificates */
        .certificates {
            text-align: center;
        }

        .certificates img {
            width: 20vw; /* Narrower for vertical look */
            height: 40vh; /* Taller for vertical orientation */
            object-fit: cover; /* Ensures it fits without distortion */
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        /* Footer */
        .footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 1rem 0;
        }

        .footer .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .footer-left {
            text-align: left;
        }

        .footer-right {
            text-align: right;
        }

        .social-icons a {
            margin: 0 1rem;
            color: #fff;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <!-- Header/Navbar -->
    <header class="navbar">
        <div class="container">
            <div class="logo">Aarav Gupta</div>
            <nav class="nav-links">
                <a href="#hero">Home</a>
                <a href="#about">About</a>
                <a href="#skills">Skills</a>
                <a href="#projects">Projects</a>
                <a href="#certificates">Certificates</a>
            </nav>
            <div class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="hero">
        <div class="container">
            <h1>Welcome to My Portfolio</h1>
            <p>A passionate student exploring technology, science, and creativity to build a brighter future.</p>
            <a href="https://aaravgupta02.github.io/aarav-/" target="_blank" class="cta-btn">View My Work</a>
        </div>
    </section>

    <!-- About Me Section -->
    <section id="about" class="about">
        <div class="container">
            <h2>About Me</h2>
            <p class="fade-in">I'm Aarav, a dedicated student with a love for learning and problem-solving. Currently pursuing studies in computer science and economics, I'm passionate about blending technology with real-world applications. My journey is about constant growth—exploring new skills, tackling challenges, and turning ideas into reality. I believe in discipline, creativity, and the power of curiosity to drive innovation.</p>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2>Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>HTML</h3>
                    <div class="progress-bar" data-level="80"><div class="progress"></div></div>
                </div>
                <div class="skill-card">
                    <h3>CSS</h3>
                    <div class="progress-bar" data-level="75"><div class="progress"></div></div>
                </div>
                <div class="skill-card">
                    <h3>JavaScript</h3>
                    <div class="progress-bar" data-level="70"><div class="progress"></div></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2>Projects & Assignments</h2>
            <div class="filter-buttons">
                <button class="filter-btn active" data-filter="all">All</button>
                <button class="filter-btn" data-filter="websites">Websites</button>
                <button class="filter-btn" data-filter="assignments">Assignments</button>
            </div>
            <div class="projects-grid">
                <div class="project-card" data-category="websites">
                    <h3>Previous Portfolio Website</h3>
                    <p>My earlier portfolio website showcasing initial projects and skills. <a href="https://aaravgupta02.github.io/aarav-/" target="_blank">View here</a>.</p>
                    <p><strong>Learned:</strong> Basics of web development and self-presentation.</p>
                </div>
                <div class="project-card" data-category="websites">
                    <h3>Personal Portfolio Website</h3>
                    <p>A responsive website showcasing skills and projects, built with HTML, CSS, and JS.</p>
                    <p><strong>Learned:</strong> Responsive design and JavaScript interactivity.</p>
                </div>
                <div class="project-card" data-category="assignments">
                    <h3>Physics Simulation</h3>
                    <p>A computational model of projectile motion using Python.</p>
                    <p><strong>Learned:</strong> Applying physics principles to code.</p>
                </div>
                <div class="project-card" data-category="websites">
                    <h3>E-commerce Mockup</h3>
                    <p>A simple online store prototype with product listings.</p>
                    <p><strong>Learned:</strong> UI/UX design and front-end development.</p>
                </div>
                <div class="project-card" data-category="assignments">
                    <h3>Economic Analysis Report</h3>
                    <p>A case study on market trends and data visualization.</p>
                    <p><strong>Learned:</strong> Research and presentation skills.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Certificates Section -->
    <section id="certificates" class="certificates">
        <div class="container">
            <h2>Certificates</h2>
            <img src="AARAV GUPTA.png" alt="Certificate">
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-left">
                <p>aarav0774@gmail.com</p>
            </div>
            <div class="footer-right">
                <p>&copy; 2023 Aarav Gupta. All rights reserved.</p>
                <div class="social-icons">
                    <a href="mailto:aarav0774@gmail.com">Contact Me</a>
                    <a href="https://aaravgupta02.github.io/aarav-/" target="_blank">GitHub</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Hamburger Menu
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });

        // Smooth Scrolling
        document.querySelectorAll('.nav-links a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth' });
                navLinks.classList.remove('active'); // Close mobile menu
                hamburger.classList.remove('active');
            });
        });

        // Scroll Animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                    // Animate progress bars
                    if (entry.target.classList.contains('skill-card')) {
                        const progress = entry.target.querySelector('.progress');
                        const level = entry.target.querySelector('.progress-bar').dataset.level;
                        progress.style.width = level + '%';
                    }
                }
            });
        });

        // Observe elements
        document.querySelectorAll('.about p, .skill-card').forEach(el => observer.observe(el));

        // Project Filtering
        const filterButtons = document.querySelectorAll('.filter-btn');
        const projectCards = document.querySelectorAll('.project-card');

        filterButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                filterButtons.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                const filter = btn.dataset.filter;
                projectCards.forEach(card => {
                    if (filter === 'all' || card.dataset.category === filter) {
                        card.style.display = 'block';
                    } else {
                        card.style.display = 'none';
                    }
                });
            });
        });
    </script>
</body>
</html>