<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JDM Heritage | Japanese Domestic Market Classics</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Barlow:wght@300;400;500;600&family=Barlow+Condensed:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --black: #0a0a0a;
    --off-black: #111111;
    --dark: #1a1a1a;
    --mid: #2c2c2c;
    --steel: #888;
    --light: #c8c8c8;
    --white: #f5f3ef;
    --gold: #c9a84c;
    --gold-light: #e4c97a;
    --red: #c0392b;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.5rem 4rem;
    background: linear-gradient(to bottom, rgba(10,10,10,0.95), transparent);
    border-bottom: 0.5px solid rgba(201,168,76,0.15);
  }
  .nav-logo {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600; font-size: 1.25rem; letter-spacing: 0.3em;
    text-transform: uppercase; color: var(--gold);
  }
  .nav-logo span { color: var(--white); font-weight: 300; }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.8rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--light); text-decoration: none; transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }
  .nav-cta {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.75rem; letter-spacing: 0.2em; text-transform: uppercase;
    padding: 0.6rem 1.5rem; border: 1px solid var(--gold);
    color: var(--gold); background: transparent; cursor: pointer;
    transition: all 0.3s;
  }
  .nav-cta:hover { background: var(--gold); color: var(--black); }

  /* HERO */
  .hero {
    height: 100vh; position: relative;
    display: flex; align-items: flex-end;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      linear-gradient(to right, rgba(10,10,10,0.85) 40%, rgba(10,10,10,0.2) 100%),
      url('https://images.unsplash.com/photo-1549473472-b8972f16f96d?w=1800&q=80') center/cover no-repeat;
  }
  .hero-content {
    position: relative; z-index: 2;
    padding: 0 4rem 5rem;
    max-width: 700px;
  }
  .hero-eyebrow {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.75rem; letter-spacing: 0.4em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 1rem;
    display: flex; align-items: center; gap: 1rem;
  }
  .hero-eyebrow::before {
    content: ''; display: block; width: 40px; height: 1px; background: var(--gold);
  }
  .hero-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 7vw, 6rem);
    font-weight: 300; line-height: 1.05;
    margin-bottom: 1.5rem;
  }
  .hero-title em { font-style: italic; color: var(--gold-light); }
  .hero-sub {
    font-size: 1rem; color: var(--light); line-height: 1.7;
    margin-bottom: 2.5rem; font-weight: 300; max-width: 500px;
  }
  .hero-btns { display: flex; gap: 1rem; }
  .btn-primary {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.8rem; letter-spacing: 0.2em; text-transform: uppercase;
    padding: 0.9rem 2.5rem; background: var(--gold); color: var(--black);
    border: none; cursor: pointer; transition: background 0.3s; text-decoration: none;
    display: inline-flex; align-items: center;
  }
  .btn-primary:hover { background: var(--gold-light); }
  .btn-ghost {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.8rem; letter-spacing: 0.2em; text-transform: uppercase;
    padding: 0.9rem 2.5rem; background: transparent; color: var(--white);
    border: 1px solid rgba(255,255,255,0.3); cursor: pointer; transition: all 0.3s;
    text-decoration: none; display: inline-flex; align-items: center;
  }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

  .hero-stats {
    position: absolute; bottom: 5rem; right: 4rem; z-index: 2;
    display: flex; gap: 3rem;
  }
  .stat { text-align: center; }
  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.5rem; font-weight: 300; color: var(--gold);
    display: block; line-height: 1;
  }
  .stat-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.65rem; letter-spacing: 0.25em; text-transform: uppercase;
    color: var(--steel); margin-top: 0.4rem; display: block;
  }

  /* SECTION COMMONS */
  section { padding: 7rem 4rem; }
  .section-eyebrow {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem; letter-spacing: 0.4em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 1rem;
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 4vw, 3.5rem); font-weight: 300; line-height: 1.1;
  }
  .section-title em { font-style: italic; color: var(--gold-light); }
  .divider {
    width: 60px; height: 1px; background: var(--gold);
    margin: 1.5rem 0;
  }

  /* ABOUT / INTRO */
  .intro {
    background: var(--off-black);
    display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center;
  }
  .intro-text p {
    color: var(--light); line-height: 1.85; font-size: 0.95rem;
    margin-bottom: 1.5rem;
  }
  .intro-image-wrap { position: relative; }
  .intro-image-wrap img {
    width: 100%; aspect-ratio: 4/3; object-fit: cover; display: block;
  }
  .intro-image-wrap::after {
    content: ''; position: absolute; inset: 0;
    border: 1px solid rgba(201,168,76,0.3);
    transform: translate(12px, 12px);
    pointer-events: none;
  }
  .facts-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2rem;
  }
  .fact {
    border-left: 2px solid var(--gold); padding-left: 1rem;
  }
  .fact-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2rem; font-weight: 300; color: var(--gold); display: block;
  }
  .fact-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--steel);
  }

  /* MODELS GRID */
  .models { background: var(--black); }
  .models-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 4rem;
  }
  .cars-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px;
    background: var(--mid);
  }
  .car-card {
    background: var(--off-black); position: relative;
    overflow: hidden; cursor: pointer;
    transition: transform 0.4s;
  }
  .car-card:hover { transform: scale(1.02); z-index: 2; }
  .car-card:hover .car-overlay { opacity: 1; }
  .car-card:first-child { grid-column: span 2; }
  .car-img {
    width: 100%; aspect-ratio: 16/9; object-fit: cover;
    display: block; transition: transform 0.6s;
    filter: brightness(0.85) saturate(0.9);
  }
  .car-card:hover .car-img { transform: scale(1.05); filter: brightness(0.7) saturate(1.1); }
  .car-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(10,10,10,0.9) 0%, transparent 50%);
    opacity: 0.7; transition: opacity 0.4s;
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: 2rem;
  }
  .car-badge {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.65rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 0.4rem;
  }
  .car-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.8rem; font-weight: 300; line-height: 1;
    margin-bottom: 0.5rem;
  }
  .car-spec-inline {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.75rem; letter-spacing: 0.15em; color: var(--light);
    opacity: 0;
    transition: opacity 0.4s 0.1s;
  }
  .car-card:hover .car-spec-inline { opacity: 1; }

  /* FEATURED MODEL */
  .featured {
    background: var(--off-black);
    padding: 0;
    display: grid; grid-template-columns: 1fr 1fr;
    min-height: 80vh;
  }
  .featured-image {
    position: relative; overflow: hidden;
  }
  .featured-image img {
    width: 100%; height: 100%; object-fit: cover;
    display: block; filter: brightness(0.9);
  }
  .featured-label {
    position: absolute; top: 3rem; left: 3rem;
    background: var(--gold); color: var(--black);
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.65rem; letter-spacing: 0.3em; text-transform: uppercase;
    padding: 0.4rem 1rem;
  }
  .featured-content {
    padding: 5rem; display: flex; flex-direction: column; justify-content: center;
  }
  .featured-content .section-title { font-size: clamp(2.5rem, 3.5vw, 4rem); }
  .featured-content p {
    color: var(--light); line-height: 1.8; font-size: 0.95rem;
    margin-bottom: 1.5rem;
  }
  .specs-table { margin: 2rem 0; border-collapse: collapse; width: 100%; }
  .specs-table tr { border-bottom: 0.5px solid rgba(255,255,255,0.08); }
  .specs-table td { padding: 0.75rem 0; font-size: 0.85rem; }
  .specs-table td:first-child {
    font-family: 'Barlow Condensed', sans-serif;
    letter-spacing: 0.15em; text-transform: uppercase;
    font-size: 0.7rem; color: var(--steel); width: 40%;
  }
  .specs-table td:last-child { color: var(--white); font-weight: 400; }
  .specs-table td span.highlight { color: var(--gold); }

  /* CULTURE SECTION */
  .culture {
    background: var(--black);
    display: grid; grid-template-columns: 1fr 2fr; gap: 5rem; align-items: start;
  }
  .culture-right { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
  .culture-card {
    background: var(--off-black); padding: 2rem;
    border-top: 1px solid var(--gold);
  }
  .culture-card h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 1rem; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--white); margin-bottom: 1rem;
  }
  .culture-card p {
    color: var(--steel); font-size: 0.85rem; line-height: 1.7;
  }
  .culture-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 4rem; font-weight: 300; color: rgba(201,168,76,0.15);
    line-height: 1; margin-bottom: 0.5rem;
  }

  /* ALL MODELS LIST */
  .all-models { background: var(--off-black); }
  .models-list-header {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr 1fr;
    padding: 0 2rem 1rem;
    border-bottom: 0.5px solid var(--mid);
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.65rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--steel);
    margin-bottom: 0;
  }
  .model-row {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr 1fr;
    padding: 1.5rem 2rem; border-bottom: 0.5px solid rgba(255,255,255,0.05);
    align-items: center; transition: background 0.2s; cursor: pointer;
  }
  .model-row:hover { background: rgba(201,168,76,0.05); }
  .model-row:hover .model-name { color: var(--gold); }
  .model-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.2rem; font-weight: 300; transition: color 0.2s;
  }
  .model-maker {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--steel); margin-top: 0.2rem;
  }
  .model-cell {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.85rem; color: var(--light); letter-spacing: 0.05em;
  }
  .model-cell.gold { color: var(--gold); }
  .status-badge {
    display: inline-block; padding: 0.25rem 0.75rem;
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase;
    border: 1px solid;
  }
  .status-available { border-color: #2ecc71; color: #2ecc71; }
  .status-sold { border-color: var(--red); color: var(--red); }
  .status-reserved { border-color: var(--gold); color: var(--gold); }

  /* FOOTER */
  footer {
    background: var(--black); border-top: 0.5px solid var(--mid);
    padding: 4rem;
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem;
  }
  .footer-brand {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 1.5rem; font-weight: 600; letter-spacing: 0.3em;
    color: var(--gold); margin-bottom: 1rem;
  }
  .footer-brand span { color: var(--white); font-weight: 300; }
  footer p { color: var(--steel); font-size: 0.85rem; line-height: 1.7; }
  .footer-col h4 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--white); margin-bottom: 1.5rem;
  }
  .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 0.75rem; }
  .footer-col a {
    color: var(--steel); font-size: 0.85rem; text-decoration: none; transition: color 0.2s;
  }
  .footer-col a:hover { color: var(--gold); }
  .footer-bottom {
    padding: 1.5rem 4rem; border-top: 0.5px solid var(--mid);
    display: flex; justify-content: space-between; align-items: center;
  }
  .footer-bottom p {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--steel);
  }

  /* SCROLL REVEAL */
  .reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.7s, transform 0.7s; }
  .reveal.visible { opacity: 1; transform: translateY(0); }
  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }

  /* HERO ANIMATION */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .hero-eyebrow { animation: fadeUp 0.8s ease both 0.3s; }
  .hero-title { animation: fadeUp 0.8s ease both 0.5s; }
  .hero-sub { animation: fadeUp 0.8s ease both 0.7s; }
  .hero-btns { animation: fadeUp 0.8s ease both 0.9s; }
  .hero-stats { animation: fadeUp 0.8s ease both 1.1s; }

  @media (max-width: 900px) {
    nav { padding: 1.5rem 2rem; }
    .nav-links { display: none; }
    section { padding: 4rem 2rem; }
    .intro, .featured, .culture { grid-template-columns: 1fr; }
    .cars-grid { grid-template-columns: 1fr; }
    .car-card:first-child { grid-column: span 1; }
    footer { grid-template-columns: 1fr 1fr; }
    .models-list-header, .model-row { grid-template-columns: 2fr 1fr 1fr; }
    .models-list-header > *:nth-child(4),
    .models-list-header > *:nth-child(5),
    .model-row > *:nth-child(4),
    .model-row > *:nth-child(5) { display: none; }
    .hero-stats { display: none; }
    .hero-content { padding: 0 2rem 4rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">JDM <span>Heritage</span></div>
  <ul class="nav-links">
    <li><a href="#models">Models</a></li>
    <li><a href="#featured">Icon</a></li>
    <li><a href="#culture">Culture</a></li>
    <li><a href="#collection">Collection</a></li>
  </ul>
  <button class="nav-cta">Enquire Now</button>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Japanese Domestic Market · Est. 1989</div>
    <h1 class="hero-title">
      Born in<br><em>Japan.</em><br>Built to Last.
    </h1>
    <p class="hero-sub">
      The legends of 1990s Japanese motorsport culture — meticulously sourced, 
      authenticated, and presented for collectors who understand the difference.
    </p>
    <div class="hero-btns">
      <a href="#models" class="btn-primary">View Collection</a>
      <a href="#culture" class="btn-ghost">Our Story</a>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat"><span class="stat-num">47</span><span class="stat-label">Cars Available</span></div>
    <div class="stat"><span class="stat-num">12</span><span class="stat-label">Icons in Stock</span></div>
    <div class="stat"><span class="stat-num">96%</span><span class="stat-label">Original Parts</span></div>
  </div>
</section>

<!-- INTRO -->
<section class="intro">
  <div class="intro-text reveal">
    <p class="section-eyebrow">The JDM Era</p>
    <h2 class="section-title">Japan's <em>Golden Decade</em> of Engineering</h2>
    <div class="divider"></div>
    <p>
      The 1990s represent the apex of Japanese automotive engineering. Under the "Gentleman's Agreement," 
      manufacturers declared a voluntary 276 hp limit — while quietly building engines that far surpassed it. 
      The result was a generation of cars disguised as everyday transport, engineered as supercars.
    </p>
    <p>
      The Nissan Skyline GT-R, Toyota Supra, Honda NSX, Mazda RX-7 — these were not accidents. They were 
      the products of a culture that valued precision, innovation, and a quiet, unassuming kind of excellence.
    </p>
    <div class="facts-grid">
      <div class="fact"><span class="fact-num">276</span><span class="fact-label">HP Gentleman's Limit</span></div>
      <div class="fact"><span class="fact-num">8</span><span class="fact-label">Iconic Models</span></div>
      <div class="fact"><span class="fact-num">30+</span><span class="fact-label">Years of Legacy</span></div>
      <div class="fact"><span class="fact-num">↑400%</span><span class="fact-label">Value Growth (10yr)</span></div>
    </div>
  </div>
  <div class="intro-image-wrap reveal reveal-delay-2">
    <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=900&q=80" alt="JDM Engine Bay">
  </div>
</section>

<!-- MODELS GRID -->
<section class="models" id="models">
  <div class="models-header">
    <div>
      <p class="section-eyebrow">The Collection</p>
      <h2 class="section-title">Select <em>Inventory</em></h2>
    </div>
    <a href="#collection" class="btn-ghost">View All 47 Cars</a>
  </div>

  <div class="cars-grid">
    <!-- Featured large card -->
    <div class="car-card reveal">
      <img class="car-img" src="https://images.unsplash.com/photo-1549473472-b8972f16f96d?w=1200&q=80" alt="Nissan Skyline GT-R R34">
      <div class="car-overlay">
        <span class="car-badge">Nissan · 1999</span>
        <h3 class="car-name">Skyline GT-R R34</h3>
        <span class="car-spec-inline">RB26DETT · 2.6L Twin-Turbo · AWD · 6-Speed Sequential</span>
      </div>
    </div>
    <!-- Right cards -->
    <div class="car-card reveal reveal-delay-1">
      <img class="car-img" src="https://images.unsplash.com/photo-1654704089641-abee50d23b7a?w=800&q=80" alt="Toyota Supra MK4">
      <div class="car-overlay">
        <span class="car-badge">Toyota · 1993</span>
        <h3 class="car-name">Supra MK4</h3>
        <span class="car-spec-inline">2JZ-GTE · 3.0L Twin-Turbo · 6-Speed Manual</span>
      </div>
    </div>
    <div class="car-card reveal reveal-delay-1">
      <img class="car-img" src="https://images.unsplash.com/photo-1569192545261-936d1ab6cf2c?w=800&q=80" alt="Mazda RX-7 FD">
      <div class="car-overlay">
        <span class="car-badge">Mazda · 1992</span>
        <h3 class="car-name">RX-7 FD3S</h3>
        <span class="car-spec-inline">13B-REW · Twin-Rotor · Sequential Twin-Turbo</span>
      </div>
    </div>
    <div class="car-card reveal reveal-delay-2">
      <img class="car-img" src="https://images.unsplash.com/photo-1740845871487-6c02a6c77f10?w=800&q=80" alt="Honda NSX">
      <div class="car-overlay">
        <span class="car-badge">Honda · 1990</span>
        <h3 class="car-name">NSX Type R</h3>
        <span class="car-spec-inline">C30A · 3.0L VTEC · Mid-Engine · RWD</span>
      </div>
    </div>
    <div class="car-card reveal reveal-delay-2">
      <img class="car-img" src="https://images.unsplash.com/photo-1558199099-ab7fa8a61cb4?w=800&q=80" alt="Mitsubishi Lancer Evo">
      <div class="car-overlay">
        <span class="car-badge">Mitsubishi · 1996</span>
        <h3 class="car-name">Lancer Evo IV</h3>
        <span class="car-spec-inline">4G63T · 2.0L Turbo · AWD · Rally-Bred</span>
      </div>
    </div>
    <div class="car-card reveal reveal-delay-3">
      <img class="car-img" src="https://images.unsplash.com/photo-1572471275423-a6e40c020a46?w=800&q=80" alt="Subaru Impreza WRX STI">
      <div class="car-overlay">
        <span class="car-badge">Subaru · 1994</span>
        <h3 class="car-name">Impreza WRX STI</h3>
        <span class="car-spec-inline">EJ20 · 2.0L Flat-4 Turbo · AWD · DCCD</span>
      </div>
    </div>
  </div>
</section>

<!-- FEATURED / ICON -->
<section class="featured" id="featured">
  <div class="featured-image">
    <img src="https://images.unsplash.com/photo-1549473472-b8972f16f96d?w=1000&q=80" alt="Nissan Skyline GT-R R34 Bayside Blue">
    <div class="featured-label">Icon of the Era</div>
  </div>
  <div class="featured-content reveal">
    <p class="section-eyebrow">The Benchmark</p>
    <h2 class="section-title">Nissan Skyline<br><em>GT-R R34</em></h2>
    <div class="divider"></div>
    <p>
      The R34 GT-R is the definitive expression of 1990s Japanese performance engineering. 
      Nicknamed "Godzilla" by Australian journalists after decimating every car at Bathurst, 
      the GT-R became a symbol of Japan's technological supremacy.
    </p>
    <p>
      Its RB26DETT inline-six, co-developed with motorsport in mind, features an advanced 
      all-wheel drive system (ATTESA E-TS Pro) and four-wheel steering (Super HICAS) — 
      technology that rivalled contemporary supercars costing three times as much.
    </p>
    <table class="specs-table">
      <tr><td>Engine</td><td>RB26DETT 2.6L Twin-Turbo Inline-6</td></tr>
      <tr><td>Power</td><td><span class="highlight">330 PS</span> (official) / ~600 PS+ (actual)</td></tr>
      <tr><td>Torque</td><td>392 Nm @ 4,400 rpm</td></tr>
      <tr><td>Drivetrain</td><td>ATTESA E-TS Pro AWD</td></tr>
      <tr><td>0–100 km/h</td><td><span class="highlight">4.1 seconds</span></td></tr>
      <tr><td>Production</td><td>1999–2002 · 11,578 built</td></tr>
      <tr><td>Nürburgring</td><td>7:42 (1999) — fastest production car of its era</td></tr>
    </table>
    <a href="#collection" class="btn-primary">View Available R34s</a>
  </div>
</section>

<!-- CULTURE -->
<section class="culture" id="culture">
  <div class="culture-left reveal">
    <p class="section-eyebrow">The Heritage</p>
    <h2 class="section-title">More Than<br><em>Machines</em></h2>
    <div class="divider"></div>
    <p style="color: var(--light); line-height: 1.85; font-size: 0.95rem;">
      JDM culture emerged from Japan's post-bubble era of extreme engineering ambition. 
      These cars were never just transportation — they were expressions of a philosophy that 
      precision, technology, and performance could coexist in perfect harmony.
    </p>
    <br>
    <p style="color: var(--steel); font-size: 0.85rem; line-height: 1.8;">
      Today, these cars have transcended their origins. They are cultural artifacts — 
      preserved by collectors worldwide who understand that what Japan produced in the 1990s 
      will never be replicated.
    </p>
  </div>
  <div class="culture-right">
    <div class="culture-card reveal reveal-delay-1">
      <div class="culture-num">01</div>
      <h3>Gentleman's Agreement</h3>
      <p>Japan's automakers agreed to self-limit output to 276 hp publicly — while engineers quietly built engines producing far more. A gentlemen's agreement that produced some of the most deceptive performance cars ever made.</p>
    </div>
    <div class="culture-card reveal reveal-delay-1">
      <div class="culture-num">02</div>
      <h3>Tuner Culture</h3>
      <p>Companies like HKS, Tomei, and Nismo turned already-capable platforms into weapons. The aftermarket ecosystem that grew around JDM cars is unparalleled in automotive history.</p>
    </div>
    <div class="culture-card reveal reveal-delay-2">
      <div class="culture-num">03</div>
      <h3>Motorsport DNA</h3>
      <p>The GT-R won the Bathurst 1000. The Impreza and Lancer dominated WRC. The Supra ruled JGTC. Every road car carried racing heritage in its DNA — not as a marketing claim, but as fact.</p>
    </div>
    <div class="culture-card reveal reveal-delay-2">
      <div class="culture-num">04</div>
      <h3>The 25-Year Rule</h3>
      <p>As these icons cross the 25-year import threshold into the US market, values have exploded. Certified originals from this era are now legitimate collectibles, with some R34 GT-Rs exceeding $1 million.</p>
    </div>
  </div>
</section>

<!-- FULL COLLECTION TABLE -->
<section class="all-models" id="collection">
  <p class="section-eyebrow reveal">Current Inventory</p>
  <h2 class="section-title reveal" style="margin-bottom: 3rem;">The Full <em>Collection</em></h2>

  <div class="models-list-header">
    <span>Model</span>
    <span>Year</span>
    <span>Engine</span>
    <span>Mileage</span>
    <span>Status</span>
  </div>

  <div class="model-row reveal">
    <div><div class="model-name">Skyline GT-R R34 V-Spec II</div><div class="model-maker">Nissan</div></div>
    <div class="model-cell">2002</div>
    <div class="model-cell">RB26DETT 2.6T</div>
    <div class="model-cell gold">28,400 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Supra RZ Twin Turbo</div><div class="model-maker">Toyota</div></div>
    <div class="model-cell">1994</div>
    <div class="model-cell">2JZ-GTE 3.0T</div>
    <div class="model-cell gold">41,000 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">RX-7 Type RB FD3S</div><div class="model-maker">Mazda</div></div>
    <div class="model-cell">1997</div>
    <div class="model-cell">13B-REW Rotary</div>
    <div class="model-cell gold">52,200 km</div>
    <div><span class="status-badge status-reserved">Reserved</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">NSX Type R</div><div class="model-maker">Honda / Acura</div></div>
    <div class="model-cell">1992</div>
    <div class="model-cell">C32B 3.2 VTEC</div>
    <div class="model-cell gold">34,700 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Lancer Evolution VI Tommi Mäkinen</div><div class="model-maker">Mitsubishi</div></div>
    <div class="model-cell">2000</div>
    <div class="model-cell">4G63T 2.0T</div>
    <div class="model-cell gold">67,900 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Impreza WRX STI Version VI</div><div class="model-maker">Subaru</div></div>
    <div class="model-cell">1999</div>
    <div class="model-cell">EJ20G 2.0T</div>
    <div class="model-cell gold">44,100 km</div>
    <div><span class="status-badge status-sold">Sold</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Skyline GT-R R33 V-Spec</div><div class="model-maker">Nissan</div></div>
    <div class="model-cell">1995</div>
    <div class="model-cell">RB26DETT 2.6T</div>
    <div class="model-cell gold">58,300 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">MR2 GT-S Turbo SW20</div><div class="model-maker">Toyota</div></div>
    <div class="model-cell">1991</div>
    <div class="model-cell">3S-GTE 2.0T Mid</div>
    <div class="model-cell gold">76,500 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Integra Type R DC2</div><div class="model-maker">Honda / Acura</div></div>
    <div class="model-cell">1998</div>
    <div class="model-cell">B18C 1.8 VTEC</div>
    <div class="model-cell gold">62,000 km</div>
    <div><span class="status-badge status-reserved">Reserved</span></div>
  </div>
  <div class="model-row reveal">
    <div><div class="model-name">Silvia S15 Spec R</div><div class="model-maker">Nissan</div></div>
    <div class="model-cell">1999</div>
    <div class="model-cell">SR20DET 2.0T</div>
    <div class="model-cell gold">48,800 km</div>
    <div><span class="status-badge status-available">Available</span></div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>
    <div class="footer-brand">JDM <span>Heritage</span></div>
    <p>Curated Japanese performance vehicles from the golden era of automotive engineering. Each car authenticated, inspected, and ready for a new guardian.</p>
    <br>
    <p style="font-size:0.75rem; color: #444;">Project by Dior Jahaj &amp; Mateo Jaho<br>Canadian Institute of Technology · 2026</p>
  </div>
  <div class="footer-col">
    <h4>Collection</h4>
    <ul>
      <li><a href="#">Nissan GT-R</a></li>
      <li><a href="#">Toyota Supra</a></li>
      <li><a href="#">Mazda RX-7</a></li>
      <li><a href="#">Honda NSX</a></li>
      <li><a href="#">Mitsubishi Evo</a></li>
      <li><a href="#">Subaru STI</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Information</h4>
    <ul>
      <li><a href="#">Import Process</a></li>
      <li><a href="#">Certification</a></li>
      <li><a href="#">25-Year Rule</a></li>
      <li><a href="#">Financing</a></li>
      <li><a href="#">Consignment</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Contact</h4>
    <ul>
      <li><a href="#">Enquire Online</a></li>
      <li><a href="#">Book Inspection</a></li>
      <li><a href="#">Newsletter</a></li>
      <li><a href="#">Instagram</a></li>
    </ul>
  </div>
</footer>
<div class="footer-bottom">
  <p>© 2026 JDM Heritage. All rights reserved.</p>
  <p>Dior Jahaj · Mateo Jaho · CIT Computer Networks Project</p>
</div>

<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
