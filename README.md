<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anandi Lifestyle Solutions — Construction & Design</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --gold: #C9A84C;
    --gold-light: #E8CC84;
    --gold-dark: #8B6914;
    --charcoal: #1A1A1A;
    --slate: #2D2D2D;
    --concrete: #4A4A4A;
    --warm-white: #F9F5EE;
    --cream: #EDE8DC;
    --text-muted: #7A7570;
    --font-display: 'Playfair Display', Georgia, serif;
    --font-body: 'Inter', system-ui, sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--font-body);
    background: var(--charcoal);
    color: var(--warm-white);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.25rem 5%;
    background: rgba(26,26,26,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(201,168,76,0.15);
    transition: background 0.3s;
  }

  .nav-logo {
    font-family: var(--font-display);
    font-size: 1.25rem;
    color: var(--gold);
    letter-spacing: 0.02em;
    text-decoration: none;
  }
  .nav-logo span { color: var(--warm-white); font-size: 0.75rem; display: block; font-family: var(--font-body); letter-spacing: 0.15em; font-weight: 300; text-transform: uppercase; }

  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a { text-decoration: none; color: rgba(249,245,238,0.7); font-size: 0.85rem; letter-spacing: 0.08em; text-transform: uppercase; font-weight: 400; transition: color 0.2s; }
  .nav-links a:hover { color: var(--gold); }

  .nav-cta {
    background: var(--gold);
    color: var(--charcoal);
    border: none;
    padding: 0.6rem 1.5rem;
    font-family: var(--font-body);
    font-size: 0.8rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    transition: background 0.2s;
  }
  .nav-cta:hover { background: var(--gold-light); }

  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; padding: 4px; }
  .hamburger span { width: 24px; height: 1.5px; background: var(--warm-white); display: block; transition: 0.3s; }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 80px;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 5% 6rem 7%;
    position: relative;
    z-index: 2;
  }

  .hero-eyebrow {
    font-size: 0.75rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }
  .hero-eyebrow::before {
    content: '';
    width: 40px; height: 1px;
    background: var(--gold);
    display: inline-block;
  }

  .hero-headline {
    font-family: var(--font-display);
    font-size: clamp(3rem, 5.5vw, 5.5rem);
    font-weight: 700;
    line-height: 1.08;
    letter-spacing: -0.01em;
    margin-bottom: 1.75rem;
    color: var(--warm-white);
  }
  .hero-headline em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-subtext {
    font-size: 1rem;
    line-height: 1.7;
    color: rgba(249,245,238,0.6);
    max-width: 460px;
    margin-bottom: 3rem;
    font-weight: 300;
  }

  .hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; }

  .btn-primary {
    background: var(--gold);
    color: var(--charcoal);
    padding: 0.95rem 2.5rem;
    font-weight: 600;
    font-size: 0.85rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.2s, transform 0.15s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-1px); }

  .btn-ghost {
    border: 1px solid rgba(249,245,238,0.3);
    color: var(--warm-white);
    padding: 0.95rem 2.5rem;
    font-size: 0.85rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s;
    display: inline-block;
  }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

  .hero-stats {
    margin-top: 4rem;
    display: flex;
    gap: 3rem;
    padding-top: 2rem;
    border-top: 1px solid rgba(201,168,76,0.2);
  }
  .stat-num {
    font-family: var(--font-display);
    font-size: 2.25rem;
    font-weight: 700;
    color: var(--gold);
    display: block;
  }
  .stat-label {
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-top: 0.25rem;
    display: block;
  }

  .hero-right {
    position: relative;
    overflow: hidden;
  }

  /* Architectural illustration replacing stock photo */
  .hero-visual {
    width: 100%;
    height: 100%;
    position: relative;
    background: linear-gradient(135deg, #252525 0%, #1a1a1a 100%);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .hero-visual-bg {
    position: absolute;
    inset: 0;
    background:
      repeating-linear-gradient(0deg, transparent, transparent 60px, rgba(201,168,76,0.04) 60px, rgba(201,168,76,0.04) 61px),
      repeating-linear-gradient(90deg, transparent, transparent 60px, rgba(201,168,76,0.04) 60px, rgba(201,168,76,0.04) 61px);
  }

  .hero-building {
    position: relative;
    z-index: 2;
  }

  /* Gold vertical accent line */
  .hero-accent-line {
    position: absolute;
    left: 0;
    top: 0; bottom: 0;
    width: 3px;
    background: linear-gradient(180deg, transparent, var(--gold) 30%, var(--gold) 70%, transparent);
  }

  /* ── MARQUEE ── */
  .marquee-bar {
    background: var(--gold);
    padding: 0.85rem 0;
    overflow: hidden;
    white-space: nowrap;
  }
  .marquee-inner {
    display: inline-block;
    animation: marquee 28s linear infinite;
  }
  .marquee-inner span {
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--charcoal);
    padding: 0 2.5rem;
  }
  .marquee-inner span::before { content: '◆'; margin-right: 2.5rem; opacity: 0.6; }

  @keyframes marquee {
    0%   { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }

  /* ── SECTIONS COMMON ── */
  section { padding: 6rem 7%; }

  .section-tag {
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }
  .section-tag::before { content: ''; width: 30px; height: 1px; background: var(--gold); }

  .section-heading {
    font-family: var(--font-display);
    font-size: clamp(2rem, 3.5vw, 3.25rem);
    font-weight: 700;
    line-height: 1.15;
    color: var(--warm-white);
    max-width: 600px;
  }
  .section-heading em { font-style: italic; color: var(--gold); }

  /* ── SERVICES ── */
  #services { background: var(--slate); }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5px;
    margin-top: 4rem;
    background: rgba(201,168,76,0.12);
  }

  .service-card {
    background: var(--slate);
    padding: 2.5rem;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .service-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gold);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.35s cubic-bezier(0.4,0,0.2,1);
  }
  .service-card:hover { background: #323232; }
  .service-card:hover::after { transform: scaleX(1); }

  .service-number {
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 1.75rem;
    display: block;
  }

  .service-icon {
    width: 48px; height: 48px;
    margin-bottom: 1.5rem;
    opacity: 0.85;
  }

  .service-title {
    font-family: var(--font-display);
    font-size: 1.35rem;
    font-weight: 700;
    margin-bottom: 0.75rem;
    color: var(--warm-white);
  }

  .service-desc {
    font-size: 0.875rem;
    line-height: 1.7;
    color: rgba(249,245,238,0.55);
    font-weight: 300;
  }

  /* ── WHY US ── */
  #why { background: var(--charcoal); }

  .why-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
    margin-top: 4rem;
  }

  .why-list { list-style: none; display: flex; flex-direction: column; gap: 2rem; }
  .why-item {
    display: flex;
    gap: 1.5rem;
    align-items: flex-start;
    padding-bottom: 2rem;
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }
  .why-item:last-child { border-bottom: none; padding-bottom: 0; }

  .why-dot {
    width: 42px; height: 42px; flex-shrink: 0;
    border: 1px solid var(--gold);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display);
    font-size: 1rem;
    color: var(--gold);
    font-weight: 700;
  }

  .why-item-title {
    font-weight: 600;
    font-size: 0.95rem;
    margin-bottom: 0.4rem;
    color: var(--warm-white);
  }
  .why-item-text {
    font-size: 0.85rem;
    line-height: 1.65;
    color: rgba(249,245,238,0.5);
    font-weight: 300;
  }

  .why-visual {
    position: relative;
  }

  .why-blueprint {
    background: #1e2530;
    border: 1px solid rgba(201,168,76,0.2);
    padding: 2.5rem;
    position: relative;
    overflow: hidden;
  }

  .why-blueprint::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      repeating-linear-gradient(0deg, transparent, transparent 30px, rgba(100,150,255,0.06) 30px, rgba(100,150,255,0.06) 31px),
      repeating-linear-gradient(90deg, transparent, transparent 30px, rgba(100,150,255,0.06) 30px, rgba(100,150,255,0.06) 31px);
  }

  /* ── PROJECTS ── */
  #projects { background: var(--charcoal); padding-bottom: 0; }

  .projects-header {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    margin-bottom: 3rem;
    flex-wrap: wrap;
    gap: 1.5rem;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
    gap: 1.5px;
    background: rgba(201,168,76,0.08);
  }

  .project-card {
    position: relative;
    overflow: hidden;
    cursor: pointer;
    background: var(--slate);
  }

  .project-card.featured {
    grid-column: span 2;
  }

  .project-visual {
    width: 100%;
    aspect-ratio: 4/3;
    display: flex;
    align-items: flex-end;
    padding: 1.75rem;
    position: relative;
    background: var(--slate);
  }

  .project-card.featured .project-visual { aspect-ratio: 16/9; }

  .project-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, transparent 40%, rgba(26,26,26,0.92) 100%);
    transition: opacity 0.3s;
  }

  .project-card:hover .project-overlay { opacity: 1; }

  .project-svg-scene { position: absolute; inset: 0; width: 100%; height: 100%; }

  .project-info {
    position: relative;
    z-index: 2;
    transform: translateY(8px);
    transition: transform 0.3s;
  }
  .project-card:hover .project-info { transform: translateY(0); }

  .project-cat {
    font-size: 0.68rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 0.4rem;
  }
  .project-name {
    font-family: var(--font-display);
    font-size: 1.2rem;
    color: var(--warm-white);
    font-weight: 700;
  }
  .project-card.featured .project-name { font-size: 1.6rem; }

  /* ── PROCESS ── */
  #process { background: var(--slate); }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    margin-top: 4rem;
    position: relative;
  }

  .process-steps::before {
    content: '';
    position: absolute;
    top: 26px;
    left: calc(12.5% + 24px);
    right: calc(12.5% + 24px);
    height: 1px;
    background: rgba(201,168,76,0.25);
  }

  .process-step { padding: 0 1.5rem; position: relative; }

  .step-number {
    width: 52px; height: 52px;
    background: var(--charcoal);
    border: 1px solid rgba(201,168,76,0.3);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display);
    font-size: 1.1rem;
    color: var(--gold);
    font-weight: 700;
    margin-bottom: 1.75rem;
    position: relative;
    z-index: 2;
  }

  .step-title {
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--warm-white);
    margin-bottom: 0.6rem;
  }
  .step-desc {
    font-size: 0.82rem;
    line-height: 1.65;
    color: rgba(249,245,238,0.45);
    font-weight: 300;
  }

  /* ── TESTIMONIALS ── */
  #testimonials { background: var(--charcoal); }

  .testimonials-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5px;
    margin-top: 4rem;
    background: rgba(201,168,76,0.08);
  }

  .testimonial-card {
    background: var(--charcoal);
    padding: 2.5rem;
    position: relative;
  }

  .testimonial-card::before {
    content: '"';
    font-family: var(--font-display);
    font-size: 5rem;
    color: var(--gold);
    opacity: 0.25;
    position: absolute;
    top: 1rem; left: 2rem;
    line-height: 1;
  }

  .testimonial-text {
    font-size: 0.92rem;
    line-height: 1.75;
    color: rgba(249,245,238,0.65);
    font-weight: 300;
    margin-bottom: 2rem;
    position: relative;
  }

  .testimonial-author {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .author-avatar {
    width: 40px; height: 40px;
    border-radius: 50%;
    background: rgba(201,168,76,0.15);
    border: 1px solid rgba(201,168,76,0.35);
    display: flex; align-items: center; justify-content: center;
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--gold);
    flex-shrink: 0;
  }

  .author-name {
    font-weight: 600;
    font-size: 0.88rem;
    color: var(--warm-white);
  }
  .author-role {
    font-size: 0.75rem;
    color: var(--text-muted);
    margin-top: 0.15rem;
  }

  /* ── CTA BAND ── */
  #cta-band {
    background: var(--gold);
    padding: 5rem 7%;
  }

  .cta-band-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
  }

  .cta-band-text {
    font-family: var(--font-display);
    font-size: clamp(1.75rem, 3vw, 2.75rem);
    font-weight: 700;
    color: var(--charcoal);
    max-width: 560px;
    line-height: 1.2;
  }

  .btn-dark {
    background: var(--charcoal);
    color: var(--warm-white);
    padding: 1rem 2.5rem;
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    display: inline-block;
    transition: background 0.2s;
    white-space: nowrap;
  }
  .btn-dark:hover { background: var(--slate); }

  /* ── CONTACT ── */
  #contact { background: var(--slate); }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 5rem;
    margin-top: 4rem;
    align-items: start;
  }

  .contact-info { display: flex; flex-direction: column; gap: 2rem; }

  .contact-item { display: flex; gap: 1rem; }
  .contact-icon {
    width: 40px; height: 40px;
    border: 1px solid rgba(201,168,76,0.3);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }
  .contact-icon svg { width: 18px; height: 18px; stroke: var(--gold); fill: none; }

  .contact-label { font-size: 0.72rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--text-muted); margin-bottom: 0.25rem; }
  .contact-value { font-size: 0.92rem; color: var(--warm-white); font-weight: 400; }

  .contact-form { display: flex; flex-direction: column; gap: 1rem; }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-group label { font-size: 0.72rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-muted); }

  .form-group input,
  .form-group textarea,
  .form-group select {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.1);
    color: var(--warm-white);
    padding: 0.85rem 1rem;
    font-family: var(--font-body);
    font-size: 0.9rem;
    font-weight: 300;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }
  .form-group input::placeholder,
  .form-group textarea::placeholder { color: rgba(249,245,238,0.25); }
  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus { border-color: var(--gold); }
  .form-group select { cursor: pointer; appearance: none; }
  .form-group select option { background: var(--slate); }
  .form-group textarea { resize: vertical; min-height: 100px; }

  .btn-submit {
    background: var(--gold);
    color: var(--charcoal);
    border: none;
    padding: 1rem 2.5rem;
    font-family: var(--font-body);
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.2s;
    align-self: flex-start;
    margin-top: 0.5rem;
  }
  .btn-submit:hover { background: var(--gold-light); }

  .form-success {
    display: none;
    background: rgba(201,168,76,0.1);
    border: 1px solid rgba(201,168,76,0.3);
    padding: 1rem 1.5rem;
    color: var(--gold);
    font-size: 0.88rem;
    margin-top: 0.5rem;
  }

  /* ── FOOTER ── */
  footer {
    background: #111;
    padding: 4rem 7% 2rem;
  }

  .footer-top {
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr 1fr;
    gap: 3rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid rgba(255,255,255,0.07);
  }

  .footer-brand {
    font-family: var(--font-display);
    font-size: 1.35rem;
    color: var(--gold);
    margin-bottom: 0.5rem;
  }
  .footer-tagline {
    font-size: 0.8rem;
    color: var(--text-muted);
    line-height: 1.6;
    font-weight: 300;
    margin-top: 0.75rem;
  }

  .footer-col-title {
    font-size: 0.7rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 500;
    margin-bottom: 1.25rem;
  }

  .footer-col-links { list-style: none; display: flex; flex-direction: column; gap: 0.65rem; }
  .footer-col-links a {
    color: rgba(249,245,238,0.45);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 300;
    transition: color 0.2s;
  }
  .footer-col-links a:hover { color: var(--gold); }

  .footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 2rem;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-copy { font-size: 0.78rem; color: var(--text-muted); font-weight: 300; }
  .footer-website { font-size: 0.78rem; color: rgba(201,168,76,0.6); }

  /* ── RESPONSIVE ── */
  @media (max-width: 1024px) {
    #hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-right { display: none; }
    .hero-left { padding: 5rem 6%; }
    .why-grid { grid-template-columns: 1fr; gap: 3rem; }
    .projects-grid { grid-template-columns: 1fr 1fr; }
    .project-card.featured { grid-column: span 2; }
    .process-steps { grid-template-columns: 1fr 1fr; gap: 3rem; }
    .process-steps::before { display: none; }
    .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
    .footer-top { grid-template-columns: 1fr 1fr; }
  }

  @media (max-width: 768px) {
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    nav { padding: 1rem 5%; }
    section { padding: 4rem 5%; }
    .hero-left { padding: 4rem 5%; }
    .hero-headline { font-size: 2.5rem; }
    .hero-stats { gap: 1.75rem; }
    .projects-grid { grid-template-columns: 1fr; }
    .project-card.featured { grid-column: span 1; }
    .process-steps { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr; gap: 2rem; }
    .form-row { grid-template-columns: 1fr; }
    .footer-bottom { flex-direction: column; align-items: flex-start; }
    #cta-band { padding: 3.5rem 5%; }
    .cta-band-inner { flex-direction: column; align-items: flex-start; }
    .btn-dark { align-self: flex-start; }
  }

  /* ── MOBILE NAV ── */
  .mobile-nav {
    position: fixed;
    top: 60px; left: 0; right: 0;
    background: var(--charcoal);
    border-top: 1px solid rgba(201,168,76,0.15);
    border-bottom: 1px solid rgba(201,168,76,0.15);
    padding: 1.5rem 5%;
    display: none;
    flex-direction: column;
    gap: 1.25rem;
    z-index: 99;
  }
  .mobile-nav.open { display: flex; }
  .mobile-nav a {
    text-decoration: none;
    color: rgba(249,245,238,0.7);
    font-size: 0.9rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    font-weight: 400;
  }
  .mobile-nav a:hover { color: var(--gold); }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    Anandi Lifestyle Solutions
    <span>Construction & Design</span>
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Get a Quote</a>
  <button class="hamburger" onclick="toggleMobileNav()" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<div class="mobile-nav" id="mobileNav">
  <a href="#services" onclick="closeMobileNav()">Services</a>
  <a href="#projects" onclick="closeMobileNav()">Projects</a>
  <a href="#process" onclick="closeMobileNav()">Process</a>
  <a href="#testimonials" onclick="closeMobileNav()">Testimonials</a>
  <a href="#contact" onclick="closeMobileNav()">Contact</a>
