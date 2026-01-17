# fabrowicztest.github.io

<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Moje Portfolio</title>
    <style>
        :root {
            --bg: #0f172a;
            --bg-alt: #020617;
            --accent: #38bdf8;
            --accent-soft: rgba(56, 189, 248, 0.15);
            --text: #e5e7eb;
            --muted: #9ca3af;
            --card: #020617;
            --border: #1f2937;
            --radius-lg: 18px;
            --radius-md: 12px;
            --shadow-soft: 0 18px 45px rgba(15, 23, 42, 0.9);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: radial-gradient(circle at top, #1e293b 0, #020617 45%, #000 100%);
            color: var(--text);
            line-height: 1.6;
            min-height: 100vh;
        }

        .page {
            max-width: 1100px;
            margin: 0 auto;
            padding: 32px 20px 60px;
        }

        header {
            display: flex;
            flex-wrap: wrap;
            gap: 24px;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 40px;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 14px;
        }

        .avatar {
            width: 60px;
            height: 60px;
            border-radius: 999px;
            background: conic-gradient(from 180deg, #38bdf8, #a855f7, #f97316, #38bdf8);
            padding: 2px;
        }

        .avatar-inner {
            width: 100%;
            height: 100%;
            border-radius: inherit;
            background: radial-gradient(circle at 30% 0, #1f2937 0, #020617 55%, #000 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent);
            font-weight: 700;
            font-size: 1.4rem;
        }

        .brand-text h1 {
            font-size: 1.6rem;
            letter-spacing: 0.03em;
        }

        .brand-text p {
            font-size: 0.9rem;
            color: var(--muted);
        }

        nav {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        nav a {
            text-decoration: none;
            font-size: 0.9rem;
            color: var(--muted);
            padding: 8px 14px;
            border-radius: 999px;
            border: 1px solid rgba(148, 163, 184, 0.3);
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(10px);
            transition: all 0.2s ease;
        }

        nav a:hover {
            color: var(--accent);
            border-color: var(--accent);
            background: rgba(15, 23, 42, 0.95);
        }

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
            gap: 26px;
            margin-bottom: 40px;
        }

        @media (max-width: 800px) {
            .hero {
                grid-template-columns: 1fr;
            }
        }

        .hero-main {
            background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.12), transparent 55%),
                        radial-gradient(circle at bottom right, rgba(129, 140, 248, 0.12), transparent 55%),
                        var(--bg-alt);
            border-radius: var(--radius-lg);
            padding: 22px 22px 20px;
            border: 1px solid rgba(148, 163, 184, 0.35);
            box-shadow: var(--shadow-soft);
            position: relative;
            overflow: hidden;
        }

        .hero-main::before {
            content: "";
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at 0 0, rgba(56, 189, 248, 0.18), transparent 55%);
            opacity: 0.5;
            mix-blend-mode: screen;
            pointer-events: none;
        }

        .hero-main-inner {
            position: relative;
            z-index: 1;
        }

        .eyebrow {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 4px 10px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.4);
            color: var(--muted);
            font-size: 0.75rem;
            margin-bottom: 12px;
        }

        .eyebrow-dot {
            width: 7px;
            height: 7px;
            border-radius: 999px;
            background: #22c55e;
            box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.25);
        }

        .hero-title {
            font-size: clamp(1.8rem, 3vw, 2.2rem);
            margin-bottom: 10px;
        }

        .hero-title span {
            color: var(--accent);
        }

        .hero-subtitle {
            font-size: 0.98rem;
            color: var(--muted);
            max-width: 520px;
            margin-bottom: 18px;
        }

        .hero-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 18px;
        }

        .hero-tag {
            font-size: 0.75rem;
            padding: 4px 10px;
            border-radius: 999px;
            border: 1px solid rgba(148, 163, 184, 0.4);
            background: rgba(15, 23, 42, 0.9);
            color: var(--muted);
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 16px;
        }

        .btn-primary,
        .btn-ghost {
            border-radius: 999px;
            padding: 9px 16px;
            font-size: 0.9rem;
            border: 1px solid transparent;
            cursor: pointer;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
        }

        .btn-primary {
            background: linear-gradient(135deg, #38bdf8, #6366f1);
            color: #0b1120;
            font-weight: 600;
            box-shadow: 0 12px 30px rgba(37, 99, 235, 0.45);
        }

        .btn-primary:hover {
            filter: brightness(1.05);
            transform: translateY(-1px);
            box-shadow: 0 16px 40px rgba(37, 99, 235, 0.6);
        }

        .btn-ghost {
            background: rgba(15, 23, 42, 0.9);
            border-color: rgba(148, 163, 184, 0.5);
            color: var(--muted);
        }

        .btn-ghost:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: rgba(15, 23, 42, 1);
        }

        .hero-meta {
            display: flex;
            flex-wrap: wrap;
            gap: 14px;
            font-size: 0.8rem;
            color: var(--muted);
        }

        .hero-meta-item {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .hero-meta-dot {
            width: 6px;
            height: 6px;
            border-radius: 999px;
            background: rgba(148, 163, 184, 0.7);
        }

        .hero-side {
            display: flex;
            flex-direction: column;
            gap: 14px;
        }

        .card {
            background: radial-gradient(circle at top, rgba(15, 23, 42, 0.9), #020617);
            border-radius: var(--radius-md);
            border: 1px solid rgba(148, 163, 184, 0.35);
            padding: 14px 14px 12px;
            box-shadow: 0 14px 35px rgba(15, 23, 42, 0.85);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .card-title {
            font-size: 0.9rem;
            color: var(--muted);
        }

        .card-pill {
            font-size: 0.7rem;
            padding: 3px 8px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.4);
            color: var(--muted);
        }

        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .skill-pill {
            font-size: 0.75rem;
            padding: 4px 9px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.4);
            color: var(--muted);
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 4px;
        }

        .stat-label {
            font-size: 0.8rem;
            color: var(--muted);
        }

        .stat-value {
            font-size: 1.1rem;
            font-weight: 600;
        }

        .stat-bar {
            width: 100%;
            height: 5px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            overflow: hidden;
            margin-top: 6px;
        }

        .stat-bar-fill {
            height: 100%;
            border-radius: inherit;
            background: linear-gradient(90deg, #38bdf8, #6366f1);
            width: 82%;
        }

        .availability {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 10px;
            font-size: 0.8rem;
            color: var(--muted);
        }

        .availability-status {
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .availability-dot {
            width: 8px;
            height: 8px;
            border-radius: 999px;
            background: #22c55e;
            box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.25);
        }

        .availability-badge {
            font-size: 0.7rem;
            padding: 3px 8px;
            border-radius: 999px;
            background: rgba(22, 163, 74, 0.12);
            color: #4ade80;
            border: 1px solid rgba(34, 197, 94, 0.4);
        }

        .section {
            margin-bottom: 32px;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 14px;
        }

        .section-title {
            font-size: 1.1rem;
        }

        .section-subtitle {
            font-size: 0.85rem;
            color: var(--muted);
        }

        .filter-tabs {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .filter-tab {
            font-size: 0.8rem;
            padding: 5px 10px;
            border-radius: 999px;
            border: 1px solid rgba(148, 163, 184, 0.4);
            background: rgba(15, 23, 42, 0.9);
            color: var(--muted);
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .filter-tab.active {
            border-color: var(--accent);
            color: var(--accent);
            background: rgba(15, 23, 42, 1);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 18px;
        }

        .project-card {
            position: relative;
            border-radius: var(--radius-md);
            background: radial-gradient(circle at top, rgba(15, 23, 42, 0.9), #020617);
            border: 1px solid rgba(148, 163, 184, 0.35);
            padding: 12px 12px 11px;
            overflow: hidden;
            box-shadow: 0 14px 35px rgba(15, 23, 42, 0.85);
            transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease;
        }

        .project-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 18px 45px rgba(15, 23, 42, 0.95);
            border-color: rgba(56, 189, 248, 0.7);
        }

        .project-thumb {
            position: relative;
            border-radius: 12px;
            overflow: hidden;
            background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.18), transparent 55%),
                        radial-gradient(circle at bottom right, rgba(129, 140, 248, 0.18), transparent 55%),
                        #020617;
            height: 150px;
            margin-bottom: 10px;
            border: 1px solid rgba(148, 163, 184, 0.35);
        }

        .project-thumb-image {
            position: absolute;
            inset: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.4;
        }

        .project-thumb-inner {
            position: absolute;
            inset: 0;
            padding: 10px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            font-size: 0.75rem;
            color: var(--muted);
            z-index: 1;
        }

        .project-thumb-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .project-thumb-pill {
            padding: 3px 8px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.4);
        }

        .project-thumb-dots {
            display: flex;
            gap: 4px;
        }

        .project-thumb-dot {
            width: 6px;
            height: 6px;
            border-radius: 999px;
            background: rgba(148, 163, 184, 0.7);
        }

        .project-thumb-title {
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-thumb-bar {
            width: 100%;
            height: 4px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            overflow: hidden;
            margin-top: 6px;
        }

        .project-thumb-bar-fill {
            height: 100%;
            width: 70%;
            background: linear-gradient(90deg, #38bdf8, #6366f1);
        }

        .project-content {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            gap: 8px;
        }

        .project-title {
            font-size: 0.95rem;
        }

        .project-type {
            font-size: 0.75rem;
            color: var(--muted);
        }

        .project-desc {
            font-size: 0.8rem;
            color: var(--muted);
        }

        .project-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.75rem;
            margin-top: 4px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .project-tag {
            padding: 3px 7px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.4);
            color: var(--muted);
        }

        .project-link {
            text-decoration: none;
            color: var(--accent);
            display: inline-flex;
            align-items: center;
            gap: 4px;
        }

        .project-link span {
            font-size: 0.8rem;
        }

        .contact {
            display: grid;
            grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
            gap: 18px;
        }

        @media (max-width: 800px) {
            .contact {
                grid-template-columns: 1fr;
            }
        }

        .contact-card {
            border-radius: var(--radius-md);
            background: radial-gradient(circle at top, rgba(15, 23, 42, 0.9), #020617);
            border: 1px solid rgba(148, 163, 184, 0.35);
            padding: 14px 14px 12px;
            box-shadow: 0 14px 35px rgba(15, 23, 42, 0.85);
        }

        .contact-row {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            font-size: 0.85rem;
            color: var(--muted);
            margin-bottom: 10px;
        }

        .contact-item {
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .contact-item strong {
            color: var(--text);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 8px;
            font-size: 0.85rem;
        }

        .field {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }

        .field label {
            color: var(--muted);
        }

        .field input,
        .field textarea {
            border-radius: 10px;
            border: 1px solid rgba(148, 163, 184, 0.4);
            background: rgba(15, 23, 42, 0.9);
            color: var(--text);
            padding: 7px 9px;
            font-size: 0.85rem;
            outline: none;
            transition: border-color 0.2s ease, box-shadow 0.2s ease;
        }

        .field input:focus,
        .field textarea:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 1px rgba(56, 189, 248, 0.4);
        }

        .field textarea {
            resize: vertical;
            min-height: 80px;
        }

        footer {
            margin-top: 32px;
            font-size: 0.75rem;
            color: var(--muted);
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 8px;
        }

        .footer-links {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: var(--muted);
            text-decoration: none;
            font-size: 0.75rem;
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        /* Light mode theme */
        body.light-mode {
            --bg: #f8f9fa;
            --bg-alt: #ffffff;
            --accent: #10b981;
            --accent-soft: rgba(16, 185, 129, 0.15);
            --text: #1f2937;
            --muted: #6b7280;
            --card: #ffffff;
            --border: #e5e7eb;
            --shadow-soft: 0 18px 45px rgba(0, 0, 0, 0.08);
        }

        body.light-mode {
            background: linear-gradient(135deg, #f0fdf4 0%, #f8f9fa 50%, #f0f9ff 100%);
        }

        /* Toggle button styling */
        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%);
            border: 2px solid rgba(16, 185, 129, 0.3);
            color: white;
            cursor: pointer;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
        }

        .theme-toggle:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 20px rgba(16, 185, 129, 0.5);
        }

        /* Green-to-navy gradient for accent elements */
        .hero-tags, .project-card, .card, .btn-primary {
            background-image: none !important;
        }

        body.light-mode .hero-tags {
            border: 2px solid transparent;
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%);
            background-clip: padding-box;
            -webkit-background-clip: padding-box;
            padding: 12px;
            border-radius: 8px;
        }

        .hero-tag {
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%);
            color: white !important;
            border: none !important;
            transition: all 0.3s ease;
        }

        .hero-tag:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(16, 185, 129, 0.4);
        }

        .btn-primary {
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%) !important;
            color: white !important;
            border: none !important;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(16, 185, 129, 0.4);
        }

        .project-card {
            border: 2px solid transparent;
            transition: all 0.3s ease;
        }

        body.light-mode .project-card {
            background: linear-gradient(135deg, rgba(16, 185, 129, 0.05), rgba(0, 26, 77, 0.05));
            border-color: rgba(16, 185, 129, 0.2);
        }

        body.light-mode .project-card:hover {
            border-color: rgba(16, 185, 129, 0.5);
            box-shadow: 0 8px 25px rgba(16, 185, 129, 0.15);
        }

        .card {
            position: relative;
            border: 2px solid transparent;
        }

        body.light-mode .card {
            background: linear-gradient(135deg, rgba(16, 185, 129, 0.03), rgba(0, 26, 77, 0.03));
            border-color: rgba(16, 185, 129, 0.2);
        }

        .filter-tab {
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%);
            color: white !important;
            border: none !important;
            transition: all 0.3s ease;
        }

        .filter-tab:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
        }

        .filter-tab.active {
            background: linear-gradient(135deg, #10b981 0%, #001a4d 100%);
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.4);
        }
    </style>
