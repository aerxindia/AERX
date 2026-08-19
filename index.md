<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>AERX — Beyond Cooling | Next-Gen Environmental Tech</title>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700;14..32,800;14..32,900&display=swap" rel="stylesheet" />

    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />

    <style>
        /* ===== CSS VARIABLES ===== */
        :root {
            --bg-deep: #070d1a;
            --bg-card: rgba(255, 255, 255, 0.04);
            --border-glass: rgba(255, 255, 255, 0.08);
            --primary-teal: #00e5ff;
            --primary-cyan: #00b4d8;
            --gradient-accent: linear-gradient(135deg, #00e5ff, #00b4d8);
            --nature-green: #6affb0;
            --text-light: #e2e8f0;
            --text-muted: #94a3b8;
            --shadow-glow: 0 0 30px rgba(0, 229, 255, 0.15);
            --radius-xl: 24px;
            --transition: 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-deep);
            color: var(--text-light);
            line-height: 1.7;
            overflow-x: hidden;
            position: relative;
        }

        /* ===== ANIMATED BACKGROUND ===== */
        .bg-wave {
            position: fixed;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            z-index: -1;
            background: radial-gradient(circle at 20% 30%, rgba(0, 180, 216, 0.08) 0%, transparent 50%),
                        radial-gradient(circle at 80% 70%, rgba(106, 255, 176, 0.05) 0%, transparent 40%);
            animation: waveFloat 40s linear infinite;
        }

        @keyframes waveFloat {
            0% { transform: translate(0, 0) rotate(0deg); }
            100% { transform: translate(-5%, -5%) rotate(3deg); }
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }
        .particle {
            position: absolute;
            background: rgba(0, 229, 255, 0.15);
            border-radius: 50%;
            animation: floatUp 30s infinite linear;
        }
        .particle:nth-child(1) { width: 6px; height: 6px; left: 10%; animation-duration: 25s; }
        .particle:nth-child(2) { width: 12px; height: 12px; left: 30%; animation-duration: 35s; animation-delay: 5s; }
        .particle:nth-child(3) { width: 8px; height: 8px; left: 50%; animation-duration: 28s; animation-delay: 10s; }
        .particle:nth-child(4) { width: 4px; height: 4px; left: 70%; animation-duration: 20s; animation-delay: 2s; }
        .particle:nth-child(5) { width: 10px; height: 10px; left: 85%; animation-duration: 32s; animation-delay: 8s; }

        @keyframes floatUp {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-10vh) scale(1); opacity: 0; }
        }

        a { text-decoration: none; color: inherit; }
        ul { list-style: none; }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ===== BUTTONS ===== */
        .btn {
            display: inline-block;
            padding: 14px 36px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            transition: var(--transition);
            cursor: pointer;
            border: none;
            font-family: inherit;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: var(--gradient-accent);
            color: var(--bg-deep);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.3);
        }
        .btn-primary:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 0 40px rgba(0, 229, 255, 0.5);
        }

        .btn-outline {
            background: transparent;
            color: var(--primary-teal);
            border: 1px solid var(--primary-teal);
            backdrop-filter: blur(4px);
        }
        .btn-outline:hover {
            background: var(--primary-teal);
            color: var(--bg-deep);
            transform: translateY(-3px);
            box-shadow: 0 0 30px rgba(0, 229, 255, 0.3);
        }

        /* ===== GLASS NAVIGATION ===== */
        .navbar {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 1200px;
            z-index: 1000;
            background: rgba(7, 13, 26, 0.6);
            backdrop-filter: blur(16px) saturate(180%);
            -webkit-backdrop-filter: blur(16px) saturate(180%);
            border: 1px solid var(--border-glass);
            border-radius: 80px;
            padding: 12px 28px;
            transition: var(--transition);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
        }

        .navbar .container {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0;
        }

        /* Header Logo */
        .logo-css {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            cursor: pointer;
        }
        .logo-css .main-text {
            display: flex;
            font-size: 2.4rem;
            font-weight: 900;
            letter-spacing: -2px;
            line-height: 1;
            font-family: 'Inter', sans-serif;
        }
        .logo-css .main-text .ae { color: #ffffff; }
        .logo-css .main-text .r { color: #ffffff; }
        .logo-css .main-text .x {
            background: var(--gradient-accent);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .logo-css .wave-line {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            margin-top: -6px;
        }
        .logo-css .wave-line span {
            height: 3px;
            width: 20%;
            background: var(--gradient-accent);
            border-radius: 4px;
        }
        .logo-css .wave-line .swoosh {
            flex: 1;
            height: 8px;
            background: transparent;
            position: relative;
            border-radius: 50%;
        }
        .logo-css .wave-line .swoosh::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-accent);
            border-radius: 50%;
            transform: scaleX(0.6);
            opacity: 0.6;
            filter: blur(4px);
        }
        .logo-css .tagline {
            font-size: 0.65rem;
            letter-spacing: 4px;
            font-weight: 600;
            color: var(--primary-teal);
            margin-top: 2px;
            text-transform: uppercase;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
        }
        .nav-links a {
            font-weight: 500;
            font-size: 0.9rem;
            color: var(--text-muted);
            transition: var(--transition);
            position: relative;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-accent);
            transition: var(--transition);
        }
        .nav-links a:hover { color: var(--text-light); }
        .nav-links a:hover::after { width: 100%; }
        .nav-links a.active { color: var(--primary-teal); }
        .nav-links a.active::after { width: 100%; }

        .nav-cta {
            padding: 10px 24px;
            border-radius: 50px;
            background: var(--gradient-accent);
            color: var(--bg-deep) !important;
            font-weight: 700;
        }
        .nav-cta:hover { transform: translateY(-2px); box-shadow: 0 0 20px rgba(0, 229, 255, 0.3); }
        .nav-cta::after { display: none !important; }

        .hamburger {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            padding: 4px;
        }
        .hamburger span {
            width: 28px;
            height: 2px;
            background: var(--text-light);
            border-radius: 4px;
            transition: var(--transition);
        }
        .hamburger.active span:nth-child(1) { transform: rotate(45deg) translate(5px, 6px); }
        .hamburger.active span:nth-child(2) { opacity: 0; }
        .hamburger.active span:nth-child(3) { transform: rotate(-45deg) translate(5px, -6px); }

        /* ===== SECTIONS ===== */
        section {
            padding: 120px 0 80px;
        }

        .section-label {
            display: inline-block;
            font-weight: 600;
            color: var(--primary-teal);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.75rem;
            margin-bottom: 10px;
            border: 1px solid rgba(0, 229, 255, 0.2);
            padding: 4px 16px;
            border-radius: 40px;
            background: rgba(0, 229, 255, 0.05);
        }

        .section-title {
            font-size: 3rem;
            font-weight: 800;
            line-height: 1.1;
            letter-spacing: -1px;
            margin-bottom: 16px;
            background: linear-gradient(180deg, #ffffff 20%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-sub {
            font-size: 1.15rem;
            color: var(--text-muted);
            max-width: 640px;
        }

        /* ===== HERO ===== */
        #home {
            padding-top: 180px;
            padding-bottom: 100px;
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
        }

        #home .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .hero-content h1 {
            font-size: 4.2rem;
            font-weight: 900;
            line-height: 1.1;
            letter-spacing: -2px;
            color: #ffffff;
        }
        .hero-content h1 .highlight {
            background: var(--gradient-accent);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-content p {
            font-size: 1.2rem;
            color: var(--text-muted);
            max-width: 520px;
            margin: 24px 0 36px;
        }
        .hero-btns {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        /* ===== UPDATED ORB WITH YOUR LOGO ===== */
        .hero-visual {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .hero-orb {
            width: 460px;
            height: 460px;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%, rgba(0, 229, 255, 0.25), rgba(7, 13, 26, 0) 75%);
            box-shadow: 0 0 80px rgba(0, 229, 255, 0.2), inset 0 0 80px rgba(0, 229, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            animation: pulseOrb 4s ease-in-out infinite;
            position: relative;
        }
        @keyframes pulseOrb {
            0% { transform: scale(0.98); opacity: 0.8; }
            50% { transform: scale(1.02); opacity: 1; }
            100% { transform: scale(0.98); opacity: 0.8; }
        }

        /* Your logo centered inside the Orb with a subtle glass backdrop */
        .orb-logo {
            background: rgba(7, 13, 26, 0.4);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            padding: 20px 36px;
            border-radius: 24px;
            text-align: center;
            z-index: 5;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
        }
        .orb-logo .logo-main {
            font-size: 4.8rem;
            font-weight: 900;
            color: #ffffff;
            letter-spacing: -2px;
            line-height: 1;
        }
        .orb-logo .logo-main .x-highlight {
            background: var(--gradient-accent);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .orb-logo .line-separator {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            margin: 8px 0 2px 0;
        }
        .orb-logo .line-separator hr {
            flex: 1;
            border: none;
            height: 2px;
            background: var(--gradient-accent);
            opacity: 0.6;
        }
        .orb-logo .logo-tagline {
            font-size: 0.8rem;
            letter-spacing: 4px;
            font-weight: 600;
            color: var(--primary-teal);
            text-transform: uppercase;
        }

        /* Floating Badges (Exact match to your image) */
        .floating-badge {
            position: absolute;
            background: rgba(7, 13, 26, 0.9);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(0, 229, 255, 0.3);
            padding: 10px 18px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.85rem;
            color: var(--primary-teal);
            display: flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 0 25px rgba(0, 229, 255, 0.1);
            z-index: 10;
            animation: floatBadge 6s ease-in-out infinite;
        }
        @keyframes floatBadge {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-12px); }
            100% { transform: translateY(0px); }
        }
        .badge-ai { top: 8%; right: -12%; animation-delay: 0s; }
        .badge-outdoor { bottom: 10%; left: -15%; animation-delay: 2s; }
        .floating-badge i { color: var(--primary-teal); font-size: 1.1rem; }

        /* ===== ABOUT ===== */
        #about {
            background: rgba(255, 255, 255, 0.02);
            border-top: 1px solid var(--border-glass);
            border-bottom: 1px solid var(--border-glass);
            backdrop-filter: blur(4px);
        }
        #about .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        .about-visual {
            background: radial-gradient(circle, rgba(0, 229, 255, 0.05) 0%, transparent 70%);
            border-radius: var(--radius-xl);
            padding: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 300px;
            border: 1px solid var(--border-glass);
            position: relative;
        }
        .about-visual i {
            font-size: 5rem;
            color: var(--primary-teal);
            opacity: 0.6;
        }
        .about-text p { color: var(--text-muted); margin-bottom: 20px; }
        .about-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
            margin-top: 24px;
        }
        .stat-item {
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            padding: 20px;
            border-radius: 16px;
            text-align: center;
            transition: var(--transition);
        }
        .stat-item:hover {
            border-color: var(--primary-teal);
            transform: translateY(-4px);
            box-shadow: var(--shadow-glow);
        }
        .stat-item h4 {
            font-size: 2rem;
            font-weight: 800;
            color: var(--primary-teal);
        }
        .stat-item p { font-size: 0.9rem; color: var(--text-muted); margin: 0; }

        /* ===== MISSION / VISION ===== */
        #mission-vision { padding: 80px 0; }
        #mission-vision .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }
        .mv-card {
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            backdrop-filter: blur(8px);
            padding: 48px 40px;
            border-radius: var(--radius-xl);
            transition: var(--transition);
        }
        .mv-card:hover {
            transform: translateY(-8px);
            border-color: var(--nature-green);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }
        .mv-card .icon { font-size: 2.4rem; color: var(--nature-green); margin-bottom: 16px; }
        .mv-card h3 { font-size: 1.6rem; font-weight: 700; margin-bottom: 12px; }
        .mv-card p { color: var(--text-muted); font-size: 1.05rem; }

        /* ===== TECHNOLOGY ===== */
        #technology { background: rgba(255, 255, 255, 0.01); }
        #technology .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        .tech-content p { color: var(--text-muted); margin-bottom: 16px; }
        .tech-features {
            margin-top: 24px;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        .tech-feature {
            display: flex;
            align-items: center;
            gap: 14px;
            padding: 14px 20px;
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            border-radius: 14px;
            transition: var(--transition);
        }
        .tech-feature:hover {
            background: rgba(0, 229, 255, 0.05);
            border-color: var(--primary-teal);
            transform: translateX(6px);
        }
        .tech-feature i { color: var(--primary-teal); font-size: 1.2rem; width: 28px; text-align: center; }
        .tech-feature span { font-weight: 500; }

        .tech-visual {
            background: linear-gradient(145deg, rgba(7, 13, 26, 0.8), rgba(0, 180, 216, 0.2));
            border: 1px solid var(--border-glass);
            border-radius: var(--radius-xl);
            padding: 40px;
            min-height: 360px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            backdrop-filter: blur(8px);
            position: relative;
        }
        .tech-visual .hex-grid {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image:
                linear-gradient(30deg, rgba(0, 229, 255, 0.03) 12%, transparent 12.5%, transparent 87%, rgba(0, 229, 255, 0.03) 87.5%),
                linear-gradient(150deg, rgba(0, 229, 255, 0.03) 12%, transparent 12.5%, transparent 87%, rgba(0, 229, 255, 0.03) 87.5%);
            background-size: 40px 70px;
            pointer-events: none;
        }
        .tech-visual i { font-size: 4rem; color: var(--nature-green); margin-bottom: 16px; z-index: 2; }
        .tech-visual h4 { font-size: 1.4rem; font-weight: 700; z-index: 2; }
        .tech-visual p { color: var(--text-muted); max-width: 280px; margin-top: 8px; z-index: 2; }

        /* ===== HOW IT WORKS ===== */
        #how-it-works { background: rgba(255, 255, 255, 0.02); }
        #how-it-works .section-title { text-align: center; }
        #how-it-works .section-sub { text-align: center; margin: 0 auto 40px; }
        .steps-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 24px;
        }
        .step-card {
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            padding: 32px 24px;
            border-radius: var(--radius-xl);
            text-align: center;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        .step-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--gradient-accent);
            opacity: 0;
            transition: var(--transition);
        }
        .step-card:hover { transform: translateY(-8px); border-color: var(--primary-teal); }
        .step-card:hover::before { opacity: 1; }
        .step-number {
            width: 56px;
            height: 56px;
            border-radius: 50%;
            background: var(--gradient-accent);
            color: var(--bg-deep);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            margin: 0 auto 16px;
            font-size: 1.2rem;
        }
        .step-card h4 { font-size: 1.15rem; font-weight: 700; margin-bottom: 8px; }
        .step-card p { color: var(--text-muted); font-size: 0.95rem; }

        /* ===== ECOSHIELD ===== */
        #ecoshield { background: rgba(255, 255, 255, 0.01); }
        #ecoshield .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        .ecoshield-visual {
            background: radial-gradient(circle at center, rgba(106, 255, 176, 0.1) 0%, transparent 70%);
            border: 1px solid var(--border-glass);
            border-radius: var(--radius-xl);
            padding: 40px;
            min-height: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            color: var(--nature-green);
            position: relative;
        }
        .ecoshield-features {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin-top: 20px;
        }
        .ef-item {
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            padding: 16px 20px;
            border-radius: 14px;
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
        }
        .ef-item:hover { border-color: var(--nature-green); transform: translateX(4px); }
        .ef-item i { color: var(--nature-green); font-size: 1.2rem; }

        /* ===== CONTACT / FOOTER ===== */
        #contact {
            background: rgba(7, 13, 26, 1);
            border-top: 1px solid var(--border-glass);
            padding: 80px 0 40px;
        }
        #contact .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
        }
        .contact-info h2 { font-size: 2.4rem; font-weight: 800; margin-bottom: 12px; }
        .contact-info p { color: var(--text-muted); font-size: 1.05rem; margin-bottom: 24px; }
        .contact-details { display: flex; flex-direction: column; gap: 14px; }
        .contact-details div {
            display: flex;
            align-items: center;
            gap: 14px;
            font-size: 1rem;
            color: var(--text-light);
        }
        .contact-details i { width: 24px; color: var(--primary-teal); }

        .contact-form {
            background: var(--bg-card);
            border: 1px solid var(--border-glass);
            border-radius: var(--radius-xl);
            padding: 40px;
            backdrop-filter: blur(8px);
        }
        .contact-form h4 { font-size: 1.3rem; margin-bottom: 20px; }
        .contact-form input, .contact-form textarea {
            width: 100%;
            padding: 14px 18px;
            border: 1px solid var(--border-glass);
            border-radius: 12px;
            background: rgba(255, 255, 255, 0.04);
            color: var(--text-light);
            font-family: inherit;
            font-size: 1rem;
            margin-bottom: 16px;
            transition: var(--transition);
        }
        .contact-form input::placeholder, .contact-form textarea::placeholder { color: var(--text-muted); }
        .contact-form input:focus, .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary-teal);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.05);
        }
        .contact-form textarea { min-height: 120px; resize: vertical; }
        .contact-form .btn {
            width: 100%;
            background: var(--gradient-accent);
            color: var(--bg-deep);
            font-weight: 700;
        }
        .contact-form .btn:hover { box-shadow: 0 0 40px rgba(0, 229, 255, 0.4); }

        .footer-bottom {
            margin-top: 60px;
            padding-top: 30px;
            border-top: 1px solid var(--border-glass);
            text-align: center;
            font-size: 0.9rem;
            color: var(--text-muted);
        }
        .footer-bottom .socials { display: flex; justify-content: center; gap: 24px; margin-bottom: 16px; }
        .footer-bottom .socials a { color: var(--text-muted); font-size: 1.2rem; transition: var(--transition); }
        .footer-bottom .socials a:hover { color: var(--primary-teal); transform: translateY(-3px); }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 1024px) {
            .steps-grid { grid-template-columns: repeat(2, 1fr); }
            .hero-content h1 { font-size: 3.2rem; }
            .hero-orb { width: 380px; height: 380px; }
            .orb-logo .logo-main { font-size: 3.8rem; }
            .floating-badge { font-size: 0.75rem; padding: 8px 16px; }
            .badge-ai { right: -5%; }
            .badge-outdoor { left: -5%; }
        }

        @media (max-width: 768px) {
            .navbar { top: 0; width: 100%; border-radius: 0; padding: 14px 20px; }
            .nav-links {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background: rgba(7, 13, 26, 0.98);
                backdrop-filter: blur(16px);
                flex-direction: column;
                padding: 30px 24px;
                gap: 24px;
                transform: translateY(-120%);
                transition: var(--transition);
                border-bottom: 1px solid var(--border-glass);
            }
            .nav-links.open { transform: translateY(0); }
            .hamburger { display: flex; }

            #home .container, #about .container, #technology .container, #ecoshield .container, #contact .container {
                grid-template-columns: 1fr;
            }
            #home { padding-top: 120px; min-height: auto; }
            .hero-content h1 { font-size: 2.6rem; }
            
            .hero-orb { width: 320px; height: 320px; }
            .orb-logo .logo-main { font-size: 3.2rem; }
            .orb-logo { padding: 16px 24px; }
            
            .floating-badge { font-size: 0.7rem; padding: 6px 14px; }
            .badge-ai { top: 0; right: 0; }
            .badge-outdoor { bottom: 0; left: 0; }

            .section-title { font-size: 2.2rem; }
            .steps-grid { grid-template-columns: 1fr 1fr; }
            .ecoshield-features { grid-template-columns: 1fr; }
            .about-stats { grid-template-columns: 1fr 1fr; }
            .contact-form { padding: 24px; }
            #mission-vision .container { grid-template-columns: 1fr; }
        }

        @media (max-width: 480px) {
            .steps-grid { grid-template-columns: 1fr; }
            .hero-content h1 { font-size: 2rem; }
            .about-stats { grid-template-columns: 1fr; }
            .logo-css .main-text { font-size: 1.8rem; }
            .logo-css .tagline { font-size: 0.5rem; letter-spacing: 2px; }
            
            .hero-orb { width: 260px; height: 260px; }
            .orb-logo .logo-main { font-size: 2.6rem; }
            .orb-logo { padding: 12px 16px; }
            .orb-logo .logo-tagline { font-size: 0.6rem; letter-spacing: 2px; }
        }

        /* ===== SCROLL REVEAL ===== */
        .reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.8s ease, transform 0.8s ease; }
        .reveal.visible { opacity: 1; transform: translateY(0); }
    </style>
