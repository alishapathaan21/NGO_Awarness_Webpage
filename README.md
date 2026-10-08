# NGO_Awarness_Webpage
Proud to present a responsive, structured webpage designed for InAmigos Foundation using HTML &amp; CSS. It highlights core projects, community impact, and ways for people to get involved.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InAmigos Foundation - Empowering Lives, Spreading Compassion</title>
    <style>
        /* CSS RESET & VARIABLES */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #2e7d32;
            --secondary-color: #1565c0;
            --accent-color: #f57c00;
            --bg-light: #f8f9fa;
            --text-dark: #333333;
            --text-light: #ffffff;
        }

        body {
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* HEADER & NAVIGATION */
        header {
            background-color: var(--text-light);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 1.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 600;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        /* HERO SECTION */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
                        url('https://images.unsplash.com/photo-1488521787991-ed7bbaae773c?q=80&w=1200&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            color: var(--text-light);
            text-align: center;
            padding: 100px 20px;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .cta-btn {
            background-color: var(--accent-color);
            color: var(--text-light);
            padding: 12px 28px;
            text-decoration: none;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 5px;
            transition: background-color 0.3s;
            display: inline-block;
        }

        .cta-btn:hover {
            background-color: #e65100;
        }

        /* CONTAINER & SECTIONS */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 2.5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 60px;
            height: 3px;
            background-color: var(--accent-color);
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* ABOUT SECTION */
        .about-text {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 2rem;
            font-size: 1.1rem;
        }

        /* PROJECTS GRID */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: var(--text-light);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            color: var(--secondary-color);
            margin-bottom: 0.5rem;
        }

        .tag {
            display: inline-block;
            background-color: #e3f2fd;
            color: var(--secondary-color);
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
            margin-bottom: 0.8rem;
        }

        /* SOCIAL IMPACT STATS */
        .impact-section {
            background-color: #e8f5e9;
            padding: 4rem 2rem;
            margin-top: 2rem;
        }

        .stats-grid {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        .stat-item h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
        }

        .stat-item p {
            font-weight: 600;
        }

        /* CALL TO ACTION SECTION */
        .join-us {
            text-align: center;
            background-color: var(--text-light);
            padding: 4rem 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            margin-top: 3rem;
        }

        .hashtag {
            color: var(--secondary-color);
            font-weight: bold;
        }

        /* FOOTER */
        footer {
            background-color: #1b5e20;
            color: var(--text-light);
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }

        /* RESPONSIVE DESIGN */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 1rem;
            }
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <header>
        <nav>
            <div class="logo">InAmigos Foundation</div>
            <ul class="nav-links">
                <li><a href="#about">About Us</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#impact">Impact</a></li>
                <li><a href="#join">Get Involved</a></li>
            </ul>
        </nav>
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <h1>Empowering Lives, Spreading Compassion</h1>
        <p>A Section 8 Non-Profit Organization working towards education, human welfare, environment, and animal welfare across India.</p>
        <a href="#join" class="cta-btn">Join Us / Volunteer</a>
    </section>

    <!-- ABOUT SECTION -->
    <section id="about" class="container">
        <h2 class="section-title">About InAmigos Foundation</h2>
        <p class="about-text">
            Founded on September 23, 2020, by Mr. Govind Shukla, InAmigos Foundation is a Section 8 registered non-profit organization dedicated to creating sustainable social change. We focus on grassroots efforts to support underprivileged communities, educate children, empower women, protect stray animals, and preserve nature.
        </p>
    </section>

    <!-- PROJECTS SECTION -->
    <section id="projects" class="container">
        <h2 class="section-title">Our Ongoing Projects</h2>
        
        <div class="projects-grid">
            
            <!-- Project 1 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1488521787991-ed7bbaae773c?q=80&w=600&auto=format&fit=crop" alt="Food Distribution">
                <div class="project-content">
                    <span class="tag">Human Welfare</span>
                    <h3>Project SEVA</h3>
                    <p>Dedicated to ensuring no one sleeps hungry. We regularly distribute nutritious meals and clothes to underprivileged individuals and marginalized communities.</p>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1509062522246-3755977927d7?q=80&w=600&auto=format&fit=crop" alt="Children Education">
                <div class="project-content">
                    <span class="tag">Education</span>
                    <h3>Project Bachpanshala</h3>
                    <p>Focuses on increasing literacy rates in rural areas by educating children, helping them gain knowledge, confidence, and opportunities for a brighter future.</p>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1548767797-d8c844163c4c?q=80&w=600&auto=format&fit=crop" alt="Animal Rescue">
                <div class="project-content">
                    <span class="tag">Animal Welfare</span>
                    <h3>Project JEEV</h3>
                    <p>Cares for voiceless street animals by providing daily food drives, medical assistance, and rescue support for stray dogs and animals.</p>
                </div>
            </div>

            <!-- Project 4 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?q=80&w=600&auto=format&fit=crop" alt="Women Empowerment">
                <div class="project-content">
                    <span class="tag">Empowerment</span>
                    <h3>Project UDAAN</h3>
                    <p>Supports women through skill training, digital awareness campaigns, and vocational guidance to help them achieve financial independence.</p>
                </div>
            </div>

            <!-- Project 5 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?q=80&w=600&auto=format&fit=crop" alt="Tree Plantation">
                <div class="project-content">
                    <span class="tag">Environment</span>
                    <h3>Project Prakriti</h3>
                    <p>Promotes environmental sustainability through mass tree plantation drives, environmental awareness campaigns, and eco-friendly practices.</p>
                </div>
            </div>

            <!-- Project 6 -->
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=600&auto=format&fit=crop" alt="Skill Development">
                <div class="project-content">
                    <span class="tag">Youth Development</span>
                    <h3>Project Vikas</h3>
                    <p>Enhances student employability through skill development workshops, hands-on internships, and leadership opportunity programs.</p>
                </div>
            </div>

        </div>
    </section>

    <!-- SOCIAL IMPACT STATS -->
    <section id="impact" class="impact-section">
        <h2 class="section-title">Our Social Impact</h2>
        <div class="stats-grid">
            <div class="stat-item">
                <h2>50,000+</h2>
                <p>Meals Served (Project SEVA)</p>
            </div>
            <div class="stat-item">
                <h2>20,000+</h2>
                <p>Trees Planted (Project Prakriti)</p>
            </div>
            <div class="stat-item">
                <h2>900+</h2>
                <p>Girls Empowered (Project UDAAN)</p>
            </div>
            <div class="stat-item">
                <h2>50+</h2>
                <p>Animals Fed Daily (Project JEEV)</p>
            </div>
        </div>
    </section>

    <!-- CALL TO ACTION -->
    <section id="join" class="container">
        <div class="join-us">
            <h2>Be the Change You Wish to See</h2>
            <p style="margin: 1rem 0;">Join hands with InAmigos Foundation today. Share our mission using <span class="hashtag">#InAmigos</span>, <span class="hashtag">#InAmigosFoundation</span>, and <span class="hashtag">#ServingWithPurpose</span>.</p>
            <a href="https://inamigosfoundation.org.in/" target="_blank" class="cta-btn">Become a Volunteer / Support</a>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <p>&copy; 2026 InAmigos Foundation | Awareness Campaign</p>
    </footer>

</body>
</html>