</head>
<body>
<button class="theme-toggle" id="themeToggle" title="Zmień motyw">🌙</button>
<div class="page">
    <header>
        <div class="brand">
            <svg width="60" height="60" viewBox="0 0 60 60" class="logo" style="border-radius: 999px; background: linear-gradient(135deg, #38bdf8 0%, #a855f7 100%);">
                <rect width="60" height="60" fill="none"/>
                <circle cx="30" cy="20" r="8" fill="white"/>
                <path d="M 20 35 Q 30 40 40 35" stroke="white" stroke-width="2.5" fill="none" stroke-linecap="round"/>
                <rect x="18" y="42" width="24" height="12" rx="2" fill="white" opacity="0.8"/>
            </svg>
            <div class="brand-text">
                <h1>Bartosz Fabrowicz</h1>
                <p>Projektant graficzny &amp; designer marki</p>
            </div>
        </div>
        <nav>
            <a href="#portfolio">Portfolio</a>
            <a href="#o-mnie">O mnie</a>
            <a href="#kontakt">Kontakt</a>
        </nav>
    </header>

    <main>
        <section class="hero" id="o-mnie">
            <div class="hero-main">
                <div class="hero-main-inner">
                    <div class="eyebrow">
                        <span class="eyebrow-dot"></span>
                        <span>Dostępny na nowe projekty</span>
                    </div>
                    <h2 class="hero-title">
                        Tworzę <span>piękne, funkcjonalne</span> dizajny, które wyrażają istotę Twojej marki.
                    </h2>
                    <p class="hero-subtitle">
                        Specjalizuję się w lekkich, szybkich i czytelnych stronach wizytówkowych, landing page’ach oraz prostych aplikacjach
                        front‑endowych. Stawiam na przejrzystość, detale i dopasowanie do Twojej marki.
                    </p>

                    <div class="hero-tags">
                        <span class="hero-tag">Branding</span>
                        <span class="hero-tag">Logo &amp; Identyfikacja</span>
                        <span class="hero-tag">Projektowanie opakowań</span>
                        <span class="hero-tag">Materiały marketingowe</span>
                    </div>

                    <div class="hero-actions">
                        <a href="#kontakt" class="btn-primary">
                            <span>Porozmawiajmy o Twoim projekcie</span>
                            <span>→</span>
                        </a>
                        <a href="#portfolio" class="btn-ghost">
                            <span>Zobacz przykładowe realizacje</span>
                        </a>
                    </div>

                    <div class="hero-meta">
                        <div class="hero-meta-item">
                            <span class="hero-meta-dot"></span>
                            <span>4+ lata doświadczenia</span>
                        </div>
                        <div class="hero-meta-item">
                            <span class="hero-meta-dot"></span>
                            <span>15+ zrealizowanych projektów</span>
                        </div>
                        <div class="hero-meta-item">
                            <span class="hero-meta-dot"></span>
                            <span>Praca zdalna / hybrydowa</span>
                        </div>
                    </div>
                </div>
            </div>

            <aside class="hero-side">
                <div class="card">
                    <div class="card-header">
                        <span class="card-title">Narzędzia i umiejętności</span>
                        <span class="card-pill">Toolbox</span>
                    </div>
                    <div class="skills-grid">
                        <span class="skill-pill">Figma</span>
                        <span class="skill-pill">Adobe Creative Suite</span>
                        <span class="skill-pill">Branding</span>
                        <span class="skill-pill">Projektowanie opakowań</span>
                        <span class="skill-pill">Typografia</span>
                        <span class="skill-pill">Ilustracja</span>
                        <span class="skill-pill">Social Media Design</span>
                    </div>
                </div>

                <div class="card">
                    <div class="card-header">
                        <span class="card-title">Jakość i terminowość</span>
                        <span class="card-pill">Współpraca</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label">Projekty zakończone w terminie</span>
                        <span class="stat-value">92%</span>
                    </div>
                    <div class="stat-bar">
                        <div class="stat-bar-fill"></div>
                    </div>
                    <div class="availability" style="margin-top: 10px;">
                        <div class="availability-status">
                            <span class="availability-dot"></span>
                            <span>Aktualnie przyjmuję 1–2 nowe projekty miesięcznie.</span>
                        </div>
                        <span class="availability-badge">Wolne terminy</span>
                    </div>
                </div>
            </aside>
        </section>

        <section class="section" id="portfolio">
            <div class="section-header">
                <div>
                    <h3 class="section-title">Wybrane projekty</h3>
                    <p class="section-subtitle">Kilka przykładowych realizacji, które pokazują styl i sposób pracy.</p>
                </div>
                <div class="filter-tabs">
                    <button class="filter-tab active" data-filter="all">Wszystkie</button>
                    <button class="filter-tab" data-filter="biznes">Branding</button>
                    <button class="filter-tab" data-filter="kreatywne">Opakowania</button>
                    <button class="filter-tab" data-filter="landing">Materiały</button>
                </div>
            </div>

            <div class="projects-grid">
                <article class="project-card" data-category="biznes">
                    <div class="project-thumb">
                        <img src="https://picsum.photos/500/300?random=1" alt="Kancelaria" class="project-thumb-image" />
                        <div class="project-thumb-inner">
                            <div class="project-thumb-top">
                                <span class="project-thumb-pill">Projekt branding</span>
                                <div class="project-thumb-dots">
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                </div>
                            </div>
                            <div>
                                <p class="project-thumb-title">Identyfikacja wizualna dla studia kreatywnego</p>
                                <div class="project-thumb-bar">
                                    <div class="project-thumb-bar-fill"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <div class="project-header">
                            <h4 class="project-title">Identyfikacja wizualna "CreativoStudio"</h4>
                            <span class="project-type">Branding</span>
                        </div>
                        <p class="project-desc">
                            Pełny projekt identyfikacji wizualnej dla studia kreatywnego. Logo, paleta barw, typografia i wytyczne marki.
                        </p>
                        <div class="project-meta">
                            <div class="project-tags">
                                <span class="project-tag">Logo design</span>
                                <span class="project-tag">Branding</span>
                                <span class="project-tag">Brand guidelines</span>
                            </div>
                            <a href="#" class="project-link">
                                <span>Podgląd</span>
                                <span>↗</span>
                            </a>
                        </div>
                    </div>
                </article>

                <article class="project-card" data-category="kreatywne">
                    <div class="project-thumb">
                        <img src="https://picsum.photos/500/300?random=2" alt="Portfolio fotografa" class="project-thumb-image" />
                        <div class="project-thumb-inner">
                            <div class="project-thumb-top">
                                <span class="project-thumb-pill">Projekt opakowania</span>
                                <div class="project-thumb-dots">
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                </div>
                            </div>
                            <div>
                                <p class="project-thumb-title">Ekologiczne opakowanie dla kawęrni</p>
                                <div class="project-thumb-bar">
                                    <div class="project-thumb-bar-fill" style="width: 80%;"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <div class="project-header">
                            <h4 class="project-title">Projekt opakowania "EcoTea"</h4>
                            <span class="project-type">Opakowania</span>
                        </div>
                        <p class="project-desc">
                            Ekologiczne opakowanie dla małej kawęrni. Projekt łączy nowoczesny design z naturalną estetyką.
                        </p>
                        <div class="project-meta">
                            <div class="project-tags">
                                <span class="project-tag">Packaging</span>
                                <span class="project-tag">Ilustracja</span>
                                <span class="project-tag">Druk</span>
                            </div>
                            <a href="#" class="project-link">
                                <span>Podgląd</span>
                                <span>↗</span>
                            </a>
                        </div>
                    </div>
                </article>

                <article class="project-card" data-category="landing">
                    <div class="project-thumb">
                        <img src="https://picsum.photos/500/300?random=3" alt="Landing SaaS" class="project-thumb-image" />
                        <div class="project-thumb-inner">
                            <div class="project-thumb-top">
                                <span class="project-thumb-pill">Kampania marketingowa</span>
                                <div class="project-thumb-dots">
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                </div>
                            </div>
                            <div>
                                <p class="project-thumb-title">Materiały promocyjne i grafiki do mediów</p>
                                <div class="project-thumb-bar">
                                    <div class="project-thumb-bar-fill" style="width: 90%;"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <div class="project-header">
                            <h4 class="project-title">Kampania "DesignDay 2025"</h4>
                            <span class="project-type">Materiały</span>
                        </div>
                        <p class="project-desc">
                            Pełna kampania marketingowa. Plakaty, ulotki, grafiki na media społeczne i zaproszenia.
                        </p>
                        <div class="project-meta">
                            <div class="project-tags">
                                <span class="project-tag">Social Media</span>
                                <span class="project-tag">Poligrafia</span>
                                <span class="project-tag">Copywriting</span>
                            </div>
                            <a href="#" class="project-link">
                                <span>Podgląd</span>
                                <span>↗</span>
                            </a>
                        </div>
                    </div>
                </article>

                <article class="project-card" data-category="biznes">
                    <div class="project-thumb">
                        <img src="https://picsum.photos/500/300?random=4" alt="Studio kosmetyczne" class="project-thumb-image" />
                        <div class="project-thumb-inner">
                            <div class="project-thumb-top">
                                <span class="project-thumb-pill">Projekt branding</span>
                                <div class="project-thumb-dots">
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                    <span class="project-thumb-dot"></span>
                                </div>
                            </div>
                            <div>
                                <p class="project-thumb-title">Branding studia urody i piękna</p>
                                <div class="project-thumb-bar">
                                    <div class="project-thumb-bar-fill" style="width: 75%;"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <div class="project-header">
                            <h4 class="project-title">Branding "Glow Beauty"</h4>
                            <span class="project-type">Branding</span>
                        </div>
                        <p class="project-desc">
                            Elegancka identyfikacja marki dla studia urody. Logo, materiały drukowane i spójność wizualna.
                        </p>
                        <div class="project-meta">
                            <div class="project-tags">
                                <span class="project-tag">Logo</span>
                                <span class="project-tag">Poligrafia</span>
                                <span class="project-tag">Wizualizacja</span>
                            </div>
                            <a href="#" class="project-link">
                                <span>Podgląd</span>
                                <span>↗</span>
                            </a>
                        </div>
                    </div>
                </article>
            </div>
        </section>

        <section class="section" id="kontakt">
            <div class="section-header">
                <div>
                    <h3 class="section-title">Kontakt</h3>
                    <p class="section-subtitle">Napisz kilka słów o swoim projekcie – odezwę się z propozycją współpracy.</p>
                </div>
            </div>

            <div class="contact">
                <div class="contact-card">
                    <div class="contact-row">
                        <div class="contact-item">
                            <strong>E‑mail:</strong> <span>bartosz.fabrowicz@example.com</span>
                        </div>
                        <div class="contact-item">
                            <strong>Telefon:</strong> <span>+48 123 456 789</span>
                        </div>
                    </div>
                    <div class="contact-row">
                        <div class="contact-item">
                            <strong>Miasto:</strong> <span>Warszawa / zdalnie</span>
                        </div>
                        <div class="contact-item">
                            <strong>LinkedIn:</strong> <span>/bartosz-fabrowicz</span>
                        </div>
                    </div>
                    <p style="font-size: 0.85rem; color: var(--muted); margin-top: 4px;">
                        Zazwyczaj odpowiadam w ciągu jednego dnia roboczego. Możemy zacząć od krótkiej, niezobowiązującej rozmowy.
                    </p>
                </div>

                <div class="contact-card">
                    <form class="contact-form" onsubmit="event.preventDefault(); alert('To przykładowy formularz – tutaj możesz podpiąć backend lub usługę e‑mail.');">
                        <div class="field">
                            <label for="name">Imię i nazwisko</label>
                            <input type="text" id="name" name="name" placeholder="Jak mogę się do Ciebie zwracać?" required />
                        </div>
                        <div class="field">
                            <label for="email">Adres e‑mail</label>
                            <input type="email" id="email" name="email" placeholder="Twój adres e‑mail" required />
                        </div>
                        <div class="field">
                            <label for="project">Opisz krótko swój projekt</label>
                            <textarea id="project" name="project" placeholder="Np. strona wizytówkowa dla małej firmy, termin, budżet orientacyjny..." required></textarea>
                        </div>
                        <button type="submit" class="btn-primary" style="margin-top: 4px; align-self: flex-start;">
                            Wyślij wiadomość
                        </button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <span>© <span id="year"></span> Bartosz Fabrowicz – projekty stron internetowych.</span>
        <div class="footer-links">
            <a href="#o-mnie">O mnie</a>
            <a href="#portfolio">Portfolio</a>
            <a href="#kontakt">Kontakt</a>
        </div>
    </footer>
