<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>JDM Heritage — Japan's Golden Era</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:ital,wght@0,300;0,400;0,500;0,600;1,300&family=Barlow+Condensed:wght@300;400;600&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --red:#C0392B;
  --red-light:#e74c3c;
  --gold:#C8A96E;
  --dark:#0A0A0A;
  --dark2:#111111;
  --dark3:#1A1A1A;
  --mid:#2A2A2A;
  --border:#2E2E2E;
  --text:#F0EDE8;
  --muted:#8A8680;
  --font-display:'Bebas Neue',sans-serif;
  --font-body:'Barlow',sans-serif;
  --font-cond:'Barlow Condensed',sans-serif;
}
html{scroll-behavior:smooth}
body{background:var(--dark);color:var(--text);font-family:var(--font-body);overflow-x:hidden}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:0 4rem;height:72px;background:rgba(10,10,10,0.85);backdrop-filter:blur(12px);border-bottom:1px solid rgba(255,255,255,0.05)}
.nav-logo{font-family:var(--font-display);font-size:1.7rem;letter-spacing:0.08em;color:var(--text);text-decoration:none}
.nav-logo span{color:var(--red)}
.nav-links{display:flex;gap:2.5rem;list-style:none}
.nav-links a{font-family:var(--font-cond);font-size:0.85rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);text-decoration:none;transition:color 0.2s}
.nav-links a:hover{color:var(--text)}
.nav-cta{font-family:var(--font-cond);font-size:0.8rem;letter-spacing:0.15em;text-transform:uppercase;padding:8px 20px;border:1px solid var(--red);color:var(--red);background:transparent;cursor:pointer;text-decoration:none;transition:all 0.2s}
.nav-cta:hover{background:var(--red);color:#fff}

/* HERO */
.hero{position:relative;height:100vh;min-height:600px;display:flex;flex-direction:column;justify-content:flex-end;padding:0 4rem 5rem;overflow:hidden}
.hero-bg{position:absolute;inset:0;background:url('https://images.unsplash.com/photo-1626668893632-6f3a4466d22f?w=1600&q=80') center/cover no-repeat;filter:brightness(0.45)}
.hero-bg::after{content:'';position:absolute;inset:0;background:linear-gradient(to top,rgba(10,10,10,1) 0%,rgba(10,10,10,0.3) 50%,transparent 100%)}
.hero-content{position:relative;z-index:1;max-width:800px}
.hero-tag{font-family:var(--font-cond);font-size:0.75rem;letter-spacing:0.25em;text-transform:uppercase;color:var(--red);margin-bottom:1.2rem;display:flex;align-items:center;gap:0.75rem}
.hero-tag::before{content:'';width:32px;height:1px;background:var(--red)}
.hero h1{font-family:var(--font-display);font-size:clamp(4rem,9vw,8rem);line-height:0.92;letter-spacing:0.02em;margin-bottom:1.5rem}
.hero h1 em{color:var(--red);font-style:normal}
.hero p{font-size:1.05rem;font-weight:300;color:rgba(240,237,232,0.7);max-width:480px;line-height:1.7;margin-bottom:2.5rem}
.hero-actions{display:flex;gap:1rem;align-items:center}
.btn-primary{font-family:var(--font-cond);font-size:0.85rem;letter-spacing:0.15em;text-transform:uppercase;padding:14px 36px;background:var(--red);color:#fff;border:none;cursor:pointer;text-decoration:none;transition:background 0.2s}
.btn-primary:hover{background:var(--red-light)}
.btn-secondary{font-family:var(--font-cond);font-size:0.85rem;letter-spacing:0.15em;text-transform:uppercase;padding:14px 36px;background:transparent;color:var(--text);border:1px solid rgba(255,255,255,0.3);cursor:pointer;text-decoration:none;transition:all 0.2s}
.btn-secondary:hover{border-color:var(--text)}
.hero-scroll{position:absolute;bottom:2.5rem;right:4rem;z-index:1;display:flex;flex-direction:column;align-items:center;gap:8px}
.hero-scroll span{font-family:var(--font-cond);font-size:0.7rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);writing-mode:vertical-rl}
.scroll-line{width:1px;height:50px;background:linear-gradient(to bottom,var(--muted),transparent);animation:scrollDown 2s ease-in-out infinite}
@keyframes scrollDown{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

/* STATS BAR */
.stats-bar{background:var(--dark3);border-top:1px solid var(--border);border-bottom:1px solid var(--border);display:grid;grid-template-columns:repeat(4,1fr);gap:0}
.stat-item{padding:2rem;text-align:center;border-right:1px solid var(--border)}
.stat-item:last-child{border-right:none}
.stat-num{font-family:var(--font-display);font-size:2.8rem;letter-spacing:0.05em;color:var(--text)}
.stat-num span{color:var(--red)}
.stat-label{font-family:var(--font-cond);font-size:0.75rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-top:4px}

/* SECTIONS */
section{padding:6rem 4rem}
.section-tag{font-family:var(--font-cond);font-size:0.75rem;letter-spacing:0.25em;text-transform:uppercase;color:var(--red);margin-bottom:1rem;display:flex;align-items:center;gap:0.75rem}
.section-tag::before{content:'';width:24px;height:1px;background:var(--red)}
.section-title{font-family:var(--font-display);font-size:clamp(2.5rem,5vw,4.5rem);line-height:1;letter-spacing:0.03em;margin-bottom:1.5rem}
.section-subtitle{font-size:1rem;font-weight:300;color:rgba(240,237,232,0.6);max-width:520px;line-height:1.8}

/* ABOUT SPLIT */
.about{background:var(--dark2)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center}
.about-image{position:relative}
.about-image img{width:100%;height:500px;object-fit:cover;display:block}
.about-image-accent{position:absolute;bottom:-1.5rem;right:-1.5rem;width:160px;height:160px;border:1px solid var(--red);pointer-events:none}
.about-text .section-subtitle{margin-bottom:2rem}
.about-feature-list{display:flex;flex-direction:column;gap:1.2rem;margin-top:2rem}
.about-feature{display:flex;align-items:flex-start;gap:1rem}
.about-feature-num{font-family:var(--font-display);font-size:1.5rem;color:var(--red);min-width:2rem}
.about-feature-text h4{font-family:var(--font-cond);font-size:0.9rem;letter-spacing:0.1em;text-transform:uppercase;margin-bottom:4px}
.about-feature-text p{font-size:0.85rem;color:var(--muted);line-height:1.6}

/* CARS GRID */
.cars-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:3rem}
.cars-filter{display:flex;gap:0.5rem}
.filter-btn{font-family:var(--font-cond);font-size:0.75rem;letter-spacing:0.15em;text-transform:uppercase;padding:7px 16px;background:transparent;color:var(--muted);border:1px solid var(--border);cursor:pointer;transition:all 0.2s}
.filter-btn.active,.filter-btn:hover{color:var(--text);border-color:var(--text)}
.cars-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border)}
.car-card{background:var(--dark2);overflow:hidden;cursor:pointer;transition:transform 0.3s}
.car-card:hover{transform:scale(1.01);z-index:1}
.car-card-img{width:100%;height:260px;object-fit:cover;display:block;transition:transform 0.5s}
.car-card:hover .car-card-img{transform:scale(1.04)}
.car-card-body{padding:1.5rem}
.car-card-maker{font-family:var(--font-cond);font-size:0.7rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--red);margin-bottom:6px}
.car-card-name{font-family:var(--font-display);font-size:1.6rem;letter-spacing:0.04em;margin-bottom:0.4rem}
.car-card-year{font-family:var(--font-cond);font-size:0.8rem;letter-spacing:0.1em;color:var(--muted);margin-bottom:1rem}
.car-card-specs{display:grid;grid-template-columns:1fr 1fr;gap:0.5rem;border-top:1px solid var(--border);padding-top:1rem}
.spec-item label{font-family:var(--font-cond);font-size:0.65rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);display:block}
.spec-item span{font-family:var(--font-cond);font-size:0.95rem;font-weight:600;color:var(--text)}

