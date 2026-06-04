    <!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>JFX Electricidad | Hurlingham BS. As.</title>
  <meta name="description" content="Electricidad domiciliaria y armado de complejos, barrios cerrados y edificios. Presupuestos 24hs." />

  <style>
    :root{
      --bg: #070A12;
      --card: rgba(255,255,255,.06);
      --card2: rgba(255,255,255,.09);
      --text: rgba(255,255,255,.92);
      --muted: rgba(255,255,255,.68);
      --brand: #49D6FF;
      --brand2:#7C5CFF;
      --good:#3EF2B1;
      --warn:#FFD35C;
      --danger:#FF5C7A;
      --shadow: 0 18px 55px rgba(0,0,0,.45);
      --radius: 18px;
      --radius2: 26px;
      --ring: 0 0 0 3px rgba(73,214,255,.25);
      --max: 1140px;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background:
        radial-gradient(1200px 500px at 10% -10%, rgba(73,214,255,.35), transparent 60%),
        radial-gradient(900px 450px at 90% 0%, rgba(124,92,255,.25), transparent 55%),
        radial-gradient(900px 600px at 60% 100%, rgba(62,242,177,.15), transparent 60%),
        var(--bg);
      color: var(--text);
      overflow-x:hidden;
    }

    a{color:inherit; text-decoration:none}
    button,input,select,textarea{font:inherit}
    .container{max-width: var(--max); margin:0 auto; padding: 0 20px}

    /* Top bar */
    .topbar{
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: linear-gradient(to bottom, rgba(7,10,18,.85), rgba(7,10,18,.55));
      border-bottom: 1px solid rgba(255,255,255,.08);
    }
    .topbar .inner{
      display:flex; align-items:center; justify-content:space-between;
      padding: 14px 0;
      gap: 14px;
    }
    .brand{
      display:flex; align-items:center; gap: 12px;
      min-width: 220px;
    }
    .logo{
      width: 42px; height: 42px; border-radius: 14px;
      background:
        radial-gradient(circle at 30% 30%, rgba(255,255,255,.25), transparent 45%),
        linear-gradient(135deg, rgba(73,214,255,1), rgba(124,92,255,1));
      box-shadow: 0 18px 40px rgba(73,214,255,.22);
      position: relative;
      overflow:hidden;
    }
    .logo:after{
      content:"";
      position:absolute; inset:-40%;
      background: conic-gradient(from 180deg, rgba(255,255,255,.0), rgba(255,255,255,.35), rgba(255,255,255,.0));
      animation: spin 4.8s linear infinite;
      opacity:.55;
    }
    @keyframes spin {to{transform: rotate(360deg)}}

    .brand h1{
      font-size: 15px;
      margin:0;
      letter-spacing:.2px;
    }
    .brand p{
      margin:0;
      font-size: 12px;
      color: var(--muted);
    }

    .nav{
      display:flex; gap: 16px; align-items:center;
      flex-wrap: wrap;
      justify-content:flex-end;
    }
    .nav a{
      padding: 10px 12px;
      border-radius: 14px;
      color: var(--muted);
      border: 1px solid transparent;
      transition: .2s ease;
      font-size: 13px;
    }
    .nav a:hover{border-color: rgba(255,255,255,.12); color: var(--text); transform: translateY(-1px)}
    .cta{
      display:flex; gap:10px; align-items:center;
    }
    .btn{
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      color: var(--text);
      padding: 11px 14px;
      border-radius: 16px;
      cursor:pointer;
      transition:.2s ease;
      box-shadow: 0 10px 26px rgba(0,0,0,.25);
      display:inline-flex; align-items:center; gap:10px;
      white-space:nowrap;
    }
    .btn:hover{transform: translateY(-1px); border-color: rgba(255,255,255,.22); background: rgba(255,255,255,.08)}
    .btn-primary{
      border-color: rgba(73,214,255,.35);
      background: linear-gradient(135deg, rgba(73,214,255,.18), rgba(124,92,255,.14));
    }
    .btn-primary:focus{outline:none; box-shadow: var(--ring), var(--shadow)}
    .btn .dot{
      width: 10px; height: 10px; border-radius: 999px;
      background: var(--good);
      box-shadow: 0 0 0 5px rgba(62,242,177,.12);
    }

    /* Hero */
    .hero{
      padding: 54px 0 20px;
      position: relative;
    }
    .hero-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 22px;
      align-items: start;
    }
    @media (max-width: 980px){
      .hero-grid{grid-template-columns: 1fr; }
      .brand{min-width: auto}
      .nav{justify-content:flex-start}
    }

    .badge{
      display:inline-flex; align-items:center; gap:10px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.05);
      padding: 10px 12px;
      border-radius: 999px;
      color: var(--muted);
      font-size: 13px;
    }
    .badge strong{color: var(--text)}
    .hero h2{
      font-size: clamp(30px, 4vw, 48px);
      margin: 14px 0 10px;
      line-height: 1.05;
      letter-spacing: -0.6px;
    }
    .grad-text{
      background: linear-gradient(135deg, var(--brand), var(--brand2));
      -webkit-background-clip:text;
      background-clip:text;
      color: transparent;
    }
    .hero p{
      margin: 0 0 18px;
      color: var(--muted);
      font-size: 15.5px;
      line-height: 1.6;
      max-width: 60ch;
    }
    .hero-actions{
      display:flex; gap:12px; flex-wrap:wrap; margin-top: 16px;
    }

    .hero-card{
      background: linear-gradient(180deg, rgba(255,255,255,.09), rgba(255,255,255,.04));
      border: 1px solid rgba(255,255,255,.10);
      border-radius: var(--radius2);
      box-shadow: var(--shadow);
      overflow:hidden;
      position: relative;
    }
    .hero-card .inner{
      padding: 18px;
    }
    .spark{
      height: 10px;
      background: linear-gradient(90deg, rgba(73,214,255,.0), rgba(73,214,255,.8), rgba(124,92,255,.8), rgba(124,92,255,.0));
      opacity:.75;
      border-radius: 999px;
      margin-bottom: 14px;
    }

    .quick-grid{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }
    .q{
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.10);
      border-radius: 16px;
      padding: 12px;
      min-height: 88px;
    }
    .q .k{
      display:flex; align-items:center; justify-content:space-between;
      gap:10px;
      margin-bottom: 6px;
    }
    .icon{
      width: 38px; height: 38px; border-radius: 14px;
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.10);
      display:grid; place-items:center;
      font-size: 18px;
    }
    .q strong{font-size: 13px}
    .q span{display:block; color: var(--muted); font-size: 12.5px; line-height:1.3}

    .section{
      padding: 54px 0;
    }
    .section-title{
      display:flex; align-items:flex-end; justify-content:space-between; gap: 16px;
      margin-bottom: 18px;
    }
    .section-title h3{
      margin:0;
      font-size: 22px;
      letter-spacing: -0.2px;
    }
    .section-title p{
      margin:0;
      color: var(--muted);
      font-size: 13.5px;
      max-width: 55ch;
      line-height:1.5;
    }

    .grid-2{
      display:grid; grid-template-columns: 1fr 1fr; gap: 18px;
    }
    @media (max-width: 900px){ .grid-2{grid-template-columns: 1fr} }

    .card{
      background: var(--card);
      border: 1px solid rgba(255,255,255,.10);
      border-radius: var(--radius);
      box-shadow: 0 12px 32px rgba(0,0,0,.25);
    }
    .card .pad{padding: 18px}

    /* Interactive portfolio/filter */
    .filterbar{
      display:flex; gap: 10px; flex-wrap:wrap;
      margin-bottom: 14px;
    }
    .chip{
      cursor:pointer;
      padding: 10px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      color: var(--muted);
      font-size: 13px;
      transition:.18s ease;
      user-select:none;
    }
    .chip.active{
      color: var(--text);
      border-color: rgba(73,214,255,.4);
      background: linear-gradient(135deg, rgba(73,214,255,.18), rgba(124,92,255,.12));
    }
    .portfolio-grid{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
    }
    @media (max-width: 980px){ .portfolio-grid{grid-template-columns: repeat(2, 1fr);} }
    @media (max-width: 560px){ .portfolio-grid{grid-template-columns: 1fr;} }

    .work{
      padding: 14px;
      border-radius: 18px;
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(255,255,255,.10);
      transition:.18s ease;
      position: relative;
      overflow:hidden;
      min-height: 128px;
    }
    .work:hover{transform: translateY(-2px); border-color: rgba(255,255,255,.18); background: rgba(255,255,255,.06)}
    .work h4{margin: 10px 0 6px; font-size: 14.5px}
    .work p{margin:0; color: var(--muted); font-size: 12.8px; line-height:1.45}
    .tagrow{display:flex; gap: 8px; flex-wrap:wrap; margin-top: 10px}
    .tag{
      font-size: 12px;
      color: rgba(255,255,255,.78);
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.03);
      padding: 6px 10px;
      border-radius: 999px;
    }
    .tag.hot{border-color: rgba(73,214,255,.35); background: rgba(73,214,255,.10)}
    .tag.purple{border-color: rgba(124,92,255,.35); background: rgba(124,92,255,.10)}

    /* Accordion */
    details{
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(255,255,255,.10);
      border-radius: 16px;
      padding: 10px 14px;
    }
    summary{
      cursor:pointer;
      list-style:none;
      display:flex; align-items:center; justify-content:space-between; gap: 12px;
      font-weight: 650;
      color: var(--text);
    }
    summary::-webkit-details-marker{display:none}
    .chev{opacity:.75; transition:.18s ease}
    details[open] .chev{transform: rotate(180deg)}
    details .body{
      margin-top: 10px;
      color: var(--muted);
      line-height:1.6;
      font-size: 13.5px;
    }

    /* Testimonials */
    .carousel{
      display:grid;
      grid-template-columns: 1fr;
      gap: 12px;
    }
    .quote{
      padding: 18px;
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
      position: relative;
      overflow:hidden;
    }
    .quote:before{
      content:"“";
      position:absolute;
      left: 16px;
      top: -10px;
      font-size: 60px;
      opacity:.15;
      color: var(--brand);
    }
    .quote .name{margin-top: 12px; color: var(--muted); font-size: 13px}
    .quote .stars{color: var(--warn); letter-spacing:2px; font-size: 12px}
    .carousel-controls{
      display:flex; gap: 10px; justify-content:flex-end; flex-wrap:wrap;
    }

    /* Counters */
    .stats{
      display:grid; grid-template-columns: repeat(4, 1fr); gap: 12px;
    }
    @media (max-width: 980px){ .stats{grid-template-columns: repeat(2, 1fr);} }
    @media (max-width: 520px){ .stats{grid-template-columns: 1fr;} }
    .stat{
      padding: 16px;
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
    }
    .stat .num{
      font-size: 28px;
      font-weight: 800;
      letter-spacing: -0.6px;
      margin: 0 0 6px;
    }
    .stat .lbl{color: var(--muted); margin:0; font-size: 13.5px; line-height:1.4}

    /* Form */
    form{display:grid; gap: 12px}
    .form-grid{
      display:grid; grid-template-columns: 1fr 1fr;
      gap: 12px;
    }
    @media (max-width: 720px){ .form-grid{grid-template-columns: 1fr;} }
    label{
      display:grid;
      gap: 7px;
      color: var(--muted);
      font-size: 13px;
    }
    input, select, textarea{
      width:100%;
      padding: 12px 12px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      color: var(--text);
      outline:none;
      transition:.18s ease;
    }
    textarea{min-height: 110px; resize: vertical}
    input:focus, select:focus, textarea:focus{
      border-color: rgba(73,214,255,.45);
      box-shadow: var(--ring);
    }
    .hint{
      color: var(--muted);
      font-size: 12.5px;
      line-height:1.5;
      margin-top: -4px;
    }
    .form-actions{
      display:flex; gap: 12px; flex-wrap:wrap; align-items:center;
      justify-content:space-between;
    }
    .small{
      color: var(--muted);
      font-size: 12.5px;
      line-height:1.4;
    }
    .toast{
      display:none;
      margin-top: 10px;
      padding: 12px;
      border-radius: 16px;
      border: 1px solid rgba(62,242,177,.35);
      background: rgba(62,242,177,.10);
      color: rgba(255,255,255,.9);
    }

    /* Footer */
    footer{
      padding: 28px 0 70px;
      color: var(--muted);
      font-size: 13px;
    }
    .footer-grid{
      display:flex; justify-content:space-between; align-items:center; gap: 10px; flex-wrap:wrap;
      border-top: 1px solid rgba(255,255,255,.10);
      padding-top: 18px;
    }

    /* Floating WhatsApp */
    .wa-float{
      position: fixed;
      right: 18px;
      bottom: 18px;
      z-index: 80;
    }
    .wa-btn{
      width: 58px; height: 58px;
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,.15);
      background: linear-gradient(135deg, #22c55e, #10b981);
      box-shadow: 0 18px 42px rgba(16,185,129,.25);
      display:grid; place-items:center;
      cursor:pointer;
      transition:.18s ease;
    }
    .wa-btn:hover{transform: translateY(-3px) scale(1.02)}
    .wa-btn svg{filter: drop-shadow(0 10px 20px rgba(0,0,0,.25))}
    .wa-sub{
      position:absolute;
      right: 70px;
      bottom: 10px;
      background: rgba(0,0,0,.55);
      border: 1px solid rgba(255,255,255,.12);
      backdrop-filter: blur(10px);
      padding: 10px 12px;
      border-radius: 14px;
      color: rgba(255,255,255,.92);
      font-size: 12.5px;
      max-width: 220px;
      display:none;
    }
    @media (min-width: 900px){
      .wa-float:hover .wa-sub{display:block}
    }

    /* Smooth scroll */
    html{scroll-behavior:smooth}
    .sr-only{
      position:absolute;
      width:1px;height:1px;
      padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0;
    }
  </style>
