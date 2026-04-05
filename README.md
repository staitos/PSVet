<!DOCTYPE html>
<!-- saved from url=(0051)file:///C:/Users/pc/Downloads/plan_sanitario_1.html -->
<html lang="es"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Plan Sanitario Ganadero</title>
<link href="./Plan Sanitario Ganadero_files/css2" rel="stylesheet">
<style>
  :root {
    --verde: #1a7a55;
    --verde-claro: #e8f5ef;
    --verde-oscuro: #0d5238;
    --tierra: #8b6914;
    --tierra-claro: #fdf3e0;
    --rojo: #c0392b;
    --rojo-claro: #fdf0ee;
    --gris: #5a5a5a;
    --gris-claro: #f5f4f1;
    --borde: #d8d4cc;
    --texto: #1c1c1a;
    --blanco: #fefefe;
    --sombra: 0 2px 12px rgba(0,0,0,0.08);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: #f0ede6;
    background-image:
      radial-gradient(circle at 20% 20%, rgba(26,122,85,0.06) 0%, transparent 50%),
      radial-gradient(circle at 80% 80%, rgba(139,105,20,0.05) 0%, transparent 50%);
    min-height: 100vh;
    color: var(--texto);
    padding: 2rem 1rem 4rem;
  }

  .container {
    max-width: 640px;
    margin: 0 auto;
  }

  /* HEADER */
  .header {
    text-align: center;
    margin-bottom: 2rem;
    animation: fadeDown 0.6s ease;
  }

  .logo-wrap {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.75rem;
  }

  .logo-icon {
    width: 72px;
    height: 72px;
    background: var(--verde);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 4px 20px rgba(26,122,85,0.3);
  }

  .logo-icon svg {
    width: 40px;
    height: 40px;
  }

  .logo-nombre {
    font-family: 'Lora', serif;
    font-size: 22px;
    font-weight: 600;
    color: var(--verde-oscuro);
    letter-spacing: -0.3px;
  }

  .logo-sub {
    font-size: 13px;
    color: var(--gris);
    font-weight: 300;
    letter-spacing: 0.3px;
  }

  /* PROGRESS */
  .progress-bar {
    background: var(--borde);
    height: 3px;
    border-radius: 2px;
    margin-bottom: 2rem;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    background: var(--verde);
    border-radius: 2px;
    transition: width 0.4s ease;
    width: 0%;
  }

  /* CARD */
  .card {
    background: var(--blanco);
    border-radius: 16px;
    border: 0.5px solid var(--borde);
    padding: 1.75rem;
    margin-bottom: 1rem;
    box-shadow: var(--sombra);
    animation: fadeUp 0.5s ease both;
  }

  .card:nth-child(2) { animation-delay: 0.05s; }
  .card:nth-child(3) { animation-delay: 0.1s; }
  .card:nth-child(4) { animation-delay: 0.15s; }

  .card-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 1.25rem;
    padding-bottom: 1rem;
    border-bottom: 0.5px solid var(--borde);
  }

  .card-icon {
    width: 36px;
    height: 36px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .icon-verde { background: var(--verde-claro); }
  .icon-tierra { background: var(--tierra-claro); }
  .icon-rojo { background: var(--rojo-claro); }

  .card-title {
    font-family: 'Lora', serif;
    font-size: 16px;
    font-weight: 500;
    color: var(--texto);
  }

  .card-subtitle {
    font-size: 12px;
    color: var(--gris);
    margin-top: 2px;
  }

  /* FIELDS */
  .field { margin-bottom: 1rem; }
  .field:last-child { margin-bottom: 0; }

  .field-grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  label {
    display: block;
    font-size: 12.5px;
    font-weight: 500;
    color: var(--gris);
    margin-bottom: 5px;
    letter-spacing: 0.2px;
  }

  .required-dot {
    display: inline-block;
    width: 5px;
    height: 5px;
    background: var(--verde);
    border-radius: 50%;
    margin-left: 4px;
    vertical-align: middle;
    position: relative;
    top: -1px;
  }

  input[type="text"],
  input[type="tel"],
  input[type="date"],
  select {
    width: 100%;
    height: 42px;
    border: 1px solid var(--borde);
    border-radius: 10px;
    padding: 0 14px;
    font-size: 14px;
    font-family: 'DM Sans', sans-serif;
    color: var(--texto);
    background: #fafaf8;
    transition: border-color 0.2s, box-shadow 0.2s, background 0.2s;
    -webkit-appearance: none;
  }

  input:focus, select:focus {
    outline: none;
    border-color: var(--verde);
    background: #fff;
    box-shadow: 0 0 0 3px rgba(26,122,85,0.12);
  }

  input.filled { background: #fff; border-color: #bbd8cc; }
  input.error { border-color: var(--rojo); box-shadow: 0 0 0 3px rgba(192,57,43,0.1); }

  input[type="date"] {
    color: var(--gris);
    cursor: pointer;
  }
  input[type="date"]:valid { color: var(--texto); }

  /* TOGGLE SI/NO */
  .yn-wrap {
    display: flex;
    gap: 8px;
    margin-top: 4px;
  }

  .yn-btn {
    flex: 1;
    height: 40px;
    border: 1px solid var(--borde);
    border-radius: 10px;
    background: #fafaf8;
    font-size: 13.5px;
    font-family: 'DM Sans', sans-serif;
    cursor: pointer;
    transition: all 0.18s ease;
    font-weight: 400;
    color: var(--gris);
    position: relative;
    overflow: hidden;
  }

  .yn-btn:hover { border-color: #aaa; color: var(--texto); }

  .yn-btn.si-active {
    background: var(--verde-claro);
    border-color: var(--verde);
    color: var(--verde-oscuro);
    font-weight: 500;
  }

  .yn-btn.no-active {
    background: var(--rojo-claro);
    border-color: #e8a09a;
    color: #922b21;
    font-weight: 500;
  }

  /* RISK ITEMS */
  .risk-item {
    background: var(--gris-claro);
    border-radius: 12px;
    padding: 12px 14px;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    border: 0.5px solid var(--borde);
    transition: background 0.2s;
  }

  .risk-item.riesgo-si { background: #fef9e7; border-color: #d4ac0d55; }

  .risk-label {
    font-size: 13.5px;
    color: var(--texto);
    flex: 1;
  }

  .risk-hint {
    font-size: 11px;
    color: var(--gris);
    margin-top: 2px;
  }

  .risk-yn {
    display: flex;
    gap: 6px;
    flex-shrink: 0;
  }

  .risk-yn .yn-btn {
    width: 52px;
    flex: none;
    height: 34px;
    font-size: 12.5px;
    border-radius: 8px;
  }

  /* SUBMIT */
  .submit-wrap {
    margin-top: 1.5rem;
  }

  .btn-submit {
    width: 100%;
    height: 52px;
    background: var(--verde);
    color: white;
    border: none;
    border-radius: 12px;
    font-size: 16px;
    font-weight: 500;
    font-family: 'DM Sans', sans-serif;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    transition: background 0.2s, transform 0.15s;
    letter-spacing: 0.2px;
  }

  .btn-submit:hover { background: var(--verde-oscuro); transform: translateY(-1px); }
  .btn-submit:active { transform: translateY(0); }
  .btn-submit:disabled { background: #aaa; cursor: not-allowed; transform: none; }

  .btn-submit svg { width: 20px; height: 20px; }

  .submit-note {
    text-align: center;
    font-size: 11.5px;
    color: var(--gris);
    margin-top: 10px;
  }

  /* SUCCESS */
  .success-screen {
    display: none;
    text-align: center;
    padding: 3rem 1.5rem;
    background: var(--blanco);
    border-radius: 16px;
    border: 0.5px solid var(--borde);
    box-shadow: var(--sombra);
    animation: fadeUp 0.5s ease;
  }

  .success-icon {
    width: 72px;
    height: 72px;
    background: var(--verde-claro);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 1.25rem;
  }

  .success-title {
    font-family: 'Lora', serif;
    font-size: 22px;
    font-weight: 600;
    color: var(--verde-oscuro);
    margin-bottom: 0.75rem;
  }

  .success-text {
    font-size: 14px;
    color: var(--gris);
    line-height: 1.7;
    max-width: 380px;
    margin: 0 auto 1.5rem;
  }

  .success-name {
    font-weight: 500;
    color: var(--verde);
  }

  .btn-nuevo {
    display: inline-block;
    padding: 10px 24px;
    border: 1px solid var(--verde);
    border-radius: 10px;
    color: var(--verde);
    font-size: 13.5px;
    font-family: 'DM Sans', sans-serif;
    cursor: pointer;
    background: none;
    transition: all 0.2s;
  }
  .btn-nuevo:hover { background: var(--verde); color: white; }

  /* SPINNER */
  .spinner {
    display: none;
    width: 20px;
    height: 20px;
    border: 2.5px solid rgba(255,255,255,0.3);
    border-top-color: white;
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
  }

  /* VALIDATION MSG */
  .field-error {
    font-size: 11.5px;
    color: var(--rojo);
    margin-top: 4px;
    display: none;
  }

  /* ALERT */
  .alert {
    padding: 12px 14px;
    border-radius: 10px;
    font-size: 13px;
    margin-bottom: 1rem;
    display: none;
  }
  .alert.error { background: var(--rojo-claro); color: #922b21; border: 1px solid #e8a09a; display: block; }

  /* ANIMATIONS */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  /* MOBILE */
  @media (max-width: 480px) {
    .field-grid-2 { grid-template-columns: 1fr; }
    .card { padding: 1.25rem; }
    body { padding: 1rem 0.75rem 3rem; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="logo-wrap">
      <div class="logo-icon">
        <svg viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
          <ellipse cx="20" cy="17" rx="12" ry="10" fill="white" opacity="0.15"></ellipse>
          <ellipse cx="20" cy="17" rx="8" ry="7" fill="white" opacity="0.9"></ellipse>
          <circle cx="20" cy="17" r="4" fill="#1a7a55"></circle>
          <path d="M8 28 Q20 35 32 28" stroke="white" stroke-width="2" fill="none" stroke-linecap="round"></path>
          <path d="M14 7 Q20 3 26 7" stroke="white" stroke-width="1.8" fill="none" stroke-linecap="round"></path>
          <circle cx="9" cy="16" r="2.5" fill="white" opacity="0.7"></circle>
          <circle cx="31" cy="16" r="2.5" fill="white" opacity="0.7"></circle>
        </svg>
      </div>
      <div>
        <div class="logo-nombre">Plan Sanitario Ganadero</div>
        <div class="logo-sub">Información fundamental del establecimiento</div>
      </div>
    </div>
  </div>

  <!-- PROGRESS -->
  <div class="progress-bar"><div class="progress-fill" id="progressFill"></div></div>

  <!-- ALERT -->
  <div class="alert" id="alertMsg"></div>

  <!-- FORM -->
  <form id="mainForm" novalidate="">

    <!-- CARD 1: Datos del productor -->
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-verde">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#1a7a55" stroke-width="2" stroke-linecap="round">
            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
            <circle cx="12" cy="7" r="4"></circle>
          </svg>
        </div>
        <div>
          <div class="card-title">Datos del productor</div>
          <div class="card-subtitle">Información de contacto y establecimiento</div>
        </div>
      </div>

      <div class="field">
        <label>Nombre completo <span class="required-dot"></span></label>
        <input type="text" id="nombre" placeholder="Ej: Juan Pérez" autocomplete="name" required="">
        <div class="field-error" id="err-nombre">Por favor ingresá tu nombre.</div>
      </div>

      <div class="field">
        <label>Nombre del establecimiento <span class="required-dot"></span></label>
        <input type="text" id="establecimiento" placeholder="Ej: Estancia La Esperanza" required="">
        <div class="field-error" id="err-establecimiento">Ingresá el nombre del establecimiento.</div>
      </div>

      <div class="field">
        <label>Ubicación / Departamento <span class="required-dot"></span></label>
        <input type="text" id="ubicacion" placeholder="Ej: Tacuarembó, Uruguay" required="">
        <div class="field-error" id="err-ubicacion">Ingresá la ubicación.</div>
      </div>

      <div class="field">
        <label>Número de celular WhatsApp <span class="required-dot"></span></label>
        <input type="tel" id="celular" placeholder="Ej: +598 99 123 456" autocomplete="tel" required="">
        <div class="field-error" id="err-celular">Ingresá un número de celular válido.</div>
      </div>
    </div>

    <!-- CARD 2: Fechas del ciclo -->
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-tierra">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#8b6914" stroke-width="2" stroke-linecap="round">
            <rect x="3" y="4" width="18" height="18" rx="2"></rect>
            <line x1="16" y1="2" x2="16" y2="6"></line>
            <line x1="8" y1="2" x2="8" y2="6"></line>
            <line x1="3" y1="10" x2="21" y2="10"></line>
          </svg>
        </div>
        <div>
          <div class="card-title">Fechas del ciclo productivo</div>
          <div class="card-subtitle">Seleccioná las fechas clave de tu rodeo</div>
        </div>
      </div>

      <div class="field-grid-2">
        <div class="field">
          <label>Finalización de partos anteriores</label>
          <input type="date" id="fin_partos">
        </div>
        <div class="field">
          <label>Finalización de entore</label>
          <input type="date" id="fin_entore">
        </div>
      </div>

      <div class="field-grid-2">
        <div class="field">
          <label>Inicio de servicios reproductivos <span class="required-dot"></span></label>
          <input type="date" id="inicio_servicios" required="">
          <div class="field-error" id="err-inicio_servicios">Requerido.</div>
        </div>
        <div class="field">
          <label>Fin de servicios reproductivos <span class="required-dot"></span></label>
          <input type="date" id="fin_servicios" required="">
          <div class="field-error" id="err-fin_servicios">Requerido.</div>
        </div>
      </div>
    </div>

    <!-- CARD 3: Riesgos sanitarios -->
    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-rojo">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#c0392b" stroke-width="2" stroke-linecap="round">
            <path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path>
            <line x1="12" y1="9" x2="12" y2="13"></line>
            <line x1="12" y1="17" x2="12.01" y2="17"></line>
          </svg>
        </div>
        <div>
          <div class="card-title">Riesgos sanitarios</div>
          <div class="card-subtitle">Marcá los riesgos presentes en tu establecimiento</div>
        </div>
      </div>

      <div class="risk-item" id="r-brucelosis">
        <div>
          <div class="risk-label">Riesgo de brucelosis</div>
          <div class="risk-hint">Presencia o antecedentes en la zona</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;brucelosis&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;brucelosis&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-garrapatas">
        <div>
          <div class="risk-label">Presencia de garrapatas</div>
          <div class="risk-hint">En animales o en el campo</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;garrapatas&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;garrapatas&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-tristeza">
        <div>
          <div class="risk-label">Garrapatas portadoras de Tristeza bovina</div>
          <div class="risk-hint">Babesiosis / Anaplasmosis en la región</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;tristeza&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;tristeza&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-carbunco">
        <div>
          <div class="risk-label">Carbunco (Ántrax)</div>
          <div class="risk-hint">Antecedentes en suelos del establecimiento</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;carbunco&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;carbunco&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-paramphistomum">
        <div>
          <div class="risk-label">Paramphistomum</div>
          <div class="risk-hint">Trematode ruminal, zonas con bañados</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;paramphistomum&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;paramphistomum&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-saguaype">
        <div>
          <div class="risk-label">Saguaypé (Fasciola hepatica)</div>
          <div class="risk-hint">Distomatosis hepática, zonas húmedas</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;saguaype&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;saguaype&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>

      <div class="risk-item" id="r-mosca" style="margin-bottom:0;">
        <div>
          <div class="risk-label">Mosca de cuernos (Haematobia irritans)</div>
          <div class="risk-hint">Presencia en el rodeo durante el verano</div>
        </div>
        <div class="risk-yn">
          <button type="button" class="yn-btn" onclick="setRisk(&#39;mosca&#39;,&#39;si&#39;,this)">Sí</button>
          <button type="button" class="yn-btn" onclick="setRisk(&#39;mosca&#39;,&#39;no&#39;,this)">No</button>
        </div>
      </div>
    </div>

    <!-- SUBMIT -->
    <div class="submit-wrap">
      <button type="submit" class="btn-submit" id="btnSubmit">
        <svg id="btnIcon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round">
          <polyline points="9 11 12 14 22 4"></polyline>
          <path d="M21 12v7a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h11"></path>
        </svg>
        <div class="spinner" id="btnSpinner"></div>
        <span id="btnText">Enviar y generar mi plan sanitario</span>
      </button>
      <div class="submit-note">Tus datos se guardan de forma segura. Recibirás confirmación por WhatsApp.</div>
    </div>

  </form>

  <!-- SUCCESS -->
  <div class="success-screen" id="successScreen">
    <div class="success-icon">
      <svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#1a7a55" stroke-width="2.5" stroke-linecap="round">
        <polyline points="20 6 9 17 4 12"></polyline>
      </svg>
    </div>
    <div class="success-title">¡Registro exitoso!</div>
    <div class="success-text">
      <span class="success-name" id="successNombre"></span>, tu información fue guardada correctamente.<br>
      En las próximas horas recibirás tu plan sanitario personalizado y el calendario de actividades por WhatsApp.
    </div>
    <button class="btn-nuevo" onclick="resetForm()">Registrar otro establecimiento</button>
  </div>

</div>

<script>
  // =============================================
  // CONFIGURACIÓN — REEMPLAZÁ CON TU URL
  // =============================================
  const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxSt1XxMSHmmyuEf_fv_ANUkqaE2V-QtAZF_WW_kJLcCqEAmzw0r0ftB_BsAafqlBzoLg/exec';
  // =============================================

  const risks = {
    brucelosis: null, garrapatas: null, tristeza: null,
    carbunco: null, paramphistomum: null, saguaype: null, mosca: null
  };

  function setRisk(name, val, btn) {
    risks[name] = val;
    const group = btn.closest('.risk-yn');
    group.querySelectorAll('.yn-btn').forEach(b => {
      b.classList.remove('si-active', 'no-active');
    });
    btn.classList.add(val === 'si' ? 'si-active' : 'no-active');
    const item = document.getElementById('r-' + name);
    item.classList.toggle('riesgo-si', val === 'si');
    updateProgress();
  }

  // Progress tracking
  const requiredFields = ['nombre','establecimiento','ubicacion','celular','inicio_servicios','fin_servicios'];

  function updateProgress() {
    let filled = 0;
    const total = requiredFields.length + 7; // + 7 riesgos
    requiredFields.forEach(id => {
      if (document.getElementById(id)?.value.trim()) filled++;
    });
    Object.values(risks).forEach(v => { if (v !== null) filled++; });
    document.getElementById('progressFill').style.width = Math.round((filled / total) * 100) + '%';
  }

  document.querySelectorAll('input').forEach(inp => {
    inp.addEventListener('input', () => {
      inp.classList.toggle('filled', inp.value.trim().length > 0);
      updateProgress();
    });
  });

  // Validation
  function validate() {
    let ok = true;
    requiredFields.forEach(id => {
      const el = document.getElementById(id);
      const err = document.getElementById('err-' + id);
      if (!el.value.trim()) {
        el.classList.add('error');
        if (err) err.style.display = 'block';
        ok = false;
      } else {
        el.classList.remove('error');
        if (err) err.style.display = 'none';
      }
    });
    // Validate phone
    const cel = document.getElementById('celular').value.trim();
    if (cel && !/[\d\s+\-()]{7,}/.test(cel)) {
      document.getElementById('celular').classList.add('error');
      document.getElementById('err-celular').style.display = 'block';
      ok = false;
    }
    // Validate date range
    const ini = document.getElementById('inicio_servicios').value;
    const fin = document.getElementById('fin_servicios').value;
    if (ini && fin && fin < ini) {
      document.getElementById('fin_servicios').classList.add('error');
      document.getElementById('err-fin_servicios').textContent = 'La fecha de fin debe ser posterior al inicio.';
      document.getElementById('err-fin_servicios').style.display = 'block';
      ok = false;
    }
    return ok;
  }

  // Collect data
  function collectData() {
    const g = id => document.getElementById(id)?.value || '';
    return {
      timestamp: new Date().toLocaleString('es-UY'),
      nombre: g('nombre'),
      establecimiento: g('establecimiento'),
      ubicacion: g('ubicacion'),
      celular: g('celular'),
      fin_partos: g('fin_partos'),
      fin_entore: g('fin_entore'),
      inicio_servicios: g('inicio_servicios'),
      fin_servicios: g('fin_servicios'),
      brucelosis: risks.brucelosis || '',
      garrapatas: risks.garrapatas || '',
      tristeza: risks.tristeza || '',
      carbunco: risks.carbunco || '',
      paramphistomum: risks.paramphistomum || '',
      saguaype: risks.saguaype || '',
      mosca: risks.mosca || ''
    };
  }

  // Submit
  document.getElementById('mainForm').addEventListener('submit', async function(e) {
    e.preventDefault();
    const alertEl = document.getElementById('alertMsg');
    alertEl.className = 'alert';

    if (!validate()) {
      alertEl.className = 'alert error';
      alertEl.textContent = 'Por favor completá los campos obligatorios marcados.';
      window.scrollTo({ top: 0, behavior: 'smooth' });
      return;
    }

    const btn = document.getElementById('btnSubmit');
    const btnText = document.getElementById('btnText');
    const btnIcon = document.getElementById('btnIcon');
    const spinner = document.getElementById('btnSpinner');

    btn.disabled = true;
    btnIcon.style.display = 'none';
    spinner.style.display = 'block';
    btnText.textContent = 'Enviando...';

    const data = collectData();

    try {
      // Intentar enviar a Google Sheets
      if (GOOGLE_SCRIPT_URL.includes('TU_ID')) {
        // MODO DEMO — sin Google Script configurado
        await new Promise(r => setTimeout(r, 1500));
        showSuccess(data.nombre);
      } else {
        const formData = new FormData();
        Object.entries(data).forEach(([k, v]) => formData.append(k, v));
        const resp = await fetch(GOOGLE_SCRIPT_URL, {
          method: 'POST',
          body: formData
        });
        const result = await resp.json();
        if (result.result === 'success') {
          showSuccess(data.nombre);
        } else {
          throw new Error(result.message || 'Error desconocido');
        }
      }
    } catch (err) {
      btn.disabled = false;
      btnIcon.style.display = 'block';
      spinner.style.display = 'none';
      btnText.textContent = 'Enviar y generar mi plan sanitario';
      alertEl.className = 'alert error';
      alertEl.textContent = 'Ocurrió un error al enviar. Verificá tu conexión e intentá nuevamente.';
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }
  });

  function showSuccess(nombre) {
    document.getElementById('mainForm').style.display = 'none';
    document.getElementById('progressFill').style.width = '100%';
    const success = document.getElementById('successScreen');
    success.style.display = 'block';
    document.getElementById('successNombre').textContent = nombre;
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function resetForm() {
    document.getElementById('mainForm').reset();
    document.getElementById('mainForm').style.display = 'block';
    document.getElementById('successScreen').style.display = 'none';
    Object.keys(risks).forEach(k => risks[k] = null);
    document.querySelectorAll('.yn-btn').forEach(b => b.classList.remove('si-active','no-active'));
    document.querySelectorAll('.risk-item').forEach(r => r.classList.remove('riesgo-si'));
    document.querySelectorAll('input').forEach(i => { i.classList.remove('filled','error'); });
    document.querySelectorAll('.field-error').forEach(e => e.style.display = 'none');
    document.getElementById('progressFill').style.width = '0%';
    document.getElementById('alertMsg').className = 'alert';
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>


</body></html>
