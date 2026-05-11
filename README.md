# SecureX
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SecureX - Discord Anti-Nuke Bot</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            font-size: 2rem;
            color: #00ff88;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .cta-button {
            background: #00ff88;
            color: #000;
            padding: 12px 24px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0,255,136,0.3);
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0,255,136,0.4);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 120px 0 80px;
            text-align: center;
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease 0.4s both;
        }

        .btn-primary {
            background: #00ff88;
            color: #000;
            padding: 18px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 8px 25px rgba(0,255,136,0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0,255,136,0.5);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 18px 40px;
            border: 2px solid white;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        .btn-secondary:hover {
            background: white;
            color: #667eea;
        }

        /* Features Section */
        .features {
            padding: 100px 0;
            background: #f8f9ff;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            color: #2d3748;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: all 0.3s;
            border-top: 4px solid transparent;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
        }

        .feature-card.shield {
            border-top-color: #00ff88;
        }

        .feature-card i {
            font-size: 3.5rem;
            color: #00ff88;
            margin-bottom: 1.5rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #2d3748;
        }

        /* Stats Section */
        .stats {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .stat {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        /* Owner Section */
        .owner {
            padding: 100px 0;
            background: white;
        }

        .owner-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .owner-info h2 {
            font-size: 2.5rem;
            color: #2d3748;
            margin-bottom: 1rem;
        }

        .owner-info p {
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .owner-avatar {
            text-align: center;
        }

        .avatar {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            margin: 0 auto 1.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
        }

        /* Footer */
        footer {
            background: #1a1a2e;
            color: white;
            text-align: center;
            padding: 3rem 0 1.5rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .social-links a {
            width: 50px;
            height: 50px;
            background: #00ff88;
            color: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            text-decoration: none;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            transform: translateY(-3px) scale(1.1);
            box-shadow: 0 10px 25px rgba(0,255,136,0.4);
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
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .owner-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">
                <i class="fas fa-shield-alt"></i>
                SecureX
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#owner">Owner</a></li>
                <li><a href="#invite">Invite</a></li>
            </ul>
            <a href="#invite" class="cta-button">Add to Discord</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>SecureX Anti-Nuke Bot</h1>
            <p>Protect your Discord server from raids, nukes, and malicious activity with enterprise-grade protection.</p>
            <div class="hero-buttons">
                <a href="https://discord.com/oauth2/authorize?client_id=1490295767041183934&permissions=0&integration_type=0&scope=bot" class="btn-primary" target="_blank">
                    <i class="fab fa-discord"></i> Add to Discord
                </a>
                <a href="#features" class="btn-secondary">Learn More</a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
        <div class="container">
            <h2 class="section-title">Powerful Protection Features</h2>
            <div class="features-grid">
                <div class="feature-card shield">
                    <i class="fas fa-ban"></i>
                    <h3>Anti-Nuke</h3>
                    <p>Automatically detects and prevents mass deletions, bans, kicks, and channel spam attacks.</p>
                </div>
                <div class="feature-card shield">
                    <i class="fas fa-shield-virus"></i>
                    <h3>Anti-Raid</h3>
                    <p>Blocks raid bots and suspicious mass joins with intelligent filtering and verification.</p>
                </div>
                <div class="feature-card shield">
                    <i class="fas fa-user-slash"></i>
                    <h3>Anti-Alt</h3>
                    <p>Detects and manages alternate accounts trying to bypass your server security.</p>
                </div>
                <div class="feature-card shield">
                    <i class="fas fa-chart-line"></i>
                    <h3>Real-time Logs</h3>
                    <p>Complete audit logs and real-time monitoring dashboard for all security events.</p>
                </div>
                <div class="feature-card shield">
                    <i class="fas fa-cog"></i>
                    <h3>Fully Customizable</h3>
                    <p>Configure protection levels, whitelists, and automation to fit your server's needs.</p>
                </div>
                <div class="feature-card shield">
                    <i class="fas fa-bolt"></i>
                    <h3>Lightning Fast</h3>
                    <p>Sub-second response times with 99.99% uptime guarantee.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div>
                    <div class="stat">999+</div>
                    <div class="stat-label">Servers Protected</div>
                </div>
                <div>
                    <div class="stat">99.99%</div>
                    <div class="stat-label">Uptime</div>
                </div>
                <div>
                    <div class="stat">1M+</div>
                    <div class="stat-label">Attacks Blocked</div>
                </div>
                <div>
                    <div class="stat">24/7</div>
                    <div class="stat-label">Support</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Owner Section -->
    <section id="owner" class="owner">
        <div class="container">
            <div class="owner-content">
                <div class="owner-info">
                    <h2>Trusted by melxi1</h2>
                    <p>SecureX was developed by melxi1, a Discord bot developer with years of experience creating enterprise-grade moderation solutions. Your server's security is in expert hands.</p>
                    <a href="https://discord.com/oauth2/authorize?client_id=1490295767041183934&permissions=0&integration_type=0&scope=bot" class="btn-primary" style="display: inline-flex; align-items: center; gap: 10px;">
                        <i class="fab fa-discord"></i>
                        Invite SecureX Now
                    </a>
                </div>
                <div class="owner-avatar">
                    <div class="avatar">
                        <i class="fas fa-user"></i>
                    </div>
                    <h3>melxi1</h3>
                    <p>Bot Developer & Owner</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="social-links">
                <a href="https://discord.com/users/melxi1" target="_blank"><i class="fab fa-discord"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
            </div>
            <p>&copy; 2024 SecureX by melxi1. All rights reserved. | <a href="#" style="color: #00ff88;">Privacy Policy</a></p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
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

        // Navbar background on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(102, 126, 234, 0.95)';
                header.style.backdropFilter = 'blur(10px)';
            } else {
                header.style.background = 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)';
                header.style.backdropFilter = 'none';
            }
        });

        // Animate stats on scroll
        const animateStats = () => {
            const stats = document.querySelectorAll('.stat');
            stats.forEach(stat => {
                const target = parseInt(stat.textContent);
                let count = 0;
                const increment = target / 100;
                const timer = setInterval(() => {
                    count += increment;
                    if (count >= target) {
                        stat.textContent = target;
                        clearInterval(timer);
                    } else {
                        stat.textContent = Math.floor(count) + (count % 1 >= 0.5 ? '+' : '');
                    }
                }, 20);
            });
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateStats();
                    observer.unobserve(entry.target);
                }
            });
        });

        observer.observe(document.querySelector('.stats'));
    </script>
</body>
</html>