</div>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">Est. 2010 · Manipur, India</div>
    <h1 class="hero-headline">
      Building Spaces<br>That <em>Define</em><br>How You Live
    </h1>
    <p class="hero-subtext">
      From residential homes to commercial landmarks, Anandi Lifestyle Solutions delivers precision craftsmanship and inspired design — built to endure, designed to inspire.
    </p>
    <div class="hero-actions">
      <a href="#projects" class="btn-primary">View Our Work</a>
      <a href="#contact" class="btn-ghost">Start a Project</a>
    </div>
    <div class="hero-stats">
      <div>
        <span class="stat-num">200+</span>
        <span class="stat-label">Projects Completed</span>
      </div>
      <div>
        <span class="stat-num">15+</span>
        <span class="stat-label">Years of Excellence</span>
      </div>
      <div>
        <span class="stat-num">98%</span>
        <span class="stat-label">Client Satisfaction</span>
      </div>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-accent-line"></div>
    <div class="hero-visual">
      <div class="hero-visual-bg"></div>
      <svg class="hero-building" viewBox="0 0 420 520" width="420" height="520" xmlns="http://www.w3.org/2000/svg">
        <!-- Ground -->
        <rect x="0" y="490" width="420" height="30" fill="#111" opacity="0.8"/>
        <!-- Main building body -->
        <rect x="60" y="180" width="300" height="310" fill="#252525" stroke="#C9A84C" stroke-width="1" opacity="0.9"/>
        <!-- Building facade grid lines (horizontal) -->
        <line x1="60" y1="220" x2="360" y2="220" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="260" x2="360" y2="260" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="300" x2="360" y2="300" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="340" x2="360" y2="340" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="380" x2="360" y2="380" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="420" x2="360" y2="420" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="60" y1="460" x2="360" y2="460" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <!-- Building facade grid lines (vertical) -->
        <line x1="120" y1="180" x2="120" y2="490" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="180" y1="180" x2="180" y2="490" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="240" y1="180" x2="240" y2="490" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <line x1="300" y1="180" x2="300" y2="490" stroke="#C9A84C" stroke-width="0.4" opacity="0.3"/>
        <!-- Windows — floor 1 -->
        <rect x="80" y="200" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="140" y="200" width="28" height="18" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="200" y="200" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="260" y="200" width="28" height="18" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="320" y="200" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Windows — floor 2 -->
        <rect x="80" y="240" width="28" height="18" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="140" y="240" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="200" y="240" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="260" y="240" width="28" height="18" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="320" y="240" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Windows — floor 3 -->
        <rect x="80" y="280" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="140" y="280" width="28" height="18" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="200" y="280" width="28" height="18" fill="rgba(201,168,76,0.25)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="260" y="280" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="320" y="280" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Windows — floor 4 -->
        <rect x="80" y="320" width="28" height="18" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="140" y="320" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="200" y="320" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="260" y="320" width="28" height="18" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="320" y="320" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Windows — floor 5 -->
        <rect x="80" y="360" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="140" y="360" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="200" y="360" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="260" y="360" width="28" height="18" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <rect x="320" y="360" width="28" height="18" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Ground floor entrance -->
        <rect x="155" y="430" width="110" height="60" fill="#1a1a1a" stroke="rgba(201,168,76,0.5)" stroke-width="1"/>
        <line x1="210" y1="430" x2="210" y2="490" stroke="rgba(201,168,76,0.4)" stroke-width="0.5"/>
        <!-- Steps -->
        <rect x="140" y="485" width="140" height="5" fill="#2a2a2a" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
        <rect x="145" y="483" width="130" height="3" fill="#333"/>
        <!-- Roof accent -->
        <rect x="60" y="170" width="300" height="12" fill="#C9A84C" opacity="0.9"/>
        <!-- Rooftop elements -->
        <rect x="140" y="130" width="140" height="42" fill="#1e1e1e" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
        <rect x="190" y="100" width="40" height="32" fill="#1e1e1e" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
        <!-- Cranes / structure top -->
        <line x1="210" y1="40" x2="210" y2="100" stroke="rgba(201,168,76,0.5)" stroke-width="1.5"/>
        <line x1="130" y1="55" x2="280" y2="55" stroke="rgba(201,168,76,0.5)" stroke-width="1.5"/>
        <line x1="250" y1="55" x2="265" y2="100" stroke="rgba(201,168,76,0.3)" stroke-width="1"/>
        <!-- Small left building -->
        <rect x="10" y="320" width="45" height="170" fill="#1e1e1e" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
        <rect x="15" y="340" width="12" height="10" fill="rgba(201,168,76,0.1)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="30" y="340" width="12" height="10" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="15" y="360" width="12" height="10" fill="rgba(201,168,76,0.1)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="30" y="360" width="12" height="10" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="15" y="380" width="12" height="10" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="30" y="380" width="12" height="10" fill="rgba(201,168,76,0.1)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <!-- Small right building -->
        <rect x="365" y="290" width="45" height="200" fill="#1e1e1e" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
        <rect x="370" y="310" width="12" height="10" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="385" y="310" width="12" height="10" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="370" y="330" width="12" height="10" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <rect x="385" y="330" width="12" height="10" fill="rgba(201,168,76,0.1)" stroke="rgba(201,168,76,0.25)" stroke-width="0.4"/>
        <!-- Gold accent label -->
        <rect x="64" y="186" width="3" height="300" fill="#C9A84C" opacity="0.6"/>
        <!-- Stars / sky -->
        <circle cx="320" cy="30" r="1" fill="#C9A84C" opacity="0.6"/>
        <circle cx="350" cy="70" r="1.2" fill="#C9A84C" opacity="0.5"/>
        <circle cx="380" cy="20" r="0.8" fill="#C9A84C" opacity="0.7"/>
        <circle cx="30" cy="60" r="1" fill="#C9A84C" opacity="0.4"/>
        <circle cx="80" cy="30" r="0.8" fill="#C9A84C" opacity="0.5"/>
        <circle cx="390" cy="50" r="0.6" fill="#C9A84C" opacity="0.6"/>
      </svg>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-bar">
  <div class="marquee-inner">
    <span>Residential Construction</span>
    <span>Commercial Builds</span>
    <span>Interior Design</span>
    <span>Renovation & Remodeling</span>
    <span>Project Management</span>
    <span>Structural Engineering</span>
    <span>Turnkey Solutions</span>
    <span>Residential Construction</span>
    <span>Commercial Builds</span>
    <span>Interior Design</span>
    <span>Renovation & Remodeling</span>
    <span>Project Management</span>
    <span>Structural Engineering</span>
    <span>Turnkey Solutions</span>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="section-tag">What We Build</div>
  <h2 class="section-heading">Crafting Spaces Across <em>Every Scale</em></h2>
  <div class="services-grid">
    <div class="service-card">
      <span class="service-number">01</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 40V20L24 8l18 12v20H6z"/>
        <rect x="18" y="28" width="12" height="12" stroke-width="1.2"/>
        <line x1="24" y1="8" x2="24" y2="4" stroke-width="1.5"/>
      </svg>
      <div class="service-title">Residential Construction</div>
      <p class="service-desc">Custom homes, villas, and multi-family residences built from the ground up. We translate your vision into a home that stands as a testament to quality craftsmanship.</p>
    </div>
    <div class="service-card">
      <span class="service-number">02</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <rect x="4" y="14" width="40" height="26" rx="1"/>
        <path d="M4 20h40"/>
        <rect x="10" y="8" width="28" height="6"/>
        <line x1="16" y1="26" x2="16" y2="34"/>
        <line x1="24" y1="26" x2="24" y2="34"/>
        <line x1="32" y1="26" x2="32" y2="34"/>
      </svg>
      <div class="service-title">Commercial Projects</div>
      <p class="service-desc">Offices, retail spaces, hotels, and industrial facilities — engineered for functionality, built for impact. We handle projects from boutique to landmark scale.</p>
    </div>
    <div class="service-card">
      <span class="service-number">03</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <path d="M8 40V18l8-8h16l8 8v22H8z"/>
        <path d="M16 10v6M32 10v6"/>
        <rect x="14" y="28" width="8" height="12"/>
        <rect x="26" y="24" width="8" height="8"/>
      </svg>
      <div class="service-title">Interior Design</div>
      <p class="service-desc">Thoughtful interiors that merge aesthetics with livability. Our design team creates spaces that feel personal, functional, and timeless — from concept to final furnishing.</p>
    </div>
    <div class="service-card">
      <span class="service-number">04</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 38l10-12 8 6 8-10 10 16H6z"/>
        <circle cx="38" cy="12" r="6"/>
        <line x1="38" y1="6" x2="38" y2="4"/>
        <line x1="38" y1="18" x2="38" y2="20"/>
        <line x1="32" y1="12" x2="30" y2="12"/>
        <line x1="44" y1="12" x2="46" y2="12"/>
      </svg>
      <div class="service-title">Renovation & Remodeling</div>
      <p class="service-desc">Breathing new life into existing structures. From kitchen overhauls to full building retrofits, we modernize and transform spaces while preserving their structural integrity.</p>
    </div>
    <div class="service-card">
      <span class="service-number">05</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <rect x="4" y="8" width="40" height="32" rx="1"/>
        <line x1="4" y1="18" x2="44" y2="18"/>
        <line x1="16" y1="8" x2="16" y2="40"/>
        <circle cx="10" cy="13" r="2" fill="#C9A84C" stroke="none"/>
        <line x1="20" y1="24" x2="38" y2="24"/>
        <line x1="20" y1="30" x2="32" y2="30"/>
        <line x1="20" y1="36" x2="36" y2="36"/>
      </svg>
      <div class="service-title">Project Management</div>
      <p class="service-desc">End-to-end coordination of timelines, contractors, budgets, and compliance. We act as your single point of accountability — so your project runs on schedule and within budget.</p>
    </div>
    <div class="service-card">
      <span class="service-number">06</span>
      <svg class="service-icon" viewBox="0 0 48 48" fill="none" stroke="#C9A84C" stroke-width="1.5" xmlns="http://www.w3.org/2000/svg">
        <path d="M24 6L6 18v24h36V18L24 6z"/>
        <path d="M24 6v36"/>
        <path d="M6 18l18 6 18-6"/>
        <circle cx="24" cy="12" r="2" fill="#C9A84C" stroke="none"/>
      </svg>
      <div class="service-title">Turnkey Solutions</div>
      <p class="service-desc">Hand over the key — that is our promise. We manage every phase from architectural design and permits through construction, finishing, and delivery of a fully functional space.</p>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="why">
  <div class="section-tag">Why Anandi</div>
  <h2 class="section-heading">Precision at Every <em>Stage</em></h2>
  <div class="why-grid">
    <ul class="why-list">
      <li class="why-item">
        <div class="why-dot">01</div>
        <div>
          <div class="why-item-title">Local Expertise, Regional Vision</div>
          <p class="why-item-text">Deep knowledge of Manipur's terrain, climate, and construction regulations means fewer surprises and faster delivery.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-dot">02</div>
        <div>
          <div class="why-item-title">Transparent Pricing</div>
          <p class="why-item-text">Detailed, itemized cost breakdowns before we break ground. No hidden charges, no mid-project shocks.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-dot">03</div>
        <div>
          <div class="why-item-title">Quality Materials, Certified Partners</div>
          <p class="why-item-text">We source only from trusted suppliers and use certified contractors — your structure is built to outlast decades.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-dot">04</div>
        <div>
          <div class="why-item-title">On-Time Delivery</div>
          <p class="why-item-text">Our project management system tracks every milestone. We have a 94% on-time completion record across 200+ projects.</p>
        </div>
      </li>
    </ul>
    <div class="why-visual">
      <div class="why-blueprint">
        <!-- Blueprint SVG -->
        <svg viewBox="0 0 320 260" width="100%" xmlns="http://www.w3.org/2000/svg">
          <!-- Grid -->
          <defs>
            <pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse">
              <path d="M 20 0 L 0 0 0 20" fill="none" stroke="rgba(100,150,255,0.15)" stroke-width="0.5"/>
            </pattern>
          </defs>
          <rect width="320" height="260" fill="url(#grid)"/>
          <!-- Main floor plan outline -->
          <rect x="40" y="40" width="240" height="180" fill="none" stroke="#6496E0" stroke-width="1.5" opacity="0.8"/>
          <!-- Rooms -->
          <rect x="40" y="40" width="100" height="90" fill="rgba(100,150,220,0.06)" stroke="#6496E0" stroke-width="1" opacity="0.7"/>
          <rect x="140" y="40" width="140" height="90" fill="rgba(100,150,220,0.04)" stroke="#6496E0" stroke-width="1" opacity="0.7"/>
          <rect x="40" y="130" width="80" height="90" fill="rgba(100,150,220,0.06)" stroke="#6496E0" stroke-width="1" opacity="0.7"/>
          <rect x="120" y="130" width="80" height="90" fill="rgba(100,150,220,0.04)" stroke="#6496E0" stroke-width="1" opacity="0.7"/>
          <rect x="200" y="130" width="80" height="90" fill="rgba(100,150,220,0.06)" stroke="#6496E0" stroke-width="1" opacity="0.7"/>
          <!-- Door arcs -->
          <path d="M 40 80 Q 60 80 60 60" fill="none" stroke="#C9A84C" stroke-width="0.8" stroke-dasharray="3,2"/>
          <path d="M 140 170 Q 140 190 160 190" fill="none" stroke="#C9A84C" stroke-width="0.8" stroke-dasharray="3,2"/>
          <!-- Dimension lines -->
          <line x1="40" y1="230" x2="280" y2="230" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <line x1="40" y1="225" x2="40" y2="235" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <line x1="280" y1="225" x2="280" y2="235" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <line x1="300" y1="40" x2="300" y2="220" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <line x1="295" y1="40" x2="305" y2="40" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <line x1="295" y1="220" x2="305" y2="220" stroke="#C9A84C" stroke-width="0.8" opacity="0.7"/>
          <!-- Labels -->
          <text x="83" y="90" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Living</text>
          <text x="83" y="100" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Room</text>
          <text x="210" y="85" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Master Bedroom</text>
          <text x="80" y="178" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Kitchen</text>
          <text x="160" y="178" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Bedroom 2</text>
          <text x="240" y="178" font-family="monospace" font-size="7" fill="#6496E0" opacity="0.8" text-anchor="middle">Bath</text>
          <text x="160" y="244" font-family="monospace" font-size="7" fill="#C9A84C" opacity="0.8" text-anchor="middle">12.0 m</text>
          <text x="312" y="135" font-family="monospace" font-size="7" fill="#C9A84C" opacity="0.8" text-anchor="middle" transform="rotate(90 312 135)">9.0 m</text>
          <!-- North arrow -->
          <line x1="20" y1="20" x2="20" y2="8" stroke="#C9A84C" stroke-width="1"/>
          <polygon points="20,5 17,13 23,13" fill="#C9A84C" opacity="0.9"/>
          <text x="20" y="28" font-family="monospace" font-size="7" fill="#C9A84C" opacity="0.8" text-anchor="middle">N</text>
        </svg>
        <div style="margin-top: 1.25rem; display: flex; gap: 1.5rem;">
          <div>
            <div style="font-size: 0.68rem; letter-spacing: 0.1em; text-transform: uppercase; color: #6496E0; opacity: 0.7; margin-bottom: 0.25rem;">Scale</div>
            <div style="font-size: 0.82rem; color: rgba(249,245,238,0.6); font-weight: 300;">1 : 100</div>
          </div>
          <div>
            <div style="font-size: 0.68rem; letter-spacing: 0.1em; text-transform: uppercase; color: #6496E0; opacity: 0.7; margin-bottom: 0.25rem;">Type</div>
            <div style="font-size: 0.82rem; color: rgba(249,245,238,0.6); font-weight: 300;">Floor Plan — G+2</div>
          </div>
          <div>
            <div style="font-size: 0.68rem; letter-spacing: 0.1em; text-transform: uppercase; color: #C9A84C; opacity: 0.8; margin-bottom: 0.25rem;">Status</div>
            <div style="font-size: 0.82rem; color: var(--gold); font-weight: 500;">Approved</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="projects-header">
    <div>
      <div class="section-tag">Our Portfolio</div>
      <h2 class="section-heading">Selected <em>Works</em></h2>
    </div>
    <a href="#contact" class="btn-ghost">Discuss Your Project</a>
  </div>
  <div class="projects-grid">
    <!-- Featured -->
    <div class="project-card featured">
      <div class="project-visual">
        <svg class="project-svg-scene" viewBox="0 0 700 400" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="700" height="400" fill="#1a2030"/>
          <!-- Sky gradient effect -->
          <rect width="700" height="200" fill="#1a2030"/>
          <!-- Building complex -->
          <rect x="80" y="80" width="180" height="320" fill="#252535" stroke="rgba(201,168,76,0.3)" stroke-width="0.8"/>
          <rect x="270" y="120" width="200" height="280" fill="#1e2030" stroke="rgba(201,168,76,0.25)" stroke-width="0.8"/>
          <rect x="480" y="60" width="140" height="340" fill="#252535" stroke="rgba(201,168,76,0.3)" stroke-width="0.8"/>
          <!-- Window rows -->
          <rect x="90" y="100" width="22" height="14" fill="rgba(201,168,76,0.18)" stroke="rgba(201,168,76,0.35)" stroke-width="0.4"/>
          <rect x="120" y="100" width="22" height="14" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="150" y="100" width="22" height="14" fill="rgba(201,168,76,0.22)" stroke="rgba(201,168,76,0.35)" stroke-width="0.4"/>
          <rect x="180" y="100" width="22" height="14" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="220" y="100" width="22" height="14" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="90" y="130" width="22" height="14" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="120" y="130" width="22" height="14" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.35)" stroke-width="0.4"/>
          <rect x="150" y="130" width="22" height="14" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="180" y="130" width="22" height="14" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <rect x="220" y="130" width="22" height="14" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.4"/>
          <!-- Gold band on featured building -->
          <rect x="80" y="80" width="180" height="6" fill="#C9A84C" opacity="0.9"/>
          <!-- Ground floor -->
          <rect x="80" y="370" width="540" height="30" fill="#111" opacity="0.9"/>
          <!-- Gold highlights -->
          <rect x="80" y="80" width="3" height="320" fill="#C9A84C" opacity="0.6"/>
          <rect x="480" y="60" width="3" height="340" fill="#C9A84C" opacity="0.4"/>
          <!-- Stars -->
          <circle cx="400" cy="30" r="1.2" fill="#C9A84C" opacity="0.7"/>
          <circle cx="450" cy="50" r="0.8" fill="#C9A84C" opacity="0.5"/>
          <circle cx="350" cy="20" r="1" fill="#C9A84C" opacity="0.6"/>
          <circle cx="30" cy="40" r="0.8" fill="#C9A84C" opacity="0.5"/>
          <circle cx="650" cy="25" r="1" fill="#C9A84C" opacity="0.4"/>
        </svg>
        <div class="project-overlay"></div>
        <div class="project-info">
          <div class="project-cat">Commercial Complex</div>
          <div class="project-name">Imphal Business Centre</div>
        </div>
      </div>
    </div>
    <!-- Project 2 -->
    <div class="project-card">
      <div class="project-visual">
        <svg class="project-svg-scene" viewBox="0 0 340 280" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="340" height="280" fill="#1c1a18"/>
          <!-- Residential home illustration -->
          <polygon points="50,120 170,50 290,120" fill="#1e2030" stroke="rgba(201,168,76,0.4)" stroke-width="1"/>
          <rect x="70" y="120" width="200" height="130" fill="#252525" stroke="rgba(201,168,76,0.3)" stroke-width="0.8"/>
          <!-- Chimney -->
          <rect x="135" y="70" width="20" height="50" fill="#1e1e2a" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <!-- Windows -->
          <rect x="90" y="140" width="40" height="40" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
          <line x1="110" y1="140" x2="110" y2="180" stroke="rgba(201,168,76,0.3)" stroke-width="0.5"/>
          <line x1="90" y1="160" x2="130" y2="160" stroke="rgba(201,168,76,0.3)" stroke-width="0.5"/>
          <rect x="210" y="140" width="40" height="40" fill="rgba(201,168,76,0.18)" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
          <line x1="230" y1="140" x2="230" y2="180" stroke="rgba(201,168,76,0.3)" stroke-width="0.5"/>
          <line x1="210" y1="160" x2="250" y2="160" stroke="rgba(201,168,76,0.3)" stroke-width="0.5"/>
          <!-- Door -->
          <rect x="148" y="195" width="44" height="55" fill="#1a1a1a" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
          <circle cx="185" cy="225" r="2.5" fill="#C9A84C" opacity="0.8"/>
          <!-- Ground -->
          <rect x="0" y="248" width="340" height="32" fill="#111" opacity="0.9"/>
          <!-- Gold roof accent -->
          <line x1="50" y1="120" x2="290" y2="120" stroke="#C9A84C" stroke-width="2" opacity="0.8"/>
        </svg>
        <div class="project-overlay"></div>
        <div class="project-info">
          <div class="project-cat">Residential</div>
          <div class="project-name">Luxury Villa, Lamphelpat</div>
        </div>
      </div>
    </div>
    <!-- Project 3 -->
    <div class="project-card">
      <div class="project-visual">
        <svg class="project-svg-scene" viewBox="0 0 340 280" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="340" height="280" fill="#1a1818"/>
          <!-- Interior / renovation illustration -->
          <!-- Room walls -->
          <rect x="30" y="40" width="280" height="210" fill="#1e1e1e"/>
          <!-- Floor perspective -->
          <polygon points="30,250 310,250 270,200 70,200" fill="#252520" stroke="rgba(201,168,76,0.15)" stroke-width="0.5"/>
          <!-- Back wall -->
          <rect x="70" y="40" width="200" height="160" fill="#2a2a28"/>
          <!-- Large window on back wall -->
          <rect x="100" y="55" width="140" height="100" fill="rgba(100,140,200,0.08)" stroke="rgba(201,168,76,0.5)" stroke-width="1.5"/>
          <line x1="170" y1="55" x2="170" y2="155" stroke="rgba(201,168,76,0.3)" stroke-width="1"/>
          <!-- Furniture silhouettes -->
          <rect x="85" y="200" width="80" height="10" fill="#333" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <rect x="175" y="200" width="80" height="10" fill="#333" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <rect x="110" y="175" width="120" height="26" fill="#2d2d2d" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <!-- Gold trim accent -->
          <rect x="70" y="195" width="200" height="2" fill="#C9A84C" opacity="0.5"/>
          <!-- Ceiling light -->
          <circle cx="170" cy="55" r="8" fill="rgba(201,168,76,0.15)" stroke="#C9A84C" stroke-width="0.8"/>
          <line x1="170" y1="40" x2="170" y2="47" stroke="#C9A84C" stroke-width="1" opacity="0.7"/>
          <!-- Light rays -->
          <line x1="170" y1="63" x2="120" y2="110" stroke="rgba(201,168,76,0.06)" stroke-width="8"/>
          <line x1="170" y1="63" x2="220" y2="110" stroke="rgba(201,168,76,0.06)" stroke-width="8"/>
          <!-- Baseboard -->
          <rect x="30" y="245" width="280" height="5" fill="#222" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
        </svg>
        <div class="project-overlay"></div>
        <div class="project-info">
          <div class="project-cat">Interior Design</div>
          <div class="project-name">Modern Office Interior</div>
        </div>
      </div>
    </div>
    <!-- Project 4 -->
    <div class="project-card">
      <div class="project-visual">
        <svg class="project-svg-scene" viewBox="0 0 340 280" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="340" height="280" fill="#181c1a"/>
          <!-- Apartment block -->
          <rect x="50" y="60" width="240" height="200" fill="#1e2018" stroke="rgba(201,168,76,0.25)" stroke-width="0.8"/>
          <!-- Balcony rows -->
          <rect x="50" y="100" width="240" height="8" fill="#252820" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <rect x="50" y="150" width="240" height="8" fill="#252820" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <rect x="50" y="200" width="240" height="8" fill="#252820" stroke="rgba(201,168,76,0.2)" stroke-width="0.5"/>
          <!-- Apartment windows -->
          <rect x="65" y="75" width="35" height="22" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.35)" stroke-width="0.6"/>
          <rect x="115" y="75" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="165" y="75" width="35" height="22" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.4)" stroke-width="0.6"/>
          <rect x="215" y="75" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="65" y="122" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="115" y="122" width="35" height="22" fill="rgba(201,168,76,0.18)" stroke="rgba(201,168,76,0.35)" stroke-width="0.6"/>
          <rect x="165" y="122" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="215" y="122" width="35" height="22" fill="rgba(201,168,76,0.12)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="65" y="172" width="35" height="22" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="115" y="172" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="165" y="172" width="35" height="22" fill="rgba(201,168,76,0.08)" stroke="rgba(201,168,76,0.3)" stroke-width="0.6"/>
          <rect x="215" y="172" width="35" height="22" fill="rgba(201,168,76,0.2)" stroke="rgba(201,168,76,0.35)" stroke-width="0.6"/>
          <!-- Gold roof -->
          <rect x="50" y="60" width="240" height="5" fill="#C9A84C" opacity="0.9"/>
          <!-- Entrance -->
          <rect x="138" y="222" width="64" height="38" fill="#111" stroke="rgba(201,168,76,0.4)" stroke-width="0.8"/>
          <!-- Ground -->
          <rect x="0" y="258" width="340" height="22" fill="#111" opacity="0.9"/>
        </svg>
        <div class="project-overlay"></div>
        <div class="project-info">
          <div class="project-cat">Multi-Family</div>
          <div class="project-name">Anandi Heights, Porompat</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="section-tag">How We Work</div>
  <h2 class="section-heading">From Concept to <em>Completion</em></h2>
  <div class="process-steps">
    <div class="process-step">
      <div class="step-number">01</div>
      <div class="step-title">Discovery & Consultation</div>
      <p class="step-desc">We begin with a deep conversation about your goals, site conditions, budget, and timeline. No obligation — just clarity.</p>
    </div>
    <div class="process-step">
      <div class="step-number">02</div>
      <div class="step-title">Design & Planning</div>
      <p class="step-desc">Our architects and designers produce detailed floor plans, 3D renders, and cost estimates for your approval before a single brick is laid.</p>
    </div>
    <div class="process-step">
      <div class="step-number">03</div>
      <div class="step-title">Construction</div>
      <p class="step-desc">Skilled teams execute with precision. You receive weekly progress updates, site access, and a dedicated project manager throughout.</p>
    </div>
    <div class="process-step">
      <div class="step-number">04</div>
      <div class="step-title">Handover & Support</div>
      <p class="step-desc">We walk you through every corner of your new space, provide all documentation, and remain available for post-completion support.</p>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials">
  <div class="section-tag">Client Voices</div>
  <h2 class="section-heading">Built on <em>Trust</em></h2>
  <div class="testimonials-grid">
    <div class="testimonial-card">
      <p class="testimonial-text">Anandi Lifestyle Solutions transformed our vision into a home we are genuinely proud of. From the first meeting to handing over the keys, they were professional, transparent, and meticulous in every detail.</p>
      <div class="testimonial-author">
        <div class="author-avatar">RS</div>
        <div>
          <div class="author-name">Ranjit Singh</div>
          <div class="author-role">Homeowner, Imphal West</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <p class="testimonial-text">We contracted Anandi for our commercial office build and they delivered two weeks ahead of schedule. Their project management is exceptional — we always knew exactly where things stood.</p>
      <div class="testimonial-author">
        <div class="author-avatar">PD</div>
        <div>
          <div class="author-name">Priya Devi</div>
          <div class="author-role">Director, Northeast Ventures</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <p class="testimonial-text">The interior design team at Anandi understood exactly what we wanted — a space that felt warm yet modern. The craftsmanship is on another level. We have already recommended them to three friends.</p>
      <div class="testimonial-author">
        <div class="author-avatar">TL</div>
        <div>
          <div class="author-name">Thomas Laishram</div>
          <div class="author-role">Restaurateur, Imphal</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA BAND -->