/* FEATURED CAR */
.featured{background:var(--dark3);overflow:hidden}
.featured-inner{display:grid;grid-template-columns:1fr 1fr;gap:0;min-height:500px}
.featured-image{position:relative;overflow:hidden}
.featured-image img{width:100%;height:100%;object-fit:cover;display:block;min-height:500px}
.featured-image-overlay{position:absolute;inset:0;background:linear-gradient(to right,transparent 60%,var(--dark3) 100%)}
.featured-content{padding:4rem 3rem;display:flex;flex-direction:column;justify-content:center}
.featured-badge{display:inline-block;font-family:var(--font-cond);font-size:0.7rem;letter-spacing:0.2em;text-transform:uppercase;padding:5px 14px;background:rgba(192,57,43,0.15);color:var(--red);border:1px solid rgba(192,57,43,0.4);margin-bottom:1.5rem}
.featured-content h2{font-family:var(--font-display);font-size:clamp(2.5rem,4vw,4rem);line-height:1;margin-bottom:0.5rem}
.featured-content .year{font-family:var(--font-cond);font-size:0.85rem;letter-spacing:0.15em;color:var(--muted);margin-bottom:1.5rem}
.featured-content p{font-size:0.95rem;font-weight:300;color:rgba(240,237,232,0.65);line-height:1.8;margin-bottom:2rem}
.featured-specs{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin-bottom:2.5rem}
.f-spec{padding:1rem;background:rgba(255,255,255,0.03);border:1px solid var(--border)}
.f-spec label{font-family:var(--font-cond);font-size:0.65rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);display:block;margin-bottom:4px}
.f-spec span{font-family:var(--font-display);font-size:1.4rem;letter-spacing:0.05em}

