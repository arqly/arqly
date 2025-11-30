<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <title>arqly – Digital Product & Architecture</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <style>
        :root {
            --bg: #f5eee7;          /* bež */
            --bg-alt: #fbf7f2;
            --text: #2b2624;
            --accent: #6b1437;      /* bordo */
            --accent-soft: #8b3454;
            --border-soft: #e0d4c7;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }

        a {
            color: var(--accent);
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        /* NAVBAR */

        header {
            position: sticky;
            top: 0;
            z-index: 10;
            backdrop-filter: blur(12px);
            background: rgba(245, 238, 231, 0.92);
            border-bottom: 1px solid var(--border-soft);
        }

        .nav {
            max-width: 1040px;
            margin: 0 auto;
            padding: 14px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-size: 22px;
            font-weight: 700;
            letter-spacing: 0.12em;
            text-transform: uppercase;
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 20px;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.12em;
        }

        .nav-links a {
            position: relative;
            padding-bottom: 4px;
        }

        .nav-links a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: 0;
            width: 0;
            height: 1px;
            background: var(--accent);
            transition: width 0.18s ease-out;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* LAYOUT */

        main {
            max-width: 1040px;
            margin: 0 auto;
            padding: 32px 20px 60px;
        }

        section {
            margin-bottom: 80px;
        }

        h1, h2, h3 {
            margin: 0 0 12px;
        }

        h2 {
            font-size: 26px;
            letter-spacing: 0.18em;
            text-transform: uppercase;
        }

        .section-label {
            font-size: 11px;
            letter-spacing: 0.25em;
            text-transform: uppercase;
            color: var(--accent-soft);
            margin-bottom: 8px;
        }

        /* HERO */

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 2.2fr) minmax(0, 1.6fr);
            gap: 40px;
            align-items: center;
            padding-top: 24px;
        }

        .hero-title {
            font-size: 40px;
            line-height: 1.1;
            margin-bottom: 14px;
        }

        .hero-subtitle {
            font-size: 16px;
            max-width: 420px;
        }

        .hero-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin: 18px 0 26px;
        }

        .tag {
            font-size: 12px;
            padding: 6px 10px;
            border-radius: 999px;
            border: 1px solid var(--border-soft);
            background: var(--bg-alt);
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .btn {
            border-radius: 999px;
            padding: 10px 18px;
            font-size: 14px;
            cursor: pointer;
            border: 1px solid transparent;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .btn-primary {
            background: var(--accent);
            color: #fff;
        }

        .btn-primary:hover {
            background: var(--accent-soft);
        }

        .btn-ghost {
            background: transparent;
            border-color: var(--border-soft);
        }

        .btn-ghost:hover {
            border-color: var(--accent-soft);
        }

        .hero-card {
            background: linear-gradient(135deg, #f8f0ea, #f3e4da);
            border-radius: 24px;
            border: 1px solid var(--border-soft);
            padding: 20px 18px 18px;
        }

        .hero-card-title {
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.22em;
            margin-bottom: 14px;
        }

        .hero-card-list {
            list-style: none;
            padding: 0;
            margin: 0 0 10px;
            font-size: 13px;
        }

        .hero-card-list li {
            display: flex;
            justify-content: space-between;
            padding: 6px 0;
            border-bottom: 1px dashed rgba(0,0,0,0.06);
        }

        .hero-card-list span:first-child {
            opacity: 0.8;
        }

        .hero-card-note {
            font-size: 11px;
            opacity: 0.75;
            margin-top: 6px;
        }

        /* SERVICES */

        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 18px;
        }

        .service-card {
            background: var(--bg-alt);
            border-radius: 18px;
            padding: 14px 14px 16px;
            border: 1px solid var(--border-soft);
            font-size: 14px;
        }

        .service-title {
            font-size: 15px;
            font-weight: 600;
            margin-bottom: 6px;
        }

        .service-note {
            font-size: 12px;
            opacity: 0.8;
            margin-top: 6px;
        }

        /* PORTFOLIO */

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 18px;
        }

        .project-card {
            background: #fff;
            border-radius: 18px;
            border: 1px solid var(--border-soft);
            padding: 12px 12px 14px;
            font-size: 13px;
        }

        .project-label {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.18em;
            color: var(--accent-soft);
            margin-bottom: 4px;
        }

        .project-title {
            font-size: 15px;
            font-weight: 600;
            margin-bottom: 4px;
        }

        .project-meta {
            font-size: 11px;
            opacity: 0.7;
            margin-top: 4px;
        }

        /* CONTACT */

        .contact-box {
            background: var(--bg-alt);
            border-radius: 20px;
            border: 1px solid var(--border-soft);
            padding: 18px 18px 20px;
            max-width: 520px;
        }

        .contact-row {
            display: flex;
            flex-direction: column;
            gap: 4px;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .contact-label {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.18em;
            opacity: 0.7;
        }

        footer {
            border-top: 1px solid var(--border-soft);
            padding: 14px 20px 20px;
            font-size: 12px;
            text-align: center;
            color: #7b6c63;
        }

        /* RESPONSIVE */

        @media (max-width: 820px) {
            .hero {
                grid-template-columns: minmax(0, 1fr);
            }

            .services-grid,
            .portfolio-grid {
                grid-template-columns: repeat(2, minmax(0, 1fr));
            }
        }

        @media (max-width: 600px) {
            .nav {
                flex-direction: column;
                align-items: flex-start;
                gap: 6px;
            }

            .nav-links {
                flex-wrap: wrap;
                gap: 12px;
            }

            .hero-title {
                font-size: 30px;
            }

            .services-grid,
            .portfolio-grid {
                grid-template-columns: minmax(0, 1fr);
            }
        }
    </style>
</head>

<body>
<header>
    <div class="nav">
        <div class="logo">arqly</div>
        <nav class="nav-links">
            <a href="#about">about</a>
            <a href="#services">services</a>
            <a href="#portfolio">work</a>
            <a href="#contact">contact</a>
        </nav>
    </div>
</header>

<main>
    <!-- HERO -->
    <section class="hero" id="top">
        <div>
            <div class="section-label">digital · architecture</div>
            <h1 class="hero-title">Digital product designer and architecture student.</h1>
            <p class="hero-subtitle">
                I design clear layouts, floor plans, 3D concepts and digital systems that make projects
                more organized, visual and easy to understand.
            </p>

            <div class="hero-tags">
                <span class="tag">AutoCAD · 2D drafting</span>
                <span class="tag">SketchUp · 3D concepts</span>
                <span class="tag">Digital planners & templates</span>
                <span class="tag">Space planning</span>
            </div>

            <div class="hero-actions">
                <a class="btn btn-primary" href="#contact">
                    Work with me →
                </a>
                <a class="btn btn-ghost" href="https://www.etsy.com/shop/Arqly" target="_blank">
                    Visit Arqly on Etsy
                </a>
            </div>
        </div>

        <aside class="hero-card">
            <div class="hero-card-title">What I do</div>
            <ul class="hero-card-list">
                <li>
                    <span>2D AutoCAD drawings</span>
                    <span>plans · sections · facades</span>
                </li>
                <li>
                    <span>3D SketchUp concepts</span>
                    <span>houses · interiors</span>
                </li>
                <li>
                    <span>Digital planners</span>
                    <span>PDF, printables</span>
                </li>
                <li>
                    <span>Organization systems</span>
                    <span>to-do & project lists</span>
                </li>
            </ul>
            <p class="hero-card-note">
                Available for remote collaboration and digital product work.
            </p>
        </aside>
    </section>

    <!-- ABOUT -->
    <section id="about">
        <div class="section-label">about</div>
        <h2>Studio</h2>
        <p>
            arqly is a small one–person studio combining architecture thinking and digital product design.
            I enjoy turning chaotic ideas into organized layouts, clear drawings and simple visual systems.
        </p>
    </section>

    <!-- SERVICES -->
    <section id="services">
        <div class="section-label">services</div>
        <h2>What you can book</h2>

        <div class="services-grid">
            <div class="service-card">
                <div class="service-title">2D AutoCAD drafting</div>
                <p>Floor plans, sections, elevations and basic details prepared as clean, readable drawings.</p>
                <p class="service-note">Ideal for students, small studios and real estate presentations.</p>
            </div>

            <div class="service-card">
                <div class="service-title">3D SketchUp concepts</div>
                <p>Fast 3D massing and concept models to visualize space, volume and basic interior layouts.</p>
                <p class="service-note">Perfect for early–stage design and quick client presentations.</p>
            </div>

            <div class="service-card">
                <div class="service-title">CAD blocks & assets</div>
                <p>Curated sets of furniture, fixtures, people and layouts ready to drop into your drawings.</p>
                <p class="service-note">Available as digital products and custom libraries.</p>
            </div>

            <div class="service-card">
                <div class="service-title">Digital planners & templates</div>
                <p>Printable and digital planners for projects, semesters, travel and everyday organization.</p>
                <p class="service-note">Designed to be simple, clean and actually usable.</p>
            </div>

            <div class="service-card">
                <div class="service-title">Floor plan layout & space planning</div>
                <p>Helping you arrange rooms, furniture and circulation to make spaces functional and calm.</p>
                <p class="service-note">For apartments, small houses and student projects.</p>
            </div>

            <div class="service-card">
                <div class="service-title">Organization lists & systems</div>
                <p>Custom to-do lists, project trackers and task maps for your workflow.</p>
                <p class="service-note">Because good design starts with good organization.</p>
            </div>
        </div>
    </section>

    <!-- PORTFOLIO -->
    <section id="portfolio">
        <div class="section-label">work</div>
        <h2>Selected work</h2>

        <div class="portfolio-grid">
            <article class="project-card">
                <div class="project-label">AutoCAD · 2D</div>
                <div class="project-title">Compact apartment floor plan</div>
                <p>Functional layout for a small apartment focusing on storage, circulation and light.</p>
                <div class="project-meta">2D drafting · space planning</div>
            </article>

            <article class="project-card">
                <div class="project-label">SketchUp · 3D</div>
                <div class="project-title">Small family house concept</div>
                <p>Simple volume study and basic interiors modeled for early design discussions.</p>
                <div class="project-meta">3D concept · massing</div>
            </article>

            <article class="project-card">
                <div class="project-label">digital product</div>
                <div class="project-title">Architecture student digital planner</div>
                <p>Planner created to track studio tasks, deadlines, exams and project milestones.</p>
                <div class="project-meta">PDF · printable · Etsy</div>
            </article>

            <article class="project-card">
                <div class="project-label">digital product</div>
                <div class="project-title">History of architecture coloring pages</div>
                <p>Line–art illustrations of iconic architecture, designed as a learning + coloring tool.</p>
                <div class="project-meta">line art · education</div>
            </article>

            <article class="project-card">
                <div class="project-label">system</div>
                <div class="project-title">Project task board & to-do lists</div>
                <p>Simple structure for breaking large design projects into clear, manageable steps.</p>
                <div class="project-meta">organization · workflow</div>
            </article>

            <article class="project-card">
                <div class="project-label">concept</div>
                <div class="project-title">Digital wall art collection</div>
                <p>Minimal prints combining line work, architecture and soft beige–bordo color palette.</p>
                <div class="project-meta">printable art · Etsy</div>
            </article>
        </div>
    </section>

    <!-- CONTACT -->
    <section id="contact">
        <div class="section-label">contact</div>
        <h2>Let’s work together</h2>

        <div class="contact-box">
            <div class="contact-row">
                <span class="contact-label">Email</span>
                <span><a href="mailto:arqly.studio@gmail.com">arqly.studio@gmail.com</a></span>
            </div>

            <div class="contact-row">
                <span class="contact-label">Etsy shop</span>
                <span>
                    <a href="https://www.etsy.com/shop/Arqly" target="_blank">
                        https://www.etsy.com/shop/Arqly
                    </a>
                </span>
            </div>

            <p style="font-size: 13px; margin-top: 8px;">
                Send a short message with what you need (2D drawings, 3D concepts, planner, or custom digital work)
                and I will get back to you with questions and a simple plan.
            </p>
        </div>
    </section>
</main>

<footer>
    © <span id="year"></span> arqly · digital products & architecture
</footer>

<script>
    // automatski upisuje trenutnu godinu u footer
    document.getElementById("year").textContent = new Date().getFullYear();
</script>

</body>
</html>