</head>

<body>
  <!-- Topbar -->
  <header class="topbar">
    <div class="container">
      <div class="inner">
        <div class="brand">
          <div class="logo" aria-hidden="true"></div>
          <div>
            <h1>JFX Electricidad</h1>
            <p>Hurlingham · Electricidad domiciliaria y complejos</p>
          </div>
        </div>

        <nav class="nav" aria-label="Navegación">
          <a href="#servicios">Servicios</a>
          <a href="#historia">Historia</a>
          <a href="#trabajos">Trabajos</a>
          <a href="#clientes">Clientes</a>
          <a href="#presupuesto">Presupuesto</a>
        </nav>

        <div class="cta">
          <a class="btn btn-primary" href="#presupuesto" title="Pedir presupuesto">
            <span class="dot" aria-hidden="true"></span>
            Pedí tu presupuesto
          </a>
        </div>
      </div>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero">
    <div class="container">
      <div class="hero-grid">
        <div>
          <div class="badge">
            <span>⚡ Atención 24hs · </span><strong>Lunes a Domingo</strong>
          </div>

          <h2>
            Electricidad confiable para <span class="grad-text">tu hogar</span> y para
            <span class="grad-text">complejos</span>, barrios cerrados y edificios
          </h2>

          <p>
            Soluciones para instalaciones eléctricas domiciliarias, armado y mejoras en conjuntos,
            con respuesta rápida, orden en obra y comunicación clara.
          </p>

          <div class="hero-actions">
            <a class="btn btn-primary" href="#trabajos">
              Ver trabajos realizados
              <span aria-hidden="true">→</span>
            </a>
            <a class="btn" href="#presupuesto">
              Pedir presupuesto
              <span aria-hidden="true">🧾</span>
            </a>
            <a class="btn" href="javascript:void(0)" id="btnWhatsAppInline" title="Abrir WhatsApp">
              Consultar por WhatsApp
              <span aria-hidden="true">💬</span>
            </a>
          </div>
        </div>

        <aside class="hero-card" aria-label="Resumen rápido">
          <div class="inner">
            <div class="spark"></div>

            <div class="quick-grid">
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">🏠</div>
                  <strong>Domiciliaria</strong>
                </div>
                <span>Cortes, tableros, luminarias, tomas, cableado y más.</span>
              </div>
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">🏢</div>
                  <strong>Edificios</strong>
                </div>
                <span>Instalaciones, armado y mantenimiento eléctrico.</span>
              </div>
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">🏘️</div>
                  <strong>Barrios cerrados</strong>
                </div>
                <span>Trabajos en complejos y zonas comunes.</span>
              </div>
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">🚨</div>
                  <strong>Emergencias</strong>
                </div>
                <span>Atención de urgencias · respuesta 24hs.</span>
              </div>
            </div>

            <div style="margin-top: 14px" class="hint">
              <strong>Disponibilidad:</strong> Lunes a Domingo, <strong>24hs</strong> (incluye emergencias).
            </div>
          </div>
        </aside>
      </div>
    </div>
  </section>

  <!-- Servicios / Interactivo -->
  <section id="servicios" class="section">
    <div class="container">
      <div class="section-title">
        <div>
          <h3>Servicios</h3>
          <p>Elegí el tipo de trabajo para ver el enfoque (interactivo) y lo que normalmente abarcamos.</p>
        </div>
      </div>

      <div class="grid-2">
        <div class="card">
          <div class="pad">
            <div class="filterbar" role="tablist" aria-label="Filtrar servicios">
              <span class="chip active" data-mode="todos" role="tab" aria-selected="true">Todos</span>
              <span class="chip" data-mode="domiciliaria" role="tab" aria-selected="false">Domiciliaria</span>
              <span class="chip" data-mode="complejos" role="tab" aria-selected="false">Complejos</span>
              <span class="chip" data-mode="barrios" role="tab" aria-selected="false">Barrios cerrados</span>
              <span class="chip" data-mode="edificios" role="tab" aria-selected="false">Edificios</span>
            </div>

            <div id="serviceDetails" style="display:grid; gap:12px;">
              <details open>
                <summary>
                  ¿Cómo trabajamos?
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Diagnóstico, plan de acción y ejecución con orden. Trabajamos con comunicación clara
                  para que sepas qué se hace, cómo y cuándo.
                </div>
              </details>

              <details>
                <summary>
                  Seguridad y criterios de obra
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Instalaciones prolijas, verificaciones y recomendaciones para el uso seguro.
                  En emergencias priorizamos la estabilización y luego la solución completa.
                </div>
              </details>

              <details>
                <summary>
                  ¿Qué incluye un presupuesto?
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Alcance del trabajo, materiales sugeridos (cuando aplica), mano de obra, tiempos
                  estimados y condiciones para avanzar.
                </div>
              </details>
            </div>
          </div>
        </div>

        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 10px; font-size:16.5px">Atención rápida (Hurlingham y alrededores)</h4>
            <p style="margin:0 0 12px; color: var(--muted); line-height:1.6; font-size: 13.8px;">
              Si es urgente, contanos el síntoma (por ejemplo: “se corta”, “salta térmica”, “sin luz en sector”)
              y te orientamos para un diagnóstico inicial.
            </p>

            <div class="stats" style="margin-top: 12px">
              <div class="stat">
                <div class="num" data-count="24">0</div>
                <p class="lbl">Atención 24hs<br/>Lun a Dom</p>
              </div>
              <div class="stat">
                <div class="num" data-count="500">0</div>
                <p class="lbl">Obras y mantenimientos<br/>(estimado)</p>
              </div>
              <div class="stat">
                <div class="num" data-count="15">0</div>
                <p class="lbl">Años de experiencia<br/>(aprox.)</p>
              </div>
              <div class="stat">
                <div class="num" data-count="100">0</div>
                <p class="lbl">Comunicación clara<br/>en cada paso</p>
              </div>
            </div>

            <div class="hint" style="margin-top: 12px">
              *Los números pueden ajustarse a tu realidad. Decime y lo dejamos exacto.
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Historia -->
  <section id="historia" class="section">
    <div class="container">
      <div class="section-title">
        <div>
          <h3>Historia de la empresa</h3>
          <p>Una marca nacida para resolver problemas eléctricos con responsabilidad y continuidad.</p>
        </div>
      </div>

      <div class="grid-2">
        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 10px; font-size:16.5px">JFX en Hurlingham (Bs. As.)</h4>
            <p style="margin:0; color: var(--muted); line-height:1.7; font-size: 13.8px;">
              En <strong>Hurlingham, Buenos Aires</strong>, JFX Electricidad creció con un enfoque simple:
              atender como se debe, dar soluciones duraderas y mantener a los clientes al tanto durante todo el proceso.
              Desde instalaciones domiciliarias hasta obras de mayor envergadura, trabajamos con profesionalismo,
              cumplimiento y cuidado en cada proyecto.
            </p>

            <div style="margin-top:14px; display:grid; gap:10px;">
              <div class="badge" style="justify-content:flex-start; border-radius: 16px;">
                <span aria-hidden="true">📍</span>
                <span><strong>Base:</strong> Hurlingham</span>
              </div>
              <div class="badge" style="justify-content:flex-start; border-radius: 16px;">
                <span aria-hidden="true">🛠️</span>
                <span><strong>Especialidad:</strong> electricidad domiciliaria y armado de complejos</span>
              </div>
              <div class="badge" style="justify-content:flex-start; border-radius: 16px;">
                <span aria-hidden="true">⚡</span>
                <span><strong>Respuesta:</strong> emergencias 24hs</span>
              </div>
            </div>
          </div>
        </div>

        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 10px; font-size:16.5px">Nuestros valores</h4>
            <div style="display:grid; gap:12px;">
              <details open>
                <summary>
                  Honestidad en el diagnóstico
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Te decimos qué está pasando, qué conviene hacer y cuál es la solución más segura.
                </div>
              </details>
              <details>
                <summary>
                  Calidad y prolijidad
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Trabajo cuidado para instalaciones eléctricas que se mantienen en el tiempo.
                </div>
              </details>
              <details>
                <summary>
                  Compromiso con el cliente
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">
                  Coordinación clara y atención con respeto. En emergencias priorizamos rapidez.
                </div>
              </details>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Trabajos realizados (interactivo) -->
  <section id="trabajos" class="section">
    <div class="container">
      <div class="section-title">
        <div>
          <h3>Trabajos realizados</h3>
          <p>Mostrá tu portfolio por tipo de obra. (Podés reemplazar los textos por tus proyectos reales).</p>
        </div>
      </div>

      <div class="card">
        <div class="pad">
          <div class="filterbar" aria-label="Filtrar trabajos">
            <span class="chip active" data-work="all">Todo</span>
            <span class="chip" data-work="domiciliaria">Domiciliaria</span>
            <span class="chip" data-work="complejos">Complejos</span>
            <span class="chip" data-work="barrios">Barrios cerrados</span>
            <span class="chip" data-work="edificios">Edificios</span>
          </div>

          <div class="portfolio-grid" id="workGrid">
            <!-- items -->
            <div class="work" data-cat="domiciliaria">
              <div class="tagrow">
                <span class="tag hot">Tableros</span>
                <span class="tag purple">Seguridad</span>
              </div>
              <h4>Actualización de tablero y térmicas</h4>
              <p>Ordenamiento de circuito, verificación y mejoras para un funcionamiento estable.</p>
            </div>

            <div class="work" data-cat="domiciliaria">
              <div class="tagrow">
                <span class="tag hot">Cableado</span>
              </div>
              <h4>Tomas y luminarias</h4>
              <p>Instalación prolija de puntos eléctricos y puesta a punto.</p>
            </div>

            <div class="work" data-cat="complejos">
              <div class="tagrow">
                <span class="tag purple">Armado</span>
                <span class="tag hot">Obra</span>
              </div>
              <h4>Armado de complejos</h4>
              <p>Instalación eléctrica para áreas comunes y sectores de servicios.</p>
            </div>

            <div class="work" data-cat="barrios">
              <div class="tagrow">
                <span class="tag purple">Zonas comunes</span>
              </div>
              <h4>Barrios cerrados</h4>
              <p>Soporte eléctrico para iluminación, tableros y mantenimiento programado.</p>
            </div>

            <div class="work" data-cat="edificios">
              <div class="tagrow">
                <span class="tag hot">Edificio</span>
                <span class="tag purple">Mantenimiento</span>
              </div>
              <h4>Servicios eléctricos para edificios</h4>
              <p>Revisión, correcciones y mantenimiento para asegurar continuidad.</p>
            </div>

            <div class="work" data-cat="complejos">
              <div class="tagrow">
                <span class="tag hot">Instalaciones</span>
              </div>
              <h4>Mejoras y ampliaciones</h4>
              <p>Ampliación de circuitos y adecuación según necesidad del proyecto.</p>
            </div>
          </div>

          <div class="hint" style="margin-top: 12px">
            Tip: tocá / clickeá los filtros para ver solo los trabajos de esa categoría.
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Clientes -->
  <section id="clientes" class="section">
    <div class="container">
      <div class="section-title">
        <div>
          <h3>Clientes satisfechos</h3>
          <p>Testimonios (ajustalos con nombres reales y experiencias reales).</p>
        </div>
      </div>

      <div class="grid-2">
        <div class="carousel">
          <div class="quote" id="quoteBox">
            <div class="stars" id="quoteStars">★★★★★</div>
            <p id="quoteText" style="margin:0; line-height:1.7; font-size: 14.2px; color: rgba(255,255,255,.88)">
              “Respondieron rápido por una emergencia, dejaron todo prolijo y explicaron claramente qué se estaba haciendo.”
            </p>
            <div class="name" id="quoteName">— Cliente en Hurlingham</div>
          </div>

          <div class="carousel-controls">
            <button class="btn" type="button" id="prevQuote">← Anterior</button>
            <button class="btn btn-primary" type="button" id="nextQuote">
              Siguiente →
            </button>
          </div>
        </div>

        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 10px; font-size:16.5px">Promesa de atención</h4>
            <div style="display:grid; gap:12px;">
              <details open>
                <summary>
                  Coordinación y tiempos
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">Te brindamos una estimación y nos comunicamos durante la ejecución.</div>
              </details>
              <details>
                <summary>
                  Presupuesto claro
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">Sin vueltas: alcance, mano de obra y condiciones para avanzar.</div>
              </details>
              <details>
                <summary>
                  Atención de emergencias
                  <span class="chev" aria-hidden="true">▾</span>
                </summary>
                <div class="body">Si es urgente, priorizamos estabilizar y resolver con seguridad.</div>
              </details>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Presupuesto -->
  <section id="presupuesto" class="section">
    <div class="container">
      <div class="section-title">
        <div>
          <h3>Pedí presupuesto</h3>
          <p>
            Completá el formulario y te respondemos. Horarios: <strong>Lunes a Domingo 24hs</strong> (emergencias incluidas).
          </p>
        </div>
      </div>

      <div class="grid-2">
        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 8px; font-size:16.5px">Contacto rápido</h4>
            <p style="margin:0 0 14px; color: var(--muted); line-height:1.6; font-size: 13.8px;">
              Si querés acelerar, contanos el tipo de trabajo y el barrio/localidad.
            </p>

            <form id="quoteForm">
              <div class="form-grid">
                <label>
                  Nombre y apellido
                  <input name="nombre" type="text" placeholder="Ej: Juan Pérez" required />
                </label>

                <label>
                  Teléfono / WhatsApp
                  <input name="telefono" type="tel" placeholder="Ej: +5491550038092" required />
                </label>
              </div>

              <div class="form-grid">
                <label>
                  Tipo de trabajo
                  <select name="tipo" required>
                    <option value="" selected disabled>Elegí una opción</option>
                    <option value="Domiciliaria">Electricidad domiciliaria</option>
                    <option value="Complejos">Armado de complejos</option>
                    <option value="Barrios cerrados">Barrios cerrados</option>
                    <option value="Edificios">Edificios</option>
                    <option value="Emergencia">Emergencia</option>
                  </select>
                </label>

                <label>
                  Localidad / zona
                  <input name="zona" type="text" placeholder="Ej: Hurlingham, Villa Tesei, etc." required />
                </label>
              </div>

              <label>
                Contanos tu consulta
                <textarea name="mensaje" placeholder="Ej: Se corta la luz en el sector / necesito actualización de tablero / armado de instalación para proyecto..." required></textarea>
              </label>

              <div class="form-actions">
                <button class="btn btn-primary" type="submit">
                  Enviar solicitud
                  <span aria-hidden="true">✅</span>
                </button>
                <div class="small">
                  Al enviar, generamos un mensaje listo para WhatsApp (y te mostramos un resumen).
                </div>
              </div>

              <div class="toast" id="toast">
                ✅ ¡Listo! Abrimos WhatsApp con tu mensaje para que nos comuniquemos.
              </div>
            </form>
          </div>
        </div>

        <div class="card">
          <div class="pad">
            <h4 style="margin:0 0 10px; font-size:16.5px">Atención 24hs y emergencias</h4>
            <p style="margin:0; color: var(--muted); line-height:1.7; font-size: 13.8px;">
              Trabajamos <strong>Lunes a Domingo, 24 horas</strong>. En caso de emergencia eléctrica,
              indicá: qué pasó, desde cuándo y si hay algún disyuntor/térmica saltada.
            </p>

            <div style="margin-top: 14px; display:grid; gap: 12px;">
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">🕒</div>
                  <strong>Horarios</strong>
                </div>
                <span>Lun a Dom · <strong>24hs</strong> · emergencias incluidas</span>
              </div>
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">📍</div>
                  <strong>Zona</strong>
                </div>
                <span>Hurlingham y alrededores (ajustable según tu cobertura)</span>
              </div>
              <div class="q">
                <div class="k">
                  <div class="icon" aria-hidden="true">💡</div>
                  <strong>Recomendación</strong>
                </div>
                <span>Si es urgente, mandanos foto/video del tablero o la falla.</span>
              </div>
            </div>

            <div class="hint" style="margin-top: 12px">
              ¿Querés que la página ya tenga tus fotos reales y el mapa? Decime y lo armamos.
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <div class="footer-grid">
        <div>© <span id="year"></span> JFX Electricidad · Hurlingham, Buenos Aires</div>
        <div>Hecho para promover electricidad domiciliaria y armado de obras.</div>
      </div>
    </div>
  </footer>

  <!-- Floating WhatsApp -->
  <div class="wa-float" aria-label="WhatsApp">
    <div class="wa-sub">
      Consultá por una emergencia o presupuesto.
      <br/><strong>Respondemos 24hs</strong>.
    </div>
    <a class="wa-btn" id="whatsAppBtn" href="#" target="_blank" rel="noopener" aria-label="Abrir WhatsApp">
      <svg width="28" height="28" viewBox="0 0 32 32" fill="none" aria-hidden="true">
        <path d="M19.06 18.47c-.26-.13-1.54-.76-1.78-.84-.24-.08-.41-.13-.58.13-.17.26-.67.84-.83 1.01-.16.17-.31.19-.57.06-.26-.13-1.1-.4-2.1-1.29-.78-.7-1.31-1.56-1.46-1.82-.15-.26-.02-.4.11-.53.11-.11.26-.31.39-.46.13-.15.17-.26.26-.43.08-.17.04-.32-.02-.45-.06-.13-.58-1.54-.79-2.11-.21-.57-.42-.49-.58-.5-.15-.01-.32-.01-.49-.01-.17 0-.45.06-.69.32-.24.26-.9.88-.9 2.14 0 1.26.92 2.47 1.05 2.64.13.17 1.82 2.77 4.4 3.88.62.27 1.1.43 1.48.55.62.2 1.19.17 1.64.1.5-.08 1.54-.64 1.76-1.26.22-.62.22-1.15.16-1.26-.06-.11-.24-.17-.5-.3Z" fill="white"/>
        <path d="M16 3C9.93 3 5 7.93 5 14c0 2.12.6 4.13 1.74 5.86L5 29l9.39-1.74A10.93 10.93 0 0 0 16 25c6.07 0 11-4.93 11-11S22.07 3 16 3Z" stroke="rgba(255,255,255,.55)" stroke-width="1.6"/>
      </svg>
    </a>
  </div>

  <script>
    // WhatsApp setup
    const phone = "+5491550038092"; // tu número
    const whatsappBase = "https://wa.me/" + phone;

    const autoMessage = "Hola, soy [TU NOMBRE]. ¿En qué podemos ayudarte? (Presupuesto de electricidad domiciliaria / complejos / edificios)";
    // We will encode it for URLs
    const waUrl = whatsappBase + "?text=" + encodeURIComponent(autoMessage);

    function setWhatsLinks(){
      document.getElementById("whatsAppBtn").href = waUrl;
      document.getElementById("btnWhatsAppInline").href = waUrl;
    }
    setWhatsLinks();

    // Portfolio filter
    const workChips = Array.from(document.querySelectorAll('[data-work]'));
    const workItems = Array.from(document.querySelectorAll('.work'));

    workChips.forEach(chip=>{
      chip.addEventListener('click', ()=>{
        workChips.forEach(c=>c.classList.remove('active'));
        chip.classList.add('active');

        const cat = chip.getAttribute('data-work');
        workItems.forEach(item=>{
          const ok = (cat === 'all') || item.getAttribute('data-cat') === cat;
          item.style.display = ok ? '' : 'none';
        });
      });
    });

    // Services interactive (just updates details text by mode)
    const serviceChips = Array.from(document.querySelectorAll('[data-mode]'));
    const serviceDetails = document.getElementById('serviceDetails');

    const modeCopy = {
      todos: [
        "Diagnóstico, plan de acción y ejecución con orden. Trabajamos con comunicación clara para que sepas qué se hace, cómo y cuándo.",
        "Instalaciones prolijas, verificaciones y recomendaciones para el uso seguro. En emergencias priorizamos la estabilización y luego la solución completa.",
        "Alcance del trabajo, materiales sugeridos (cuando aplica), mano de obra, tiempos estimados y condiciones para avanzar."
      ],
      domiciliaria: [
        "Para problemas del hogar: tablero, circuitos, iluminación, tomas y cableado. Diagnosticamos la causa y solucionamos de manera segura.",
        "Priorizamos seguridad y orden: chequeos, protecciones y recomendaciones para reducir fallas futuras.",
        "Presupuesto con alcance claro: qué se reemplaza/ajusta, mano de obra y tiempos."
      ],
      complejos: [
        "Armado de complejos con foco en áreas comunes y coordinación de instalación eléctrica según proyecto.",
        "Verificaciones, prolijidad y trabajo planificado para mantener continuidad en obra.",
        "Incluimos alcance y tiempos estimados para que el proyecto avance sin sorpresas."
      ],
      barrios: [
        "Trabajo en barrios cerrados: iluminación, mantenimiento y actualización de infraestructura eléctrica.",
        "Ajustamos protecciones y circuitos para un uso estable y seguro.",
        "Te cotizamos con alcance definido y condiciones claras."
      ],
      edificios: [
        "Para edificios: mantenimiento y mejoras en instalaciones, con revisión y correcciones donde sea necesario.",
        "Cuidamos seguridad, continuidad y orden en cada intervención.",
        "Presupuesto con detalle del alcance y tiempos."
      ]
    };

    // Map to three details bodies
    function applyMode(mode){
      const copies = modeCopy[mode] || modeCopy.todos;
      const details = serviceDetails.querySelectorAll('details');
      const bodies = Array.from(details).map(d => d.querySelector('.body'));
      // assumes 3 details as defined above
      for(let i=0;i<Math.min(3,bodies.length);i++){
        bodies[i].textContent = copies[i];
      }
    }

    serviceChips.forEach(chip=>{
      chip.addEventListener('click', ()=>{
        serviceChips.forEach(c=>{ c.classList.remove('active'); c.setAttribute('aria-selected','false');});
        chip.classList.add('active');
        chip.setAttribute('aria-selected','true');
        applyMode(chip.dataset.mode);
      });
    });

    // Quotes carousel
    const quotes = [
      { text: "Respondieron rápido por una emergencia, dejaron todo prolijo y explicaron claramente qué se estaba haciendo.", name: "— Cliente en Hurlingham", stars: "★★★★★" },
      { text: "Muy buena atención y seguimiento. El presupuesto fue claro y cumplieron con el tiempo estimado.", name: "— Cliente barrio cerrado", stars: "★★★★★" },
      { text: "Se encargaron del armado eléctrico del complejo con orden y seriedad. Quedó todo funcionando perfecto.", name: "— Cliente por obra de complejos", stars: "★★★★★" }
    ];
    let qi = 0;
    const quoteText = document.getElementById('quoteText');
    const quoteName = document.getElementById('quoteName');
    const quoteStars = document.getElementById('quoteStars');

    function renderQuote(){
      const q = quotes[qi];
      quoteText.textContent = q.text;
      quoteName.textContent = q.name;
      quoteStars.textContent = q.stars;
    }
    document.getElementById('prevQuote').addEventListener('click', ()=>{
      qi = (qi - 1 + quotes.length) % quotes.length;
      renderQuote();
    });
    document.getElementById('nextQuote').addEventListener('click', ()=>{
      qi = (qi + 1) % quotes.length;
      renderQuote();
    });

    // Stats count-up
    const statsNums = Array.from(document.querySelectorAll('[data-count]'));
    function animateCounts(){
      statsNums.forEach(el=>{
        const target = Number(el.dataset.count);
        const start = 0;
        const duration = 900;
        const startTime = performance.now();
        function step(now){
          const t = Math.min(1, (now - startTime)/duration);
          const val = Math.round(start + (target-start)* (t*(2-t))); // easeOutQuad
          el.textContent = val.toString();
          if(t < 1) requestAnimationFrame(step);
        }
        requestAnimationFrame(step);
      });
    }
    // run soon
    setTimeout(animateCounts, 450);

    // Form -> build WhatsApp message
    const form = document.getElementById('quoteForm');
    const toast = document.getElementById('toast');

    function sanitize(s){ return (s||"").toString().trim(); }

    form.addEventListener('submit', (e)=>{
      e.preventDefault();

      const data = {
        nombre: sanitize(form.nombre.value),
        telefono: sanitize(form.telefono.value),
        tipo: sanitize(form.tipo.value),
        zona: sanitize(form.zona.value),
        mensaje: sanitize(form.mensaje.value)
      };

      if(!data.nombre || !data.telefono || !data.tipo || !data.zona || !data.mensaje){
        alert("Por favor completá todos los campos requeridos.");
        return;
      }

      const msg =
        `Hola, soy ${data.nombre}. Mi teléfono: ${data.telefono}.\n` +
        `Consulta: ${data.tipo}\n` +
        `Zona/localidad: ${data.zona}\n\n` +
        `Mensaje: ${data.mensaje}\n\n` +
        `Disponibilidad: Lunes a Domingo 24hs (emergencias incluidas).`;

      const url = whatsappBase + "?text=" + encodeURIComponent(msg);

      toast.style.display = 'block';
      setTimeout(()=>{ toast.style.display = 'none'; }, 3800);

      // open whatsapp
      window.open(url, "_blank", "noopener,noreferrer");
    });

    // Year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