/* LEGACY / TIMELINE */
.legacy{background:var(--dark)}
.timeline{margin-top:3rem;position:relative;padding-left:2rem}
.timeline::before{content:'';position:absolute;left:0;top:0;bottom:0;width:1px;background:var(--border)}
.tl-item{position:relative;padding:0 0 2.5rem 2.5rem}
.tl-item::before{content:'';position:absolute;left:-4px;top:6px;width:9px;height:9px;background:var(--dark);border:1px solid var(--red)}
.tl-year{font-family:var(--font-display);font-size:1rem;letter-spacing:0.1em;color:var(--red);margin-bottom:0.4rem}
.tl-title{font-family:var(--font-cond);font-size:1.1rem;letter-spacing:0.05em;text-transform:uppercase;margin-bottom:0.4rem}
.tl-desc{font-size:0.85rem;color:var(--muted);line-height:1.7;max-width:500px}

/* TECH SECTION */
.tech{background:var(--dark2)}
.tech-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:1px;background:var(--border);margin-top:3rem}
.tech-item{background:var(--dark2);padding:2.5rem;position:relative;overflow:hidden}
.tech-item::before{content:attr(data-num);position:absolute;right:1.5rem;top:1rem;font-family:var(--font-display);font-size:5rem;color:rgba(255,255,255,0.03);line-height:1}
.tech-icon{font-size:1.5rem;margin-bottom:1rem;color:var(--red)}
.tech-item h3{font-family:var(--font-cond);font-size:1.1rem;letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.6rem}
.tech-item p{font-size:0.85rem;color:var(--muted);line-height:1.7}

/* GALLERY */
.gallery-grid{display:grid;grid-template-columns:repeat(4,1fr);grid-template-rows:auto auto;gap:4px;margin-top:2rem}
.gallery-item{overflow:hidden;cursor:pointer}
.gallery-item img{width:100%;height:200px;object-fit:cover;display:block;transition:transform 0.5s,filter 0.3s;filter:grayscale(20%)}
.gallery-item:hover img{transform:scale(1.06);filter:grayscale(0%)}
.gallery-item.wide{grid-column:span 2}
.gallery-item.wide img{height:260px}

/* FOOTER */
footer{background:var(--dark3);border-top:1px solid var(--border);padding:4rem}
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:3rem;margin-bottom:3rem}
.footer-brand .logo{font-family:var(--font-display);font-size:1.5rem;letter-spacing:0.08em;margin-bottom:0.75rem}
.footer-brand .logo span{color:var(--red)}
.footer-brand p{font-size:0.85rem;color:var(--muted);line-height:1.7;max-width:280px}
.footer-col h4{font-family:var(--font-cond);font-size:0.75rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--text);margin-bottom:1.2rem}
.footer-col ul{list-style:none;display:flex;flex-direction:column;gap:0.6rem}
.footer-col ul a{font-size:0.85rem;color:var(--muted);text-decoration:none;transition:color 0.2s}
.footer-col ul a:hover{color:var(--text)}
.footer-bottom{border-top:1px solid var(--border);padding-top:1.5rem;display:flex;justify-content:space-between;align-items:center}
.footer-bottom p{font-size:0.78rem;color:var(--muted)}

/* MODAL */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.88);z-index:200;display:none;align-items:center;justify-content:center;padding:2rem}
.modal-overlay.active{display:flex}
.modal{background:var(--dark2);max-width:900px;width:100%;position:relative;overflow:hidden;max-height:90vh;overflow-y:auto}
.modal-close{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.5rem;cursor:pointer;z-index:10;width:32px;height:32px;display:flex;align-items:center;justify-content:center}
.modal-close:hover{color:var(--text)}
.modal img{width:100%;height:320px;object-fit:cover;display:block}
.modal-body{padding:2rem}
.modal-body h2{font-family:var(--font-display);font-size:2.5rem;margin-bottom:0.3rem}
.modal-body .modal-sub{font-family:var(--font-cond);font-size:0.8rem;letter-spacing:0.15em;color:var(--red);text-transform:uppercase;margin-bottom:1rem}
.modal-body p{font-size:0.9rem;color:rgba(240,237,232,0.7);line-height:1.8;margin-bottom:1.5rem}
.modal-specs-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1rem}
.ms-item label{font-family:var(--font-cond);font-size:0.65rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);display:block;margin-bottom:3px}
.ms-item span{font-family:var(--font-cond);font-size:1rem;font-weight:600}

