import { useState } from "react";

const cars = [
  {
    id: 1,
    name: "Nissan Skyline GT-R",
    code: "BNR32",
    year: "1989–1994",
    engine: "RB26DETT — Twin-Turbo 2.6L Inline-6",
    power: "280 hp",
    drive: "ATTESA E-TS AWD",
    weight: "1,430 kg",
    description:
      "The R32 GT-R ended Porsche's dominance at Spa-Francorchamps and earned the name 'Godzilla' from the Australian press. Its RB26DETT engine and ATTESA all-wheel drive system set a new benchmark in performance.",
    tag: "Godzilla",
    color: "#C8A96E",
    img: "https://images.unsplash.com/photo-1632245889029-e406faaa34cd?w=900&q=80",
  },
  {
    id: 2,
    name: "Toyota Supra",
    code: "JZA80",
    year: "1993–2002",
    engine: "2JZ-GTE — Twin-Turbo 3.0L Inline-6",
    power: "280 hp (factory)",
    drive: "RWD",
    weight: "1,560 kg",
    description:
      "The A80 Supra's legendary 2JZ-GTE engine is capable of handling well over 1,000 hp with minimal modifications. Its sequential twin-turbo setup and iron block made it one of the most tunable engines ever built.",
    tag: "The Legend",
    color: "#A0C4E0",
    img: "https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=900&q=80",
  },
  {
    id: 3,
    name: "Mazda RX-7",
    code: "FD3S",
    year: "1991–2002",
    engine: "13B-REW — Sequential Twin-Rotor Wankel",
    power: "255 hp",
    drive: "RWD",
    weight: "1,280 kg",
    description:
      "The FD RX-7 was engineering poetry — sequential twin turbos on a rotary engine, wrapped in one of the most beautiful bodies ever penned. Its 50/50 weight distribution and feather-light chassis made it a driver's dream.",
    tag: "Rotary Soul",
    color: "#D4A0A0",
    img: "https://images.unsplash.com/photo-1614162692292-7ac56d7f7f1e?w=900&q=80",
  },
  {
    id: 4,
    name: "Honda NSX",
    code: "NA1",
    year: "1990–2005",
    engine: "C30A — Naturally Aspirated 3.0L V6",
    power: "270 hp",
    drive: "RWD",
    weight: "1,370 kg",
    description:
      "Developed with input from Ayrton Senna, the NSX proved Japan could build a supercar rivaling Ferrari. Its all-aluminium monocoque, mid-engine layout, and VTEC V6 offered supercar performance with everyday reliability.",
    tag: "The Daily Supercar",
    color: "#A8D8A8",
    img: "https://images.unsplash.com/photo-1612825173281-9a193378527e?w=900&q=80",
  },
  {
    id: 5,
    name: "Mitsubishi Lancer Evolution",
    code: "CP9A",
    year: "1999–2001",
    engine: "4G63T — Turbocharged 2.0L Inline-4",
    power: "280 hp",
    drive: "AYC AWD",
    weight: "1,350 kg",
    description:
      "Born from rally racing, the Evo VI Tommi Mäkinen Edition was raw, purpose-built performance. Its active yaw control and viscous centre differential gave drivers superhuman cornering ability on any surface.",
    tag: "Rally Bred",
    color: "#E0C080",
    img: "https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=900&q=80",
  },
  {
    id: 6,
    name: "Subaru Impreza WRX STI",
    code: "GC8",
    year: "1994–2000",
    engine: "EJ20 — Turbocharged 2.0L Flat-4",
    power: "280 hp",
    drive: "DCCD AWD",
    weight: "1,240 kg",
    description:
      "The GC8 STI combined the boxer engine's low centre of gravity with Subaru's driver-controlled centre differential. Its iconic exhaust note and all-weather capability made it a rally icon that translated perfectly to the road.",
    tag: "Boxer Spirit",
    color: "#80A8E0",
    img: "https://images.unsplash.com/photo-1607853202273-797f1c22a38e?w=900&q=80",
  },
];

const stats = [
  { label: "Iconic Models", value: "6" },
  { label: "Avg. Power Output", value: "274hp" },
  { label: "Years Covered", value: "1989–2002" },
  { label: "JDM Legacy", value: "∞" },
];

