<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>JDM90s — Japanese Domestic Market Heritage</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --gold: #C8A96E;
      --bg: #0a0a0a;
      --bg2: #0d0d0d;
      --bg3: #080808;
      --bg4: #111;
      --border: #1a1a1a;
      --border2: #2a2a2a;
      --text: #e8e2d9;
      --text2: #c8c0b0;
      --text3: #a09880;
      --text4: #8a8070;
      --text5: #5a5040;
      --text6: #3a3028;
    }
    html { scroll-behavior: smooth; }
    body { font-family: 'Cormorant Garamond', Georgia, serif; background: var(--bg); color: var(--text); min-height: 100vh; overflow-x: hidden; }
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: #111; }
    ::-webkit-scrollbar-thumb { background: #444; border-radius: 2px; }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      background: rgba(10,10,10,0.95); border-bottom: 1px solid var(--border);
      padding: 0 48px; height: 64px; display: flex; align-items: center; justify-content: space-between;
    }
    .logo { font-family: 'Cormorant Garamond', serif; font-size: 22px; font-weight: 300; letter-spacing: 4px; color: var(--text); text-decoration: none; }
    .logo span { color: var(--gold); }
    .nav-links { display: flex; gap: 32px; }
    .nav-link { font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--text3); text-decoration: none; transition: color 0.3s; cursor: pointer; background: none; border: none; }
    .nav-link:hover { color: var(--text); }

    /* HERO */
    .hero {
      padding-top: 64px; position: relative; height: 100vh;
      display: flex; align-items: center; overflow: hidden;
    }
    .hero-bg { position: absolute; inset: 0; background: linear-gradient(135deg, #0a0a0a 0%, #111 40%, #0d0d0d 100%); }
    .hero-img {
      position: absolute; right: 0; top: 0; bottom: 0; width: 55%;
      background: url('https://upload.wikimedia.org/wikipedia/commons/0/04/Nissan_Skyline_GT-R_R32_Gun_Grey_Metallic_front_left.jpg') center/cover;
      opacity: 0.15;
    }
    .hero-fade { position: absolute; inset: 0; background: linear-gradient(90deg, #0a0a0a 45%, transparent 100%); }
    .hero-content { position: relative; padding: 0 80px; max-width: 680px; }
    .section-label { font-family: 'Montserrat', sans-serif; font-size: 10px; letter-spacing: 3px; text-transform: uppercase; color: var(--gold); }
    .hero-line { width: 60px; height: 1px; background: var(--gold); margin: 20px 0; }
    .hero-title { font-family: 'Cormorant Garamond', serif; font-size: clamp(48px, 7vw, 88px); font-weight: 300; line-height: 1.0; color: var(--text); margin-bottom: 24px; }
    .hero-title em { font-style: italic; color: var(--gold); }
    .hero-sub { font-family: 'Montserrat', sans-serif; font-size: 13px; font-weight: 300; line-height: 1.9; color: var(--text4); max-width: 420px; margin-bottom: 40px; }
    .explore-btn {
      font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; text-transform: uppercase;
      background: transparent; border: 1px solid var(--gold); color: var(--gold);
      padding: 14px 32px; cursor: pointer; transition: all 0.3s;
    }
    .explore-btn:hover { background: var(--gold); color: var(--bg); }

    /* STATS */
    .stats {
      background: var(--bg2); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border);
      padding: 60px 80px; display: grid; grid-template-columns: repeat(4, 1fr); gap: 40px;
    }
    .stat { text-align: center; }
    .stat-num { font-family: 'Cormorant Garamond', serif; font-size: 48px; font-weight: 300; line-height: 1; color: var(--gold); }
    .stat-label { font-family: 'Montserrat', sans-serif; font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--text5); margin-top: 10px; }

    /* PHILOSOPHY */
    .philosophy { padding: 100px 80px; max-width: 900px; }
    .philosophy-text { font-family: 'Cormorant Garamond', serif; font-size: 28px; font-weight: 300; line-height: 1.6; color: var(--text2); }

    /* MODELS GRID */
    .models { padding: 0 80px 100px; }
    .cars-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2px; margin-top: 40px; }
    .car-card {
      background: var(--bg2); border: 1px solid var(--border); cursor: pointer;
      transition: transform 0.4s cubic-bezier(.25,.8,.25,1); overflow: hidden;
    }
    .car-card:hover { transform: translateY(-6px); }
    .card-img-wrap { height: 220px; overflow: hidden; background: #111; }
    .card-img { width: 100%; height: 100%; object-fit: cover; filter: grayscale(20%); transition: filter 0.4s, transform 0.6s; display: block; }
    .car-card:hover .card-img { filter: grayscale(0%); transform: scale(1.03); }
    .card-body { padding: 24px; }
    .card-tag { font-family: 'Montserrat', sans-serif; font-size: 9px; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 8px; }
    .card-name { font-family: 'Cormorant Garamond', serif; font-size: 22px; font-weight: 400; color: var(--text); margin-bottom: 4px; }
    .card-code { font-family: 'Montserrat', sans-serif; font-size: 10px; color: var(--text5); letter-spacing: 1px; }
    .card-footer { margin-top: 20px; display: flex; justify-content: space-between; align-items: center; }
    .card-power { font-family: 'Montserrat', sans-serif; font-size: 11px; color: var(--text3); }
    .card-cta { font-family: 'Montserrat', sans-serif; font-size: 10px; letter-spacing: 2px; text-transform: uppercase; }

    /* HERITAGE STRIP */
    .heritage { background: var(--gold); padding: 60px 80px; display: flex; align-items: center; justify-content: space-between; gap: 60px; }
    .heritage-title { font-family: 'Cormorant Garamond', serif; font-size: 36px; font-weight: 300; color: #0a0a0a; line-height: 1.2; flex-shrink: 0; }
    .heritage-text { font-family: 'Montserrat', sans-serif; font-size: 12px; line-height: 1.9; color: #3a3020; font-weight: 300; max-width: 400px; }

    /* FOOTER */
    footer {
      background: var(--bg3); border-top: 1px solid var(--border);
      padding: 60px 80px; display: flex; justify-content: space-between; align-items: flex-end;
    }
    .footer-logo { font-family: 'Cormorant Garamond', serif; font-size: 28px; font-weight: 300; color: var(--text); letter-spacing: 4px; margin-bottom: 12px; }
    .footer-logo span { color: var(--gold); }
    .footer-sub { font-family: 'Montserrat', sans-serif; font-size: 10px; color: #3a3028; letter-spacing: 1px; }
    .footer-credit { text-align: right; }
    .credit-label { font-family: 'Montserrat', sans-serif; font-size: 10px; color: var(--text5); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 6px; }
    .credit-name { font-family: 'Cormorant Garamond', serif; font-size: 18px; color: var(--gold); font-weight: 400; letter-spacing: 2px; }
    .credit-school { font-family: 'Montserrat', sans-serif; font-size: 10px; color: #3a3028; margin-top: 4px; }

    /* MODAL */
    .modal-overlay {
      position: fixed; inset: 0; background: rgba(0,0,0,0.92); z-index: 1000;
      display: flex; align-items: center; justify-content: center; padding: 20px;
      opacity: 0; pointer-events: none; transition: opacity 0.3s;
    }
    .modal-overlay.active { opacity: 1; pointer-events: all; }
    .modal-inner {
      background: #111; border: 1px solid var(--border2); max-width: 900px; width: 100%;
      max-height: 90vh; overflow-y: auto;
      transform: translateY(30px); transition: transform 0.35s cubic-bezier(.25,.8,.25,1);
    }
    .modal-overlay.active .modal-inner { transform: translateY(0); }
    .modal-hero { position: relative; height: 320px; overflow: hidden; }
    .modal-hero-img { width: 100%; height: 100%; object-fit: cover; filter: brightness(0.6); display: block; }
    .modal-hero-fade { position: absolute; inset: 0; background: linear-gradient(0deg, #111 0%, transparent 60%); }
    .modal-hero-info { position: absolute; bottom: 32px; left: 40px; }
    .modal-tag { font-family: 'Montserrat', sans-serif; font-size: 9px; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 8px; }
    .modal-title { font-family: 'Cormorant Garamond', serif; font-size: 42px; font-weight: 300; color: var(--text); line-height: 1; }
    .modal-code { font-family: 'Montserrat', sans-serif; font-size: 11px; color: #7a7060; letter-spacing: 1px; margin-top: 6px; }
    .modal-close {
      position: absolute; top: 20px; right: 20px; background: rgba(0,0,0,0.6);
      border: 1px solid #333; color: var(--text3); font-size: 20px; width: 36px; height: 36px;
      cursor: pointer; display: flex; align-items: center; justify-content: center;
      transition: all 0.3s; line-height: 1;
    }
    .modal-close:hover { border-color: var(--text); color: var(--text); }
    .modal-body { padding: 40px; }
    .modal-desc { font-family: 'Cormorant Garamond', serif; font-size: 19px; font-weight: 300; line-height: 1.8; color: var(--text2); margin-bottom: 36px; }
    .specs-table { width: 100%; border-top: 1px solid #1e1e1e; }
    .spec-row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #1e1e1e; }
    .spec-key { font-family: 'Montserrat', sans-serif; font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--text5); }
    .spec-val { font-family: 'Montserrat', sans-serif; font-size: 12px; color: var(--text2); font-weight: 400; }
    .modal-actions { margin-top: 32px; text-align: right; }
    .close-btn {
      font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; text-transform: uppercase;
      background: none; border: 1px solid #333; color: var(--text3); padding: 10px 20px; cursor: pointer; transition: all 0.3s;
    }
    .close-btn:hover { border-color: var(--text); color: var(--text); }

    @media (max-width: 900px) {
      nav { padding: 0 24px; }
      .hero-content { padding: 0 24px; }
      .stats { padding: 40px 24px; grid-template-columns: repeat(2, 1fr); }
      .philosophy { padding: 60px 24px; }
      .models { padding: 0 24px 80px; }
      .cars-grid { grid-template-columns: repeat(2, 1fr); }
      .heritage { padding: 40px 24px; flex-direction: column; gap: 24px; }
      footer { padding: 40px 24px; flex-direction: column; gap: 32px; }
      .footer-credit { text-align: left; }
    }
    @media (max-width: 600px) {
      .cars-grid { grid-template-columns: 1fr; }
      .hero-title { font-size: 42px; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a class="logo" href="#">JDM<span>90s</span></a>
    <div class="nav-links">
      <button class="nav-link" onclick="document.querySelector('.philosophy').scrollIntoView({behavior:'smooth'})">Heritage</button>
      <button class="nav-link" onclick="document.getElementById('models').scrollIntoView({behavior:'smooth'})">Models</button>
      <button class="nav-link" onclick="document.querySelector('footer').scrollIntoView({behavior:'smooth'})">About</button>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-img"></div>
    <div class="hero-fade"></div>
    <div class="hero-content">
      <div class="section-label">Japanese Domestic Market · 1989–2002</div>
      <div class="hero-line"></div>
      <h1 class="hero-title">Born in<br /><em>Japan.</em><br />Built for<br />Eternity.</h1>
      <p class="hero-sub">The golden era of Japanese performance. An era when engineers ignored convention and built machines that would define automotive culture for decades.</p>
      <button class="explore-btn" onclick="document.getElementById('models').scrollIntoView({behavior:'smooth'})">Discover the Models</button>
    </div>
  </section>

  <!-- STATS -->
  <div class="stats">
    <div class="stat"><div class="stat-num">6</div><div class="stat-label">Iconic Models</div></div>
    <div class="stat"><div class="stat-num">274hp</div><div class="stat-label">Avg. Power Output</div></div>
    <div class="stat"><div class="stat-num">1989–2002</div><div class="stat-label">Years Covered</div></div>
    <div class="stat"><div class="stat-num">∞</div><div class="stat-label">JDM Legacy</div></div>
  </div>

  <!-- PHILOSOPHY -->
  <div class="philosophy">
    <div class="section-label">The Philosophy</div>
    <div class="hero-line"></div>
    <p class="philosophy-text">In the 1990s, Japan's automakers operated under a gentleman's agreement — a self-imposed 280 hp limit. What they built within that constraint defied all expectation.</p>
  </div>

  <!-- MODELS -->
  <section id="models" class="models">
    <div class="section-label">The Machines</div>
    <div class="hero-line"></div>
    <div class="cars-grid" id="carsGrid"></div>
  </section>

  <!-- HERITAGE STRIP -->
  <div class="heritage">
    <div class="heritage-title">The 280hp Gentleman's<br />Agreement</div>
    <p class="heritage-text">From 1988 to 2004, Japanese manufacturers voluntarily capped advertised power at 280 horsepower — a gentleman's agreement to avoid a power war. Reality? Most exceeded it. The Supra's 2JZ was tuned to 320+. The limit was fiction.</p>
  </div>

  <!-- FOOTER -->
  <footer>
    <div>
      <div class="footer-logo">JDM<span>90s</span></div>
      <div class="footer-sub">Japanese Domestic Market Heritage Archive</div>
    </div>
    <div class="footer-credit">
      <div class="credit-label">Created by</div>
      <div class="credit-name">Dior Jahaj &amp; Mateo Jaho</div>
      <div class="credit-school">Canadian Institute of Technology · 2026</div>
    </div>
  </footer>

  <!-- MODAL -->
  <div class="modal-overlay" id="modal" onclick="closeModal(event)">
    <div class="modal-inner" id="modalInner">
      <div class="modal-hero">
        <img class="modal-hero-img" id="modalImg" src="" alt="" />
        <div class="modal-hero-fade"></div>
        <div class="modal-hero-info">
          <div class="modal-tag" id="modalTag"></div>
          <div class="modal-title" id="modalTitle"></div>
          <div class="modal-code" id="modalCode"></div>
        </div>
        <button class="modal-close" onclick="hideModal()">×</button>
      </div>
      <div class="modal-body">
        <p class="modal-desc" id="modalDesc"></p>
        <div class="specs-table" id="specsTable"></div>
        <div class="modal-actions"><button class="close-btn" onclick="hideModal()">Close</button></div>
      </div>
    </div>
  </div>

  <script>
    const cars = [
      {
        id: 1, name: "Nissan Skyline GT-R", code: "BNR32", year: "1989–1994",
        engine: "RB26DETT — Twin-Turbo 2.6L Inline-6", power: "280 hp", drive: "ATTESA E-TS AWD", weight: "1,430 kg",
        description: "The R32 GT-R ended Porsche's dominance at Spa-Francorchamps and earned the name 'Godzilla' from the Australian press. Its RB26DETT engine and ATTESA all-wheel drive system set a new benchmark in performance.",
        tag: "Godzilla", color: "#C8A96E",
        img: "https://upload.wikimedia.org/wikipedia/commons/0/04/Nissan_Skyline_GT-R_R32_Gun_Grey_Metallic_front_left.jpg"
      },
      {
        id: 2, name: "Toyota Supra", code: "JZA80", year: "1993–2002",
        engine: "2JZ-GTE — Twin-Turbo 3.0L Inline-6", power: "280 hp (factory)", drive: "RWD", weight: "1,560 kg",
        description: "The A80 Supra's legendary 2JZ-GTE engine is capable of handling well over 1,000 hp with minimal modifications. Its sequential twin-turbo setup and iron block made it one of the most tunable engines ever built.",
        tag: "The Legend", color: "#A0C4E0",
        img: "https://upload.wikimedia.org/wikipedia/commons/f/f3/Toyota_Supra_A80_(54203285362).jpg"
      },
      {
        id: 3, name: "Mazda RX-7", code: "FD3S", year: "1991–2002",
        engine: "13B-REW — Sequential Twin-Rotor Wankel", power: "255 hp", drive: "RWD", weight: "1,280 kg",
        description: "The FD RX-7 was engineering poetry — sequential twin turbos on a rotary engine, wrapped in one of the most beautiful bodies ever penned. Its 50/50 weight distribution and feather-light chassis made it a driver's dream.",
        tag: "Rotary Soul", color: "#D4A0A0",
        img: "https://upload.wikimedia.org/wikipedia/commons/3/33/The_frontview_of_Mazda_RX-7_(FD3S).JPG"
      },
      {
        id: 4, name: "Honda NSX", code: "NA1", year: "1990–2005",
        engine: "C30A — Naturally Aspirated 3.0L V6", power: "270 hp", drive: "RWD", weight: "1,370 kg",
        description: "Developed with input from Ayrton Senna, the NSX proved Japan could build a supercar rivaling Ferrari. Its all-aluminium monocoque, mid-engine layout, and VTEC V6 offered supercar performance with everyday reliability.",
        tag: "The Daily Supercar", color: "#A8D8A8",
        img: "https://upload.wikimedia.org/wikipedia/commons/b/b2/Honda_NSX_(NA1)_front.JPG"
      },
      {
        id: 5, name: "Mitsubishi Lancer Evolution", code: "CP9A", year: "1999–2001",
        engine: "4G63T — Turbocharged 2.0L Inline-4", power: "280 hp", drive: "AYC AWD", weight: "1,350 kg",
        description: "Born from rally racing, the Evo VI Tommi Mäkinen Edition was raw, purpose-built performance. Its active yaw control and viscous centre differential gave drivers superhuman cornering ability on any surface.",
        tag: "Rally Bred", color: "#E0C080",
        img: "https://upload.wikimedia.org/wikipedia/commons/e/ea/The_frontview_of_Mitsubishi_LANCER_Evolution_VI_GSR.JPG"
      },
      {
        id: 6, name: "Subaru Impreza WRX STI", code: "GC8", year: "1994–2000",
        engine: "EJ20 — Turbocharged 2.0L Flat-4", power: "280 hp", drive: "DCCD AWD", weight: "1,240 kg",
        description: "The GC8 STI combined the boxer engine's low centre of gravity with Subaru's driver-controlled centre differential. Its iconic exhaust note and all-weather capability made it a rally icon that translated perfectly to the road.",
        tag: "Boxer Spirit", color: "#80A8E0",
        img: "https://upload.wikimedia.org/wikipedia/commons/1/13/Tuned_Subaru_Impreza_WRX_STi_(GC8)_at_night_front.JPG"
      }
    ];

    // Build grid
    const grid = document.getElementById('carsGrid');
    cars.forEach(car => {
      const card = document.createElement('div');
      card.className = 'car-card';
      card.innerHTML = `
        <div class="card-img-wrap">
          <img class="card-img" src="${car.img}" alt="${car.name}" onerror="this.style.display='none'" />
        </div>
        <div class="card-body">
          <div class="card-tag" style="color:${car.color}">${car.tag}</div>
          <div class="card-name">${car.name}</div>
          <div class="card-code">${car.code} · ${car.year}</div>
          <div class="card-footer">
            <span class="card-power">${car.power}</span>
            <span class="card-cta" style="color:${car.color}">View →</span>
          </div>
        </div>
      `;
      card.addEventListener('click', () => openModal(car));
      grid.appendChild(card);
    });

    function openModal(car) {
      document.getElementById('modalImg').src = car.img;
      document.getElementById('modalImg').alt = car.name;
      document.getElementById('modalTag').textContent = car.tag;
      document.getElementById('modalTag').style.color = car.color;
      document.getElementById('modalTitle').textContent = car.name;
      document.getElementById('modalCode').textContent = `${car.code} · ${car.year}`;
      document.getElementById('modalDesc').textContent = car.description;

      const specs = [
        ['Engine', car.engine],
        ['Power Output', car.power],
        ['Drivetrain', car.drive],
        ['Kerb Weight', car.weight],
        ['Production', car.year],
      ];
      const table = document.getElementById('specsTable');
      table.innerHTML = specs.map(([k, v]) => `
        <div class="spec-row">
          <span class="spec-key">${k}</span>
          <span class="spec-val">${v}</span>
        </div>
      `).join('');

      document.getElementById('modal').classList.add('active');
      document.body.style.overflow = 'hidden';
    }

    function hideModal() {
      document.getElementById('modal').classList.remove('active');
      document.body.style.overflow = '';
    }

    function closeModal(e) {
      if (e.target === document.getElementById('modal')) hideModal();
    }

    document.addEventListener('keydown', e => { if (e.key === 'Escape') hideModal(); });
  </script>
</body>
</html>
