<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Joyson Rudrapogu - Site Reliability Engineer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --text-color: #333;
            --text-light: #666;
            --bg-light: #f8f9fa;
            --border-color: #e1e8ed;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            z-index: 1000;
            padding: 1rem 0;
        }

        nav .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--secondary-color);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            padding: 6rem 2rem 4rem;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 0.8s ease;
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            opacity: 0.9;
            animation: fadeInUp 0.8s ease 0.2s backwards;
        }

        .hero-content .tagline {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            opacity: 0.8;
            animation: fadeInUp 0.8s ease 0.4s backwards;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease 0.6s backwards;
        }

        .btn {
            padding: 0.875rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: white;
            color: var(--primary-color);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-secondary:hover {
            background: white;
            color: var(--primary-color);
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Section */
        section {
            padding: 5rem 0;
        }

        section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
            text-align: center;
        }

        section .section-subtitle {
            text-align: center;
            color: var(--text-light);
            font-size: 1.1rem;
            margin-bottom: 3rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* About Section */
        .about {
            background: var(--bg-light);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text p {
            margin-bottom: 1rem;
            color: var(--text-light);
            line-height: 1.8;
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-box {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .stat-box .number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--secondary-color);
        }

        .stat-box .label {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 2px 20px rgba(0,0,0,0.08);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 30px rgba(0,0,0,0.15);
        }

        .skill-card h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skill-card ul {
            list-style: none;
        }

        .skill-card li {
            padding: 0.5rem 0;
            color: var(--text-light);
            border-bottom: 1px solid var(--border-color);
        }

        .skill-card li:last-child {
            border-bottom: none;
        }

        .skill-icon {
            font-size: 1.5rem;
        }

        /* Projects Section */
        .projects {
            background: var(--bg-light);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 2px 20px rgba(0,0,0,0.08);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 30px rgba(0,0,0,0.15);
        }

        .project-header {
            background: linear-gradient(135deg, var(--secondary-color), #667eea);
            padding: 2rem;
            color: white;
        }

        .project-header h3 {
            margin-bottom: 0.5rem;
        }

        .project-tag {
            display: inline-block;
            background: rgba(255,255,255,0.2);
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.85rem;
            margin-top: 0.5rem;
        }

        .project-body {
            padding: 2rem;
        }

        .project-body p {
            color: var(--text-light);
            margin-bottom: 1rem;
            line-height: 1.6;
        }

        .project-metrics {
            display: flex;
            gap: 1.5rem;
            margin: 1.5rem 0;
        }

        .metric {
            text-align: center;
        }

        .metric .value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--secondary-color);
        }

        .metric .label {
            font-size: 0.85rem;
            color: var(--text-light);
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tech-badge {
            background: var(--bg-light);
            padding: 0.25rem 0.75rem;
            border-radius: 5px;
            font-size: 0.85rem;
            color: var(--text-color);
        }

        /* Experience Section */
        .timeline {
            position: relative;
            max-width: 900px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 100%;
            background: var(--border-color);
        }

        .timeline-item {
            margin-bottom: 3rem;
            position: relative;
        }

        .timeline-content {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 2px 20px rgba(0,0,0,0.08);
            width: calc(50% - 2rem);
        }

        .timeline-item:nth-child(odd) .timeline-content {
            margin-left: auto;
        }

        .timeline-dot {
            position: absolute;
            left: 50%;
            top: 0;
            transform: translateX(-50%);
            width: 20px;
            height: 20px;
            background: var(--secondary-color);
            border: 4px solid white;
            border-radius: 50%;
            box-shadow: 0 0 0 4px var(--border-color);
        }

        .timeline-content h3 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .timeline-content .company {
            color: var(--secondary-color);
            font-weight: 600;
            margin-bottom: 0.25rem;
        }

        .timeline-content .date {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .timeline-content ul {
            margin-left: 1.5rem;
        }

        .timeline-content li {
            color: var(--text-light);
            margin-bottom: 0.5rem;
        }

        /* Blog Section */
        .blog {
            background: var(--bg-light);
        }

        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .blog-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 2px 20px rgba(0,0,0,0.08);
            transition: transform 0.3s;
            cursor: pointer;
        }

        .blog-card:hover {
            transform: translateY(-5px);
        }

        .blog-image {
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .blog-content {
            padding: 1.5rem;
        }

        .blog-content .date {
            color: var(--text-light);
            font-size: 0.85rem;
            margin-bottom: 0.5rem;
        }

        .blog-content h3 {
            color: var(--primary-color);
            margin-bottom: 0.75rem;
        }

        .blog-content p {
            color: var(--text-light);
            line-height: 1.6;
        }

        /* Contact Section */
        .contact {
            text-align: center;
        }

        .contact-methods {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 2px 20px rgba(0,0,0,0.08);
            min-width: 200px;
            transition: transform 0.3s;
        }

        .contact-card:hover {
            transform: translateY(-5px);
        }

        .contact-card .icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }

        .contact-card h3 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .contact-card a {
            color: var(--secondary-color);
            text-decoration: none;
        }

        /* Footer */
        footer {
            background: var(--primary-color);
            color: white;
            text-align: center;
            padding: 2rem;
        }

        footer p {
            opacity: 0.8;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav ul {
                display: none;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content .subtitle {
                font-size: 1.2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .timeline::before {
                left: 0;
            }

            .timeline-content {
                width: calc(100% - 2rem);
                margin-left: 2rem !important;
            }

            .timeline-dot {
                left: 0;
            }

            .projects-grid,
            .blog-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Smooth scroll */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="container">
            <div class="logo">JR</div>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Joyson Rudrapogu</h1>
            <p class="subtitle">Site Reliability Engineer</p>
            <p class="tagline">Building resilient systems | 99.9%+ uptime | Automation enthusiast</p>
            <div class="hero-buttons">
                <a href="#contact" class="btn btn-primary">Get In Touch</a>
                <a href="#projects" class="btn btn-secondary">View Projects</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2>About Me</h2>
            <p class="section-subtitle">SRE with a passion for reliability, automation, and continuous improvement</p>
            
            <div class="about-content">
                <div class="about-text">
                    <p>
                        I'm a Site Reliability Engineer with 4 years of experience, having successfully transitioned from Quality Engineering to SRE practices. I specialize in building and maintaining high-availability AWS infrastructure, Kubernetes orchestration, and implementing SRE best practices.
                    </p>
                    <p>
                        My journey from Quality Engineering to SRE has given me a unique perspective – I bring rigorous testing mindset to production reliability. I've maintained 99.9%+ uptime for production services through proactive observability, automated incident response, and systematic toil reduction.
                    </p>
                    <p>
                        Currently focused on: SLO-based monitoring, chaos engineering, infrastructure automation, and building self-healing systems.
                    </p>
                </div>
                
                <div class="about-stats">
                    <div class="stat-box">
                        <div class="number">4+</div>
                        <div class="label">Years Experience</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">99.9%</div>
                        <div class="label">Uptime Maintained</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">60%</div>
                        <div class="label">Toil Reduced</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">200+</div>
                        <div class="label">Servers Managed</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <h2>Technical Skills</h2>
            <p class="section-subtitle">Core competencies in cloud infrastructure, containers, and reliability engineering</p>
            
            <div class="skills-grid">
                <div class="skill-card">
                    <h3><span class="skill-icon">☁️</span> Cloud Platforms</h3>
                    <ul>
                        <li>AWS (EC2, EKS, S3, Lambda)</li>
                        <li>VPC, Route53, CloudFront</li>
                        <li>RDS, ElastiCache</li>
                        <li>CloudWatch, CloudFormation</li>
                    </ul>
                </div>

                <div class="skill-card">
                    <h3><span class="skill-icon">🐳</span> Containers & Orchestration</h3>
                    <ul>
                        <li>Kubernetes (EKS)</li>
                        <li>Docker & Docker Compose</li>
                        <li>Helm Charts</li>
                        <li>HPA & Cluster Autoscaler</li>
                    </ul>
                </div>

                <div class="skill-card">
                    <h3><span class="skill-icon">🏗️</span> Infrastructure as Code</h3>
                    <ul>
                        <li>Terraform</li>
                        <li>Ansible</li>
                        <li>AWS CloudFormation</li>
                        <li>GitOps Practices</li>
                    </ul>
                </div>

                <div class="skill-card">
                    <h3><span class="skill-icon">📊</span> Observability</h3>
                    <ul>
                        <li>Prometheus & Grafana</li>
                        <li>ELK Stack</li>
                        <li>AWS CloudWatch</li>
                        <li>Distributed Tracing</li>
                    </ul>
                </div>

                <div class="skill-card">
                    <h3><span class="skill-icon">⚙️</span> CI/CD & Automation</h3>
                    <ul>
                        <li>GitHub Actions</li>
                        <li>Jenkins</li>
                        <li>GitLab CI</li>
                        <li>Automated Deployments</li>
                    </ul>
                </div>

                <div class="skill-card">
                    <h3><span class="skill-icon">🎯</span> SRE Practices</h3>
                    <ul>
                        <li>SLO/SLI Management</li>
                        <li>Incident Response</li>
                        <li>Error Budget Tracking</li>
                        <li>Chaos Engineering</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2>Key Projects</h2>
            <p class="section-subtitle">Production-grade SRE implementations with measurable impact</p>
            
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <h3>Global Production Platform</h3>
                        <span class="project-tag">High Availability</span>
                    </div>
                    <div class="project-body">
                        <p>
                            Led reliability transformation for customer-facing platform, implementing comprehensive SRE practices from ground up.
                        </p>
                        <div class="project-metrics">
                            <div class="metric">
                                <div class="value">99.9%</div>
                                <div class="label">Uptime Achieved</div>
                            </div>
                            <div class="metric">
                                <div class="value">50%</div>
                                <div class="label">Latency Reduced</div>
                            </div>
                            <div class="metric">
                                <div class="value">60%</div>
                                <div class="label">Faster MTTR</div>
                            </div>
                        </div>
                        <div class="tech-stack">
                            <span class="tech-badge">CloudFront</span>
                            <span class="tech-badge">AWS WAF</span>
                            <span class="tech-badge">Prometheus</span>
                            <span class="tech-badge">Grafana</span>
                            <span class="tech-badge">Terraform</span>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>Automated Patching Pipeline</h3>
                        <span class="project-tag">Automation</span>
                    </div>
                    <div class="project-body">
                        <p>
                            Built zero-downtime automated patching system using Ansible and AWS SSM for 200+ Linux servers.
                        </p>
                        <div class="project-metrics">
                            <div class="metric">
                                <div class="value">200+</div>
                                <div class="label">Servers Managed</div>
                            </div>
                            <div class="metric">
                                <div class="value">0</div>
                                <div class="label">Downtime</div>
                            </div>
                            <div class="metric">
                                <div class="value">70%</div>
                                <div class="label">Time Saved</div>
                            </div>
                        </div>
                        <div class="tech-stack">
                            <span class="tech-badge">Ansible</span>
                            <span class="tech-badge">AWS SSM</span>
                            <span class="tech-badge">Python</span>
                            <span class="tech-badge">EventBridge</span>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>Self-Healing Infrastructure</h3>
                        <span class="project-tag">Resilience</span>
                    </div>
                    <div class="project-body">
                        <p>
                            Developed proactive remediation framework using AWS Lambda to automatically detect and recover from failures.
                        </p>
                        <div class="project-metrics">
                            <div class="metric">
                                <div class="value">70%</div>
                                <div class="label">Less On-call</div>
                            </div>
                            <div class="metric">
                                <div class="value">25%</div>
                                <div class="label">Fewer Alerts</div>
                            </div>
                            <div class="metric">
                                <div class="value">24/7</div>
                                <div class="label">Auto-Recovery</div>
                            </div>
                        </div>
                        <div class="tech-stack">
                            <span class="tech-badge">AWS Lambda</span>
                            <span class="tech-badge">EventBridge</span>
                            <span class="tech-badge">CloudWatch</span>
                            <span class="tech-badge">Python</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience">
        <div class="container">
            <h2>Experience</h2>
            <p class="section-subtitle">My professional journey from QE to SRE</p>
            
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Site Reliability Engineer</h3>
                        <div class="company">Zensar Technologies</div>
                        <div class="date">May 2022 - Present | Hyderabad, India</div>
                        <ul>
                            <li>Maintained 99.9%+ uptime for production services through SLO-based monitoring</li>
                            <li>Reduced operational toil by 60% through infrastructure automation</li>
                            <li>Led incident response for 15+ critical outages with formal postmortems</li>
                            <li>Managed Kubernetes (EKS) clusters running 50+ microservices</li>
                            <li>Built comprehensive observability using Prometheus and Grafana</li>
                        </ul>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Quality Engineer → SRE Transition</h3>
                        <div class="company">Zensar Technologies</div>
                        <div class="date">June 2021 - April 2022 | Hyderabad, India</div>
                        <ul>
                            <li>Transitioned from QE to SRE through self-study and hands-on projects</li>
                            <li>Built test automation frameworks with 70% reduction in manual effort</li>
                            <li>Collaborated with DevOps team on CI/CD pipelines</li>
                            <li>Gained exposure to production operations and monitoring</li>
                            <li>Completed AWS certifications and Google SRE books</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="blog">
        <div class="container">
            <h2>Blog & Learning</h2>
            <p class="section-subtitle">Sharing knowledge and documenting my SRE journey</p>
            
            <div class="blog-grid">
                <div class="blog-card">
                    <div class="blog-image">📊</div>
                    <div class="blog-content">
                        <div class="date">Coming Soon</div>
                        <h3>Building Production-Ready Monitoring</h3>
                        <p>How to design monitoring systems that give signal, not noise. Lessons from implementing Prometheus and Grafana at scale.</p>
                    </div>
                </div>

                <div class="blog-card">
                    <div class="blog-image">🔥</div>
                    <div class="blog-content">
                        <div class="date">Coming Soon</div>
                        <h3>Lessons from Chaos Engineering</h3>
                        <p>What I learned from breaking production (intentionally). Game Days, failure injection, and building resilient systems.</p>
                    </div>
                </div>

                <div class="blog-card">
                    <div class="blog-image">⚙️</div>
                    <div class="blog-content">
                        <div class="date">Coming Soon</div>
                        <h3>Eliminating Toil Through Automation</h3>
                        <p>How I reduced operational toil by 60%. Practical examples of automation that actually work in production.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2>Get In Touch</h2>
            <p class="section-subtitle">Let's connect and discuss SRE, reliability engineering, or opportunities</p>
            
            <div class="contact-methods">
                <div class="contact-card">
                    <div class="icon">📧</div>
                    <h3>Email</h3>
                    <a href="/cdn-cgi/l/email-protection#751f1a0c061a1b5b0700110714051a1200454c351218141c195b161a18"><span class="__cf_email__" data-cfemail="73191c0a001c1d5d0106170112031c1406434a33141e121a1f5d101c1e">[email&#160;protected]</span></a>
                </div>

                <div class="contact-card">
                    <div class="icon">💼</div>
                    <h3>LinkedIn</h3>
                    <a href="https://linkedin.com/in/yourprofile" target="_blank">Connect with me</a>
                </div>

                <div class="contact-card">
                    <div class="icon">💻</div>
                    <h3>GitHub</h3>
                    <a href="https://github.com/yourusername" target="_blank">View my code</a>
                </div>

                <div class="contact-card">
                    <div class="icon">📱</div>
                    <h3>Phone</h3>
                    <a href="tel:+916303447489">+91 6303447489</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Joyson Rudrapogu. Built with passion for reliability engineering.</p>
            <p style="margin-top: 0.5rem; font-size: 0.9rem;">Site Reliability Engineer | Hyderabad, India</p>
        </div>
    </footer>

    <script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
        // Smooth scroll for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add active class to nav on scroll
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('nav a');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= (sectionTop - 100)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.fo
