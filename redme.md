<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Advanced Portfolio</title>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #0a0a0a;
            --text-primary: #ffffff;
            --accent-color: #ff4d6d;
            --secondary-accent: #7af1ff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Space Grotesk', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            overflow-x: hidden;
            cursor: none; /* Custom cursor logic */
        }

        /* Custom Cursor Styling */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            border: 2px solid var(--accent-color);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50%);
            transition: width 0.3s, height 0.3s;
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 5%;
            position: fixed;
            width: 100%;
            z-index: 100;
            background: rgba(10, 10, 10, 0.8);
            backdrop-filter: blur(10px);
        }

        .logo {
            font-weight: 700;
            font-size: 1.5rem;
            letter-spacing: -1px;
        }

        .nav-links a {
            color: var(--text-primary);
            text-decoration: none;
            margin-left: 2rem;
            position: relative;
            transition: 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--accent-color);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s ease-out;
        }

        .nav-links a:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 10%;
        }

        h1.hero-title {
            font-size: 5rem;
            line-height: 1.1;
            margin-bottom: 1rem;
        }

        .hero-title span {
            display: inline-block;
            background: linear-gradient(90deg, var(--accent-color), var(--secondary-accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #888;
            margin-bottom: 2rem;
        }

        .btn-hero {
            padding: 1rem 2.5rem;
            background: transparent;
            border: 1px solid var(--accent-color);
            color: var(--text-primary);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.9rem;
            cursor: pointer; /* JS will override this */
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .btn-hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 50%;
            height: 100%;
            background: var(--accent-color);
            transition: 0.5s ease;
        }

        .btn-hero:hover::before {
            left: 0;
        }
        
        /* Skills Section */
        .skills {
            padding: 5rem 10%;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
        }

        .skill-cards-container {
            display: flex;
            gap: 2rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .skill-card {
            background: #151515;
            border-radius: 15px;
            padding: 2rem;
            width: 300px;
            border: 1px solid #222;
            transition: transform 0.3s;
        }

        .skill-card:hover {
            border-color: var(--secondary-accent);
        }

        /* Projects Section */
        .projects {
            padding: 5rem 10%;
        }
        
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: #151515;
            border-radius: 20px;
            overflow: hidden;
            position: relative;
            height: 350px;
            transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
        }

        .project-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .project-info {
            position: absolute;
            bottom: -50px; /* Initially hidden */
            left: 0;
            width: 100%;
            padding: 2rem;
            background: linear-gradient(to top, rgba(0,0,0,0.9), transparent);
            transition: all 0.4s ease;
        }

        .project-card:hover .project-img {
            transform: scale(1.1);
        }

        .project-card:hover .project-info {
            bottom: 0;
        }

    </style>
</head>
<body>

    <!-- Custom Cursor -->
    <div class="cursor"></div>

    <nav>
        <div class="logo">MyPortfolio.</div>
        <div class="nav-links">
            <a href="#" class="active" onmouseenter="hoverEffect()">Home</a>
            <a href="#skills" onmouseenter="hoverEffect()">Skills</a>
            <a href="#projects" onmouseenter="hoverEffect()">Projects</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <h1 class="hero-title" id="hero-text">Creative <br><span>Developer.</span></h1>
        <p class="hero-subtitle">Building digital experiences with code and design.</p>
        <button class="btn-hero" onmouseenter="cursorHover()">Let's Talk</button>
    </section>

    <!-- Skills Section -->
    <section class="skills" id="skills">
        <h2 class="section-title">My Tech Stack</h2>
        <div class="skill-cards-container">
            <div class="skill-card gsap-target scroll-trigger-item">
                <h3>Frontend</h3>
                <p>HTML5, CSS3, JS (ES6+), React, Tailwind</p>
            </div>
            <div class="skill-card gsap-target scroll-trigger-item">
                <h3>Backend</h3>
                <p>Node.js, Python, Firebase, SQL</p>
            </div>
            <div class="skill-card gsap-target scroll-trigger-item">
                <h3>Tools</h3>
                <p>VsCode, Git, Docker, Figma</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects" id="projects">
        <h2 class="section-title">Latest Works</h2>
        <div class="project-grid">
            <div class="project-card gsap-target scroll-trigger-item">
                <!-- Placeholder Image URL -->
                <img src="https://images.unsplash.com/photo-1498050108023-c5dc4d207bf7?auto=format&fit=crop&w=600&q=80" alt="Project 1" class="project-img">
                <div class="project-info">
                    <h3>E-Commerce Platform</h3>
                    <p>Full stack build with React & Node.js.</p>
                </div>
            </div>
            <div class="project-card gsap-target scroll-trigger-item" style="margin-top: 4rem;">
                <img src="https://images.unsplash.com/photo-1518770660437-4636190af475?auto=format&fit=crop&w=600&q=80" alt="Project 2" class="project-img">
                <div class="project-info">
                    <h3>AI Dashboard</h3>
                    <p>Data visualization tool using D3.js.</p>
                </div>
            </div>
            <div class="project-card gsap-target scroll-trigger-item">
                <img src="https://images.unsplash.com/photo-1526374995308-ef462f58b27e?auto=format