<div id="cta-band">
  <div class="cta-band-inner">
    <div class="cta-band-text">Ready to Build Something That Lasts?</div>
    <a href="#contact" class="btn-dark">Start Your Project Today</a>
  </div>
</div>

<!-- CONTACT -->
<section id="contact">
  <div class="section-tag">Get in Touch</div>
  <h2 class="section-heading">Let's <em>Build Together</em></h2>
  <div class="contact-grid">
    <div class="contact-info">
      <div class="contact-item">
        <div class="contact-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z" stroke="#C9A84C" fill="none" stroke-width="1.5"/></svg>
        </div>
        <div>
          <div class="contact-label">Office Location</div>
          <div class="contact-value">Imphal, Manipur, India — 795001</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z" stroke="#C9A84C" fill="none" stroke-width="1.5"/></svg>
        </div>
        <div>
          <div class="contact-label">Phone</div>
          <div class="contact-value">+91 98765 43210</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z" stroke="#C9A84C" fill="none" stroke-width="1.5"/></svg>
        </div>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">hello@anandilifestylesolutions.com</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="10" stroke="#C9A84C" stroke-width="1.5" fill="none"/><polyline points="12 6 12 12 16 14" stroke="#C9A84C" stroke-width="1.5" fill="none"/></svg>
        </div>
        <div>
          <div class="contact-label">Working Hours</div>
          <div class="contact-value">Mon – Sat, 9:00 AM – 6:00 PM</div>
        </div>
      </div>
      <!-- Website domain -->
      <div style="margin-top: 1rem; padding: 1.25rem; border: 1px solid rgba(201,168,76,0.2); background: rgba(201,168,76,0.04);">
        <div class="contact-label" style="margin-bottom: 0.4rem;">Website</div>
        <div style="color: var(--gold); font-size: 0.88rem; font-weight: 400;">hello-anandilifestylesolutions.com</div>
      </div>
    </div>

    <div>
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <div class="form-group">
            <label for="name">Full Name</label>
            <input type="text" id="name" placeholder="Your name" required>
          </div>
          <div class="form-group">
            <label for="phone">Phone Number</label>
            <input type="tel" id="phone" placeholder="+91 XXXXX XXXXX">
          </div>
        </div>
        <div class="form-group">
          <label for="email">Email Address</label>
          <input type="email" id="email" placeholder="your@email.com" required>
        </div>
        <div class="form-group">
          <label for="service">Service Required</label>
          <select id="service">
            <option value="">Select a service...</option>
            <option>Residential Construction</option>
            <option>Commercial Project</option>
            <option>Interior Design</option>
            <option>Renovation & Remodeling</option>
            <option>Project Management</option>
            <option>Turnkey Solution</option>
            <option>Other</option>
          </select>
        </div>
        <div class="form-group">
          <label for="budget">Approximate Budget</label>
          <select id="budget">
            <option value="">Select range...</option>
            <option>Under ₹10 Lakhs</option>
            <option>₹10 – 25 Lakhs</option>
            <option>₹25 – 50 Lakhs</option>
            <option>₹50 Lakhs – 1 Crore</option>
            <option>Above ₹1 Crore</option>
          </select>
        </div>
        <div class="form-group">
          <label for="message">Tell Us About Your Project</label>
          <textarea id="message" placeholder="Describe your project, timeline, location, and any specific requirements..."></textarea>
        </div>
        <button type="submit" class="btn-submit">Send Enquiry</button>
        <div class="form-success" id="formSuccess">
          ✓ Thank you! We will get back to you within 24 hours.
        </div>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div>
      <div class="footer-brand">Anandi Lifestyle Solutions</div>
      <div style="font-size: 0.72rem; letter-spacing: 0.12em; text-transform: uppercase; color: rgba(201,168,76,0.5);">Construction & Design</div>
      <p class="footer-tagline">Building homes, spaces, and landmarks that define how Manipur lives, works, and grows — one project at a time.</p>
    </div>
    <div>
      <div class="footer-col-title">Services</div>
      <ul class="footer-col-links">
        <li><a href="#services">Residential Construction</a></li>
        <li><a href="#services">Commercial Projects</a></li>
        <li><a href="#services">Interior Design</a></li>
        <li><a href="#services">Renovation & Remodeling</a></li>
        <li><a href="#services">Turnkey Solutions</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Company</div>
      <ul class="footer-col-links">
        <li><a href="#why">About Us</a></li>
        <li><a href="#projects">Portfolio</a></li>
        <li><a href="#process">Our Process</a></li>
        <li><a href="#testimonials">Testimonials</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Contact</div>
      <ul class="footer-col-links">
        <li><a href="tel:+919876543210">+91 98765 43210</a></li>
        <li><a href="mailto:hello@anandilifestylesolutions.com">hello@<br>anandilifestylesolutions.com</a></li>
        <li><a href="#">Imphal, Manipur — 795001</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2025 Anandi Lifestyle Solutions. All rights reserved.</div>
    <div class="footer-website">hello-anandilifestylesolutions.com</div>
  </div>
</footer>

<script>
  function toggleMobileNav() {
    const nav = document.getElementById('mobileNav');
    nav.classList.toggle('open');
  }
  function closeMobileNav() {
    document.getElementById('mobileNav').classList.remove('open');
  }

  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.btn-submit');
    const success = document.getElementById('formSuccess');
    btn.textContent = 'Sending...';
    btn.disabled = true;
    setTimeout(() => {
      btn.style.display = 'none';
      success.style.display = 'block';
      e.target.reset();
    }, 1200);
  }

  // Smooth nav bg on scroll
  window.addEventListener('scroll', () => {
    const nav = document.querySelector('nav');
    if (window.scrollY > 60) {
      nav.style.background = 'rgba(26,26,26,0.98)';
    } else {
      nav.style.background = 'rgba(26,26,26,0.92)';
    }
  });

  // Animate sections into view
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(el => {
      if (el.isIntersecting) {
        el.target.style.opacity = '1';
        el.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.service-card, .why-item, .process-step, .testimonial-card, .project-card').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = 'opacity 0.55s ease, transform 0.55s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
