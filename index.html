<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <title>Ultra Listener — Terminal Live (No Chunks)</title>
  <style>
    :root{
      color-scheme: dark;
      --bg:#000000;
      --panel:#050505;
      --border:#0f3a18;
      --green:#35ff6a;
      --green-dim: rgba(53,255,106,.78);
      --green-faint: rgba(53,255,106,.28);
      --warn: rgba(255, 215, 64, .18);
      --warn-b: rgba(255, 215, 64, .45);
      --red: #ff4d4d;
      --font: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
    }
    body{ margin:0; padding:14px; background:var(--bg); color:var(--green); font-family:var(--font); letter-spacing:.2px; }
    h1{ margin:0 0 10px; font-size:16px; text-shadow:0 0 8px rgba(53,255,106,.25); }
    .grid{ display:grid; gap:12px; grid-template-columns: 1fr; }
    @media (min-width: 980px){ .grid{ grid-template-columns: 1.2fr 0.8fr; } }
    .card{
      background: linear-gradient(180deg, rgba(53,255,106,.05), transparent 35%), var(--panel);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 12px;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset, 0 0 18px rgba(0,0,0,.55);
    }
    .row{ display:flex; gap:10px; flex-wrap:wrap; align-items:center; }
    .col{ display:flex; flex-direction:column; gap:6px; }
    button{
      background: transparent; color: var(--green);
      border: 1px solid var(--border);
      padding: 10px 12px; border-radius: 10px;
      font-weight: 800; cursor: pointer;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    button:hover{ box-shadow:0 0 0 1px rgba(53,255,106,.25) inset, 0 0 12px rgba(53,255,106,.12); }
    button:disabled{ opacity:.55; cursor:not-allowed; }
    button.danger{ border-color: rgba(255,77,77,.6); color: var(--red); }
    .pill{
      display:inline-flex; align-items:center; gap:8px;
      padding: 4px 8px; border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      font-size: 12px; white-space: nowrap;
    }
    .small{ font-size: 12px; color: var(--green-dim); line-height: 1.35; }
    .warn{
      border: 1px solid var(--warn-b);
      background: var(--warn);
      border-radius: 10px;
      padding: 10px;
      color: rgba(255, 231, 140, .95);
      font-size: 12px; line-height: 1.35;
    }
    canvas{ width:100%; height:190px; border-radius:10px; border:1px solid var(--border); background:#000; }
    textarea{
      width:100%; min-height: 300px; resize: vertical;
      border-radius: 10px; border: 1px solid var(--border);
      background:#000; color: var(--green);
      padding: 12px; font-family: var(--font);
      font-size: 14px; line-height: 1.45;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    textarea::placeholder{ color: rgba(53,255,106,.35); }
    .banner{
      display:none; border-radius:10px; padding:10px;
      border: 1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      margin-bottom: 12px;
      font-size: 12px; line-height: 1.35;
    }
    .banner.show{ display:block; }

    /* Toggle switch */
    .toggle{
      display:inline-flex; align-items:center; gap:10px;
      border: 1px solid var(--border);
      background: rgba(53,255,106,.04);
      padding: 8px 10px;
      border-radius: 999px;
      user-select:none;
    }
    .toggle input{ display:none; }
    .toggle .track{
      width: 42px; height: 22px;
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(0,0,0,.7);
      position: relative;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    .toggle .thumb{
      width: 18px; height: 18px;
      border-radius: 999px;
      position:absolute; top:1px; left:1px;
      background: rgba(53,255,106,.25);
      border: 1px solid rgba(53,255,106,.6);
      transition: transform .18s ease;
      box-shadow: 0 0 10px rgba(53,255,106,.22);
    }
    .toggle input:checked + .track .thumb{ transform: translateX(20px); background: rgba(53,255,106,.85); }
    .toggle .label{ font-size: 12px; color: var(--green-dim); }

    /* Mode segmented control */
    .seg{
      display:inline-flex;
      border: 1px solid var(--border);
      border-radius: 999px;
      overflow:hidden;
      background: rgba(53,255,106,.04);
    }
    .seg input{ display:none; }
    .seg label{
      padding: 8px 10px;
      font-size: 12px;
      color: var(--green-dim);
      cursor:pointer;
      border-right: 1px solid rgba(53,255,106,.18);
    }
    .seg label:last-child{ border-right: 0; }
    .seg input:checked + label{
      color: var(--bg);
      background: rgba(53,255,106,.85);
      text-shadow:none;
    }

    input[type="range"]{ width: min(520px, 100%); accent-color: #35ff6a; }
    select{
      background:#000; color: var(--green);
      border:1px solid var(--border);
      border-radius: 10px;
      padding: 8px 10px;
      font-family: var(--font);
    }

    /* Permission overlay */
    .overlay{ position:fixed; inset:0; display:none; align-items:center; justify-content:center; background: rgba(0,0,0,.75); padding:14px; z-index:50; }
    .overlay.show{ display:flex; }
    .modal{
      width:min(820px, 100%); border-radius:14px; background:#000;
      border: 1px solid var(--border); padding: 12px;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset, 0 0 24px rgba(0,0,0,.65);
    }
    .modal h2{ margin:0 0 8px; font-size: 14px; color: var(--green); }
    .modal .sub{ margin:0 0 10px; font-size: 12px; color: var(--green-dim); line-height: 1.35; }
    .modal .err{ border: 1px solid rgba(255,77,77,.55); background: rgba(255,77,77,.08); border-radius: 10px; padding: 10px; color: rgba(255,150,150,.95); font-size:12px; }
    .steps{ display:grid; gap:10px; grid-template-columns:1fr; }
    @media (min-width: 760px){ .steps{ grid-template-columns:1fr 1fr; } }
    .step{ border: 1px solid var(--border); background: rgba(53,255,106,.04); border-radius: 10px; padding: 10px; }
    .step b{ font-size: 12px; color: var(--green); }
    .muted{ font-size: 12px; color: var(--green-dim); line-height: 1.35; }
    .actions{ display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end; margin-top: 10px; }
    .codepill{ display:inline-block; padding: 2px 6px; border-radius: 8px; border:1px solid var(--border); background: rgba(53,255,106,.04); }
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // TERMINAL LIVE (WEB AUDIO STREAM)</h1>

  <div id="envBanner" class="banner"></div>

  <div class="grid">
    <div class="card">
      <div class="row">
        <button id="btnStart">Start Mic</button>
        <button id="btnStop" class="danger" disabled>Stop</button>
        <button id="btnLoadModel">Load AI Model</button>
        <button id="btnHelp">Mic Help</button>
        <span class="pill" id="status">idle</span>
      </div>
<div style="margin-top:10px">
        <canvas id="spec" width="1200" height="360"></canvas>
      </div>

      <div class="row small" style="margin-top:8px">
        <span class="pill">sampleRate: <span id="sr">-</span> Hz</span>
        <span class="pill">nyquist: <span id="ny">-</span> Hz</span>
        <span class="pill">peak: <span id="pk">-</span> Hz</span>
        <span class="pill">level: <span id="lvl">-</span> dBFS</span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>Mode</b></div>
          <div class="seg" role="tablist" aria-label="Mode">
            <input type="radio" name="mode" id="modeNormal" checked>
            <label for="modeNormal">Normal Speech</label>
            <input type="radio" name="mode" id="modeShift">
            <label for="modeShift">Spectral / Hz Shift</label>
          </div>
          <div class="small">Normal = raw mic → AI. Shift = heterodyne-shifted mic → AI (experimental).</div>
        </div>

        <div class="col" style="flex:1 1 320px">
          <div class="small"><b>Voice</b></div>
          <label class="toggle" title="Toggle audible voice">
            <input id="voiceOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Speak detected words</span>
          </label>
          <div class="small">If off, words still appear in the output box.</div>
        </div>
        <div style="height:6px"></div>
        <div class="small"><b>Translate</b></div>
        <label class="toggle" title="Translate detected speech to English">
          <input id="translateOn" type="checkbox" />
          <span class="track"><span class="thumb"></span></span>
          <span class="label">Translate to English</span>
        </label>
        <div class="small">Requires a multilingual model (recommended: <b>whisper-tiny</b>).</div>

      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Shift amount</b> (Hz): <span id="shiftHzLabel">12000</span></div>
          <input id="shiftHz" type="range" min="1000" max="20000" value="12000" />
          <div class="small">Used only in Spectral/Hz Shift mode.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Window</b> seconds (transcribe): <span id="winSecLabel">3.0</span></div>
          <input id="winSec" type="range" min="1" max="8" step="0.5" value="3.0" />
          <div class="small">How much recent audio is sent to the model each update.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Update</b> every seconds: <span id="updSecLabel">1.0</span></div>
          <input id="updSec" type="range" min="0.5" max="3" step="0.5" value="1.0" />
          <div class="small">How often the model runs (lower = more live, higher CPU).</div>
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>AI model</b></div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (fastest, English)</option>
            <option value="Xenova/whisper-tiny">whisper-tiny (fast, multilingual)</option>
            <option value="Xenova/whisper-base.en">whisper-base.en (better, slower)</option>
          </select>
          <div class="small">Runs locally in your browser.</div>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>Deduplicate</b></div>
          <label class="toggle" title="Avoid repeating identical lines every update">
            <input id="dedupeOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Skip exact repeats</span>
          </label>
          <div class="small">Keeps the output box from spamming the same phrase.</div>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT // WORDS ONLY</b></div>
          <div class="small">All detected words are appended here as they are recognized.</div>
        </div>
        <div class="row">
          <button id="btnCopy">Copy</button>
          <button id="btnClear">Clear</button>
        </div>
      </div>

      <textarea id="out" placeholder="(detected words will appear here)"></textarea>

      <div class="small" style="margin-top:10px">
        If you want it to feel more “instant”, lower <b>Update</b> to 0.5s and keep <b>Window</b> around 2–3s.
      </div>
    </div>
  </div>

  <!-- Permission / help overlay -->
  <div id="permOverlay" class="overlay" role="dialog" aria-modal="true">
    <div class="modal">
      <h2 id="permTitle">Microphone permission needed</h2>
      <p class="sub" id="permSubtitle">Your browser must allow microphone access. You must tap Allow when prompted.</p>
      <div id="permErrorBox" class="err" style="display:none"></div>

      <div class="steps">
        <div class="step">
          <b>1) Use HTTPS (or localhost)</b>
          <div class="muted">Mic works on <span class="codepill">https://</span> or <span class="codepill">http://localhost</span>. Not on <span class="codepill">file://</span> or GitHub <span class="codepill">blob</span> view.</div>
        </div>
        <div class="step">
          <b>2) Allow Microphone</b>
          <div class="muted">Tap the 🔒 icon → Site settings → Microphone → Allow, then refresh.</div>
        </div>
        <div class="step">
          <b>3) If permission is blocked</b>
          <div class="muted">Change it to Allow in site settings. Close other apps using the mic.</div>
        </div>
        <div class="step">
          <b>4) Best browsers</b>
          <div class="muted">Chrome/Edge/Firefox are best. Some private modes restrict mic use.</div>
        </div>
      </div>

      <div class="actions">
        <button id="btnTryAgain">Try Start Mic Again</button>
        <button id="btnCloseOverlay">Close</button>
      </div>
    </div>
  </div>

  <script type="module">
    import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";

    const $ = (id) => document.getElementById(id);

    // UI
    const btnStart = $("btnStart");
    const btnStop = $("btnStop");
    const btnLoadModel = $("btnLoadModel");
    const btnHelp = $("btnHelp");
    const btnCopy = $("btnCopy");
    const btnClear = $("btnClear");
    const statusEl = $("status");

    const modeNormal = $("modeNormal");
    const modeShift = $("modeShift");
    const voiceOn = $("voiceOn");
    const dedupeOn = $("dedupeOn");

    const translateOn = $("translateOn");
    

    const shiftHz = $("shiftHz");
    const shiftHzLabel = $("shiftHzLabel");

    const winSec = $("winSec");
    const winSecLabel = $("winSecLabel");

    const updSec = $("updSec");
    const updSecLabel = $("updSecLabel");

    const modelSel = $("modelSel");
    const out = $("out");

    const envBanner = $("envBanner");

    // Overlay
    const permOverlay = $("permOverlay");
    const permTitle = $("permTitle");
    const permSubtitle = $("permSubtitle");
    const permErrorBox = $("permErrorBox");
    const btnTryAgain = $("btnTryAgain");
    const btnCloseOverlay = $("btnCloseOverlay");

    // Visuals
    const spec = $("spec");
    const ctx2d = spec.getContext("2d");
    const srEl = $("sr");
    const nyEl = $("ny");
    const pkEl = $("pk");
    const lvlEl = $("lvl");

    // Audio state
    let audioCtx = null;
    let stream = null;
    let source = null;

    let analyser = null;
    let freqData = null;
    let timeData = null;

    // Live capture node (AudioWorklet)
    let captureNode = null;

    // Ring buffer
    let rb = null;                 // Float32Array
    let rbSize = 0;
    let rbWrite = 0;
    let rbFilled = 0;

    // Heterodyne phase (for shifted transcription)
    let heteroPhase = 0;

    // ASR
    let asr = null;
    let modelLoaded = false;
    let busy = false;

    // Inference loop
    let inferTimer = null;
    let lastEmitted = "";

    function setStatus(s){ statusEl.textContent = s; }

    function appendWords(text){
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + text;
      out.scrollTop = out.scrollHeight;
    }

    function speak(text){
      if (!voiceOn.checked) return;
      if (!("speechSynthesis" in window)) return;
      const u = new SpeechSynthesisUtterance(text);
      u.rate = 1.0; u.pitch = 1.0; u.volume = 1.0;
      window.speechSynthesis.cancel();
      window.speechSynthesis.speak(u);
    }

    // Filter non-word cues (aggressive)
    // This app is WORDS-ONLY. Anything that looks like a caption/tag (e.g. [BLANK_AUDIO], [MUS_AUDIO], (wind howling))
    // is removed and will never be shown or spoken.
    const NON_WORD_CUES = [
      "sigh","sighs","sniff","sniffs","sniffling","snore","snoring",
      "breath","breathing","inhale","exhale",
      "cough","coughs","coughing",
      "laugh","laughs","laughter",
      "mumbling","grunt","groan","humming",
      "music","mus","mus_audio","applause","clapping",
      "silence","background noise","noise",
      "blank_audio","audio","no_audio",
      "cry","crying","sob","sobbing",
      "yawn","yawning",
      "clears throat","clearing throat",
      "lip smack","smacking",
      "wind","wind howling","howling","whistling",
      "static","buzz","hiss","hum"
    ];

    function looksLikeCue(s){
      const t = String(s||"").trim().toLowerCase();
      if (!t) return true;

      // If it's a common Whisper tag/caption format like BLANK_AUDIO or MUS_AUDIO (often all caps/underscores)
      const raw = String(s||"").trim();
      if (/^[A-Z0-9_]+$/.test(raw) && raw.length >= 4) return true; // e.g. BLANK_AUDIO, MUS_AUDIO
      if (t.includes("blank_audio") || t.includes("mus_audio") || t.includes("no_audio")) return true;
      if (t.includes("wind") && (t.includes("howl") || t.includes("howling"))) return true;

      // If it explicitly says it's a sound caption
      if (t.startsWith("sound of ") || t.startsWith("sounds of ")) return true;

      // Mostly non-letters? Treat as cue
      const letters = (t.match(/[a-z]/g) || []).length;
      if (letters === 0) return true;

      // Match known cue words/phrases
      for (const cue of NON_WORD_CUES){
        if (t === cue) return true;
        if (t.includes(cue) && t.length <= cue.length + 14) return true; // e.g. "loud wind"
      }

      // If it's short and clearly environmental (two words like "wind howling", "door slam")
      if (t.split(/\s+/).length <= 3 && /^(wind|door|rain|thunder|footsteps|steps|breathing|snoring|sighing|sigh|sniffing|sniff|music|static|silence)\b/.test(t)){
        return true;
      }

      return false;
    }

    function cleanTranscript(raw){
      if (!raw) return "";
      let t = String(raw);

      // Remove musical notes
      t = t.replace(/[♪♫]+/g, " ");

      // Remove bracketed/parenthesized captions/tags aggressively
      t = t.replace(/\[([^\]]+)\]/g, (m, inner) => looksLikeCue(inner) ? " " : m);
      t = t.replace(/\(([^\)]+)\)/g, (m, inner) => looksLikeCue(inner) ? " " : m);

      // Also remove standalone tags that sometimes appear without brackets
      // Examples: BLANK_AUDIO, MUS_AUDIO
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");

      // If the whole thing is basically a cue, drop it
      if (looksLikeCue(t.trim())) return "";

      // Normalize whitespace
      t = t.replace(/\s+/g, " ").trim();

      // Must contain at least one letter (real words)
      if (!/[A-Za-z]/.test(t)) return "";

      return t;
    }

    function environmentChecks(){
      const isSecure = window.isSecureContext || location.hostname === "localhost";
      const isFile = location.protocol === "file:";
      const isGithubBlob = location.hostname === "github.com" && location.pathname.includes("/blob/");
      const msgs = [];
      if (isFile) msgs.push("Opened as file:// — mic is usually blocked. Use GitHub Pages (https://) or localhost.");
      if (isGithubBlob) msgs.push("github.com blob view — mic will not work. Open the github.io Pages URL.");
      if (!isSecure) msgs.push("Not a secure context — mic requires https:// or http://localhost.");
      if (msgs.length){
        envBanner.classList.add("show");
        envBanner.innerHTML = "<b>HEADS UP</b><br>" + msgs.map(m => "• " + m).join("<br>");
      } else {
        envBanner.classList.remove("show");
      }
    }

    function showOverlay({title, subtitle, errorHtml} = {}){
      permTitle.textContent = title || "Microphone permission needed";
      permSubtitle.textContent = subtitle || "Your browser must allow microphone access. You must tap Allow when prompted.";
      if (errorHtml){
        permErrorBox.style.display = "block";
        permErrorBox.innerHTML = errorHtml;
      } else {
        permErrorBox.style.display = "none";
        permErrorBox.textContent = "";
      }
      permOverlay.classList.add("show");
    }

    function hideOverlay(){
      permOverlay.classList.remove("show");
      permErrorBox.style.display = "none";
      permErrorBox.textContent = "";
    }

    async function queryPermissionIfPossible(){
      try{
        if (!navigator.permissions?.query) return null;
        const p = await navigator.permissions.query({ name: "microphone" });
        return p.state;
      }catch{ return null; }
    }

    function dbfsFromTimeDomain(arr){
      let sumSq = 0;
      for (let i=0;i<arr.length;i++){
        const v = (arr[i]-128)/128;
        sumSq += v*v;
      }
      const rms = Math.sqrt(sumSq/arr.length);
      if (rms <= 1e-9) return "-inf";
      return (20*Math.log10(rms)).toFixed(1);
    }

    function findPeakHz(freqBytes, nyquist){
      let peakIdx = 0;
      for (let i=1;i<freqBytes.length;i++){
        if (freqBytes[i] > freqBytes[peakIdx]) peakIdx = i;
      }
      const hz = (peakIdx / freqBytes.length) * nyquist;
      return { peakIdx, hz };
    }

    function maxAbs(pcm){
      let m = 0;
      for (let i = 0; i < pcm.length; i++){
        const a = Math.abs(pcm[i]);
        if (a > m) m = a;
      }
      return m;
    }

    function normalizeIfNeeded(pcm){
      // If audio is very quiet, normalize a bit so the model doesn't treat it as blank.
      // Hard cap to avoid blasting noise.
      const m = maxAbs(pcm);
      if (m <= 0) return { pcm, max: 0 };
      // If the max is below ~-50 dBFS (~0.003), boost up to ~0.05 max.
      if (m < 0.003){
        const gain = Math.min(20, 0.05 / m);
        const out = new Float32Array(pcm.length);
        for (let i = 0; i < pcm.length; i++) out[i] = pcm[i] * gain;
        return { pcm: out, max: m * gain };
      }
      return { pcm, max: m };
    }

    function applyHeterodyneToPCM(pcm, sampleRate, shiftHzVal){
      const outArr = new Float32Array(pcm.length);
      const twoPi = 2 * Math.PI;
      let ph = heteroPhase;
      const inc = twoPi * shiftHzVal / sampleRate;
      for (let i=0;i<pcm.length;i++){
        outArr[i] = pcm[i] * Math.cos(ph);
        ph += inc;
        if (ph > 1e9) ph = ph % twoPi;
      }
      heteroPhase = ph;
      return outArr;
    }

    // Ring buffer helpers
    function rbInit(sampleRate){
      // keep last 12 seconds
      rbSize = Math.max(1, Math.floor(sampleRate * 12));
      rb = new Float32Array(rbSize);
      rbWrite = 0;
      rbFilled = 0;
    }

    function rbPush(block){
      // block is Float32Array
      const n = block.length;
      for (let i=0;i<n;i++){
        rb[rbWrite] = block[i];
        rbWrite = (rbWrite + 1) % rbSize;
      }
      rbFilled = Math.min(rbSize, rbFilled + n);
    }

    function rbGetLast(seconds, sampleRate){
      const need = Math.min(rbFilled, Math.floor(seconds * sampleRate));
      const outArr = new Float32Array(need);
      const start = (rbWrite - need + rbSize) % rbSize;
      if (start + need <= rbSize){
        outArr.set(rb.subarray(start, start + need));
      } else {
        const firstLen = rbSize - start;
        outArr.set(rb.subarray(start), 0);
        outArr.set(rb.subarray(0, need - firstLen), firstLen);
      }
      return outArr;
    }

    
    function modelIsEnglishOnly(modelId){
      // crude heuristic: models ending with .en are English-only in this UI
      return String(modelId || "").toLowerCase().includes(".en");
    }

    function requireMultilingualForTranslate(){
      const modelId = modelSel.value;
      if (translateOn.checked && modelIsEnglishOnly(modelId)){
        showOverlay({
          title: "Translation needs a multilingual model",
          subtitle: "You selected an English-only model (.en).",
          errorHtml: "Choose <b>whisper-tiny</b> (multilingual) in the model dropdown, then reload the page to load it."
        });
        return false;
      }
      return true;
    }

