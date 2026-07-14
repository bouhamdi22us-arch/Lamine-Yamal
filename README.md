<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Lamine Yamal — Extremo del FC Barcelona y la selección española. Talento, regate y nueva era." />
  <title>YAMAL — Lamine Yamal</title>
  <link href="https://db.onlinewebfonts.com/c/8b75d9dcff6a48c35a46656192adf019?family=FSP+DEMO+-+PODIUM+Sharp+4.11" rel="stylesheet" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --yamal-red: #A50044;
      --yamal-blue: #004D98;
      --yamal-gold: #EDBB00;
      --yamal-deep: #070B14;
      --yamal-night: #0B1220;
      --font-podium: "FSP DEMO - PODIUM Sharp 4.11", sans-serif;
      --font-inter: "Inter", system-ui, sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: var(--font-inter);
      background: var(--yamal-deep);
      color: #fff;
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }
    body.menu-open { overflow: hidden; }
    img, video { display: block; max-width: 100%; }
    a { color: inherit; text-decoration: none; }
    button { font-family: inherit; border: none; background: none; cursor: pointer; color: inherit; }

    .font-podium { font-family: var(--font-podium); }

    /* Animations */
    @keyframes fade-up {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes yamal-aura {
      0%, 100% { opacity: 0.35; transform: scale(1); }
      50% { opacity: 0.75; transform: scale(1.08); }
    }
    @keyframes yamal-dribble {
      0% { transform: translate(-18%, 10%) rotate(-2deg); }
      50% { transform: translate(18%, -8%) rotate(2deg); }
      100% { transform: translate(-18%, 10%) rotate(-2deg); }
    }
    @keyframes yamal-sprint {
      0% { transform: translateX(-130%) skewX(-14deg); opacity: 0; }
      25% { opacity: 0.85; }
      100% { transform: translateX(230%) skewX(-14deg); opacity: 0; }
    }
    @keyframes yamal-glow {
      0%, 100% { text-shadow: 0 0 0 transparent; filter: brightness(1); }
      50% { text-shadow: 0 0 26px rgba(165,0,68,0.65), 0 0 48px rgba(0,77,152,0.35); filter: brightness(1.08); }
    }
    @keyframes yamal-shine {
      0% { transform: translateX(-120%) skewX(-18deg); }
      100% { transform: translateX(220%) skewX(-18deg); }
    }

    .animate-fade-up { opacity: 0; animation: fade-up 0.8s ease-out forwards; }
    .animate-fade-up-delay-1 { opacity: 0; animation: fade-up 0.8s ease-out 0.2s forwards; }
    .animate-fade-up-delay-2 { opacity: 0; animation: fade-up 0.8s ease-out 0.4s forwards; }
    .animate-fade-up-delay-3 { opacity: 0; animation: fade-up 0.8s ease-out 0.6s forwards; }
    .animate-fade-up-delay-4 { opacity: 0; animation: fade-up 0.8s ease-out 0.8s forwards; }
    .animate-yamal-aura { animation: yamal-aura 3.4s ease-in-out infinite; }
    .animate-yamal-dribble { animation: yamal-dribble 6.5s ease-in-out infinite; }
    .animate-yamal-sprint { animation: yamal-sprint 3.2s ease-in-out infinite; }
    .animate-yamal-glow { animation: yamal-glow 2.8s ease-in-out infinite; }
    .animate-yamal-shine { animation: yamal-shine 2.8s ease-in-out infinite; }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.8s ease-out, transform 0.8s ease-out;
    }
    .reveal.in { opacity: 1; transform: translateY(0); }

    /* HERO */
    .hero {
      position: relative;
      height: 100vh;
      height: 100dvh;
      width: 100%;
      overflow: hidden;
    }
    .hero-video {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .hero-grad-1 {
      position: absolute;
      inset: 0;
      background: linear-gradient(to right, rgba(7,11,20,0.95), rgba(0,77,152,0.45), rgba(165,0,68,0.35));
    }
    .hero-grad-2 {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, var(--yamal-deep), transparent, rgba(0,0,0,0.5));
    }
    .fx { position: absolute; inset: 0; overflow: hidden; pointer-events: none; }
    .fx-red {
      position: absolute;
      left: -4rem;
      top: 25%;
      width: 18rem;
      height: 18rem;
      border-radius: 999px;
      background: rgba(165,0,68,0.25);
      filter: blur(64px);
    }
    .fx-blue {
      position: absolute;
      right: -2.5rem;
      top: 33%;
      width: 20rem;
      height: 20rem;
      border-radius: 999px;
      background: rgba(0,77,152,0.3);
      filter: blur(64px);
    }
    .fx-line {
      position: absolute;
      top: 46%;
      height: 2px;
      width: 33%;
      background: linear-gradient(to right, transparent, var(--yamal-gold), transparent);
    }
    .fx-line-2 {
      position: absolute;
      top: 54%;
      height: 1px;
      width: 25%;
      background: linear-gradient(to right, transparent, rgba(255,255,255,0.5), transparent);
      animation-delay: 1.1s;
    }

    /* NAV */
    .nav {
      position: relative;
      z-index: 40;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.25rem 1.5rem;
    }
    @media (min-width: 640px) { .nav { padding-left: 2.5rem; padding-right: 2.5rem; } }
    @media (min-width: 1024px) { .nav { padding: 1.75rem 4rem; } }

    .logo {
      font-family: var(--font-podium);
      font-size: 1.5rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: #fff;
    }
    @media (min-width: 640px) { .logo { font-size: 1.875rem; } }

    .nav-links { display: none; align-items: center; gap: 2rem; }
    @media (min-width: 768px) { .nav-links { display: flex; } }
    @media (min-width: 1024px) { .nav-links { gap: 2.5rem; } }
    .nav-links a {
      font-size: 0.875rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.8);
      transition: color 0.2s;
    }
    .nav-links a:hover { color: #fff; }

    .btn-outline {
      display: none;
      align-items: center;
      gap: 0.5rem;
      border: 1px solid rgba(255,255,255,0.3);
      padding: 0.75rem 1.5rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: #fff;
      transition: all 0.2s;
    }
    .btn-outline:hover {
      border-color: rgba(255,255,255,0.6);
      background: rgba(255,255,255,0.1);
    }
    @media (min-width: 768px) { .btn-outline.desktop { display: inline-flex; } }

    .hamburger {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 0.375rem;
    }
    @media (min-width: 768px) { .hamburger { display: none; } }
    .hamburger span {
      display: block;
      height: 2px;
      background: #fff;
    }
    .hamburger span:nth-child(1),
    .hamburger span:nth-child(2) { width: 1.5rem; }
    .hamburger span:nth-child(3) { width: 1rem; }

    /* MOBILE MENU */
    .overlay {
      position: fixed;
      inset: 0;
      z-index: 50;
      background: rgba(7,11,20,0.95);
      backdrop-filter: blur(8px);
      transition: all 0.5s;
      opacity: 0;
      visibility: hidden;
    }
    .overlay.open { opacity: 1; visibility: visible; }
    .overlay-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.25rem 1.5rem;
    }
    @media (min-width: 640px) {
      .overlay-header { padding-left: 2.5rem; padding-right: 2.5rem; }
    }
    .overlay-body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 1.5rem;
      height: calc(100% - 5rem);
      padding: 0 1.5rem;
    }
    .overlay-body a.menu-link {
      font-family: var(--font-podium);
      font-size: 2.25rem;
      text-transform: uppercase;
      color: #fff;
      transition: all 0.5s;
      opacity: 0;
      transform: translateY(20px);
    }
    @media (min-width: 640px) { .overlay-body a.menu-link { font-size: 3rem; } }
    .overlay.open .overlay-body a.menu-link {
      opacity: 1;
      transform: translateY(0);
    }
    .overlay-cta {
      margin-top: 1rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      border: 1px solid rgba(255,255,255,0.3);
      padding: 0.75rem 1.5rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      transition: all 0.5s;
      opacity: 0;
      transform: translateY(20px);
    }
    .overlay.open .overlay-cta {
      opacity: 1;
      transform: translateY(0);
    }

    /* HERO CONTENT */
    .hero-main {
      position: relative;
      z-index: 10;
      display: flex;
      align-items: center;
      height: calc(100% - 5.5rem);
      padding: 0 1.5rem;
    }
    @media (min-width: 640px) { .hero-main { padding: 0 2.5rem; } }
    @media (min-width: 1024px) { .hero-main { padding: 0 4rem; } }
    .hero-inner { width: 100%; max-width: 64rem; }

    .tagline {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      margin-bottom: 1.5rem;
    }
    @media (min-width: 1024px) { .tagline { margin-bottom: 2rem; } }
    .tagline p {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.3em;
      color: rgba(255,255,255,0.7);
    }
    @media (min-width: 640px) { .tagline p { font-size: 0.875rem; } }

    .hero h1 {
      font-family: var(--font-podium);
      font-size: clamp(2.8rem, 8vw, 7rem);
      text-transform: uppercase;
      line-height: 0.92;
      letter-spacing: -0.02em;
      color: #fff;
    }
    .hero h1 .red { color: var(--yamal-red); }

    .hero-sub {
      margin-top: 1.5rem;
      max-width: 28rem;
      font-size: 0.875rem;
      line-height: 1.625;
      color: rgba(255,255,255,0.7);
    }
    @media (min-width: 640px) { .hero-sub { font-size: 1rem; } }
    @media (min-width: 1024px) { .hero-sub { margin-top: 2rem; } }
    .hero-sub strong { color: #fff; font-weight: 700; }

    .cta-row {
      margin-top: 2rem;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 1rem;
    }
    @media (min-width: 640px) { .cta-row { gap: 1.5rem; } }
    @media (min-width: 1024px) { .cta-row { margin-top: 2.5rem; } }

    .btn-red {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--yamal-red);
      padding: 0.75rem 1.25rem;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: #fff;
      transition: background 0.2s;
    }
    @media (min-width: 640px) {
      .btn-red { padding: 1rem 1.75rem; font-size: 0.75rem; }
    }
    .btn-red:hover { background: #8a0039; }
    .btn-red svg { transition: transform 0.2s; }
    .btn-red:hover svg { transform: translate(2px, -2px); }

    .award-badge {
      display: none;
      align-items: center;
      gap: 0.75rem;
    }
    @media (min-width: 640px) { .award-badge { display: flex; } }
    .award-badge span {
      display: block;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: rgba(255,255,255,0.6);
    }

    .stats-row {
      margin-top: 2rem;
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
    }
    @media (min-width: 640px) { .stats-row { margin-top: 2.5rem; gap: 3rem; } }
    @media (min-width: 1024px) { .stats-row { margin-top: 3.5rem; gap: 4rem; } }
    .stat-value {
      font-size: 1.5rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #fff;
    }
    @media (min-width: 640px) { .stat-value { font-size: 2.25rem; } }
    @media (min-width: 1024px) { .stat-value { font-size: 3rem; } }
    .stat-label {
      margin-top: 0.25rem;
      font-size: 9px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.5);
    }
    @media (min-width: 640px) { .stat-label { font-size: 0.75rem; } }

    /* SECTIONS */
    .section {
      position: relative;
      border-top: 1px solid rgba(255,255,255,0.1);
      padding: 6rem 1.5rem;
    }
    @media (min-width: 640px) { .section { padding-left: 2.5rem; padding-right: 2.5rem; } }
    @media (min-width: 1024px) {
      .section { padding: 8rem 4rem; }
    }
    .wrap { max-width: 72rem; margin: 0 auto; }

    .label {
      margin-bottom: 1rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.3em;
      color: rgba(255,255,255,0.5);
    }
    .section h2 {
      font-family: var(--font-podium);
      font-size: clamp(2rem, 5vw, 4rem);
      text-transform: uppercase;
      line-height: 0.95;
      letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
      max-width: 48rem;
    }
    .section h2 .red { color: var(--yamal-red); }
    .lead {
      max-width: 36rem;
      font-size: 0.875rem;
      line-height: 1.65;
      color: rgba(255,255,255,0.65);
      margin-bottom: 3rem;
    }
    @media (min-width: 640px) { .lead { font-size: 1rem; } }

    .grid-2 {
      display: grid;
      gap: 1.25rem;
    }
    @media (min-width: 768px) { .grid-2 { grid-template-columns: 1fr 1fr; } }

    .photo-block {
      position: relative;
      aspect-ratio: 16/11;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.1);
    }
    .photo-block img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.7s;
    }
    .photo-block:hover img { transform: scale(1.05); }
    .photo-block .shade {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, var(--yamal-deep), transparent);
    }
    .photo-block .shine {
      position: absolute;
      inset: 0 auto 0 0;
      width: 33%;
      background: linear-gradient(to right, transparent, rgba(255,255,255,0.1), transparent);
      opacity: 0.4;
    }
    .photo-block .cap {
      position: absolute;
      bottom: 1rem;
      left: 1rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.8);
    }

    .card {
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(255,255,255,0.03);
      padding: 1.5rem;
      height: 100%;
      transition: border-color 0.2s, background 0.2s;
    }
    @media (min-width: 640px) { .card { padding: 2rem; } }
    .card:hover {
      border-color: rgba(165,0,68,0.4);
      background: rgba(255,255,255,0.05);
    }
    .card-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 1.25rem;
    }
    .card-tag {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.45);
    }
    .card h3 {
      font-family: var(--font-podium);
      font-size: 1.875rem;
      text-transform: uppercase;
      letter-spacing: -0.02em;
      margin-bottom: 0.75rem;
    }
    .card p {
      font-size: 0.875rem;
      line-height: 1.6;
      color: rgba(255,255,255,0.6);
    }

    .section-night { background: var(--yamal-night); }
    .sprint-line {
      position: absolute;
      left: 50%;
      top: 0;
      height: 1px;
      width: 66%;
      transform: translateX(-50%);
      background: linear-gradient(to right, transparent, var(--yamal-red), transparent);
      pointer-events: none;
    }

    .split {
      display: grid;
      gap: 3rem;
      align-items: start;
    }
    @media (min-width: 1024px) {
      .split { grid-template-columns: 1fr 1fr; gap: 4rem; }
    }

    .tags { display: flex; flex-wrap: wrap; gap: 0.75rem; }
    .tag {
      border: 1px solid rgba(0,77,152,0.4);
      background: rgba(0,77,152,0.1);
      padding: 0.5rem 1rem;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.8);
    }

    .trait {
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(0,0,0,0.3);
      padding: 1.25rem;
      height: 100%;
    }
    .trait .shine {
      position: absolute;
      inset: 0 auto 0 0;
      width: 50%;
      background: linear-gradient(to right, transparent, rgba(165,0,68,0.1), transparent);
      opacity: 0.5;
    }
    .trait-inner { position: relative; }
    .trait h3 {
      font-family: var(--font-podium);
      font-size: 1.25rem;
      text-transform: uppercase;
      letter-spacing: -0.02em;
      margin-bottom: 0.75rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    .trait p {
      font-size: 0.875rem;
      line-height: 1.6;
      color: rgba(255,255,255,0.6);
    }

    .gallery {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0.75rem;
    }
    @media (min-width: 768px) {
      .gallery {
        grid-template-columns: repeat(4, 1fr);
        gap: 1rem;
      }
    }
    .gallery .span-2 { grid-column: span 2; }
    .g-item {
      position: relative;
      aspect-ratio: 4/3;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.1);
    }
    .g-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.7s;
    }
    .g-item:hover img { transform: scale(1.05); }
    .g-item .shade {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(7,11,20,0.9), transparent);
    }
    .g-item figcaption {
      position: absolute;
      bottom: 0.75rem;
      left: 0.75rem;
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.8);
    }
    @media (min-width: 640px) { .g-item figcaption { font-size: 0.75rem; } }

    .section-gradient {
      background: linear-gradient(to bottom, var(--yamal-deep), var(--yamal-night), var(--yamal-deep));
    }
    .stat-grid {
      display: grid;
      gap: 1rem;
    }
    @media (min-width: 640px) { .stat-grid { grid-template-columns: 1fr 1fr; } }
    @media (min-width: 1024px) { .stat-grid { grid-template-columns: repeat(4, 1fr); } }
    .stat-card {
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(255,255,255,0.03);
      padding: 1.5rem;
      text-align: center;
      transition: border-color 0.2s;
    }
    .stat-card:hover { border-color: rgba(165,0,68,0.5); }
    .stat-card .v {
      font-family: var(--font-podium);
      font-size: 2.25rem;
      text-transform: uppercase;
      letter-spacing: -0.02em;
      margin: 1rem 0 0.5rem;
    }
    @media (min-width: 640px) { .stat-card .v { font-size: 3rem; } }
    .stat-card .l {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.5);
    }

    .info-band {
      margin-top: 2.5rem;
      display: grid;
      gap: 1rem;
      border: 1px solid rgba(255,255,255,0.1);
      background: linear-gradient(to right, rgba(0,77,152,0.25), var(--yamal-deep), rgba(165,0,68,0.25));
      padding: 1.5rem;
    }
    @media (min-width: 640px) {
      .info-band {
        grid-template-columns: repeat(3, 1fr);
        padding: 2rem;
      }
    }
    .info-band .k {
      margin-bottom: 0.25rem;
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.45);
    }
    .info-band .v {
      font-size: 1.125rem;
      font-weight: 600;
      letter-spacing: -0.02em;
    }

    .cta-block {
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.1);
    }
    .cta-block > img {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      opacity: 0.35;
    }
    .cta-block .overlay-grad {
      position: absolute;
      inset: 0;
      background: linear-gradient(to right, var(--yamal-deep), rgba(7,11,20,0.9), rgba(165,0,68,0.3));
    }
    .cta-content {
      position: relative;
      padding: 2rem;
    }
    @media (min-width: 640px) { .cta-content { padding: 3rem; } }
    @media (min-width: 1024px) { .cta-content { padding: 4rem; } }
    .cta-content h2 {
      font-size: clamp(2.2rem, 6vw, 4.5rem);
      max-width: 48rem;
    }
    .cta-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 2.5rem;
    }
    .btn-white {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: #fff;
      color: var(--yamal-deep);
      padding: 1rem 1.5rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      transition: background 0.2s;
    }
    .btn-white:hover { background: #e5e5e5; }
    .btn-white svg { transition: transform 0.2s; }
    .btn-white:hover svg { transform: translate(2px, -2px); }

    .site-footer {
      border-top: 1px solid rgba(255,255,255,0.1);
      padding: 3rem 1.5rem;
    }
    @media (min-width: 640px) { .site-footer { padding-left: 2.5rem; padding-right: 2.5rem; } }
    @media (min-width: 1024px) { .site-footer { padding-left: 4rem; padding-right: 4rem; } }
    .footer-inner {
      max-width: 72rem;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }
    @media (min-width: 768px) {
      .footer-inner {
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
      }
    }
    .footer-brand {
      font-family: var(--font-podium);
      font-size: 1.5rem;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }
    .footer-sub {
      margin-top: 0.25rem;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.4);
    }
    .footer-links {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem 1.5rem;
    }
    .footer-links a {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.5);
      transition: color 0.2s;
    }
    .footer-links a:hover { color: #fff; }
    .footer-copy {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: rgba(255,255,255,0.35);
    }

    .icon { width: 1rem; height: 1rem; flex-shrink: 0; }
    .icon-sm { width: 1.25rem; height: 1.25rem; }
    .icon-md { width: 1.5rem; height: 1.5rem; }
    .icon-lg { width: 2rem; height: 2rem; }
    .icon-gold { color: var(--yamal-gold); }
    .icon-red { color: var(--yamal-red); }
    .icon-muted { color: rgba(255,255,255,0.5); }
    .mb-10 { margin-bottom: 2.5rem; }
    .mb-12 { margin-bottom: 3rem; }
    .mt-4 { margin-top: 1rem; }
    .text-center { text-align: center; }
    .mx-auto { margin-left: auto; margin-right: auto; }
  </style>
</head>
<body>
  <!-- HERO -->
  <section class="hero" id="inicio">
    <video class="hero-video" src="https://d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/hf_20260606_154941_df1a96e1-a06f-450c-bd02-d863414cc1a0.mp4" autoplay muted loop playsinline></video>
    <div class="hero-grad-1"></div>
    <div class="hero-grad-2"></div>
    <div class="fx">
      <div class="fx-red animate-yamal-aura"></div>
      <div class="fx-blue animate-yamal-dribble"></div>
      <div class="fx-line animate-yamal-sprint"></div>
      <div class="fx-line-2 animate-yamal-sprint"></div>
    </div>

    <header class="nav">
      <a href="#inicio" class="logo" id="logo">YAMAL</a>
      <nav class="nav-links">
        <a href="#historia">Historia</a>
        <a href="#estilo">Estilo</a>
        <a href="#galeria">Galería</a>
        <a href="#cifras">Cifras</a>
        <a href="#legado">Legado</a>
      </nav>
      <a href="#legado" class="btn-outline desktop">
        VER LEGADO
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
      </a>
      <button type="button" class="hamburger" id="menu-btn" aria-label="Abrir menú" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </header>

    <div class="overlay" id="menu" aria-hidden="true">
      <div class="overlay-header">
        <span class="logo">YAMAL</span>
        <button type="button" id="close-btn" aria-label="Cerrar menú">
          <svg class="icon-lg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
        </button>
      </div>
      <div class="overlay-body">
        <a href="#historia" class="menu-link" data-nav style="transition-delay:100ms">Historia</a>
        <a href="#estilo" class="menu-link" data-nav style="transition-delay:180ms">Estilo</a>
        <a href="#galeria" class="menu-link" data-nav style="transition-delay:260ms">Galería</a>
        <a href="#cifras" class="menu-link" data-nav style="transition-delay:340ms">Cifras</a>
        <a href="#legado" class="menu-link" data-nav style="transition-delay:420ms">Legado</a>
        <a href="#legado" class="overlay-cta" data-nav style="transition-delay:500ms">
          VER LEGADO
          <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
        </a>
      </div>
    </div>

    <main class="hero-main">
      <div class="hero-inner">
        <div class="tagline animate-fade-up">
          <svg class="icon icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M11.562 3.266a.5.5 0 01.876 0L15.39 8.87a1 1 0 00.9.565h5.048a.5.5 0 01.294.904l-4.084 3.51a1 1 0 00-.364 1.118l1.518 5.274a.5.5 0 01-.772.56l-4.316-3.16a1 1 0 00-1.128 0l-4.316 3.16a.5.5 0 01-.772-.56l1.518-5.274a1 1 0 00-.364-1.118L2.37 10.34a.5.5 0 01.294-.904h5.048a1 1 0 00.9-.565l2.95-5.605z"/></svg>
          <p>Nueva era del fútbol mundial</p>
        </div>

        <h1 class="animate-fade-up-delay-1">
          <span style="display:block">Dribble.</span>
          <span style="display:block">Decide.</span>
          <span class="red" style="display:block">Dominate.</span>
        </h1>

        <p class="hero-sub animate-fade-up-delay-2">
          Lamine Yamal no espera el futuro —<br />
          <strong>lo acelera en cada jugada.</strong>
        </p>

        <div class="cta-row animate-fade-up-delay-3">
          <a href="#historia" class="btn-red">
            DESCUBRIR YAMAL
            <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
          </a>
          <div class="award-badge">
            <svg class="icon-lg" style="color:rgba(237,187,0,0.8)" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="8" r="6"/><path d="M15.477 12.89L17 22l-5-3-5 3 1.523-9.11"/></svg>
            <div>
              <span>Generación</span>
              <span>De élite</span>
            </div>
          </div>
        </div>

        <div class="stats-row animate-fade-up-delay-4">
          <div>
            <p class="stat-value animate-yamal-glow">19</p>
            <p class="stat-label">Dorsal icónico</p>
          </div>
          <div>
            <p class="stat-value animate-yamal-glow">2007</p>
            <p class="stat-label">Nacimiento</p>
          </div>
          <div>
            <p class="stat-value animate-yamal-glow">FCB</p>
            <p class="stat-label">FC Barcelona</p>
          </div>
        </div>
      </div>
    </main>
  </section>

  <!-- HISTORIA -->
  <section class="section" id="historia">
    <div class="fx" style="position:absolute;right:0;top:6rem;width:18rem;height:18rem;pointer-events:none">
      <div class="fx-blue animate-yamal-aura" style="right:0;top:0;opacity:0.5"></div>
    </div>
    <div class="wrap">
      <div class="reveal">
        <p class="label">01 — Historia</p>
        <h2>De La Masia<br /><span class="red">al planeta</span></h2>
        <p class="lead">
          Nacido en 2007, Lamine Yamal resume el fútbol moderno: cantera, personalidad
          y desborde. Un extremo que creció con exigencia azulgrana y que ya marca
          época con club y selección.
        </p>
      </div>

      <div class="grid-2 mb-10">
        <div class="photo-block reveal">
          <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=1600&q=80" alt="Estadio de fútbol" loading="lazy" />
          <div class="shade"></div>
          <div class="shine animate-yamal-shine"></div>
          <p class="cap">Grandes noches</p>
        </div>
        <div class="photo-block reveal">
          <img src="https://images.unsplash.com/photo-1574629810360-7efbbe195018?auto=format&fit=crop&w=1600&q=80" alt="Fútbol en el césped" loading="lazy" />
          <div class="shade"></div>
          <p class="cap">Talento en acción</p>
        </div>
      </div>

      <div class="grid-2">
        <article class="card reveal">
          <div class="card-top">
            <span class="card-tag">Origen</span>
            <svg class="icon-sm icon-red" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9.937 15.5A2 2 0 008.5 14.063l-6.135-1.582a.5.5 0 010-.962L8.5 9.936A2 2 0 009.937 8.5l1.582-6.135a.5.5 0 01.963 0L14.063 8.5A2 2 0 0015.5 9.937l6.135 1.581a.5.5 0 010 .964L15.5 14.063a2 2 0 00-1.437 1.437l-1.582 6.135a.5.5 0 01-.963 0z"/></svg>
          </div>
          <h3>La Masia</h3>
          <p>Crianza de cantera, ritmo de calle y exigencia de élite. Ahí se forjó el desparpajo que hoy define a Yamal.</p>
        </article>
        <article class="card reveal">
          <div class="card-top">
            <span class="card-tag">Club</span>
            <svg class="icon-sm icon-red" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.38 3.46L16 2a4 4 0 01-8 0L3.62 3.46a2 2 0 00-1.34 2.23l.58 3.48a1 1 0 00.99.83H6v10c0 1.1.9 2 2 2h8a2 2 0 002-2V10h2.15a1 1 0 00.99-.83l.58-3.48a2 2 0 00-1.34-2.23z"/></svg>
          </div>
          <h3>Barcelona</h3>
          <p>Extremo asociativo y vertical. Fija marcas, recorta y deja al equipo jugando a su favor en cada duelo de banda.</p>
        </article>
        <article class="card reveal">
          <div class="card-top">
            <span class="card-tag">Selección</span>
            <svg class="icon-sm icon-red" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 010-5H6M18 9h1.5a2.5 2.5 0 000-5H18M4 22h16M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22M18 2H6v7a6 6 0 0012 0V2z"/></svg>
          </div>
          <h3>España</h3>
          <p>Con la Roja demostró madurez precoz: personalidad, lectura táctica y calidad en la gran escena.</p>
        </article>
        <article class="card reveal">
          <div class="card-top">
            <span class="card-tag">Firma</span>
            <svg class="icon-sm icon-red" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
          </div>
          <h3>1 contra 1</h3>
          <p>Cambio de ritmo, control orientado y decisión final. El espectáculo al servicio del partido.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- ESTILO -->
  <section class="section section-night" id="estilo">
    <div class="sprint-line animate-yamal-sprint"></div>
    <div class="wrap">
      <div class="split">
        <div class="reveal">
          <p class="label">02 — Estilo de juego</p>
          <h2>Fútbol con<br />firma Yamal</h2>
          <p class="lead" style="margin-bottom:2rem">
            No es solo show: es timing, lectura y valentía. Ataca espacios, provoca
            duelos y convierte la banda en una amenaza constante.
          </p>
          <div class="tags">
            <span class="tag">Regate</span>
            <span class="tag">Asistencias</span>
            <span class="tag">Desborde</span>
            <span class="tag">Clutch</span>
          </div>
        </div>
        <div class="grid-2">
          <div class="trait reveal">
            <div class="shine animate-yamal-shine"></div>
            <div class="trait-inner">
              <h3><svg class="icon icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8.5 14.5A2.5 2.5 0 0011 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 11-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 002.5 2.5z"/></svg> Regate</h3>
              <p>Acelera, frena y rompe líneas con una naturalidad que parece improvisada… y no lo es.</p>
            </div>
          </div>
          <div class="trait reveal">
            <div class="shine animate-yamal-shine"></div>
            <div class="trait-inner">
              <h3><svg class="icon icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8.5 14.5A2.5 2.5 0 0011 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 11-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 002.5 2.5z"/></svg> Visión</h3>
              <p>No solo gana metros: encuentra el pase o el espacio que abre el bloque rival.</p>
            </div>
          </div>
          <div class="trait reveal">
            <div class="shine animate-yamal-shine"></div>
            <div class="trait-inner">
              <h3><svg class="icon icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8.5 14.5A2.5 2.5 0 0011 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 11-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 002.5 2.5z"/></svg> Garra</h3>
              <p>Compite sin esconderse. Cuanto más grande es la noche, más limpio se ve su fútbol.</p>
            </div>
          </div>
          <div class="trait reveal">
            <div class="shine animate-yamal-shine"></div>
            <div class="trait-inner">
              <h3><svg class="icon icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8.5 14.5A2.5 2.5 0 0011 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 11-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 002.5 2.5z"/></svg> Estética</h3>
              <p>Juego bonito con sentido. La belleza del desborde unida a la eficacia moderna.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- GALERÍA -->
  <section class="section" id="galeria">
    <div class="wrap">
      <div class="reveal">
        <p class="label">03 — Galería</p>
        <h2>Luz, estadio<br />y velocidad</h2>
        <p class="lead">
          Fotos reales de ambiente futbolístico. Para imágenes oficiales de Lamine,
          súbelas a tu repo y cambia las URLs.
        </p>
      </div>
      <div class="gallery">
        <figure class="g-item span-2 reveal">
          <img src="https://images.unsplash.com/photo-1574629810360-7efbbe195018?auto=format&fit=crop&w=1600&q=80" alt="Césped" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Césped · Élite</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=1200&q=80" alt="Estadio" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Noches de estadio</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1560272564-c83b66b1ad12?auto=format&fit=crop&w=1200&q=80" alt="Acción" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Acción y desborde</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1431324155629-1a6deb1dec8d?auto=format&fit=crop&w=1200&q=80" alt="Afición" loading="lazy" />
          <div class="shade"></div>
          <figcaption>La afición</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1579952363873-27f3bade9f55?auto=format&fit=crop&w=1200&q=80" alt="Entrenamiento" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Trabajo diario</figcaption>
        </figure>
        <figure class="g-item span-2 reveal">
          <img src="https://images.unsplash.com/photo-1508098682722-e99c43a406b2?auto=format&fit=crop&w=1600&q=80" alt="Ambiente" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Ambiente de partido</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1551958219-acbc608c6377?auto=format&fit=crop&w=1200&q=80" alt="Balón" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Balón y timing</figcaption>
        </figure>
        <figure class="g-item reveal">
          <img src="https://images.unsplash.com/photo-1517466787929-bc90951d0974?auto=format&fit=crop&w=1200&q=80" alt="Botas" loading="lazy" />
          <div class="shade"></div>
          <figcaption>Detalle de pro</figcaption>
        </figure>
      </div>
    </div>
  </section>

  <!-- CIFRAS -->
  <section class="section section-gradient" id="cifras">
    <div class="wrap">
      <div class="reveal">
        <p class="label">04 — Cifras & identidad</p>
        <h2>Impacto<br />fuera de serie</h2>
      </div>
      <div class="stat-grid mb-12">
        <div class="stat-card reveal">
          <svg class="icon-md icon-gold mx-auto" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
          <p class="v animate-yamal-glow">EXT</p>
          <p class="l">Posición</p>
        </div>
        <div class="stat-card reveal">
          <svg class="icon-md icon-gold mx-auto" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.38 3.46L16 2a4 4 0 01-8 0L3.62 3.46a2 2 0 00-1.34 2.23l.58 3.48a1 1 0 00.99.83H6v10c0 1.1.9 2 2 2h8a2 2 0 002-2V10h2.15a1 1 0 00.99-.83l.58-3.48a2 2 0 00-1.34-2.23z"/></svg>
          <p class="v animate-yamal-glow">FCB</p>
          <p class="l">Club</p>
        </div>
        <div class="stat-card reveal">
          <svg class="icon-md icon-gold mx-auto" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 010-5H6M18 9h1.5a2.5 2.5 0 000-5H18M4 22h16M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22M18 2H6v7a6 6 0 0012 0V2z"/></svg>
          <p class="v animate-yamal-glow">ESP</p>
          <p class="l">Selección</p>
        </div>
        <div class="stat-card reveal">
          <svg class="icon-md icon-gold mx-auto" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9.937 15.5A2 2 0 008.5 14.063l-6.135-1.582a.5.5 0 010-.962L8.5 9.936A2 2 0 009.937 8.5l1.582-6.135a.5.5 0 01.963 0L14.063 8.5A2 2 0 0015.5 9.937l6.135 1.581a.5.5 0 010 .964L15.5 14.063a2 2 0 00-1.437 1.437l-1.582 6.135a.5.5 0 01-.963 0z"/></svg>
          <p class="v animate-yamal-glow">GEN Z</p>
          <p class="l">Ícono global</p>
        </div>
      </div>
      <div class="info-band reveal">
        <div>
          <p class="k">Club</p>
          <p class="v">FC Barcelona</p>
        </div>
        <div>
          <p class="k">Selección</p>
          <p class="v">España</p>
        </div>
        <div>
          <p class="k">Perfil</p>
          <p class="v">Extremo creativo</p>
        </div>
      </div>
    </div>
  </section>

  <!-- LEGADO -->
  <section class="section" id="legado">
    <div class="fx">
      <div class="fx-red animate-yamal-aura" style="bottom:0;top:auto;left:0"></div>
      <div class="fx-blue animate-yamal-dribble" style="right:0;top:2.5rem"></div>
    </div>
    <div class="wrap">
      <div class="cta-block reveal">
        <img src="https://images.unsplash.com/photo-1508098682722-e99c43a406b2?auto=format&fit=crop&w=1600&q=80" alt="Ambiente de partido" />
        <div class="overlay-grad"></div>
        <div class="cta-content">
          <div class="tagline" style="margin-bottom:1.5rem">
            <svg class="icon-sm icon-gold" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M11.562 3.266a.5.5 0 01.876 0L15.39 8.87a1 1 0 00.9.565h5.048a.5.5 0 01.294.904l-4.084 3.51a1 1 0 00-.364 1.118l1.518 5.274a.5.5 0 01-.772.56l-4.316-3.16a1 1 0 00-1.128 0l-4.316 3.16a.5.5 0 01-.772-.56l1.518-5.274a1 1 0 00-.364-1.118L2.37 10.34a.5.5 0 01.294-.904h5.048a1 1 0 00.9-.565l2.95-5.605z"/></svg>
            <p>05 — Legado en construcción</p>
          </div>
          <h2>No es el futuro.<br /><span class="red">Es ahora.</span></h2>
          <p class="lead" style="margin-bottom:0;color:rgba(255,255,255,0.7)">
            Yamal ya cambió la conversación: juventud, elegancia y competitividad
            de élite. Esta web lleva ese mismo ritmo de la primera pantalla a la última.
          </p>
          <div class="cta-actions">
            <a href="#inicio" class="btn-white">
              VOLVER AL INICIO
              <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
            </a>
            <a href="#galeria" class="btn-outline" style="display:inline-flex">VER GALERÍA</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="site-footer">
    <div class="footer-inner">
      <div>
        <p class="footer-brand">YAMAL</p>
        <p class="footer-sub">Lamine Yamal · Barcelona · España</p>
      </div>
      <div class="footer-links">
        <a href="#historia">Historia</a>
        <a href="#estilo">Estilo</a>
        <a href="#galeria">Galería</a>
        <a href="#cifras">Cifras</a>
        <a href="#legado">Legado</a>
      </div>
      <p class="footer-copy">Fan site · Blaugrana edition</p>
    </div>
  </footer>

  <script>
    (function () {
      var btn = document.getElementById('menu-btn');
      var closeBtn = document.getElementById('close-btn');
      var menu = document.getElementById('menu');
      var open = false;

      function set(v) {
        open = v;
        menu.classList.toggle('open', v);
        menu.setAttribute('aria-hidden', v ? 'false' : 'true');
        btn.setAttribute('aria-expanded', v ? 'true' : 'false');
        document.body.classList.toggle('menu-open', v);
      }

      btn.addEventListener('click', function () { set(true); });
      closeBtn.addEventListener('click', function () { set(false); });
      menu.querySelectorAll('[data-nav]').forEach(function (a) {
        a.addEventListener('click', function () { set(false); });
      });
      document.getElementById('logo').addEventListener('click', function () { set(false); });
      document.addEventListener('keydown', function (e) {
        if (e.key === 'Escape' && open) set(false);
      });
    })();

    (function () {
      var nodes = document.querySelectorAll('.reveal');
      if (!('IntersectionObserver' in window)) {
        nodes.forEach(function (n) { n.classList.add('in'); });
        return;
      }
      var io = new IntersectionObserver(function (entries) {
        entries.forEach(function (e) {
          if (e.isIntersecting) {
            e.target.classList.add('in');
            io.unobserve(e.target);
          }
        });
      }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
      nodes.forEach(function (n) { io.observe(n); });
    })();
  </script>
</body>
</html>
