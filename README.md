<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <title>Ultra Listener — Android Live Translate (Worker Stable)</title>
  <style>
    :root{
      color-scheme: dark;
      --bg:#000;
      --panel:#050505;
      --border:#0f3a18;
      --green:#35ff6a;
      --green-dim: rgba(53,255,106,.78);
      --yellow:#ffd740;
      --red:#ff4d4d;
      --font: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
    }
    body{ margin:0; padding:14px; background:var(--bg); color:var(--green); font-family:var(--font); letter-spacing:.2px; }
    h1{ margin:0 0 10px; font-size:16px; text-shadow:0 0 8px rgba(53,255,106,.25); }
    .grid{ display:grid; gap:12px; grid-template-columns:1fr; }
    @media (min-width: 980px){ .grid{ grid-template-columns: 1.15fr 0.85fr; } }
    .card{
      background: linear-gradient(180deg, rgba(53,255,106,.05), transparent 35%), var(--panel);
      border:1px solid var(--border);
      border-radius:12px;
      padding:12px;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset, 0 0 18px rgba(0,0,0,.55);
    }
    .row{ display:flex; gap:10px; flex-wrap:wrap; align-items:center; }
    .col{ display:flex; flex-direction:column; gap:6px; }
    button{
      background: transparent; color: var(--green);
      border:1px solid var(--border);
      padding: 10px 12px; border-radius:10px;
      font-weight:800; cursor:pointer;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    button:hover{ box-shadow:0 0 0 1px rgba(53,255,106,.25) inset, 0 0 12px rgba(53,255,106,.12); }
    button:disabled{ opacity:.55; cursor:not-allowed; }
    button.danger{ border-color: rgba(255,77,77,.6); color: var(--red); }
    .pill{
      display:inline-flex; align-items:center; gap:8px;
      padding:4px 8px; border-radius:999px;
      border:1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      font-size:12px; white-space:nowrap;
    }
    .small{ font-size:12px; color:var(--green-dim); line-height:1.35; }
    canvas{ width:100%; border-radius:10px; border:1px solid var(--border); background:#000; }
    #spec{ height:150px; }
    textarea{
      width:100%; min-height: 290px; resize: vertical;
      border-radius:10px; border:1px solid var(--border);
      background:#000; color: var(--green);
      padding: 12px;
      font-family: var(--font);
      font-size: 14px; line-height: 1.45;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    textarea::placeholder{ color: rgba(53,255,106,.35); }
    input[type="range"]{ width: min(520px, 100%); accent-color: #35ff6a; }
    select{
      background:#000; color: var(--green);
      border:1px solid var(--border);
      border-radius:10px;
      padding: 8px 10px;
      font-family: var(--font);
    }
    .statusstrip{
      display:flex; gap:10px; flex-wrap:wrap; align-items:center;
      margin-top:10px; padding: 8px 10px;
      border-radius:10px; border:1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      font-size:12px;
    }
    .dot{
      width:8px; height:8px; border-radius:999px;
      display:inline-block;
      border:1px solid rgba(53,255,106,.45);
      background: rgba(53,255,106,.15);
      box-shadow: 0 0 10px rgba(53,255,106,.12);
      margin-right:6px;
      vertical-align: middle;
    }
    .dot.on{ background: rgba(53,255,106,.95); border-color: rgba(53,255,106,.95); box-shadow:0 0 14px rgba(53,255,106,.35); }
    .dot.warn{ background: rgba(255,215,64,.9); border-color: rgba(255,215,64,.9); box-shadow:0 0 14px rgba(255,215,64,.25); }
    .kv{ display:inline-flex; align-items:center; gap:8px; }
    .key{ color: rgba(53,255,106,.9); font-weight:800; }
    .val{ color: var(--green-dim); }
    .vu{ width: 130px; height: 10px; border-radius:999px; border:1px solid rgba(53,255,106,.25); background: rgba(0,0,0,.6); overflow:hidden; }
    .vu > div{ height:100%; width:0%; background: rgba(53,255,106,.85); box-shadow:0 0 10px rgba(53,255,106,.25); transition: width .08s linear; }

    .toggle{
      display:inline-flex; align-items:center; gap:10px;
      border:1px solid var(--border);
      background: rgba(53,255,106,.04);
      padding: 8px 10px;
      border-radius:999px;
      user-select:none;
    }
    .toggle input{ display:none; }
    .toggle .track{
      width: 42px; height: 22px;
      border-radius:999px;
      border:1px solid var(--border);
      background: rgba(0,0,0,.7);
      position: relative;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset;
    }
    .toggle .thumb{
      width:18px; height:18px; border-radius:999px;
      position:absolute; top:1px; left:1px;
      background: rgba(53,255,106,.25);
      border:1px solid rgba(53,255,106,.6);
      transition: transform .18s ease;
      box-shadow:0 0 10px rgba(53,255,106,.22);
    }
    .toggle input:checked + .track .thumb{ transform: translateX(20px); background: rgba(53,255,106,.85); }
    .toggle .label{ font-size:12px; color: var(--green-dim); }

    .seg{ display:inline-flex; border:1px solid var(--border); border-radius:999px; overflow:hidden; background: rgba(53,255,106,.04); }
    .seg input{ display:none; }
    .seg label{ padding:8px 10px; font-size:12px; color: var(--green-dim); cursor:pointer; border-right: 1px solid rgba(53,255,106,.18); }
    .seg label:last-child{ border-right:0; }
    .seg input:checked + label{ color: var(--bg); background: rgba(53,255,106,.85); }

    .warn{
      border: 1px solid rgba(255,215,64,.55);
      background: rgba(255,215,64,.12);
      border-radius: 10px;
      padding: 10px;
      color: rgba(255,231,140,.95);
      font-size: 12px;
      line-height: 1.35;
    }

    .overlay{ position:fixed; inset:0; display:none; align-items:center; justify-content:center; background: rgba(0,0,0,.75); padding:14px; z-index:50; }
    .overlay.show{ display:flex; }
    .modal{
      width:min(860px, 100%); border-radius:14px; background:#000;
      border: 1px solid var(--border); padding: 12px;
      box-shadow: 0 0 0 1px rgba(53,255,106,.08) inset, 0 0 24px rgba(0,0,0,.65);
    }
    .modal h2{ margin:0 0 8px; font-size: 14px; }
    .modal .sub{ margin:0 0 10px; font-size:12px; color: var(--green-dim); line-height:1.35; }
    .modal .err{ border:1px solid rgba(255,77,77,.55); background: rgba(255,77,77,.08); border-radius:10px; padding:10px; color: rgba(255,150,150,.95); font-size:12px; }
    .actions{ display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end; margin-top:10px; }
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // WORKER STABLE LIVE TRANSLATE</h1>

  <div class="grid">
    <div class="card">
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b> (locks after load)</div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny" selected>whisper-tiny (multilingual) — recommended</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (English-only)</option>
          </select>
          <div class="small">This build runs ASR in a Worker to prevent UI stutter.</div>
        </div>

        <div class="col" style="flex: 1 1 320px">
          <div class="small"><b>TRANSLATE</b></div>
          <label class="toggle">
            <input id="translateOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Translate to English</span>
          </label>
        </div>
      </div>

      <div class="row">
        <button id="btnLoadModel">Load AI Model</button>
        <button id="btnStart">Start Mic</button>
        <button id="btnStop" class="danger" disabled>Stop</button>
        <button id="btnHelp">Help</button>
        <span class="pill" id="status">idle</span>
      </div>

      <div class="statusstrip">
        <span class="kv"><span id="dotModel" class="dot"></span><span class="key">MODEL</span><span id="modelState" class="val">NOT LOADED</span></span>
        <span class="kv"><span id="dotMic" class="dot"></span><span class="key">MIC</span><span id="micState" class="val">OFF</span></span>
        <span class="kv"><span class="key">LEVEL</span><span id="lvlDb" class="val">-inf dBFS</span></span>
        <span class="kv"><span class="key">VU</span><span class="vu"><div id="vuFill"></div></span></span>
        <span class="kv"><span class="key">ASR</span><span id="asrMs" class="val">—</span></span>
        <span class="kv"><span class="key">ADAPT</span><span id="adapt" class="val">—</span></span>
      </div>

      <div class="warn" style="margin-top:10px">
        <b>Monitoring audio:</b> Use headphones. Toggle between <b>Voice-isolated</b> and <b>All sounds</b>.
        Translation runs continuously on the raw mic (windows), but the heavy work is off the UI thread.
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>TRANSCRIPTION</b></div>
          <label class="toggle">
            <input id="alwaysOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Always-on</span>
          </label>
          <div class="small">Always-on still skips truly silent audio.</div>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>MONITOR</b></div>
          <label class="toggle">
            <input id="monitorOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Monitor audio</span>
          </label>
          <label class="toggle">
            <input id="hpConfirm" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">I am wearing headphones</span>
          </label>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>LISTENING FILTER</b></div>
          <div class="seg">
            <input type="radio" name="listen" id="listenVoice" checked>
            <label for="listenVoice">Voice-isolated</label>
            <input type="radio" name="listen" id="listenAll">
            <label for="listenAll">All sounds</label>
          </div>
          <div class="small">Affects monitoring only (what you hear).</div>
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Monitor volume</b>: <span id="monVolLabel">0.00</span></div>
          <input id="monVol" type="range" min="0" max="0.6" step="0.01" value="0" disabled />
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>WINDOW</b> sec: <span id="winSecLabel">2.0</span></div>
          <input id="winSec" type="range" min="1.5" max="6" step="0.5" value="2.0" />
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>UPDATE</b> sec: <span id="updSecLabel">1.0</span></div>
          <input id="updSec" type="range" min="0.5" max="3" step="0.5" value="1.0" />
          <div class="small">Adaptive mode may raise this if ASR is slower than UPDATE.</div>
        </div>
      </div>

      <div style="margin-top:10px">
        <canvas id="spec" width="1200" height="260"></canvas>
        <div class="row small" style="margin-top:8px">
          <span class="pill">sampleRate: <span id="sr">-</span> Hz</span>
          <span class="pill">nyquist: <span id="ny">-</span> Hz</span>
          <span class="pill">peak: <span id="pk">-</span> Hz</span>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT</b></div>
          <div class="small">Appends translated text (or transcript if translate off).</div>
        </div>
        <div class="row">
          <button id="btnCopy">Copy</button>
          <button id="btnClear">Clear</button>
        </div>
      </div>
      <textarea id="out" placeholder="(live output will appear here)"></textarea>
      <div class="small" style="margin-top:10px">
        Recommended S23 defaults: WINDOW 2.0s, UPDATE 1.0s. If ASR time is high, it will auto-adapt (raise UPDATE).
      </div>
    </div>
  </div>

  <div id="overlay" class="overlay" role="dialog" aria-modal="true">
    <div class="modal">
      <h2 id="ovTitle">Help</h2>
      <p class="sub" id="ovSub"></p>
      <div id="ovErr" class="err" style="display:none"></div>
      <div class="actions">
        <button id="btnCloseOv">Close</button>
      </div>
    </div>
  </div>

  <script type="module">
    const $ = (id) => document.getElementById(id);

    const modelSel = $("modelSel");
    const translateOn = $("translateOn");
    const btnLoadModel = $("btnLoadModel");
    const btnStart = $("btnStart");
    const btnStop = $("btnStop");
    const btnHelp = $("btnHelp");
    const btnCopy = $("btnCopy");
    const btnClear = $("btnClear");

    const statusEl = $("status");
    const dotModel = $("dotModel");
    const dotMic = $("dotMic");
    const modelState = $("modelState");
    const micState = $("micState");
    const lvlDb = $("lvlDb");
    const vuFill = $("vuFill");
    const asrMs = $("asrMs");
    const adapt = $("adapt");

    const alwaysOn = $("alwaysOn");

    const monitorOn = $("monitorOn");
    const hpConfirm = $("hpConfirm");
    const listenVoice = $("listenVoice");
    const listenAll = $("listenAll");
    const monVol = $("monVol");
    const monVolLabel = $("monVolLabel");

    const winSec = $("winSec");
    const winSecLabel = $("winSecLabel");
    const updSec = $("updSec");
    const updSecLabel = $("updSecLabel");

    const srEl = $("sr");
    const nyEl = $("ny");
    const pkEl = $("pk");
    const spec = $("spec");
    const specCtx = spec.getContext("2d");
    const out = $("out");

    const overlay = $("overlay");
    const ovTitle = $("ovTitle");
    const ovSub = $("ovSub");
    const ovErr = $("ovErr");
    const btnCloseOv = $("btnCloseOv");
    btnCloseOv.addEventListener("click", () => overlay.classList.remove("show"));

    function showOverlay(title, sub, err=null){
      ovTitle.textContent = title;
      ovSub.textContent = sub || "";
      if (err){ ovErr.style.display="block"; ovErr.textContent = err; }
      else { ovErr.style.display="none"; ovErr.textContent=""; }
      overlay.classList.add("show");
    }
    function setStatus(s){ statusEl.textContent = s; }

    function appendWords(s){
      const prefix = out.value.length && !out.value.endsWith("\\n") ? "\\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }

    // ===== Audio capture =====
    let audioCtx=null, stream=null, source=null;
    let analyser=null, freqData=null, timeData=null;
    let captureNode=null;

    // monitor nodes
    let monitorGain=null;
    let speechBand=null;

    // ring buffer
    let rb=null, rbSize=0, rbWrite=0, rbFilled=0;
    function rbInit(sr){
      rbSize = Math.max(1, Math.floor(sr*12));
      rb = new Float32Array(rbSize);
      rbWrite=0; rbFilled=0;
    }
    function rbPush(block){
      const n=block.length;
      for (let i=0;i<n;i++){
        rb[rbWrite]=block[i];
        rbWrite=(rbWrite+1)%rbSize;
      }
      rbFilled = Math.min(rbSize, rbFilled+n);
    }
    function rbGetLast(seconds, sr){
      const need = Math.min(rbFilled, Math.floor(seconds*sr));
      const outArr = new Float32Array(need);
      const start = (rbWrite-need+rbSize)%rbSize;
      if (start+need <= rbSize) outArr.set(rb.subarray(start,start+need));
      else{
        const first=rbSize-start;
        outArr.set(rb.subarray(start),0);
        outArr.set(rb.subarray(0,need-first),first);
      }
      return outArr;
    }

    function maxAbs(pcm){
      let m=0;
      for (let i=0;i<pcm.length;i++){ const a=Math.abs(pcm[i]); if (a>m) m=a; }
      return m;
    }

    function cleanTranscript(raw){
      if (!raw) return "";
      let t=String(raw);
      t = t.replace(/[♪♫]+/g," ");
      t = t.replace(/\\[([^\\]]+)\\]/g, " ");
      t = t.replace(/\\(([^\\)]+)\\)/g, " ");
      t = t.replace(/\\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\\b/gi, " ");
      t = t.replace(/\\s+/g," ").trim();
      if (!/[A-Za-z]/.test(t)) return "";
      if (/\\b(blank_audio|mus_audio|no_audio|music)\\b/i.test(t)) return "";
      return t;
    }

    function dbfsFromTimeDomainByte(arr){
      let sumSq=0;
      for (let i=0;i<arr.length;i++){
        const v=(arr[i]-128)/128;
        sumSq += v*v;
      }
      const rms=Math.sqrt(sumSq/arr.length);
      if (rms<=1e-9) return "-inf";
      return (20*Math.log10(rms)).toFixed(1);
    }

    async function ensureCaptureWorklet(){
      const code = `
        class CaptureProcessor extends AudioWorkletProcessor {
          process(inputs) {
            const input = inputs[0];
            if (input && input[0]) this.port.postMessage(input[0].slice(0));
            return true;
          }
        }
        registerProcessor('capture-processor', CaptureProcessor);
      `;
      const url = URL.createObjectURL(new Blob([code], { type:"application/javascript" }));
      try{ await audioCtx.audioWorklet.addModule(url); } finally{ URL.revokeObjectURL(url); }
    }

    function requireMultilingualForTranslate(){
      if (translateOn.checked && String(modelSel.value).includes(".en")){
        showOverlay("Translation needs multilingual model", "Switch Whisper model to whisper-tiny (multilingual).");
        translateOn.checked = false;
        return false;
      }
      return true;
    }

    // ===== Worker ASR =====
    let worker = null;
    let modelLoaded = false;
    let loadedModelId = null;
    let workerBusy = false;
    let lastAsrDuration = 0;
    let adaptiveMinUpdate = 1.0;

    function makeWorker(){
      const workerCode = `
        import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";
        env.allowLocalModels = false;
        env.useBrowserCache = true;

        let asr = null;
        let loaded = false;
        let loadedId = null;

        function cleanTranscript(raw){
          if (!raw) return "";
          let t = String(raw);
          t = t.replace(/[♪♫]+/g," ");
          t = t.replace(/\\[([^\\]]+)\\]/g, " ");
          t = t.replace(/\\(([^\\)]+)\\)/g, " ");
          t = t.replace(/\\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\\b/gi, " ");
          t = t.replace(/\\s+/g," ").trim();
          if (!/[A-Za-z]/.test(t)) return "";
          if (/\\b(blank_audio|mus_audio|no_audio|music)\\b/i.test(t)) return "";
          return t;
        }

        self.onmessage = async (ev) => {
          const msg = ev.data || {};
          if (msg.type === "load"){
            const { modelId, device } = msg;
            try{
              asr = await pipeline("automatic-speech-recognition", modelId, { device });
              loaded = true;
              loadedId = modelId;
              self.postMessage({ type:"loaded", ok:true, modelId });
            } catch (e){
              self.postMessage({ type:"loaded", ok:false, error: String(e?.message || e) });
            }
            return;
          }
          if (msg.type === "run"){
            if (!loaded || !asr){
              self.postMessage({ type:"result", ok:false, error:"model_not_loaded" });
              return;
            }
            const t0 = performance.now();
            try{
              const pcm = new Float32Array(msg.pcm);
              const windowSec = msg.windowSec;
              const task = msg.task;
              const res = await asr(pcm, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false, task });
              const text = cleanTranscript((res?.text || "").trim());
              const dt = performance.now() - t0;
              self.postMessage({ type:"result", ok:true, text, ms: dt });
            } catch (e){
              const dt = performance.now() - t0;
              self.postMessage({ type:"result", ok:false, error: String(e?.message || e), ms: dt });
            }
          }
        };
      `;
      const url = URL.createObjectURL(new Blob([workerCode], { type:"text/javascript" }));
      // module worker to allow ESM import
      return new Worker(url, { type: "module" });
    }

    async function loadModel(){
      if (modelLoaded) return;
      if (!requireMultilingualForTranslate()) return;

      btnLoadModel.disabled = true;
      dotModel.classList.add("warn");
      modelState.textContent = "LOADING…";
      setStatus("loading model…");

      // create worker
      if (!worker) worker = makeWorker();

      // Android stability: use wasm
      const modelId = modelSel.value;
      workerBusy = true;

      worker.onmessage = (ev) => {
        const msg = ev.data || {};
        if (msg.type === "loaded"){
          workerBusy = false;
          if (msg.ok){
            modelLoaded = true;
            loadedModelId = msg.modelId;
            modelSel.disabled = true;
            dotModel.classList.remove("warn");
            dotModel.classList.add("on");
            modelState.textContent = "READY";
            setStatus("model loaded");
          } else {
            btnLoadModel.disabled = false;
            dotModel.classList.remove("warn");
            modelState.textContent = "ERROR";
            setStatus("model load error");
            showOverlay("Model load failed", "Could not load the AI model in worker.", msg.error || "unknown");
          }
        }
        if (msg.type === "result"){
          workerBusy = false;
          if (typeof msg.ms === "number"){
            lastAsrDuration = msg.ms;
            asrMs.textContent = msg.ms.toFixed(0) + "ms";
          }
          // Adapt update if needed (keep free and stable)
          if (lastAsrDuration > (Number(updSec.value) * 1000) * 0.85){
            adaptiveMinUpdate = Math.max(adaptiveMinUpdate, Math.min(3.0, (lastAsrDuration/1000) + 0.3));
            adapt.textContent = "raised to " + adaptiveMinUpdate.toFixed(1) + "s";
          } else if (adaptiveMinUpdate > 1.0 && lastAsrDuration < 700){
            adaptiveMinUpdate = Math.max(1.0, adaptiveMinUpdate - 0.1);
            adapt.textContent = "relax " + adaptiveMinUpdate.toFixed(1) + "s";
          }

          if (msg.ok && msg.text){
            appendWords(msg.text);
          }
          setStatus("listening");
        }
      };

      worker.postMessage({ type:"load", modelId, device:"wasm" });
    }

    function updateMonitorLock(){
      const unlocked = monitorOn.checked && hpConfirm.checked;
      monVol.disabled = !unlocked;
      if (!unlocked){
        monVol.value = "0";
        monVolLabel.textContent = "0.00";
        if (monitorGain) monitorGain.gain.value = 0;
      } else {
        if (monitorGain) monitorGain.gain.value = Number(monVol.value);
      }
    }

    function buildMonitorGraph(){
      if (!audioCtx || !source) return;
      try{ monitorGain?.disconnect(); }catch{}
      try{ speechBand?.disconnect(); }catch{}
      monitorGain = audioCtx.createGain();
      monitorGain.gain.value = 0;

      speechBand = audioCtx.createBiquadFilter();
      speechBand.type = "bandpass";
      speechBand.frequency.value = 1200;
      speechBand.Q.value = 0.6;

      if (listenVoice.checked){
        source.connect(speechBand);
        speechBand.connect(monitorGain);
      } else {
        source.connect(monitorGain);
      }
      monitorGain.connect(audioCtx.destination);
      updateMonitorLock();
    }

    function rebuildMonitor(){
      if (!audioCtx || !source) return;
      try{ source.disconnect(); }catch{}
      source.connect(analyser);
      if (captureNode) source.connect(captureNode);
      buildMonitorGraph();
    }

    async function startMic(){
      if (!navigator.mediaDevices?.getUserMedia){
        showOverlay("Mic not supported", "This browser doesn't support getUserMedia().");
        return;
      }
      if (!window.isSecureContext && location.hostname !== "localhost"){
        showOverlay("Mic needs HTTPS", "Use GitHub Pages https:// or http://localhost.");
        return;
      }
      if (audioCtx) return;

      setStatus("requesting mic…");
      btnStart.disabled = true;

      try{
        stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
      } catch (e){
        btnStart.disabled = false;
        setStatus("mic error");
        showOverlay("Microphone error", "Could not access microphone.", String(e?.message || e));
        return;
      }

      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      srEl.textContent = audioCtx.sampleRate.toFixed(0);
      nyEl.textContent = (audioCtx.sampleRate/2).toFixed(0);
      rbInit(audioCtx.sampleRate);

      source = audioCtx.createMediaStreamSource(stream);

      analyser = audioCtx.createAnalyser();
      analyser.fftSize = 1024;
      analyser.smoothingTimeConstant = 0.65;
      freqData = new Uint8Array(analyser.frequencyBinCount);
      timeData = new Uint8Array(analyser.fftSize);
      source.connect(analyser);

      if (audioCtx.audioWorklet){
        await ensureCaptureWorklet();
        captureNode = new AudioWorkletNode(audioCtx, "capture-processor", { numberOfInputs:1, numberOfOutputs:0, channelCount:1 });
        captureNode.port.onmessage = (ev) => { const b=ev.data; if (b && b.length) rbPush(b); };
        source.connect(captureNode);
      } else {
        const sp = audioCtx.createScriptProcessor(2048,1,1);
        sp.onaudioprocess = (e) => rbPush(e.inputBuffer.getChannelData(0));
        source.connect(sp);
        const zero = audioCtx.createGain(); zero.gain.value=0;
        sp.connect(zero); zero.connect(audioCtx.destination);
        captureNode = sp;
      }

      buildMonitorGraph();

      btnStop.disabled = false;
      btnStart.disabled = true;
      dotMic.classList.add("on");
      micState.textContent = "LIVE";
      setStatus("listening");

      startInferenceLoop();
      requestAnimationFrame(drawLoop);
    }

    function stopAll(){
      stopInferenceLoop();
      try{ captureNode?.disconnect(); }catch{}
      captureNode=null;

      try{ source?.disconnect(); }catch{}
      source=null; analyser=null;

      try{ monitorGain?.disconnect(); }catch{}
      try{ speechBand?.disconnect(); }catch{}
      monitorGain=null; speechBand=null;

      if (stream){
        for (const t of stream.getTracks()) t.stop();
        stream=null;
      }
      if (audioCtx){
        audioCtx.close();
        audioCtx=null;
      }
      rb=null; rbSize=rbWrite=rbFilled=0;

      btnStart.disabled = false;
      btnStop.disabled = true;
      dotMic.classList.remove("on");
      micState.textContent = "OFF";
      setStatus("stopped");
    }

    let inferTimer=null;
    function stopInferenceLoop(){
      if (inferTimer){ clearTimeout(inferTimer); inferTimer=null; }
      workerBusy = false;
    }
    function startInferenceLoop(){
      stopInferenceLoop();
      const tick = async () => {
        await runInferenceTick();
        const desired = Number(updSec.value);
        const interval = Math.max(0.5, Math.max(desired, adaptiveMinUpdate));
        updSecLabel.textContent = interval.toFixed(1);
        inferTimer = setTimeout(tick, interval*1000);
      };
      inferTimer = setTimeout(tick, 600);
    }

    async function runInferenceTick(){
      if (!audioCtx || !rb || !modelLoaded || !worker) return;
      if (workerBusy) return;

      const sr = audioCtx.sampleRate;
      const windowSec = Number(winSec.value);
      if (rbFilled < Math.floor(sr*1.0)) return;

      const pcm = rbGetLast(windowSec, sr);

      // silence guard (keeps "monitor all voices" but avoids wasting cycles)
      const m = maxAbs(pcm);
      if (m < (alwaysOn.checked ? 0.0009 : 0.0013)) return;

      workerBusy = true;
      setStatus("transcribing…");

      // Transfer PCM buffer to worker (zero-copy)
      const pcmBuf = pcm.buffer;
      try{
        worker.postMessage({
          type:"run",
          pcm: pcmBuf,
          windowSec: windowSec,
          task: (translateOn.checked ? "translate" : undefined)
        }, [pcmBuf]);
      } catch (e){
        workerBusy = false;
      }
    }

    function drawLoop(){
      if (!analyser || !audioCtx) return;

      analyser.getByteFrequencyData(freqData);
      analyser.getByteTimeDomainData(timeData);

      const db = dbfsFromTimeDomainByte(timeData);
      lvlDb.textContent = db + " dBFS";
      let dbNum = (db === "-inf") ? -99 : Number(db);
      if (!Number.isFinite(dbNum)) dbNum = -99;
      const pct = Math.max(0, Math.min(100, ((dbNum + 60) / 50) * 100));
      vuFill.style.width = pct.toFixed(0) + "%";

      let peakIdx=0;
      for (let i=1;i<freqData.length;i++) if (freqData[i] > freqData[peakIdx]) peakIdx=i;
      const peakHz = (peakIdx/freqData.length) * (audioCtx.sampleRate/2);
      pkEl.textContent = peakHz.toFixed(0);

      // throttle drawing to reduce jank
      if ((performance.now() % 2) < 1){
        specCtx.clearRect(0,0,spec.width,spec.height);
        const w=spec.width, h=spec.height;
        const n=freqData.length;
        const step=2;
        const bars=Math.floor(n/step);
        const barW=w/bars;
        let bi=0;
        for (let i=0;i<n;i+=step){
          const v = Math.max(freqData[i], freqData[i+1]||0)/255;
          const barH=v*(h-12);
          specCtx.fillStyle = `rgba(53,255,106,${0.08+v*0.85})`;
          specCtx.fillRect(bi*barW, h-barH, barW, barH);
          bi++;
        }
      }

      requestAnimationFrame(drawLoop);
    }

    // Wiring
    btnLoadModel.addEventListener("click", loadModel);
    btnStart.addEventListener("click", startMic);
    btnStop.addEventListener("click", stopAll);

    btnHelp.addEventListener("click", () => {
      showOverlay(
        "Worker Stable Help (S23)",
        "This build moves Whisper inference to a Worker to prevent UI stutter. If it still lags: raise UPDATE to 1.5–2.0s or WINDOW to 3.0s. Monitoring requires headphones confirm.",
        null
      );
    });

    btnCopy.addEventListener("click", async () => {
      try{ await navigator.clipboard.writeText(out.value||""); }
      catch{ showOverlay("Copy failed", "Clipboard blocked. Select text and copy manually."); }
    });
    btnClear.addEventListener("click", () => { out.value=""; });

    translateOn.addEventListener("change", () => { requireMultilingualForTranslate(); });

    winSec.addEventListener("input", () => { winSecLabel.textContent = Number(winSec.value).toFixed(1); });
    updSec.addEventListener("input", () => { updSecLabel.textContent = Number(updSec.value).toFixed(1); adaptiveMinUpdate = Number(updSec.value); adapt.textContent = "manual"; });

    monitorOn.addEventListener("change", () => { updateMonitorLock(); });
    hpConfirm.addEventListener("change", () => { updateMonitorLock(); });

    monVol.addEventListener("input", () => {
      monVolLabel.textContent = Number(monVol.value).toFixed(2);
      if (monitorGain) monitorGain.gain.value = (monitorOn.checked && hpConfirm.checked) ? Number(monVol.value) : 0;
    });

    listenVoice.addEventListener("change", () => { if (audioCtx) rebuildMonitor(); });
    listenAll.addEventListener("change", () => { if (audioCtx) rebuildMonitor(); });

    alwaysOn.addEventListener("change", () => { /* keep silence guard */ });

    modelSel.addEventListener("change", () => {
      if (modelLoaded && loadedModelId){
        modelSel.value = loadedModelId;
        setStatus("model locked");
        setTimeout(() => setStatus("listening"), 650);
      }
    });

    // Init
    dotModel.classList.remove("on","warn");
    dotMic.classList.remove("on");
    modelState.textContent = "NOT LOADED";
    micState.textContent = "OFF";
    setStatus("idle");
    winSecLabel.textContent = "2.0";
    updSecLabel.textContent = "1.0";
    monVolLabel.textContent = "0.00";
    monVol.disabled = true;
    asrMs.textContent = "—";
    adapt.textContent = "—";
    requireMultilingualForTranslate();
  </script>
</body>
</html>