</div>

<script>
    // Rok w stopce
    document.getElementById("year").textContent = new Date().getFullYear();

    // Prosty filtr projektów
    const tabs = document.querySelectorAll(".filter-tab");
    const projects = document.querySelectorAll(".project-card");

    tabs.forEach(tab => {
        tab.addEventListener("click", () => {
            const filter = tab.getAttribute("data-filter");

            tabs.forEach(t => t.classList.remove("active"));
            tab.classList.add("active");

            projects.forEach(project => {
                const category = project.getAttribute("data-category");
                if (filter === "all" || category === filter) {
                    project.style.display = "";
                } else {
                    project.style.display = "none";
                }
            });
        });
    });

    // Przełącznik motywu
    const themeToggle = document.getElementById("themeToggle");
    const htmlElement = document.documentElement;

    // Sprawdzenie preferowanego motywu
    const savedTheme = localStorage.getItem("theme") || "dark";
    if (savedTheme === "light") {
        document.body.classList.add("light-mode");
        themeToggle.textContent = "☀️";
    }

    themeToggle.addEventListener("click", () => {
        document.body.classList.toggle("light-mode");
        const isLightMode = document.body.classList.contains("light-mode");
        localStorage.setItem("theme", isLightMode ? "light" : "dark");
        themeToggle.textContent = isLightMode ? "☀️" : "🌙";
    });
</script>
</body>
</html>