@media(max-width:900px){
  nav{padding:0 2rem}
  .nav-links{display:none}
  section{padding:4rem 2rem}
  .hero{padding:0 2rem 4rem}
  .about-grid{grid-template-columns:1fr}
  .cars-grid{grid-template-columns:1fr 1fr}
  .featured-inner{grid-template-columns:1fr}
  .tech-grid{grid-template-columns:1fr}
  .gallery-grid{grid-template-columns:1fr 1fr}
  .footer-grid{grid-template-columns:1fr 1fr}
  .stats-bar{grid-template-columns:1fr 1fr}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#"><span>JDM</span> Heritage</a>
  <ul class="nav-links">
    <li><a href="#models">Models</a></li>
    <li><a href="#featured">Spotlight</a></li>
    <li><a href="#tech">Technology</a></li>
    <li><a href="#legacy">Legacy</a></li>
    <li><a href="#gallery">Gallery</a></li>
  </ul>
  <a href="#models" class="nav-cta">Explore</a>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-tag">Japan Domestic Market · 1989–1999</div>
    <h1>Born<br/>from the<br/><em>Rising</em> Sun</h1>
    <p>A decade of engineering obsession. When Japanese automakers competed not for sales, but for glory — producing machines that still define performance culture worldwide.</p>
    <div class="hero-actions">
      <a href="#models" class="btn-primary">View Models</a>
      <a href="#legacy" class="btn-secondary">The Legacy</a>
    </div>
  </div>
  <div class="hero-scroll">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- STATS -->
<div class="stats-bar">
  <div class="stat-item"><div class="stat-num">10<span>+</span></div><div class="stat-label">Iconic Models</div></div>
  <div class="stat-item"><div class="stat-num">280<span>ps</span></div><div class="stat-label">Gentleman's Agreement</div></div>
  <div class="stat-item"><div class="stat-num">90<span>s</span></div><div class="stat-label">Golden Era</div></div>
  <div class="stat-item"><div class="stat-num">6</div><div class="stat-label">Legendary Manufacturers</div></div>
</div>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div class="about-image">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80" alt="JDM engine bay"/>
      <div class="about-image-accent"></div>
    </div>
    <div class="about-text">
      <div class="section-tag">About the Era</div>
      <h2 class="section-title">What Made the 90s JDM Legendary</h2>
      <p class="section-subtitle">In the 1990s, Japanese manufacturers entered a self-imposed gentlemen's agreement: no car would be rated above 280 PS. The real performance figures, however, told a different story.</p>
      <div class="about-feature-list">
        <div class="about-feature">
          <div class="about-feature-num">01</div>
          <div class="about-feature-text">
            <h4>Gentleman's Agreement</h4>
            <p>Japanese manufacturers collectively capped horsepower at 280PS (276 hp) — a public limit that hid true engineering capabilities and created a culture of underrated machines.</p>
          </div>
        </div>
        <div class="about-feature">
          <div class="about-feature-num">02</div>
          <div class="about-feature-text">
            <h4>Motorsport DNA</h4>
            <p>Rally, touring car, and Group A racing directly influenced street cars. Homologation specials like the Evo and STI were built to win championships — and sold to the public.</p>
          </div>
        </div>
        <div class="about-feature">
          <div class="about-feature-num">03</div>
          <div class="about-feature-text">
            <h4>Technology Leadership</h4>
            <p>VTEC, ATTESA E-TS, Super HICAS, DCCD — the 90s saw Japan pioneer electronics-driven performance that rivaled and often surpassed European supercars at a fraction of the price.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- MODELS -->
<section id="models" style="background:var(--dark);padding:6rem 4rem">
  <div class="cars-header">
    <div>
      <div class="section-tag">The Machines</div>
      <h2 class="section-title">Iconic Models</h2>
    </div>
    <div class="cars-filter">
      <button class="filter-btn active" onclick="filterCars('all',this)">All</button>
      <button class="filter-btn" onclick="filterCars('honda',this)">Honda</button>
      <button class="filter-btn" onclick="filterCars('nissan',this)">Nissan</button>
      <button class="filter-btn" onclick="filterCars('toyota',this)">Toyota</button>
      <button class="filter-btn" onclick="filterCars('mitsubishi',this)">Mitsubishi</button>
    </div>
  </div>
  <div class="cars-grid" id="carsGrid"></div>
</section>

<!-- FEATURED -->
<section class="featured" id="featured">
  <div class="featured-inner">
    <div class="featured-image">
      <img src="https://images.unsplash.com/photo-1611859266238-4b98091d9d9b?w=800&q=80" alt="Nissan Skyline GT-R"/>
      <div class="featured-image-overlay"></div>
    </div>
    <div class="featured-content">
      <span class="featured-badge">Icon Spotlight</span>
      <h2>Skyline GT-R</h2>
      <div class="year">Nissan · R34 · 1999–2002</div>
      <p>The most feared Japanese performance car ever built. The R34 GT-R combined an advanced twin-turbocharged RB26DETT inline-six with the legendary ATTESA E-TS Pro all-wheel-drive system and an onboard computer that monitored up to 8 vehicle parameters in real time. It was the car that destroyed Porsche's reputation on the Nürburgring.</p>
      <div class="featured-specs">
        <div class="f-spec"><label>Engine</label><span>RB26</span></div>
        <div class="f-spec"><label>Power</label><span>330ps*</span></div>
        <div class="f-spec"><label>0–100</label><span>4.7s</span></div>
        <div class="f-spec"><label>Drive</label><span>AWD</span></div>
        <div class="f-spec"><label>Trans.</label><span>6MT</span></div>
        <div class="f-spec"><label>Weight</label><span>1,560kg</span></div>
      </div>
      <p style="font-size:0.75rem;color:var(--muted);">* Officially rated 280ps. Actual output significantly higher.</p>
    </div>
  </div>
</section>

<!-- TECH -->
<section class="tech" id="tech">
  <div class="section-tag">Engineering</div>
  <h2 class="section-title">Technology That Defined a Generation</h2>
  <p class="section-subtitle">Japanese engineers developed proprietary systems during the 90s that were years ahead of their time. These are the breakthroughs that made JDM cars legends.</p>
  <div class="tech-grid">
    <div class="tech-item" data-num="01">
      <div class="tech-icon">⚙</div>
      <h3>Honda VTEC</h3>
      <p>Variable Valve Timing and Lift Electronic Control — Honda's system dynamically altered valve timing based on engine RPM, effectively giving the engine two distinct personalities: fuel-efficient at low revs, aggressive and powerful at high revs. The B16B in the Civic Type R produced 185hp from just 1.6 liters — naturally aspirated.</p>
    </div>
    <div class="tech-item" data-num="02">
      <div class="tech-icon">⚡</div>
      <h3>Nissan ATTESA E-TS Pro</h3>
      <p>Active Transfer Torque Split Electronic, featured in the R33/R34 GT-R. Using a hydraulic multi-plate clutch, this all-wheel-drive system could send up to 100% of torque to the rear wheels during braking and 50% to the front under full acceleration — reacting faster than any driver input.</p>
    </div>
    <div class="tech-item" data-num="03">
      <div class="tech-icon">🔩</div>
      <h3>Twin-Turbo Architecture</h3>
      <p>Sequential and parallel twin-turbocharged setups were pioneered in Japan during the 90s. The Toyota 2JZ-GTE used sequential turbochargers — a small turbo for low-end response and a large one for high-end power — delivering a flat, usable torque curve across the entire rev range.</p>
    </div>
    <div class="tech-item" data-num="04">
      <div class="tech-icon">🎯</div>
      <h3>Mitsubishi AYC</h3>
      <p>Active Yaw Control, introduced in the Lancer Evo IV, used a rear differential to distribute torque between rear wheels independently. It could actively corner the car by overdriving the outside rear wheel, reducing understeer and allowing a higher cornering limit than passive differentials could achieve.</p>
    </div>
  </div>
</section>

<!-- LEGACY / TIMELINE -->
<section class="legacy" id="legacy">
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:start">
    <div>
      <div class="section-tag">The Story</div>
      <h2 class="section-title">A Decade That Changed Driving Forever</h2>
      <p class="section-subtitle">The 1990s represented an unprecedented convergence of motorsport investment, engineering talent, and regulatory freedom in Japan. What emerged changed global car culture permanently.</p>
    </div>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-year">1989</div>
        <div class="tl-title">R32 GT-R Debuts</div>
        <div class="tl-desc">Nissan unleashes the R32 Skyline GT-R, winning every single race in the Japanese Touring Car Championship that year. Competitors call it "Godzilla." The JDM era begins in earnest.</div>
      </div>
      <div class="tl-item">
        <div class="tl-year">1992</div>
        <div class="tl-title">Honda NSX Sets the Standard</div>
        <div class="tl-desc">Developed with input from Ayrton Senna, the mid-engine NSX proved Japanese engineering could match Ferrari — at half the price, with genuine daily-driver reliability.</div>
      </div>
      <div class="tl-item">
        <div class="tl-year">1994</div>
        <div class="tl-title">The Evo vs. STI War Begins</div>
        <div class="tl-desc">Mitsubishi Lancer Evolution and Subaru Impreza WRX STI enter the WRC in earnest, launching a generational rivalry that would produce some of the greatest all-weather performance cars ever built.</div>
      </div>
      <div class="tl-item">
        <div class="tl-year">1998</div>
        <div class="tl-title">Toyota Supra MkIV Peaks</div>
        <div class="tl-desc">The 2JZ-GTE powered Supra achieves legendary tuner status. With its forged internals, the engine routinely handles 700+ hp in modified form — triple the factory figure.</div>
      </div>
      <div class="tl-item">
        <div class="tl-year">1999</div>
        <div class="tl-title">R34 GT-R — The Final Form</div>
        <div class="tl-desc">The last of the R-series Skylines arrives, equipped with the Multi Function Display — an onboard computer monitoring chassis data in real time. Many consider it the ultimate expression of 90s JDM engineering.</div>
      </div>
    </div>
  </div>
</section>

<!-- GALLERY -->
<section id="gallery" style="background:var(--dark2);padding:6rem 4rem">
  <div class="section-tag">Gallery</div>
  <h2 class="section-title">The Icons, Captured</h2>
  <div class="gallery-grid">
    <div class="gallery-item wide"><img src="https://images.unsplash.com/photo-1580274455191-1c62238fa333?w=800&q=80" alt="JDM car"/></div>
    <div class="gallery-item"><img src="https://images.unsplash.com/photo-1607853202273-797f1c22a38e?w=600&q=80" alt="JDM car"/></div>
    <div class="gallery-item"><img src="https://images.unsplash.com/photo-1622185135505-2d795003994a?w=600&q=80" alt="JDM car"/></div>
    <div class="gallery-item"><img src="https://images.unsplash.com/photo-1544636331-e26879cd4d9b?w=600&q=80" alt="JDM car"/></div>
    <div class="gallery-item"><img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?w=600&q=80" alt="JDM car"/></div>
    <div class="gallery-item wide"><img src="https://images.unsplash.com/photo-1490902931801-d6f80ca94fe4?w=800&q=80" alt="JDM car"/></div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <div class="logo"><span>JDM</span> Heritage</div>
      <p>A tribute to Japan's golden decade of performance engineering. Celebrating the machines that shaped global car culture from 1989 to 1999.</p>
      <p style="margin-top:1rem;font-size:0.78rem;color:rgba(138,134,128,0.6)">Project by Dior Jahaj & Mateo Jaho<br/>Computer Communication & Networks — CIT</p>
    </div>
    <div class="footer-col">
      <h4>Models</h4>
      <ul>
        <li><a href="#models">Nissan Skyline GT-R</a></li>
        <li><a href="#models">Toyota Supra</a></li>
        <li><a href="#models">Honda NSX</a></li>
        <li><a href="#models">Mazda RX-7</a></li>
        <li><a href="#models">Mitsubishi Evo</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Explore</h4>
      <ul>
        <li><a href="#about">About the Era</a></li>
        <li><a href="#tech">Technology</a></li>
        <li><a href="#legacy">Timeline</a></li>
        <li><a href="#gallery">Gallery</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Manufacturers</h4>
      <ul>
        <li><a href="#models">Honda</a></li>
        <li><a href="#models">Nissan</a></li>
        <li><a href="#models">Toyota</a></li>
        <li><a href="#models">Mazda</a></li>
        <li><a href="#models">Mitsubishi</a></li>
        <li><a href="#models">Subaru</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2026 JDM Heritage · Dior Jahaj & Mateo Jaho · Canadian Institute of Technology</p>
    <p>All images via Unsplash · For educational purposes</p>
  </div>
</footer>

<!-- MODAL -->
<div class="modal-overlay" id="modal" onclick="closeModal(event)">
  <div class="modal">
    <button class="modal-close" onclick="document.getElementById('modal').classList.remove('active')">✕</button>
    <img id="modal-img" src="" alt=""/>
    <div class="modal-body">
      <div class="modal-sub" id="modal-sub"></div>
      <h2 id="modal-title"></h2>
      <p id="modal-desc"></p>
      <div class="modal-specs-grid" id="modal-specs"></div>
    </div>
  </div>
</div>

<script>
const cars=[
  {make:"nissan",name:"Skyline GT-R",model:"BNR32",years:"1989–1994",img:"https://images.unsplash.com/photo-1632245889029-e406faaa34cd?w=800&q=80",hp:"280ps*",engine:"RB26DETT",drive:"AWD",weight:"1,430kg",desc:"The original 'Godzilla.' The R32 GT-R dominated every motorsport series it entered in Japan. Powered by the legendary RB26DETT twin-turbo inline-six and the ATTESA E-TS all-wheel-drive system, it remains the car that put Japanese performance on the world map.",full_specs:[{l:"Engine",v:"RB26DETT 2.6L TT"},{l:"Power",v:"280ps (actual ~320ps)"},{l:"Torque",v:"353 Nm"},{l:"0-100",v:"5.6s"}]},
  {make:"toyota",name:"Supra MkIV",model:"A80",years:"1993–2002",img:"https://images.unsplash.com/photo-1612544448445-b8232cff3b6c?w=800&q=80",hp:"280ps*",engine:"2JZ-GTE",drive:"RWD",weight:"1,520kg",desc:"Built around the bulletproof 2JZ-GTE engine, the MkIV Supra became the ultimate tuner platform. Factory power was a conservative 280ps — modified examples routinely produce 700–1000hp from the same block, owing to its near-indestructible forged internals.",full_specs:[{l:"Engine",v:"2JZ-GTE 3.0L TT"},{l:"Power",v:"280ps (turbo)"},{l:"Torque",v:"431 Nm"},{l:"0-100",v:"5.1s"}]},
  {make:"honda",name:"NSX",model:"NA1",years:"1990–2005",img:"https://images.unsplash.com/photo-1547744173-68e5e7e8c9e6?w=800&q=80",hp:"270ps",engine:"C30A VTEC",drive:"RWD",weight:"1,370kg",desc:"Designed with input from Ayrton Senna, the mid-engine NSX was Honda's statement that Japanese engineering could match Ferrari — with the reliability of a Civic. An all-aluminium monocoque chassis and VTEC V6 made it one of the most advanced sports cars of its era.",full_specs:[{l:"Engine",v:"C30A 3.0L V6"},{l:"Power",v:"270ps"},{l:"Torque",v:"285 Nm"},{l:"0-100",v:"5.7s"}]},
  {make:"mazda",name:"RX-7 FD",model:"FD3S",years:"1991–2002",img:"https://images.unsplash.com/photo-1609630875171-b1321377ee65?w=800&q=80",hp:"255ps",engine:"13B-REW Rotary",drive:"RWD",weight:"1,260kg",desc:"The only mass-produced rotary sports car in history. The FD RX-7's sequential twin-turbo 13B engine delivered 255ps from just 1.3 liters of displacement, housed in one of the most aerodynamically beautiful bodies ever penned. It handled with surgical precision.",full_specs:[{l:"Engine",v:"13B-REW Rotary TT"},{l:"Power",v:"255ps"},{l:"Torque",v:"294 Nm"},{l:"0-100",v:"5.3s"}]},
  {make:"mitsubishi",name:"Lancer Evo VI",model:"CP9A",years:"1999–2001",img:"https://images.unsplash.com/photo-1544636331-e26879cd4d9b?w=800&q=80",hp:"280ps*",engine:"4G63T",drive:"AWD",weight:"1,360kg",desc:"Born from Mitsubishi's WRC campaign, the Lancer Evolution VI was perhaps the purest expression of rally-bred performance for the road. Active Yaw Control and a turbocharged 4G63 produced all-weather performance that embarrassed cars costing three times the price.",full_specs:[{l:"Engine",v:"4G63T 2.0L Turbo"},{l:"Power",v:"280ps"},{l:"Torque",v:"373 Nm"},{l:"0-100",v:"4.8s"}]},
  {make:"nissan",name:"Silvia S15",model:"S15",years:"1999–2002",img:"https://images.unsplash.com/photo-1543796076-c8a9f95ca9d6?w=800&q=80",hp:"250ps",engine:"SR20DET",drive:"RWD",weight:"1,250kg",desc:"The spiritual successor to the S13 and S14, the S15 Silvia is considered the definitive drift car. Lightweight, rear-wheel drive, with a responsive SR20DET turbocharged four-cylinder, the S15 combined elegant styling with track-ready dynamics. Revered worldwide.",full_specs:[{l:"Engine",v:"SR20DET 2.0L Turbo"},{l:"Power",v:"250ps"},{l:"Torque",v:"275 Nm"},{l:"0-100",v:"5.9s"}]},
  {make:"honda",name:"Civic Type R",model:"EK9",years:"1997–2000",img:"https://images.unsplash.com/photo-1603584173870-7f23fdae1b7a?w=800&q=80",hp:"185ps",engine:"B16B VTEC",drive:"FWD",weight:"1,050kg",desc:"185hp from a naturally aspirated 1.6-litre engine was nearly unheard of in 1997. Honda's B16B VTEC screamed to 8,600rpm, housed in a stripped-out Civic with a limited-slip differential and close-ratio gearbox. The best driver's front-wheel-drive car ever built.",full_specs:[{l:"Engine",v:"B16B 1.6L VTEC"},{l:"Power",v:"185ps (NA)"},{l:"Torque",v:"162 Nm"},{l:"0-100",v:"6.8s"}]},
  {make:"toyota",name:"MR2 SW20",model:"SW20",years:"1989–1999",img:"https://images.unsplash.com/photo-1571607388263-1044f9ea01dd?w=800&q=80",hp:"225ps",engine:"3S-GTE",drive:"RWD",weight:"1,270kg",desc:"Mid-engine, rear-wheel drive, turbocharged — the MR2 Turbo offered supercar proportions at an affordable price. The SW20's 3S-GTE engine delivered sharp, rev-happy performance, though the car's snap oversteer characteristics demanded respect from its driver.",full_specs:[{l:"Engine",v:"3S-GTE 2.0L Turbo"},{l:"Power",v:"225ps"},{l:"Torque",v:"275 Nm"},{l:"0-100",v:"6.1s"}]},
  {make:"mitsubishi",name:"3000GT VR-4",model:"Z15A",years:"1990–2000",img:"https://images.unsplash.com/photo-1568605117036-5fe5e7bab0b7?w=800&q=80",hp:"286ps*",engine:"6G72 TT",drive:"AWD",weight:"1,720kg",desc:"Mitsubishi's technological flagship pushed every boundary of what was possible in 1990. Four-wheel steering, twin-turbocharged V6, active aerodynamics with automatic rear spoiler, and all-wheel drive. The VR-4 was an engineering tour de force that competed directly with Ferrari and Porsche.",full_specs:[{l:"Engine",v:"6G72 3.0L V6 TT"},{l:"Power",v:"286ps"},{l:"Torque",v:"420 Nm"},{l:"0-100",v:"5.0s"}]}
];

function renderCars(filter){
  const grid=document.getElementById('carsGrid');
  grid.innerHTML='';
  const filtered=filter==='all'?cars:cars.filter(c=>c.make===filter);
  filtered.forEach((c,i)=>{
    const card=document.createElement('div');
    card.className='car-card';
    card.innerHTML=`<img class="car-card-img" src="${c.img}" alt="${c.name}" loading="lazy"/>
    <div class="car-card-body">
      <div class="car-card-maker">${c.make}</div>
      <div class="car-card-name">${c.name}</div>
      <div class="car-card-year">${c.model} · ${c.years}</div>
      <div class="car-card-specs">
        <div class="spec-item"><label>Power</label><span>${c.hp}</span></div>
        <div class="spec-item"><label>Engine</label><span>${c.engine}</span></div>
        <div class="spec-item"><label>Drive</label><span>${c.drive}</span></div>
        <div class="spec-item"><label>Weight</label><span>${c.weight}</span></div>
      </div>
    </div>`;
    card.addEventListener('click',()=>openModal(c));
    grid.appendChild(card);
  });
}

function filterCars(filter,btn){
  document.querySelectorAll('.filter-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderCars(filter);
}

function openModal(c){
  document.getElementById('modal-img').src=c.img;
  document.getElementById('modal-sub').textContent=c.make.toUpperCase()+' · '+c.model+' · '+c.years;
  document.getElementById('modal-title').textContent=c.name;
  document.getElementById('modal-desc').textContent=c.desc;
  const sg=document.getElementById('modal-specs');
  sg.innerHTML=c.full_specs.map(s=>`<div class="ms-item"><label>${s.l}</label><span>${s.v}</span></div>`).join('');
  document.getElementById('modal').classList.add('active');
  document.body.style.overflow='hidden';
}

function closeModal(e){
  if(e.target.id==='modal'){
    document.getElementById('modal').classList.remove('active');
    document.body.style.overflow='';
  }
}

document.querySelector('.modal-close').addEventListener('click',()=>{
  document.getElementById('modal').classList.remove('active');
  document.body.style.overflow='';
});

renderCars('all');

// Scroll reveal
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.style.opacity='1';e.target.style.transform='translateY(0)'}});
},{threshold:0.1});
document.querySelectorAll('.car-card,.tl-item,.tech-item,.about-feature').forEach(el=>{
  el.style.opacity='0';el.style.transform='translateY(24px)';el.style.transition='opacity 0.5s ease,transform 0.5s ease';
  obs.observe(el);
});
</script>
</body>
</html>