export default function App() {
  const [active, setActive] = useState(null);
  const [hoveredCard, setHoveredCard] = useState(null);

  const selected = cars.find((c) => c.id === active);

  return (
    <div style={{ fontFamily: "'Cormorant Garamond', 'Georgia', serif", background: "#0a0a0a", color: "#e8e2d9", minHeight: "100vh" }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600&family=Montserrat:wght@300;400;500;600;700&display=swap');
        * { box-sizing: border-box; margin: 0; padding: 0; }
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: #111; }
        ::-webkit-scrollbar-thumb { background: #444; border-radius: 2px; }
        .nav-link { font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: #a09880; text-decoration: none; transition: color 0.3s; cursor: pointer; }
        .nav-link:hover { color: #e8e2d9; }
        .car-card { cursor: pointer; transition: transform 0.4s cubic-bezier(.25,.8,.25,1); }
        .car-card:hover { transform: translateY(-6px); }
        .stat-num { font-family: 'Cormorant Garamond', serif; font-size: 48px; font-weight: 300; line-height: 1; }
        .modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.92); z-index: 1000; display: flex; align-items: center; justify-content: center; padding: 20px; animation: fadeIn 0.3s ease; }
        @keyframes fadeIn { from { opacity: 0 } to { opacity: 1 } }
        .modal-inner { background: #111; border: 1px solid #2a2a2a; max-width: 900px; width: 100%; max-height: 90vh; overflow-y: auto; animation: slideUp 0.35s cubic-bezier(.25,.8,.25,1); }
        @keyframes slideUp { from { transform: translateY(30px); opacity: 0 } to { transform: translateY(0); opacity: 1 } }
        .close-btn { background: none; border: 1px solid #333; color: #a09880; font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; padding: 10px 20px; cursor: pointer; transition: all 0.3s; }
        .close-btn:hover { border-color: #e8e2d9; color: #e8e2d9; }
        .spec-row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #1e1e1e; }
        .hero-line { width: 60px; height: 1px; background: #C8A96E; margin: 20px 0; }
        .section-label { font-family: 'Montserrat', sans-serif; font-size: 10px; letter-spacing: 3px; text-transform: uppercase; color: #C8A96E; }
        .explore-btn { font-family: 'Montserrat', sans-serif; font-size: 11px; letter-spacing: 2px; text-transform: uppercase; background: transparent; border: 1px solid #C8A96E; color: #C8A96E; padding: 14px 32px; cursor: pointer; transition: all 0.3s; }
        .explore-btn:hover { background: #C8A96E; color: #0a0a0a; }
        .grid-card-img { width: 100%; height: 220px; object-fit: cover; filter: grayscale(20%); transition: filter 0.4s, transform 0.6s; }
        .car-card:hover .grid-card-img { filter: grayscale(0%); transform: scale(1.03); }
        .overflow-hidden { overflow: hidden; }
      `}</style>

      {/* NAV */}
      <nav style={{ position: "fixed", top: 0, left: 0, right: 0, zIndex: 100, background: "rgba(10,10,10,0.95)", borderBottom: "1px solid #1a1a1a", padding: "0 48px", height: "64px", display: "flex", alignItems: "center", justifyContent: "space-between" }}>
        <div style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "22px", fontWeight: 300, letterSpacing: "4px", color: "#e8e2d9" }}>
          JDM<span style={{ color: "#C8A96E" }}>90s</span>
        </div>
        <div style={{ display: "flex", gap: "32px" }}>
          {["Heritage", "Models", "About"].map((l) => (
            <span key={l} className="nav-link">{l}</span>
          ))}
        </div>
      </nav>

      {/* HERO */}
      <div style={{ paddingTop: "64px", position: "relative", height: "100vh", display: "flex", alignItems: "center", overflow: "hidden" }}>
        <div style={{ position: "absolute", inset: 0, background: "linear-gradient(135deg, #0a0a0a 0%, #111 40%, #0d0d0d 100%)" }} />
        <div style={{ position: "absolute", right: 0, top: 0, bottom: 0, width: "55%", background: "url(https://images.unsplash.com/photo-1632245889029-e406faaa34cd?w=1200&q=80) center/cover", opacity: 0.15 }} />
        <div style={{ position: "absolute", inset: 0, background: "linear-gradient(90deg, #0a0a0a 45%, transparent 100%)" }} />

        <div style={{ position: "relative", padding: "0 80px", maxWidth: "680px" }}>
          <div className="section-label">Japanese Domestic Market · 1989–2002</div>
          <div className="hero-line" />
          <h1 style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "clamp(48px, 7vw, 88px)", fontWeight: 300, lineHeight: 1.0, color: "#e8e2d9", marginBottom: "24px" }}>
            Born in<br /><span style={{ fontStyle: "italic", color: "#C8A96E" }}>Japan.</span><br />Built for<br />Eternity.
          </h1>
          <p style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "13px", fontWeight: 300, lineHeight: 1.9, color: "#8a8070", maxWidth: "420px", marginBottom: "40px" }}>
            The golden era of Japanese performance. An era when engineers ignored convention and built machines that would define automotive culture for decades.
          </p>
          <button className="explore-btn" onClick={() => document.getElementById("models").scrollIntoView({ behavior: "smooth" })}>
            Discover the Models
          </button>
        </div>
      </div>

      {/* STATS */}
      <div style={{ background: "#0d0d0d", borderTop: "1px solid #1a1a1a", borderBottom: "1px solid #1a1a1a", padding: "60px 80px", display: "grid", gridTemplateColumns: "repeat(4, 1fr)", gap: "40px" }}>
        {stats.map((s) => (
          <div key={s.label} style={{ textAlign: "center" }}>
            <div className="stat-num" style={{ color: "#C8A96E" }}>{s.value}</div>
            <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", letterSpacing: "2px", textTransform: "uppercase", color: "#5a5040", marginTop: "10px" }}>{s.label}</div>
          </div>
        ))}
      </div>

      {/* INTRO TEXT */}
      <div style={{ padding: "100px 80px", maxWidth: "900px" }}>
        <div className="section-label">The Philosophy</div>
        <div className="hero-line" />
        <p style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "28px", fontWeight: 300, lineHeight: 1.6, color: "#c8c0b0" }}>
          In the 1990s, Japan's automakers operated under a gentleman's agreement — a self-imposed 280 hp limit. What they built within that constraint defied all expectation.
        </p>
      </div>

      {/* MODELS GRID */}
      <div id="models" style={{ padding: "0 80px 100px" }}>
        <div className="section-label">The Machines</div>
        <div className="hero-line" />
        <div style={{ display: "grid", gridTemplateColumns: "repeat(3, 1fr)", gap: "2px", marginTop: "40px" }}>
          {cars.map((car) => (
            <div key={car.id} className="car-card" onClick={() => setActive(car.id)}
              onMouseEnter={() => setHoveredCard(car.id)} onMouseLeave={() => setHoveredCard(null)}
              style={{ background: "#0d0d0d", border: "1px solid #1a1a1a", position: "relative" }}>
              <div className="overflow-hidden" style={{ height: "220px" }}>
                <img src={car.img} alt={car.name} className="grid-card-img" onError={(e) => { e.target.style.display = "none"; }} />
              </div>
              <div style={{ padding: "24px" }}>
                <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "9px", letterSpacing: "2px", textTransform: "uppercase", color: car.color, marginBottom: "8px" }}>{car.tag}</div>
                <div style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "22px", fontWeight: 400, color: "#e8e2d9", marginBottom: "4px" }}>{car.name}</div>
                <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", color: "#5a5040", letterSpacing: "1px" }}>{car.code} · {car.year}</div>
                <div style={{ marginTop: "20px", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
                  <span style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "11px", color: "#a09880" }}>{car.power}</span>
                  <span style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", letterSpacing: "2px", color: car.color, textTransform: "uppercase" }}>View →</span>
                </div>
              </div>
            </div>
          ))}
        </div>
      </div>

      {/* HERITAGE STRIP */}
      <div style={{ background: "#C8A96E", padding: "60px 80px", display: "flex", alignItems: "center", justifyContent: "space-between" }}>
        <div>
          <div style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "36px", fontWeight: 300, color: "#0a0a0a", lineHeight: 1.2 }}>
            The 280hp Gentleman's<br />Agreement
          </div>
        </div>
        <div style={{ maxWidth: "400px" }}>
          <p style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "12px", lineHeight: 1.9, color: "#3a3020", fontWeight: 300 }}>
            From 1988 to 2004, Japanese manufacturers voluntarily capped advertised power at 280 horsepower — a gentleman's agreement to avoid a power war. Reality? Most exceeded it. The Supra's 2JZ was tuned to 320+. The limit was fiction.
          </p>
        </div>
      </div>

      {/* FOOTER */}
      <footer style={{ background: "#080808", borderTop: "1px solid #1a1a1a", padding: "60px 80px", display: "flex", justifyContent: "space-between", alignItems: "flex-end" }}>
        <div>
          <div style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "28px", fontWeight: 300, color: "#e8e2d9", letterSpacing: "4px", marginBottom: "12px" }}>
            JDM<span style={{ color: "#C8A96E" }}>90s</span>
          </div>
          <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", color: "#3a3028", letterSpacing: "1px" }}>
            Japanese Domestic Market Heritage Archive
          </div>
        </div>
        <div style={{ textAlign: "right" }}>
          <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", color: "#5a5040", letterSpacing: "2px", textTransform: "uppercase", marginBottom: "6px" }}>Created by</div>
          <div style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "18px", color: "#C8A96E", fontWeight: 400, letterSpacing: "2px" }}>
            Dior Jahaj &amp; Mateo Jaho
          </div>
          <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", color: "#3a3028", marginTop: "4px" }}>
            Canadian Institute of Technology · 2026
          </div>
        </div>
      </footer>

      {/* MODAL */}
      {selected && (
        <div className="modal-overlay" onClick={() => setActive(null)}>
          <div className="modal-inner" onClick={(e) => e.stopPropagation()}>
            <div style={{ position: "relative", height: "320px", overflow: "hidden" }}>
              <img src={selected.img} alt={selected.name} style={{ width: "100%", height: "100%", objectFit: "cover", filter: "brightness(0.6)" }} onError={(e) => { e.target.style.background = "#1a1a1a"; }} />
              <div style={{ position: "absolute", inset: 0, background: "linear-gradient(0deg, #111 0%, transparent 60%)" }} />
              <div style={{ position: "absolute", bottom: "32px", left: "40px" }}>
                <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "9px", letterSpacing: "2px", textTransform: "uppercase", color: selected.color, marginBottom: "8px" }}>{selected.tag}</div>
                <h2 style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "42px", fontWeight: 300, color: "#e8e2d9", lineHeight: 1 }}>{selected.name}</h2>
                <div style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "11px", color: "#7a7060", letterSpacing: "1px", marginTop: "6px" }}>{selected.code} · {selected.year}</div>
              </div>
              <button onClick={() => setActive(null)} style={{ position: "absolute", top: "20px", right: "20px", background: "rgba(0,0,0,0.6)", border: "1px solid #333", color: "#a09880", fontFamily: "'Montserrat', sans-serif", fontSize: "18px", width: "36px", height: "36px", cursor: "pointer", display: "flex", alignItems: "center", justifyContent: "center" }}>×</button>
            </div>
            <div style={{ padding: "40px" }}>
              <p style={{ fontFamily: "'Cormorant Garamond', serif", fontSize: "19px", fontWeight: 300, lineHeight: 1.8, color: "#c8c0b0", marginBottom: "36px" }}>{selected.description}</p>
              <div style={{ borderTop: "1px solid #1e1e1e" }}>
                {[
                  ["Engine", selected.engine],
                  ["Power Output", selected.power],
                  ["Drivetrain", selected.drive],
                  ["Kerb Weight", selected.weight],
                  ["Production", selected.year],
                ].map(([k, v]) => (
                  <div key={k} className="spec-row">
                    <span style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "10px", letterSpacing: "2px", textTransform: "uppercase", color: "#5a5040" }}>{k}</span>
                    <span style={{ fontFamily: "'Montserrat', sans-serif", fontSize: "12px", color: "#c8c0b0", fontWeight: 400 }}>{v}</span>
                  </div>
                ))}
              </div>
              <div style={{ marginTop: "32px", textAlign: "right" }}>
                <button className="close-btn" onClick={() => setActive(null)}>Close</button>
              </div>
            </div>
          </div>
        </div>
      )}
    </div>
  );
}
