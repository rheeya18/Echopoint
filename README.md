<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>EchoPoint – Precision Sound Detection & Localization</title>
  <style>
    :root {
      --bg: #0b1220;
      --card: #111a2b;
      --muted: #9fb2d0;
      --text: #e8f0ff;
      --brand: #6aa8ff;
      --accent: #8ef;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 18px;
    }
    * { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji"; background: var(--bg); color: var(--text); }
    a { color: var(--accent); text-decoration: none; }
    .container { width: min(1150px, 92vw); margin: 0 auto; }
    header { position: sticky; top: 0; backdrop-filter: blur(8px); background: rgba(11,18,32,.7); border-bottom: 1px solid rgba(255,255,255,.06); z-index: 50; }
    nav { display: flex; align-items: center; justify-content: space-between; padding: 14px 0; gap: 16px; }
    nav .brand { font-weight: 800; letter-spacing:.3px; }
    nav ul { display: flex; flex-wrap: wrap; gap: 14px; list-style: none; margin: 0; padding: 0; }
    nav a:hover { text-decoration: underline; }

    .hero { padding: 64px 0 32px; }
    .hero .title { font-size: clamp(28px, 5vw, 48px); line-height: 1.08; margin: 0 0 8px; }
    .hero .subtitle { color: var(--muted); margin: 0 0 22px; }
    .pill { display: inline-flex; align-items: center; gap: 8px; padding: 8px 12px; border: 1px solid rgba(255,255,255,.1); border-radius: 999px; color: var(--muted); background: rgba(255,255,255,.02); }

    .grid { display: grid; gap: 18px; }
    .grid-2 { grid-template-columns: repeat(2, minmax(0,1fr)); }
    .grid-3 { grid-template-columns: repeat(3, minmax(0,1fr)); }
    @media (max-width: 900px){ .grid-2, .grid-3 { grid-template-columns: 1fr; } }

    .card { background: linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); border: 1px solid rgba(255,255,255,.08); border-radius: var(--radius); padding: 20px; box-shadow: var(--shadow); }
    .card h3 { margin: 0 0 10px; font-size: 20px; }
    .kpi { display: grid; grid-template-columns: 1fr auto; align-items: baseline; gap: 12px; padding: 12px 0; border-bottom: 1px dashed rgba(255,255,255,.08); }
    .kpi:last-child { border-bottom: 0; }
    .kpi b { font-size: 18px; }
    .muted { color: var(--muted); }

    section { padding: 28px 0; }
    section h2 { font-size: 28px; margin: 0 0 12px; }
    .code { font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; background: #08101f; padding: 10px 12px; border-radius: 10px; border: 1px solid rgba(255,255,255,.08); display: inline-block; }

    .list { margin: 0; padding-left: 18px; }
    .list li { margin: 8px 0; }

    .role { display:flex; align-items:flex-start; gap:12px; padding:12px; border-radius:12px; background: rgba(255,255,255,.03); border:1px solid rgba(255,255,255,.06); }

    footer { border-top: 1px solid rgba(255,255,255,.08); margin-top: 40px; padding: 24px 0 56px; color: var(--muted); }
    .tag { font-size: 12px; color: var(--muted); }
    .imgbox { display:flex; align-items:center; justify-content:center; min-height: 220px; border:1px dashed rgba(255,255,255,.25); border-radius:12px; background: rgba(255,255,255,.02); }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <nav>
        <div class="brand">EchoPoint</div>
        <ul>
          <li><a href="#problem">Problem</a></li>
          <li><a href="#motivation">Motivation</a></li>
          <li><a href="#proposed">Proposed Design</a></li>
          <li><a href="#methodology">Design Considerations/Methodology</a></li>
          <li><a href="#requirements">Requirements</a></li>
          <li><a href="#simulations">Simulation Results</a></li>
          <li><a href="#prototyping">Prototyping</a></li>
          <li><a href="#testing">Testing</a></li>
          <li><a href="#analysis">Analysis of Results</a></li>
          <li><a href="#timeline">Timeline</a></li>
          <li><a href="#conclusion">Conclusion</a></li>
          <li><a href="#team">Work Division</a></li>
          <li><a href="#references">References</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero">
      <p class="pill">Precision Sound Detection & Localization System</p>
      <h1 class="title">EchoPoint</h1>
      <p class="subtitle">University of South Florida • Sponsor: Exata Tech LLC • Advisor: Dr. Zhuo Lu</p>
    </section>

    <section id="problem">
      <h2>Problem Definition</h2>
      <div class="card">
        <p>Accurately determining the direction of a sound in outdoor environments is difficult due to wind, echoes, background noise, and the lack of consumer-friendly localization tools. Existing solutions are either expensive, bulky, or limited to controlled indoor settings. Users such as hikers, campers, and first responders often need a portable way to identify where a sound is coming from, especially in scenarios where visibility is low or quick situational awareness is required. EchoPoint addresses this gap by creating a compact, multi-microphone system capable of real-time sound direction estimation with reliable accuracy.</p>
      </div>
    </section>

    <section id="motivation">
      <h2>Motivation</h2>
      <div class="card">
        <p>Sound localization has practical value in outdoor safety, wildlife awareness, navigation, and emergency response. Situations such as hearing an animal, a distressed person, or an approaching object require fast and accurate directional awareness—but humans alone often struggle to localize sound precisely.</p>
        <p>Our motivation is to make sound direction-finding accessible to anyone by designing a portable, accurate, and intuitive device. EchoPoint aims to deliver ±5° angular precision through a multi-microphone array and real-time processing, helping users stay informed, aware, and safe in unpredictable outdoor environments.</p>
      </div>
    </section>

    <section id="proposed">
      <h2>Proposed Design</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>What the System Does</h3>
          <p>EchoPoint uses a multi-microphone array and TDOA (Time Difference of Arrival) to estimate sound direction and distance in real time, with environmental sensing to contextualize noise sources.</p>
          <div class="kpi"><span class="muted">Angular precision</span><b>±5° target</b></div>
          <div class="kpi"><span class="muted">Distance error</span><b>&lt; 10%</b></div>
          <div class="kpi"><span class="muted">Processing latency</span><b>&lt; 1 s</b></div>
        </div>
        <div class="card">
          <div class="imgbox"><span class="muted">Insert design diagram / render here</span></div>
        </div>
      </div>
    </section>

    <section id="methodology">
      <h2>Design Considerations / Methodology</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Array & Mechanics</h3>
          <ul class="list">
            <li>Tripod height 5–6 ft; angled arms enable triangulation.</li>
            <li>Adjustable mic spacing 6–10″ (15–25 cm) to tune TDOA and avoid aliasing.</li>
            <li>Weather-resistant enclosure; portable and field-ready.</li>
          </ul>
          <h3>Interfaces</h3>
          <ul class="list">
            <li><b>I²S</b> for 4× INMP441 microphones (up to 48 kHz sampling).</li>
            <li><b>I²C</b> for BME280 environmental sensor.</li>
            <li><b>USB</b> serial for control & telemetry.</li>
          </ul>
        </div>
        <div class="card">
          <h3>Key Equations</h3>
          <p class="muted">Spatial aliasing constraint</p>
          <p class="code">D ≤ c / (2 f<sub>max</sub>) &nbsp; with &nbsp; c = 343&nbsp;m/s</p>
          <p>For <b>f<sub>max</sub> = 1000 Hz</b> → <b>D ≤ 0.1715 m ≈ 6.75″</b>.</p>
          <p class="muted">TDOA model</p>
          <p class="code">Δt = (d · sinθ) / v</p>
          <ul class="list">
            <li>With <b>d = 25 cm</b>, <b>v = 343 m/s</b> → max inter-mic delay ≈ <b>±730 µs</b>.</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="requirements">
      <h2>Requirements</h2>
      <div class="grid grid-3">
        <div class="card">
          <h3>Functional Requirements</h3>
          <ul class="list">
            <li>Accurately determine the angle of incoming sound within ±5°.</li>
            <li>Perform real-time sound localization using a synchronized multi-microphone array.</li>
            <li>Display direction and approximate distance on a visual interface.</li>
            <li>Adapt dynamically to environmental noise, echoes, and wind.</li>
            <li>Maintain reliable operation in outdoor conditions (portable, lightweight, durable).</li>
          </ul>
        </div>
        <div class="card">
          <h3>Engineering Requirements</h3>
          <ul class="list">
            <li>Implement signal processing algorithms (beamforming, triangulation, noise filtering).</li>
            <li>Use a microcontroller/embedded system capable of real-time audio processing.</li>
            <li>Maintain microphone synchronization and equal sampling across all channels.</li>
            <li>Provide stable power using portable or battery-based solutions.</li>
            <li>Ensure system robustness and minimize latency in direction estimation.</li>
          </ul>
        </div>
        <div class="card">
          <h3>System / Product Requirements</h3>
          <ul class="list">
            <li>Multi-microphone array prototype.</li>
            <li>Real-time signal processing hardware integrated with the array.</li>
            <li>User interface that visualizes the sound’s direction and approximate distance.</li>
            <li>Documentation covering design decisions, testing procedures, results, and scalability recommendations.</li>
            <li>Completion of SRR, SBDR, PDR, and CDR design reviews.</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="simulations">
      <h2>Simulation Results</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Analytical</h3>
          <ul class="list">
            <li>TDOA model with d = 25 cm, v = 343 m/s.</li>
            <li>Delays resolvable within Teensy timing precision.</li>
          </ul>
        </div>
        <div class="card">
          <h3>MATLAB (Concept)</h3>
          <ul class="list">
            <li>fs = 44.1 kHz, 4× mics, 25 cm spacing.</li>
            <li>Angle detection across −90°…+90° with ≤ ±5° error (simulated).</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="prototyping">
      <h2>Prototyping</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Hardware</h3>
          <ul class="list">
            <li>Teensy 4.1 controller; custom perfboard with headers and screw terminals.</li>
            <li>4× INMP441 I²S MEMS microphones on breakouts.</li>
            <li>BME280 sensor over I²C; portable 5 V power bank.</li>
          </ul>
        </div>
        <div class="card">
          <h3>Software</h3>
          <ul class="list">
            <li>Embedded C++ on Teensy (capture, buffering, FFT/TDOA pipeline).</li>
            <li>Python host utility for serial commands and telemetry visualization.</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="testing">
      <h2>Testing</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Plan</h3>
          <ul class="list">
            <li><b>Unit</b>: Power, I²C (BME280), I²S (mics).</li>
            <li><b>Calibration</b>: mic timing, gain, geometry.</li>
            <li><b>Indoor</b>: localization with known sources.</li>
            <li><b>Outdoor</b>: wind/noise/echo robustness.</li>
            <li><b>Integration</b>: data fusion, latency, display.</li>
          </ul>
        </div>
        <div class="card">
          <h3>Metrics</h3>
          <div class="kpi"><span class="muted">Angular precision</span><b>±5° target</b></div>
          <div class="kpi"><span class="muted">Distance estimation</span><b>&lt; 10% error</b></div>
          <div class="kpi"><span class="muted">Processing latency</span><b>&lt; 1 s</b></div>
          <div class="kpi"><span class="muted">SNR improvement</span><b>quantified vs baseline</b></div>
        </div>
      </div>
    </section>

    <section id="analysis">
      <h2>Analysis of Results</h2>
      <div class="card">
        <ul class="list">
          <li>Simulated angular error within ±5° across −90°…+90° indicates acceptable array geometry.</li>
          <li>Expected max TDOA ≈ ±730 µs is measurable on Teensy 4.1, enabling robust cross-correlation.</li>
          <li>Environmental data (BME280) supports velocity-of-sound compensation in post-processing.</li>
        </ul>
      </div>
    </section>

    <section id="timeline">
      <h2>Timeline</h2>
      <div class="card">
        <ul class="list">
          <li><b>Week 1–2:</b> Hardware bring-up (power, I²C/I²S) and mic calibration.</li>
          <li><b>Week 3–4:</b> TDOA pipeline integration; indoor tests & parameter sweeps.</li>
          <li><b>Week 5:</b> Outdoor validation; latency & accuracy tuning.</li>
          <li><b>Week 6:</b> Final integration; documentation; demo.</li>
        </ul>
      </div>
    </section>

    <section id="conclusion">
      <h2>Conclusion</h2>
      <div class="card">
        <p>EchoPoint demonstrates a portable, low-cost acoustic localization platform that meets targeted accuracy and latency using a Teensy-based microphone array and TDOA processing. Next work focuses on full-field validation and UI polish for deployment-ready demonstrations.</p>
      </div>
    </section>

    <section id="team">
      <h2>Work Division</h2>
      <div class="grid grid-2">
        <div class="card">
          <div class="role"><div>
            <strong>Rheeya Patel</strong> — <em>Project Lead & Testing Validation</em>
            <div class="tag">Coordination, documentation, sponsor liaison; field testing, data analysis, calibration.</div>
          </div></div>
          <div class="role"><div>
            <strong>Sophia Tompkins</strong> — <em>Hardware Lead</em>
            <div class="tag">Microphone array design, wiring/boards, mechanical.</div>
          </div></div>
          <div class="role"><div>
            <strong>Olmedo Alonso Lopez</strong> — <em>Signal Processing Lead</em>
            <div class="tag">TDOA/FFT pipeline, simulation, optimization.</div>
          </div></div>
          <div class="role"><div>
            <strong>Nicholas Wasselle</strong> — <em>Software/Embedded Lead</em>
            <div class="tag">Firmware, host UI, real-time integration.</div>
          </div></div>
        </div>
        <div class="card">
          <h3>Affiliations</h3>
          <ul class="list">
            <li><b>Advisor:</b> Dr. Zhuo Lu</li>
            <li><b>Sponsor:</b> Exata Tech LLC</li>
            <li><b>Institution:</b> University of South Florida</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="demo">
      <h2>Demo Video</h2>
      <div class="card" style="text-align:center;">
        <div class="imgbox" style="flex-direction:column;">
          <video controls style="max-width:100%;border-radius:12px;">
            <source src="demo-video.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p class="muted" style="margin-top:8px;">Project demonstration video showcasing EchoPoint in action</p>
        </div>
      </div>
    </section>

<section id="gallery">
  <h2>Gallery</h2>
  <div class="card">
    <p class="muted">Progress photos showing EchoPoint’s evolution from early breadboards to field-ready tests.</p>
    <div class="grid grid-3">
      <div class="imgbox">
        <img src="images/gallery/prototype1.jpg" alt="Early EchoPoint breadboard prototype" style="max-width:100%; border-radius:12px;">
      </div>
      <div class="imgbox">
        <img src="images/gallery/prototype2.jpg" alt="Microphone array assembly" style="max-width:100%; border-radius:12px;">
      </div>
      <div class="imgbox">
        <img src="images/gallery/test-setup.jpg" alt="Indoor test setup" style="max-width:100%; border-radius:12px;">
      </div>
      <div class="imgbox">
        <img src="images/gallery/outdoor-demo.jpg" alt="Outdoor EchoPoint demo" style="max-width:100%; border-radius:12px;">
      </div>
      <!-- Add more images as needed -->
    </div>
  </div>
</section>

    <section id="references">
      <h2>References</h2>
      <div class="card">
        <ul class="list">
          <li>INMP441 Datasheet (I²S digital MEMS microphone).</li>
          <li>BME280 Datasheet (Temperature/Pressure/Humidity sensor).</li>
          <li>Teensy 4.1 Technical Reference Manual.</li>
          <li>Standard acoustics texts for TDOA and array processing fundamentals.</li>
        </ul>
      </div>
    </section>

    <footer>
      <div class="container">
        <div>© EchoPoint — University of South Florida Capstone Project.</div>
      </div>
    </footer>
  </main>
</body>
</html>
