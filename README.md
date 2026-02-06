[ib-focuslock (2).html](https://github.com/user-attachments/files/25125804/ib-focuslock.2.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Catalyst – Productivity, not passivity</title>
    <link href="https://fonts.googleapis.com/css2?family=Darker+Grotesque:wght@700;900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --electric-blue: #00D4FF;
            --deep-purple: #1a0b2e;
            --vivid-pink: #FF006E;
            --lime-green: #CCFF00;
            --dark-bg: #0a0515;
            --card-bg: #16101f;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'DM Sans', sans-serif;
            background: var(--dark-bg);
            color: white;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated gradient background */
        body::before {
            content: '';
            position: fixed;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 212, 255, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 0, 110, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(204, 255, 0, 0.1) 0%, transparent 50%);
            animation: drift 20s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes drift {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(-5%, 5%) rotate(5deg); }
            66% { transform: translate(5%, -5%) rotate(-5deg); }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 5, 21, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(0, 212, 255, 0.2);
        }

        .logo {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--electric-blue), var(--lime-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.05em;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-links a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--electric-blue);
            transition: width 0.3s;
        }

        .nav-links a:hover {
            color: white;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .cta-button {
            padding: 0.75rem 1.5rem;
            background: linear-gradient(135deg, var(--electric-blue), var(--vivid-pink));
            border: none;
            border-radius: 50px;
            color: white;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.4);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 8rem 5% 4rem;
            position: relative;
        }

        .hero-content {
            max-width: 1200px;
            text-align: center;
            animation: fadeInUp 1s ease-out;
        }

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

        .hero h1 {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: clamp(3rem, 8vw, 7rem);
            font-weight: 900;
            line-height: 0.95;
            margin-bottom: 1.5rem;
            letter-spacing: -0.03em;
        }

        .gradient-text {
            background: linear-gradient(135deg, var(--electric-blue), var(--lime-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
        }

        .pink-text {
            color: var(--vivid-pink);
        }

        .hero p {
            font-size: 1.3rem;
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 3rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.3s backwards;
        }

        .primary-btn {
            padding: 1.2rem 3rem;
            background: linear-gradient(135deg, var(--electric-blue), var(--vivid-pink));
            border: none;
            border-radius: 50px;
            color: white;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .primary-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .primary-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .primary-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 212, 255, 0.5);
        }

        .secondary-btn {
            padding: 1.2rem 3rem;
            background: transparent;
            border: 2px solid var(--electric-blue);
            border-radius: 50px;
            color: white;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
        }

        .secondary-btn:hover {
            background: rgba(0, 212, 255, 0.1);
            transform: translateY(-3px);
        }

        /* Stats Bar */
        .stats-bar {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            padding: 3rem 5%;
            background: rgba(22, 16, 31, 0.6);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(0, 212, 255, 0.2);
            border-bottom: 1px solid rgba(0, 212, 255, 0.2);
            animation: fadeInUp 1s ease-out 0.6s backwards;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 3rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--electric-blue), var(--lime-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }

        /* Features Section */
        .features {
            padding: 8rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 5rem;
        }

        .section-header h2 {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            margin-bottom: 1rem;
            letter-spacing: -0.02em;
        }

        .section-header p {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.6);
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: var(--card-bg);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 20px;
            padding: 2.5rem;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--electric-blue), var(--vivid-pink), var(--lime-green));
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .feature-card:hover::before {
            transform: scaleX(1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--electric-blue);
            box-shadow: 0 20px 60px rgba(0, 212, 255, 0.2);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--electric-blue), var(--vivid-pink));
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
        }

        .feature-card h3 {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 1.8rem;
            font-weight: 900;
            margin-bottom: 1rem;
            color: var(--lime-green);
        }

        .feature-card p {
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.7;
        }

        /* Token Economy Section */
        .token-section {
            padding: 8rem 5%;
            background: linear-gradient(180deg, transparent, rgba(0, 212, 255, 0.05), transparent);
        }

        .token-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .token-visual {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .token-card {
            background: var(--card-bg);
            border: 2px solid rgba(204, 255, 0, 0.3);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s;
        }

        .token-card:hover {
            border-color: var(--lime-green);
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(204, 255, 0, 0.2);
        }

        .token-amount {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 3.5rem;
            font-weight: 900;
            color: var(--lime-green);
            margin-bottom: 0.5rem;
        }

        .token-description {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.95rem;
        }

        .token-earn {
            margin-top: 1rem;
            padding: 0.75rem 1.5rem;
            background: rgba(204, 255, 0, 0.1);
            border-radius: 10px;
            color: var(--lime-green);
            font-weight: 700;
        }

        /* Pricing Section */
        .pricing {
            padding: 8rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .pricing-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .pricing-card {
            background: var(--card-bg);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            padding: 3rem 2rem;
            text-align: center;
            position: relative;
            transition: all 0.4s;
        }

        .pricing-card.featured {
            border: 2px solid var(--vivid-pink);
            transform: scale(1.05);
        }

        .pricing-card.featured::before {
            content: 'MOST POPULAR';
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--vivid-pink);
            color: white;
            padding: 0.5rem 2rem;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.8rem;
            letter-spacing: 0.1em;
        }

        .pricing-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 60px rgba(0, 212, 255, 0.3);
        }

        .price {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 4rem;
            font-weight: 900;
            color: var(--electric-blue);
            margin: 1rem 0;
        }

        .price span {
            font-size: 1.5rem;
            color: rgba(255, 255, 255, 0.5);
        }

        .pricing-features {
            list-style: none;
            margin: 2rem 0;
            text-align: left;
        }

        .pricing-features li {
            padding: 0.75rem 0;
            color: rgba(255, 255, 255, 0.7);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .pricing-features li::before {
            content: '✓';
            color: var(--lime-green);
            font-weight: 900;
            margin-right: 0.75rem;
        }

        .discount-badge {
            background: linear-gradient(135deg, var(--lime-green), var(--electric-blue));
            color: var(--deep-purple);
            padding: 0.5rem 1rem;
            border-radius: 10px;
            font-weight: 700;
            font-size: 0.9rem;
            margin-top: 1rem;
            display: inline-block;
        }

        /* Social Sprint Section */
        .social-sprint {
            padding: 8rem 5%;
            background: linear-gradient(135deg, rgba(255, 0, 110, 0.1), rgba(0, 212, 255, 0.1));
        }

        .sprint-container {
            max-width: 1000px;
            margin: 0 auto;
            text-align: center;
        }

        .sprint-visual {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin: 3rem 0;
            flex-wrap: wrap;
        }

        .sprint-user {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--electric-blue), var(--vivid-pink));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            animation: pulse 2s ease-in-out infinite;
        }

        .sprint-user:nth-child(2) { animation-delay: 0.2s; }
        .sprint-user:nth-child(3) { animation-delay: 0.4s; }
        .sprint-user:nth-child(4) { animation-delay: 0.6s; }
        .sprint-user:nth-child(5) { animation-delay: 0.8s; }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .sprint-warning {
            background: rgba(255, 0, 110, 0.15);
            border: 2px solid var(--vivid-pink);
            border-radius: 15px;
            padding: 2rem;
            margin-top: 2rem;
        }

        .sprint-warning h4 {
            color: var(--vivid-pink);
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        /* Footer */
        footer {
            padding: 4rem 5%;
            background: var(--deep-purple);
            border-top: 1px solid rgba(0, 212, 255, 0.2);
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .footer-section h4 {
            font-family: 'Darker Grotesque', sans-serif;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--lime-green);
        }

        .footer-section a {
            display: block;
            color: rgba(255, 255, 255, 0.6);
            text-decoration: none;
            padding: 0.5rem 0;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--electric-blue);
        }

        .footer-bottom {
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            color: rgba(255, 255, 255, 0.4);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .features-grid,
            .pricing-cards {
                grid-template-columns: 1fr;
            }

            .stats-bar {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease-out forwards;
        }

        .fade-in:nth-child(1) { animation-delay: 0.1s; }
        .fade-in:nth-child(2) { animation-delay: 0.2s; }
        .fade-in:nth-child(3) { animation-delay: 0.3s; }
        .fade-in:nth-child(4) { animation-delay: 0.4s; }
        .fade-in:nth-child(5) { animation-delay: 0.5s; }
        .fade-in:nth-child(6) { animation-delay: 0.6s; }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="logo">Catalyst</div>
        <div class="nav-links">
            <a href="#features">Features</a>
            <a href="#tokens">Tokens</a>
            <a href="#pricing">Pricing</a>
            <a href="#sprint">Social Sprint</a>
            <a href="#" class="cta-button">Start Free Trial</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>
                Productivity,<br>
                not <span class="gradient-text">passivity</span>
            </h1>
            <p>The only app built for IB students that rewards real work. Lock your phone, unlock your potential, and earn credits for every focused minute.</p>
            <div class="hero-buttons">
                <button class="primary-btn">Start 1-Month Free Trial</button>
                <button class="secondary-btn">See How It Works</button>
            </div>
        </div>
    </section>

    <!-- Stats Bar -->
    <div class="stats-bar">
        <div class="stat">
            <div class="stat-number">1:12</div>
            <div class="stat-label">Tokens Per Hour</div>
        </div>
        <div class="stat">
            <div class="stat-number">60min</div>
            <div class="stat-label">Group Sprints</div>
        </div>
        <div class="stat">
            <div class="stat-number">$4-10</div>
            <div class="stat-label">Monthly (Earn Less)</div>
        </div>
        <div class="stat">
            <div class="stat-number">2x</div>
            <div class="stat-label">Nemesis App Cost</div>
        </div>
    </div>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="section-header">
            <h2>Built for <span class="pink-text">IB DP</span> Students</h2>
            <p>Every feature designed to help you crush your Extended Essay, TOK, and IAs</p>
        </div>
        <div class="features-grid">
            <div class="feature-card fade-in">
                <div class="feature-icon">🎯</div>
                <h3>AI-Verified Goals</h3>
                <p>Set a goal like "300 words for Bio IA" and your phone stays locked until Claude confirms you've hit it. No cheating, no shortcuts.</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🔗</div>
                <h3>ManageBac Integration</h3>
                <p>Auto-import assignments from ManageBac, Google Classroom, and Google Docs. See your week at a glance.</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">⚡</div>
                <h3>Quick Token Wins</h3>
                <p>Earn 1 token every 5 minutes of verified focus work. Perfect for ADHD-friendly motivation and instant gratification.</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🎮</div>
                <h3>Nemesis App Targeting</h3>
                <p>Pick your biggest distraction (TikTok, Instagram, etc.) and it costs double tokens to unlock. Hit your weakness hardest.</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">📊</div>
                <h3>Smart Focus Detection</h3>
                <p>Syncs with your laptop's focus mode. Docs open on "TOK Essay"? Tokens flowing. Alt-tabbing to YouTube? Timer pauses.</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🏆</div>
                <h3>School Perks</h3>
                <p>Trade banked tokens for Free Dress Day passes or other school rewards. Partner schools subsidize for bulk users.</p>
            </div>
        </div>
    </section>

    <!-- Token Economy Section -->
    <section class="token-section" id="tokens">
        <div class="token-container">
            <div class="section-header">
                <h2>The <span class="gradient-text">Token Economy</span></h2>
                <p>Micro-wins that keep you hooked through the IB grind</p>
            </div>
            <div class="token-visual">
                <div class="token-card">
                    <div class="token-amount">1🪙</div>
                    <div class="token-description">Every 5 minutes</div>
                    <div class="token-earn">Verified focused work</div>
                </div>
                <div class="token-card">
                    <div class="token-amount">2🪙</div>
                    <div class="token-description">Low distraction</div>
                    <div class="token-earn">Notes, Calendar (10min unlock)</div>
                </div>
                <div class="token-card">
                    <div class="token-amount">4🪙</div>
                    <div class="token-description">Medium distraction</div>
                    <div class="token-earn">YouTube, Spotify (10min unlock)</div>
                </div>
                <div class="token-card">
                    <div class="token-amount">8🪙</div>
                    <div class="token-description">Your nemesis app</div>
                    <div class="token-earn">Instagram, TikTok, etc. (10min unlock)</div>
                </div>
            </div>
            <div style="text-align: center; margin-top: 3rem;">
                <p style="font-size: 1.1rem; color: rgba(255, 255, 255, 0.7); max-width: 700px; margin: 0 auto;">
                    Tokens roll over weekly. Bank extras to trade for school perks or save for that Extended Essay crunch week when you need flexibility.
                </p>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="pricing" id="pricing">
        <div class="section-header">
            <h2>Smart <span class="gradient-text">Pricing</span></h2>
            <p>The more you focus, the less you pay</p>
        </div>
        <div class="pricing-cards">
            <div class="pricing-card">
                <h3>Free Trial</h3>
                <div class="price">$0<span>/month</span></div>
                <ul class="pricing-features">
                    <li>First month completely free</li>
                    <li>All features unlocked</li>
                    <li>Token system access</li>
                    <li>AI goal verification</li>
                    <li>ManageBac integration</li>
                </ul>
                <button class="cta-button" style="width: 100%; margin-top: 1rem;">Start Free Trial</button>
            </div>
            <div class="pricing-card featured">
                <h3>Standard</h3>
                <div class="price">$10<span>/month</span></div>
                <ul class="pricing-features">
                    <li>All features included</li>
                    <li>Social sprint access</li>
                    <li>School perks integration</li>
                    <li>Weekly token rollover</li>
                    <li>Priority support</li>
                </ul>
                <button class="cta-button" style="width: 100%; margin-top: 1rem;">Get Started</button>
                <div class="discount-badge">Earn discounts by focusing!</div>
            </div>
            <div class="pricing-card">
                <h3>Achiever</h3>
                <div class="price">$7<span>/month</span></div>
                <ul class="pricing-features">
                    <li>Everything in Standard</li>
                    <li>50+ tokens earned weekly</li>
                    <li>Automatic discount applied</li>
                    <li>Advanced analytics</li>
                    <li>Custom rewards</li>
                </ul>
                <button class="cta-button" style="width: 100%; margin-top: 1rem;">Unlock Discount</button>
                <p style="color: var(--lime-green); margin-top: 1rem; font-size: 0.9rem;">Earn $4/month with 20+ assignments completed</p>
            </div>
        </div>
        <div style="text-align: center; margin-top: 3rem;">
            <p style="color: rgba(255, 255, 255, 0.6); font-size: 1.1rem;">
                💡 <strong>School partnerships:</strong> Schools can subsidize subscriptions for all students. Contact us about bulk pricing.
            </p>
        </div>
    </section>

    <!-- Social Sprint Section -->
    <section class="social-sprint" id="sprint">
        <div class="sprint-container">
            <div class="section-header">
                <h2>Social <span class="pink-text">Sprint</span></h2>
                <p>Lock in together. Win together. Lose together.</p>
            </div>
            <div class="sprint-visual">
                <div class="sprint-user">👤</div>
                <div class="sprint-user">👤</div>
                <div class="sprint-user">👤</div>
                <div class="sprint-user">👤</div>
                <div class="sprint-user">👤</div>
            </div>
            <p style="font-size: 1.2rem; max-width: 800px; margin: 2rem auto; color: rgba(255, 255, 255, 0.7);">
                Join a 60-minute sprint with other IB students. Everyone's phone locks simultaneously. Complete your goal and everyone earns bonus tokens.
            </p>
            <div class="sprint-warning">
                <h4>⚠️ The Stakes Are Real</h4>
                <p style="color: rgba(255, 255, 255, 0.7);">
                    If anyone checks Instagram mid-sprint or doesn't finish their assignment, <strong>the entire group loses their reward</strong>. 
                    Accountability meets productivity. Perfect for those Extended Essay all-nighters.
                </p>
            </div>
            <button class="primary-btn" style="margin-top: 2rem;">Find a Sprint Partner</button>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4>Catalyst</h4>
                <p style="color: rgba(255, 255, 255, 0.6);">
                    Productivity, not passivity.<br>
                    Built by IB students, for IB students.
                </p>
            </div>
            <div class="footer-section">
                <h4>Product</h4>
                <a href="#">Features</a>
                <a href="#">Token System</a>
                <a href="#">Pricing</a>
                <a href="#">Social Sprints</a>
            </div>
            <div class="footer-section">
                <h4>Resources</h4>
                <a href="#">ManageBac Setup</a>
                <a href="#">Study Tips</a>
                <a href="#">IB Survival Guide</a>
                <a href="#">API Docs</a>
            </div>
            <div class="footer-section">
                <h4>Company</h4>
                <a href="#">About Us</a>
                <a href="#">School Partnerships</a>
                <a href="#">Contact</a>
                <a href="#">Privacy Policy</a>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 Catalyst. Designed for IB Diploma Programme students worldwide.</p>
        </div>
    </footer>

    <script>
        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

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
    </script>
</body>
</html>