async function loadModel(){
      if (modelLoaded) return;
      btnLoadModel.disabled = true;

      if (!requireMultilingualForTranslate()) { btnLoadModel.disabled = false; return; }

      env.allowLocalModels = false;
      env.useBrowserCache = true;

      const modelId = modelSel.value;
      setStatus("loading model…");

      const device = (navigator.gpu ? "webgpu" : "wasm");
      asr = await pipeline("automatic-speech-recognition", modelId, { device });

      modelLoaded = true;
      setStatus("model loaded");
    }

    async function ensureCaptureWorklet(){
      // Single-file worklet via Blob URL
      const code = `
        class CaptureProcessor extends AudioWorkletProcessor {
          process(inputs, outputs, parameters) {
            const input = inputs[0];
            if (input && input[0]) {
              // Copy so it's transferable-like (structured clone)
              const ch0 = input[0];
              this.port.postMessage(ch0.slice(0));
            }
            return true;
          }
        }
        registerProcessor('capture-processor', CaptureProcessor);
      `;
      const url = URL.createObjectURL(new Blob([code], { type: "application/javascript" }));
      try{
        await audioCtx.audioWorklet.addModule(url);
      } finally {
        URL.revokeObjectURL(url);
      }
    }

    async function startMic(){
      if (!navigator.mediaDevices?.getUserMedia){
        showOverlay({ title: "Mic not supported", subtitle: "This browser does not support getUserMedia(). Try Chrome/Edge/Firefox." });
        return;
      }
      if (!window.isSecureContext && location.hostname !== "localhost"){
        showOverlay({ title: "Mic needs HTTPS", subtitle: "Browsers require a secure origin for mic access.", errorHtml: "Use <b>https://</b> (GitHub Pages) or <b>http://localhost</b>." });
        return;
      }
      if (location.hostname === "github.com" && location.pathname.includes("/blob/")){
        showOverlay({ title: "Open GitHub Pages", subtitle: "Mic won't work on github.com blob view.", errorHtml: "Open your <b>https://username.github.io/repo/</b> URL instead." });
        return;
      }
      if (audioCtx) return;

      const permState = await queryPermissionIfPossible();
      if (permState === "denied"){
        showOverlay({ title: "Microphone blocked", subtitle: "Site permission is set to Block.", errorHtml: "Tap 🔒 → Site settings → Microphone → <b>Allow</b>, then refresh." });
        return;
      }

      setStatus("requesting mic…");
      try{
        stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
      }catch(e){
        const name = e?.name || "Error";
        const msg = e?.message || String(e);
        showOverlay({ title: "Microphone error", subtitle: "Browser could not access the microphone.", errorHtml: `<b>${name}</b>: ${msg}` });
        setStatus("mic error");
        return;
      }

      hideOverlay();

      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      srEl.textContent = audioCtx.sampleRate.toFixed(0);
      nyEl.textContent = (audioCtx.sampleRate/2).toFixed(0);

      rbInit(audioCtx.sampleRate);
      heteroPhase = 0;

      source = audioCtx.createMediaStreamSource(stream);

      analyser = audioCtx.createAnalyser();
      analyser.fftSize = 1024;
      analyser.smoothingTimeConstant = 0.6;
      freqData = new Uint8Array(analyser.frequencyBinCount);
      timeData = new Uint8Array(analyser.fftSize);

      source.connect(analyser);

      // Live capture node
      if (audioCtx.audioWorklet){
        await ensureCaptureWorklet();
        captureNode = new AudioWorkletNode(audioCtx, "capture-processor", { numberOfInputs: 1, numberOfOutputs: 0, channelCount: 1 });
        captureNode.port.onmessage = (ev) => {
          const block = ev.data;
          if (block && block.length) rbPush(block);
        };
        source.connect(captureNode);
      } else {
        // Fallback: ScriptProcessorNode (older)
        const sp = audioCtx.createScriptProcessor(2048, 1, 1);
        sp.onaudioprocess = (e) => {
          const input = e.inputBuffer.getChannelData(0);
          rbPush(input);
        };
        source.connect(sp);
        // connect to destination silently to keep node running
        const zero = audioCtx.createGain(); zero.gain.value = 0;
        sp.connect(zero); zero.connect(audioCtx.destination);
        captureNode = sp;
      }

      startInferenceLoop();

      btnStart.disabled = true;
      btnStop.disabled = false;
      setStatus("listening");
      requestAnimationFrame(drawLoop);
    }

    function stopAll(){
      stopInferenceLoop();

      try{ captureNode?.disconnect(); }catch{}
      captureNode = null;

      try{ source?.disconnect(); }catch{}
      source = null;
      analyser = null;

      if (stream){
        for (const t of stream.getTracks()) t.stop();
        stream = null;
      }
      if (audioCtx){
        audioCtx.close();
        audioCtx = null;
      }

      rb = null; rbSize = 0; rbWrite = 0; rbFilled = 0;
      btnStart.disabled = false;
      btnStop.disabled = true;
      setStatus("stopped");
    }

    function stopInferenceLoop(){
      if (inferTimer){ clearInterval(inferTimer); inferTimer = null; }
      busy = false;
    }

    function startInferenceLoop(){
      stopInferenceLoop();
      const intervalMs = Math.max(250, Number(updSec.value) * 1000);
      inferTimer = setInterval(runInferenceTick, intervalMs);
    }

    async function runInferenceTick(){
      if (!audioCtx || !rb || !modelLoaded || !asr) return;
      if (busy) return;

      const sr = audioCtx.sampleRate;
      const windowSec = Number(winSec.value);

      // need at least ~0.8s of audio in the ring buffer
      if (rbFilled < Math.floor(sr * 0.8)) return;

      // Pull last window and check energy BEFORE calling the model.
      let pcm = rbGetLast(windowSec, sr);

      // Basic silence/blank detection. If too quiet, skip rather than triggering blank_audio.
      const rawMax = maxAbs(pcm);
      if (rawMax < 0.0008){
        // too quiet (roughly below -62 dBFS), treat as silence
        return;
      }

      busy = true;
      setStatus("transcribing…");

      try{
        // Mode: shift or normal
        if (modeShift.checked){
          pcm = applyHeterodyneToPCM(pcm, sr, Number(shiftHz.value));
        }

        // Normalize very quiet audio slightly to avoid blank_audio.
        const norm = normalizeIfNeeded(pcm);
        pcm = norm.pcm;

        const result = await asr(pcm, {
          chunk_length_s: windowSec,
          stride_length_s: 0.2,
          return_timestamps: false,
          task: (translateOn.checked ? "translate" : undefined)
        });

        const rawText = (result?.text || "").trim();
        const cleaned = cleanTranscript(rawText);

        if (cleaned){
          // Final guard: never show/speak model tags/captions
          if (/(blank_audio|mus_audio|no_audio|music)/i.test(cleaned)) {
            // ignore
          } else {

          if (dedupeOn.checked){
            if (cleaned !== lastEmitted){
              lastEmitted = cleaned;
              appendWords(cleaned);
              speak(cleaned);
            }
                    }
        }} else {
            lastEmitted = cleaned;
            appendWords(cleaned);
            speak(cleaned);
          }
        }
      } catch (err){
        const msg = String(err?.message || err);
        // Common benign case: model reports blank audio
        if (msg.toLowerCase().includes("blank_audio")){
          // ignore and continue listening
        } else {
          console.error(err);
          showOverlay({ title: "Transcription error", subtitle: "Something went wrong while transcribing.", errorHtml: msg });
        }
      } finally {
        busy = false;
        setStatus("listening");
      }
    }

    function drawLoop(){
      if (!analyser || !audioCtx) return;

      analyser.getByteFrequencyData(freqData);
      analyser.getByteTimeDomainData(timeData);

      const nyquist = audioCtx.sampleRate / 2;
      const { peakIdx, hz: peakHz } = findPeakHz(freqData, nyquist);
      pkEl.textContent = peakHz.toFixed(0);
      lvlEl.textContent = dbfsFromTimeDomain(timeData);

      // draw bars
      ctx2d.clearRect(0,0,spec.width,spec.height);
      const w = spec.width, h = spec.height;
      const n = freqData.length;
      const barW = w / n;

      for (let i=0;i<n;i++){
        const v = freqData[i]/255;
        const barH = v*(h-20);
        const a = 0.10 + v*0.85;
        ctx2d.fillStyle = `rgba(53,255,106,${a})`;
        ctx2d.fillRect(i*barW, h-barH, barW, barH);
      }

      // peak marker
      const x = peakIdx * barW;
      ctx2d.fillStyle = "rgba(255,255,255,0.75)";
      ctx2d.fillRect(x, 0, 2, h);

      requestAnimationFrame(drawLoop);
    }

    // Events
    btnStart.addEventListener("click", startMic);
    btnStop.addEventListener("click", stopAll);

    btnLoadModel.addEventListener("click", async () => {
      try{ await loadModel(); }
      catch(e){
        console.error(e);
        showOverlay({ title: "Model load failed", subtitle: "Could not load the AI model.", errorHtml: String(e?.message || e) });
        btnLoadModel.disabled = false;
        setStatus("model load error");
      }
    });

    btnHelp.addEventListener("click", async () => {
      const permState = await queryPermissionIfPossible();
      showOverlay({
        title: "Microphone help",
        subtitle: "Follow the steps to enable mic access.",
        errorHtml: permState ? `Permissions API: <b>${permState}</b>` : ""
      });
    });

    btnTryAgain.addEventListener("click", async () => { hideOverlay(); await startMic(); });
    btnCloseOverlay.addEventListener("click", hideOverlay);

    btnClear.addEventListener("click", () => { out.value = ""; lastEmitted = ""; });

    btnCopy.addEventListener("click", async () => {
      try{ await navigator.clipboard.writeText(out.value || ""); }
      catch{ showOverlay({ title: "Copy failed", subtitle: "Clipboard permissions blocked.", errorHtml: "Manually select and copy the text." }); }
    });

    // Controls
    shiftHz.addEventListener("input", () => { shiftHzLabel.textContent = shiftHz.value; });
    winSec.addEventListener("input", () => { winSecLabel.textContent = Number(winSec.value).toFixed(1); });
    updSec.addEventListener("input", () => {
      updSecLabel.textContent = Number(updSec.value).toFixed(1);
      if (audioCtx) startInferenceLoop();
    });

    function onModeChange(){
      // reset duplicate tracking when mode changes
      lastEmitted = "";
    }
    modeNormal.addEventListener("change", onModeChange);
    modeShift.addEventListener("change", onModeChange);

    modelSel.addEventListener("change", () => {
      if (modelLoaded) {
        showOverlay({ title: "Model already loaded", subtitle: "Reload the page to switch models.", errorHtml: "Whisper model can’t be swapped mid-session in this one-file build." });
      }
    });

    
    translateOn.addEventListener("change", () => {
      // If user enables translation after loading an English-only model, show guidance.
      if (translateOn.checked && modelIsEnglishOnly(modelSel.value)){
        showOverlay({
          title: "Switch to multilingual model",
          subtitle: "Translation requires a multilingual model.",
          errorHtml: "Select <b>whisper-tiny</b> (multilingual) and reload the page. The current loaded model can't be swapped without reload."
        });
        translateOn.checked = false;
      }
      // reset dedupe memory so first translated line shows
      lastEmitted = "";
    });


    // Init labels
    shiftHzLabel.textContent = shiftHz.value;
    winSecLabel.textContent = Number(winSec.value).toFixed(1);
    updSecLabel.textContent = Number(updSec.value).toFixed(1);
    environmentChecks();
    setStatus("idle (Start Mic, then Load AI Model)");
  </script>
</body>
</html>