</head>
<body>

    <!-- ===== ANIMATED BACKGROUND ===== -->
    <div class="bg-wave"></div>
    <div class="particles">
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
    </div>

    <!-- ===== NAVIGATION ===== -->
    <nav class="navbar" id="navbar">
        <div class="container">
            <!-- Header Logo -->
            <a href="#home" class="logo-css">
                <div class="main-text">
                    <span class="ae">AE</span><span class="r">R</span><span class="x">X</span>
                </div>
                <div class="wave-line">
                    <span></span>
                    <div class="swoosh"></div>
                    <span></span>
                </div>
                <div class="tagline">Beyond Cooling</div>
            </a>

            <ul class="nav-links" id="navLinks">
                <li><a href="#home" class="active">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#technology">Technology</a></li>
                <li><a href="#ecoshield">EcoShield</a></li>
                <li><a href="#contact" class="nav-cta">Contact</a></li>
            </ul>

            <div class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- ===== HERO ===== -->
    <section id="home">
        <div class="container">
            <div class="hero-content reveal">
                <span class="section-label"><i class="fas fa-leaf" style="margin-right:6px;"></i> Next-Gen Sustainability</span>
                <h1>Engineering the <span class="highlight">Air</span> of Tomorrow</h1>
                <p>
                    AERX develops biotechnology-powered smart environmental solutions that monitor, analyze, and improve <strong>indoor and outdoor</strong> air quality through real-time sensing, AI, and natural CO₂ capture.
                </p>
                <div class="hero-btns">
                    <a href="#ecoshield" class="btn btn-primary">Discover EcoShield</a>
                    <a href="#technology" class="btn btn-outline">How It Works</a>
                </div>
            </div>

            <!-- ===== YOUR LOGO INSIDE THE ORB WITH FLOATING BADGES ===== -->
            <div class="hero-visual reveal">
                <div class="hero-orb">
                    
                    <!-- Your brand logo neatly centered -->
                    <div class="orb-logo">
                        <div class="logo-main">AER<span class="x-highlight">X</span></div>
                        <div class="line-separator">
                            <hr><hr>
                        </div>
                        <div class="logo-tagline">Beyond Cooling</div>
                    </div>

                    <!-- Floating Badges -->
                    <div class="floating-badge badge-ai">
                        <i class="fas fa-microchip"></i> AI-Powered
                    </div>
                    <div class="floating-badge badge-outdoor">
                        <i class="fas fa-wind"></i> Indoor & Outdoor
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== ABOUT ===== -->
    <section id="about">
        <div class="container">
            <div class="about-visual reveal">
                <i class="fas fa-seedling"></i>
                <i class="fas fa-arrows-spin" style="font-size:3rem; margin:0 20px;"></i>
                <i class="fas fa-city"></i>
            </div>
            <div class="about-text reveal">
                <span class="section-label">About AERX</span>
                <h2 class="section-title">Redefining Air Quality</h2>
                <p>
                    AERX is a biotechnology-driven environmental technology company that transforms conventional HVAC and open-air systems into intelligent, sustainable solutions. By integrating biotechnology, AI, and IoT, we create healthier and greener spaces.
                </p>
                <p>
                    Our flagship product, <strong>EcoShield</strong>, monitors air quality in real time and utilizes microalgae to naturally reduce CO₂ — making every building and outdoor environment breathe cleaner air.
                </p>
                <div class="about-stats">
                    <div class="stat-item">
                        <h4>80%</h4>
                        <p>CO₂ reduction potential</p>
                    </div>
                    <div class="stat-item">
                        <h4>24/7</h4>
                        <p>Real-time monitoring</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== MISSION & VISION ===== -->
    <section id="mission-vision">
        <div class="container">
            <div class="mv-card reveal">
                <div class="icon"><i class="fas fa-rocket"></i></div>
                <h3>Our Mission</h3>
                <p>
                    To engineer smart, affordable, and eco-friendly technologies that make the air we breathe cleaner — bridging the gap between comfort, nature, and environmental responsibility.
                </p>
            </div>
            <div class="mv-card reveal">
                <div class="icon"><i class="fas fa-eye"></i></div>
                <h3>Our Vision</h3>
                <p>
                    A future where every air management system contributes not only to comfort, but also to environmental sustainability and climate resilience — turning air into a force for good.
                </p>
            </div>
        </div>
    </section>

    <!-- ===== TECHNOLOGY ===== -->
    <section id="technology">
        <div class="container">
            <div class="tech-content reveal">
                <span class="section-label">Our Technology</span>
                <h2 class="section-title">Biotech + AI + IoT</h2>
                <p>
                    AERX proposes a modular system combining microalgae-based CO₂ utilization, air-quality sensing, and IoT-based monitoring. The prototype consists of a controlled airflow pathway containing a microalgal photobioreactor — adaptable for both enclosed HVAC ducts and open-air setups.
                </p>
                <p>
                    Sensors monitor CO₂, temperature, and humidity, allowing the effectiveness of the biological system to be evaluated. An ESP32-based control system collects and transmits data to a digital dashboard for real-time analysis.
                </p>
                <div class="tech-features">
                    <div class="tech-feature">
                        <i class="fas fa-dna"></i>
                        <span>Microalgae-based CO₂ capture</span>
                    </div>
                    <div class="tech-feature">
                        <i class="fas fa-microchip"></i>
                        <span>ESP32 + IoT real-time monitoring</span>
                    </div>
                    <div class="tech-feature">
                        <i class="fas fa-brain"></i>
                        <span>AI-driven predictive analytics</span>
                    </div>
                    <div class="tech-feature">
                        <i class="fas fa-chart-line"></i>
                        <span>Digital dashboard &amp; visualization</span>
                    </div>
                </div>
            </div>
            <div class="tech-visual reveal">
                <div class="hex-grid"></div>
                <i class="fas fa-microscope"></i>
                <h4>Photobioreactor Core</h4>
                <p>Selected microalgae utilize CO₂ during photosynthesis, turning air into clean, breathable oxygen.</p>
            </div>
        </div>
    </section>

    <!-- ===== HOW IT WORKS ===== -->
    <section id="how-it-works">
        <div class="container">
            <span class="section-label" style="display:block; text-align:center;">Process</span>
            <h2 class="section-title" style="text-align:center;">How EcoShield Works</h2>
            <p class="section-sub" style="text-align:center;">
                A seamless blend of biology, electronics, and intelligence.
            </p>

            <div class="steps-grid">
                <div class="step-card reveal">
                    <div class="step-number">1</div>
                    <h4>Air Intake</h4>
                    <p>Controlled air stream from indoor or outdoor environments enters the modular system.</p>
                </div>
                <div class="step-card reveal">
                    <div class="step-number">2</div>
                    <h4>Bio-Filtration</h4>
                    <p>Microalgae in the photobioreactor absorb CO₂ and release oxygen through photosynthesis.</p>
                </div>
                <div class="step-card reveal">
                    <div class="step-number">3</div>
                    <h4>Smart Sensing</h4>
                    <p>Inlet &amp; outlet sensors monitor CO₂, temperature, and humidity in real time.</p>
                </div>
                <div class="step-card reveal">
                    <div class="step-number">4</div>
                    <h4>AI Analytics</h4>
                    <p>ESP32 transmits data to the cloud for predictive optimization and environmental reporting.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== ECOSHIELD ===== -->
    <section id="ecoshield">
        <div class="container">
            <div class="ecoshield-visual reveal">
                <i class="fas fa-shield-halved" style="font-size:5rem;"></i>
                <span style="font-size:2.5rem; font-weight:800; margin-left:16px; color:var(--text-light);">EcoShield</span>
            </div>
            <div class="reveal">
                <span class="section-label">Flagship Product</span>
                <h2 class="section-title">EcoShield™</h2>
                <p style="color:var(--text-muted); font-size:1.05rem; margin:12px 0 20px;">
                    EcoShield is a smart, bio-based air treatment and monitoring system designed for both <strong>indoor HVAC environments and outdoor open-air spaces</strong>. It actively removes CO₂ while providing actionable air-quality insights — all in a compact, scalable platform.
                </p>
                <div class="ecoshield-features">
                    <div class="ef-item"><i class="fas fa-leaf"></i> Natural CO₂ capture</div>
                    <div class="ef-item"><i class="fas fa-wifi"></i> IoT-enabled</div>
                    <div class="ef-item"><i class="fas fa-chart-bar"></i> Real-time dashboard</div>
                    <div class="ef-item"><i class="fas fa-bolt"></i> Low energy footprint</div>
                    <div class="ef-item"><i class="fas fa-expand"></i> Modular &amp; scalable</div>
                    <div class="ef-item"><i class="fas fa-robot"></i> AI-ready</div>
                </div>
                <a href="#contact" class="btn btn-primary" style="margin-top:24px;">Get a Demo</a>
            </div>
        </div>
    </section>

    <!-- ===== CONTACT / FOOTER ===== -->
    <section id="contact">
        <div class="container">
            <div class="contact-info reveal">
                <h2>Let's Build<br />Cleaner Air Together</h2>
                <p>
                    Interested in bringing EcoShield to your project? Reach out — we'd love to collaborate.
                </p>
                <div class="contact-details">
                    <div><i class="fas fa-envelope"></i> aerx.india@gmail.com</div>
                    <div><i class="fas fa-phone"></i> +91 8608081881</div>
                    <div><i class="fas fa-map-pin"></i> Chennai, Tamil Nadu, India</div>
                </div>
            </div>
            <div class="contact-form reveal">
                <h4>Send a Message</h4>
                <form id="contactForm" onsubmit="event.preventDefault(); alert('Thank you for reaching out! We\'ll get back to you soon.');">
                    <input type="text" placeholder="Full Name" required />
                    <input type="email" placeholder="Email Address" required />
                    <input type="text" placeholder="Company / Organization" />
                    <textarea placeholder="Tell us about your project..."></textarea>
                    <button type="submit" class="btn">Send Message</button>
                </form>
            </div>
        </div>

        <div class="container footer-bottom">
            <div class="socials">
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
            </div>
            <p>&copy; 2026 AERX. All rights reserved. — Beyond Cooling.</p>
        </div>
    </section>

    <!-- ===== JAVASCRIPT ===== -->
    <script>
        // Hamburger Toggle
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', () => {
            hamburger.classList.toggle('active');
            navLinks.classList.toggle('open');
        });

        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navLinks.classList.remove('open');
            });
        });

        // Active nav link
        const sections = document.querySelectorAll('section[id]');
        const navAnchors = document.querySelectorAll('.nav-links a:not(.nav-cta)');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop - 150;
                if (window.scrollY >= sectionTop) {
                    current = section.getAttribute('id');
                }
            });
            navAnchors.forEach(anchor => {
                anchor.classList.remove('active');
                if (anchor.getAttribute('href') === `#${current}`) {
                    anchor.classList.add('active');
                }
            });
        });

        // Scroll Reveal
        const revealElements = document.querySelectorAll('.reveal');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.15, rootMargin: '0px 0px -40px 0px' });
        revealElements.forEach(el => observer.observe(el));
    </script>
</body>
</html>
