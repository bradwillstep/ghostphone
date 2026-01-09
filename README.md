<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <title>Ultra Listener — Hybrid Hardwired (hybrid-hardwired-1767921463-dk9nbr)</title>
  <style>
    :root{color-scheme:dark;--bg:#000;--panel:#050505;--border:#0f3a18;--green:#35ff6a;--green-dim:rgba(53,255,106,.78);--red:#ff4d4d;--font:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;}
    body{margin:0;padding:14px;background:var(--bg);color:var(--green);font-family:var(--font);letter-spacing:.2px}
    h1{margin:0 0 10px;font-size:16px;text-shadow:0 0 8px rgba(53,255,106,.25)}
    .grid{display:grid;gap:12px;grid-template-columns:1fr}
    @media (min-width:980px){.grid{grid-template-columns:1.15fr .85fr}}
    .card{background:linear-gradient(180deg, rgba(53,255,106,.05), transparent 35%), var(--panel);border:1px solid var(--border);border-radius:12px;padding:12px;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset,0 0 18px rgba(0,0,0,.55)}
    .row{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
    .col{display:flex;flex-direction:column;gap:6px}
    button{background:transparent;color:var(--green);border:1px solid var(--border);padding:10px 12px;border-radius:10px;font-weight:800;cursor:pointer;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset}
    button:hover{box-shadow:0 0 0 1px rgba(53,255,106,.25) inset,0 0 12px rgba(53,255,106,.12)}
    button:disabled{opacity:.55;cursor:not-allowed}
    button.danger{border-color:rgba(255,77,77,.6);color:var(--red)}
    .pill{display:inline-flex;align-items:center;gap:8px;padding:4px 8px;border-radius:999px;border:1px solid var(--border);background:rgba(53,255,106,.04);color:var(--green-dim);font-size:12px;white-space:nowrap}
    .small{font-size:12px;color:var(--green-dim);line-height:1.35}
    textarea{width:100%;min-height:300px;resize:vertical;border-radius:10px;border:1px solid var(--border);background:#000;color:var(--green);padding:12px;font-family:var(--font);font-size:14px;line-height:1.45;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset}
    textarea::placeholder{color:rgba(53,255,106,.35)}
    select{background:#000;color:var(--green);border:1px solid var(--border);border-radius:10px;padding:8px 10px;font-family:var(--font)}
    input[type="range"]{width:min(520px,100%);accent-color:#35ff6a}
    .statusstrip{display:flex;gap:10px;flex-wrap:wrap;align-items:center;margin-top:10px;padding:8px 10px;border-radius:10px;border:1px solid var(--border);background:rgba(53,255,106,.04);color:var(--green-dim);font-size:12px}
    .dot{width:8px;height:8px;border-radius:999px;display:inline-block;border:1px solid rgba(53,255,106,.45);background:rgba(53,255,106,.15);box-shadow:0 0 10px rgba(53,255,106,.12);margin-right:6px;vertical-align:middle}
    .dot.on{background:rgba(53,255,106,.95);border-color:rgba(53,255,106,.95);box-shadow:0 0 14px rgba(53,255,106,.35)}
    .dot.warn{background:rgba(255,215,64,.9);border-color:rgba(255,215,64,.9);box-shadow:0 0 14px rgba(255,215,64,.25)}
    .kv{display:inline-flex;align-items:center;gap:8px}
    .key{color:rgba(53,255,106,.9);font-weight:800}
    .val{color:var(--green-dim)}
    .toggle{display:inline-flex;align-items:center;gap:10px;border:1px solid var(--border);background:rgba(53,255,106,.04);padding:8px 10px;border-radius:999px;user-select:none}
    .toggle input{display:none}
    .toggle .track{width:42px;height:22px;border-radius:999px;border:1px solid var(--border);background:rgba(0,0,0,.7);position:relative;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset}
    .toggle .thumb{width:18px;height:18px;border-radius:999px;position:absolute;top:1px;left:1px;background:rgba(53,255,106,.25);border:1px solid rgba(53,255,106,.6);transition:transform .18s ease;box-shadow:0 0 10px rgba(53,255,106,.22)}
    .toggle input:checked + .track .thumb{transform:translateX(20px);background:rgba(53,255,106,.85)}
    .toggle .label{font-size:12px;color:var(--green-dim)}
    .overlay{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(0,0,0,.75);padding:14px;z-index:50}
    .overlay.show{display:flex}
    .modal{width:min(860px,100%);border-radius:14px;background:#000;border:1px solid var(--border);padding:12px;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset,0 0 24px rgba(0,0,0,.65)}
    .modal h2{margin:0 0 8px;font-size:14px}
    .modal .sub{margin:0 0 10px;font-size:12px;color:var(--green-dim);line-height:1.35}
    .modal .err{border:1px solid rgba(255,77,77,.55);background:rgba(255,77,77,.08);border-radius:10px;padding:10px;color:rgba(255,150,150,.95);font-size:12px;white-space:pre-wrap}
    .actions{display:flex;gap:10px;flex-wrap:wrap;justify-content:flex-end;margin-top:10px}
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // HYBRID HARDWIRED (hybrid-hardwired-1767921463-dk9nbr)</h1>

  <div class="grid">
    <div class="card">
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b></div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny" selected>whisper-tiny (multilingual) — recommended</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (English-only)</option>
          </select>
          <div class="small">Build: <b id="buildId">hybrid-hardwired-1767921463-dk9nbr</b> • JS: <b id="jsOk">YES</b></div>
        </div>

        <div class="col" style="flex: 1 1 320px">
          <div class="small"><b>TRANSLATE</b></div>
          <label class="toggle">
            <input id="translateOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Translate to English</span>
          </label>
          <div class="small">Engine: <b id="engTxt">MAIN</b></div>
        </div>
      </div>

      <div class="row">
        <button id="btnLoadModel" onclick="window.appLoadModel()">Load AI Model</button>
        <button id="btnStart" onclick="window.appStartMic()">Start Mic</button>
        <button id="btnStop" class="danger" onclick="window.appStop()" disabled>Stop</button>
        <button id="btnHelp" onclick="window.appHelp()">Help</button>
        <button id="btnReset" onclick="window.appReset()">Reset Site</button>
        <span class="pill" id="status">idle</span>
      </div>

      <div class="statusstrip">
        <span class="kv"><span id="dotModel" class="dot"></span><span class="key">MODEL</span><span id="modelState" class="val">NOT LOADED</span></span>
        <span class="kv"><span id="dotMic" class="dot"></span><span class="key">MIC</span><span id="micState" class="val">OFF</span></span>
        <span class="kv"><span class="key">LEVEL</span><span id="lvlDb" class="val">-inf dBFS</span></span>
        <span class="kv"><span class="key">ASR</span><span id="asrMs" class="val">—</span></span>
        <span class="kv"><span class="key">TICKS</span><span id="ticks" class="val">0</span></span>
        <span class="kv"><span class="key">LAST</span><span id="lastMsg" class="val">—</span></span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>ENGINE</b></div>
          <label class="toggle" title="Optional worker for inference. Load MAIN first.">
            <input id="workerOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Use Worker engine</span>
          </label>
          <div class="small">Load model in MAIN first, then toggle Worker.</div>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>ALWAYS-ON</b></div>
          <label class="toggle">
            <input id="alwaysOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Always-on</span>
          </label>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>WINDOW</b> sec: <span id="winSecLabel">2.0</span></div>
          <input id="winSec" type="range" min="1.5" max="6" step="0.5" value="2.0" />
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>UPDATE</b> sec: <span id="updSecLabel">1.5</span></div>
          <input id="updSec" type="range" min="0.5" max="3" step="0.5" value="1.5" />
        
      
      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>REAL-TIME MODE</b></div>
          <label class="toggle" title="Toggle between Low-latency (A) and Accurate (B)">
            <input id="modeAB" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">B = slower, more accurate</span>
          </label>
          <div class="small">OFF (A): low-latency (shorter window, adaptive longer update). ON (B): accurate (longer window, waits to finish).</div>
        </div>
      </div>
<div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>SENSITIVITY</b> (audio threshold): <span id="sensLabel">0.0003</span></div>
          <input id="sens" type="range" min="0.00005" max="0.01" step="0.00005" value="0.0003" />
          <div class="small">Lower = more sensitive (captures quiet talk, more false blanks). Higher = stricter.</div>
        </div>
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>DIAG</b></div>
          <label class="toggle" title="Show why a tick was skipped (silence / model not loaded)">
            <input id="diagOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Diagnostic status</span>
          </label>
          <div class="small">Keeps you from guessing if the app is doing anything.</div>
        </div>
      </div>
</div>
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT</b></div>
          <div class="small">Translated text appended continuously.</div>
        </div>
        <div class="row">
          <button onclick="window.appCopy()">Copy</button>
          <button onclick="window.appClear()">Clear</button>
        </div>
      </div>
      <textarea id="out" placeholder="(live output will appear here)"></textarea>
    </div>
  </div>

  <div id="overlay" class="overlay" role="dialog" aria-modal="true">
    <div class="modal">
      <h2 id="ovTitle">Message</h2>
      <p class="sub" id="ovSub"></p>
      <div id="ovErr" class="err" style="display:none"></div>
      <div class="actions">
        <button id="btnCloseOv" onclick="document.getElementById('overlay').classList.remove('show')">Close</button>
      </div>
    </div>
  </div>

  <script>
    document.getElementById("buildId").textContent = "hybrid-hardwired-1767921463-dk9nbr";
    function el(id){ return document.getElementById(id); }
    function showOverlay(title, sub, err){
      el("ovTitle").textContent = title || "Message";
      el("ovSub").textContent = sub || "";
      const box = el("ovErr");
      if (err){
        box.style.display = "block";
        box.textContent = String(err);
      } else {
        box.style.display = "none";
        box.textContent = "";
      }
      el("overlay").classList.add("show");
    }
    window.addEventListener("error", (e) => showOverlay("Script error", "Buttons won't work because JS crashed.", (e?.message||"") + "\n" + (e?.filename||"") + ":" + (e?.lineno||"")));
    window.addEventListener("unhandledrejection", (e) => showOverlay("Unhandled rejection", "Async error occurred.", e?.reason?.message || e?.reason || ""));

    const statusEl = el("status");
    const dotModel = el("dotModel");
    const dotMic = el("dotMic");
    const modelState = el("modelState");
    const micState = el("micState");
    const lvlDb = el("lvlDb");
    const asrMs = el("asrMs");
    const ticksEl = el("ticks");
    const lastMsg = el("lastMsg");
    const sens = el("sens");
    const sensLabel = el("sensLabel");
    const diagOn = el("diagOn");
    const modeAB = el("modeAB");
    const engTxt = el("engTxt");

    const modelSel = el("modelSel");
    const translateOn = el("translateOn");
    const workerOn = el("workerOn");
    const alwaysOn = el("alwaysOn");
    const winSec = el("winSec");
    const winSecLabel = el("winSecLabel");
    const updSec = el("updSec");
    const updSecLabel = el("updSecLabel");
    const out = el("out");

    const btnLoadModel = el("btnLoadModel");
    const btnStart = el("btnStart");
    const btnStop = el("btnStop");

    function setStatus(s){ statusEl.textContent = s; }
    function appendWords(s){
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }

    winSecLabel.textContent = Number(winSec.value).toFixed(1);
    updSecLabel.textContent = Number(updSec.value).toFixed(1);
    sensLabel.textContent = Number(sens.value).toFixed(4);

    function requireMultilingualForTranslate(){
      if (translateOn.checked && String(modelSel.value).includes(".en")){
        showOverlay("Translation needs multilingual model", "Select whisper-tiny (multilingual).");
        translateOn.checked = false;
        return false;
      }
      return true;
    }

    async function appReset(){
      try{
        if ("serviceWorker" in navigator){
          const regs = await navigator.serviceWorker.getRegistrations();
          for (const r of regs) await r.unregister();
        }
      }catch(e){}
      try{
        if (window.caches){
          const keys = await caches.keys();
          for (const k of keys) await caches.delete(k);
        }
      }catch(e){}
      try{ localStorage.clear(); sessionStorage.clear(); }catch(e){}
      showOverlay("Reset complete", "Service workers & caches cleared. Close this tab and reopen with ?fresh=1", null);
    }

    // Audio capture ring buffer
    let audioCtx=null, stream=null, source=null, captureNode=null;
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

    // Level meter
    let meterTimer=null;
    function startMeter(){
      stopMeter();
      meterTimer = setInterval(() => {
        if (!audioCtx || !rb || rbFilled < Math.floor(audioCtx.sampleRate*0.2)) return;
        const pcm = rbGetLast(0.2, audioCtx.sampleRate);
        const m = maxAbs(pcm);
        const db = (m <= 1e-9) ? "-inf" : (20*Math.log10(m)).toFixed(1);
        lvlDb.textContent = db + " dBFS";
      }, 250);
    }
    function stopMeter(){ if (meterTimer){ clearInterval(meterTimer); meterTimer=null; } }

    // AI engines
    let modelLoaded=false;
    let loadedModelId=null;
    let asrMain=null;

    function cleanTranscript(raw){
      if (!raw) return "";
      let t=String(raw);
      t = t.replace(/[♪♫]+/g," ");
      t = t.replace(/\[([^\]]+)\]/g, " ");
      t = t.replace(/\(([^\)]+)\)/g, " ");
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");
      t = t.replace(/\s+/g," ").trim();
      if (!/[A-Za-z]/.test(t)) return "";
      if (/\b(blank_audio|mus_audio|no_audio|music)\b/i.test(t)) return "";
      return t;
    }

    // Optional worker
    let worker=null;
    let workerBusy=false;

    function makeWorker(){
      const workerCode = `
        import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";
        env.allowLocalModels = false;
        env.useBrowserCache = true;
        let asr = null;
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
            try{
              asr = await pipeline("automatic-speech-recognition", msg.modelId, { device: msg.device || "wasm" });
              self.postMessage({ type:"loaded", ok:true, modelId: msg.modelId });
            } catch (e){
              self.postMessage({ type:"loaded", ok:false, error: String(e?.message || e) });
            }
            return;
          }
          if (msg.type === "run"){
            if (!asr){
              self.postMessage({ type:"result", ok:false, error:"model_not_loaded" });
              return;
            }
            const t0 = performance.now();
            try{
              const pcm = new Float32Array(msg.pcm);
              const res = await asr(pcm, { chunk_length_s: msg.windowSec, stride_length_s: 0.2, return_timestamps:false, task: msg.task });
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
      return new Worker(url, { type:"module" });
    }

    async function ensureWorkerLoaded(){
      if (!workerOn.checked) return;
      if (!modelLoaded) return;
      if (worker) return;

      engTxt.textContent = "WORKER";
      worker = makeWorker();
      worker.onmessage = (ev) => {
        const msg = ev.data || {};
        if (msg.type === "loaded"){
          workerBusy = false;
      asrBusy = false;
          if (msg.ok){
            setStatus("worker ready");
            setTimeout(() => setStatus("listening"), 500);
          } else {
            showOverlay("Worker load failed", "Switching back to MAIN.", msg.error || "unknown");
            workerOn.checked = false;
            engTxt.textContent = "MAIN";
            try{ worker.terminate(); }catch{}
            worker = null;
          }
        }
        if (msg.type === "result"){
          workerBusy = false;
          if (typeof msg.ms === "number") asrMs.textContent = msg.ms.toFixed(0) + "ms";
          if (msg.ok && msg.text) { appendWords(msg.text); if (diagOn.checked) lastMsg.textContent = "ok"; } else { if (diagOn.checked) lastMsg.textContent = msg.ok ? "empty" : "err"; }
          asrBusy = false;
        setStatus("listening");
        }
      };
      workerBusy = true;
      worker.postMessage({ type:"load", modelId: loadedModelId, device:"wasm" });
    }

    // Load model MAIN using dynamic import (no module script tag)
    async function appLoadModel(){
      if (modelLoaded) return;
      if (!requireMultilingualForTranslate()) return;

      btnLoadModel.disabled = true;
      dotModel.classList.add("warn");
      modelState.textContent = "LOADING…";
      setStatus("loading model…");
      engTxt.textContent = "MAIN";

      try{
        const mod = await import("https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2");
        const pipeline = mod.pipeline;
        const env = mod.env;
        env.allowLocalModels = false;
        env.useBrowserCache = true;

        const t0 = performance.now();
        asrMain = await pipeline("automatic-speech-recognition", modelSel.value, { device: "wasm" });
        const dt = performance.now() - t0;

        asrMs.textContent = dt.toFixed(0) + "ms(load)";
        modelLoaded = true;
        loadedModelId = modelSel.value;
        modelSel.disabled = true;
        dotModel.classList.remove("warn");
        dotModel.classList.add("on");
        modelState.textContent = "READY";
        setStatus("model loaded");
      } catch (e){
        btnLoadModel.disabled = false;
        dotModel.classList.remove("warn");
        modelState.textContent = "ERROR";
        setStatus("model load error");
        showOverlay("Model load failed (MAIN)", "Likely blocked CDN/model downloads (VPN/Private DNS/adblock).", e?.message || e);
      }
    }

    workerOn.addEventListener("change", async () => {
      if (workerOn.checked){
        await ensureWorkerLoaded();
      } else {
        engTxt.textContent = "MAIN";
        if (worker){
          try{ worker.terminate(); }catch{}
          worker = null;
        }
      }
    });

    async function appStartMic(){
      if (!navigator.mediaDevices?.getUserMedia){
        showOverlay("Mic not supported", "This browser doesn't support getUserMedia().");
        return;
      }
      if (!window.isSecureContext && location.hostname !== "localhost"){
        showOverlay("Mic needs HTTPS", "Open from GitHub Pages (https://) or localhost.");
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
        showOverlay("Microphone error", "Could not access microphone.", e?.message || e);
        return;
      }

      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      rbInit(audioCtx.sampleRate);

      source = audioCtx.createMediaStreamSource(stream);

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

      btnStop.disabled = false;
      dotMic.classList.add("on");
      micState.textContent = "LIVE";
      setStatus("listening");

      startInferenceLoop();
      startMeter();
    }

    function appStop(){ stopAll(); }

    function stopAll(){
      stopInferenceLoop();
      stopMeter();
      try{ captureNode && captureNode.disconnect(); }catch{}
      captureNode=null;
      try{ source && source.disconnect(); }catch{}
      source=null;
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

    function appHelp(){
      showOverlay("Help", "Load AI Model (MAIN) first. If MAIN stutters, enable Worker after load. Use Reset Site if caching/PWA is interfering.", null);
    }
    function appClear(){ out.value=""; }
    async function appCopy(){
      try{ await navigator.clipboard.writeText(out.value||""); }
      catch{ showOverlay("Copy failed","Clipboard blocked. Select and copy manually."); }
    }

    // Inference loop
    let inferTimer=null;
    let tickCount = 0;
    let asrBusy = false;
    let lastRunAt = 0;
    function stopInferenceLoop(){
      if (inferTimer){ clearTimeout(inferTimer); inferTimer=null; }
      workerBusy = false;
    }
    function startInferenceLoop(){
      stopInferenceLoop();
      const tick = async () => {
        // Do not overlap inference. Wait for current run to finish.
        if (asrBusy) {
          if (diagOn.checked) lastMsg.textContent = "busy (waiting)";
          // try again soon
          inferTimer = setTimeout(tick, 250);
          return;
        }
        await runInferenceTick();

        // Choose next schedule based on A/B mode:
        // A (unchecked): aim lower latency, but if ASR is slow, back off automatically.
        // B (checked): accuracy, allow longer runs and wait a bit after completion.
        const base = Number(updSec.value);
        const asrSec = Number(String(asrMs.textContent || "0").replace("ms",""))/1000 || 0;
        let next = base;

        if (!modeAB.checked) {
          // A: low-latency target, but never schedule faster than ASR time + 0.2s
          next = Math.max(0.5, base, asrSec + 0.2);
        } else {
          // B: accuracy. Space runs more, especially if ASR is heavy.
          next = Math.max(1.5, base, asrSec + 0.6);
        }

        inferTimer = setTimeout(tick, Math.round(next*1000));
      };
      inferTimer = setTimeout(tick, 700);
    };
      inferTimer = setTimeout(tick, 700);
    }

    async function runMain(pcm, windowSec){
      const t0 = performance.now();
      const res = await asrMain(pcm, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false, task: (translateOn.checked ? "translate" : undefined) });
      const dt = performance.now() - t0;
      asrMs.textContent = dt.toFixed(0) + "ms";
      const cleaned = cleanTranscript((res?.text || "").trim());
      if (cleaned) { appendWords(cleaned); if (diagOn.checked) lastMsg.textContent = "ok"; }
    }

    async function runInferenceTick(){
      tickCount++; ticksEl.textContent = String(tickCount);
      if (!audioCtx || !rb) { if (diagOn.checked) lastMsg.textContent = "no mic"; return; }
      if (!modelLoaded) { if (diagOn.checked) lastMsg.textContent = "model not loaded"; return; }
      const sr = audioCtx.sampleRate;
      let windowSec = Number(winSec.value);
      // Mode presets
      if (!modeAB.checked) {
        // A: low-latency
        windowSec = Math.min(windowSec, 2.0);
      } else {
        // B: accuracy
        windowSec = Math.max(windowSec, 3.0);
      }
      if (rbFilled < Math.floor(sr*1.0)) return;

      const pcm = rbGetLast(windowSec, sr);
      const m = maxAbs(pcm);
      const thr = Number(sens.value);
      if (m < (alwaysOn.checked ? thr : Math.max(thr*2, 0.001))) { if (diagOn.checked) lastMsg.textContent = "silence"; return; }

      setStatus("transcribing…");
      if (diagOn.checked) lastMsg.textContent = "transcribing";
      asrBusy = true;
      lastRunAt = Date.now();

      if (workerOn.checked){
        await ensureWorkerLoaded();
        if (worker){
          if (workerBusy) return;
          workerBusy = true;
          try{
            worker.postMessage({ type:"run", pcm: pcm.buffer, windowSec: windowSec, task: (translateOn.checked ? "translate" : undefined) }, [pcm.buffer]);
          } catch (e){
            workerBusy = false;
          }
          return;
        }
      }

      await runMain(pcm, windowSec);
      asrBusy = false;
      setStatus("listening");
    }

    // UI bindings
    winSec.addEventListener("input", () => { winSecLabel.textContent = Number(winSec.value).toFixed(1); });
    updSec.addEventListener("input", () => { updSecLabel.textContent = Number(updSec.value).toFixed(1); });
    translateOn.addEventListener("change", requireMultilingualForTranslate);
    sens.addEventListener("input", () => { sensLabel.textContent = Number(sens.value).toFixed(4); });
    modeAB.addEventListener("change", () => {
      if (modeAB.checked) {
        // B: accuracy
        if (Number(winSec.value) < 3.0) { winSec.value = "3.0"; winSecLabel.textContent = "3.0"; }
        if (Number(updSec.value) < 2.0) { updSec.value = "2.0"; updSecLabel.textContent = "2.0"; }
        if (diagOn.checked) lastMsg.textContent = "mode B";
      } else {
        // A: low latency
        if (Number(winSec.value) > 2.0) { winSec.value = "2.0"; winSecLabel.textContent = "2.0"; }
        if (Number(updSec.value) > 1.5) { updSec.value = "1.5"; updSecLabel.textContent = "1.5"; }
        if (diagOn.checked) lastMsg.textContent = "mode A";
      }
      if (audioCtx) startInferenceLoop();
    });


    // Expose for inline onclick
    window.appLoadModel = appLoadModel;
    window.appStartMic = appStartMic;
    window.appStop = appStop;
    window.appHelp = appHelp;
    window.appClear = appClear;
    window.appCopy = appCopy;
    window.appReset = appReset;

    // Init
    dotModel.classList.remove("on","warn");
    dotMic.classList.remove("on");
    modelState.textContent = "NOT LOADED";
    micState.textContent = "OFF";
    setStatus("idle");
    asrMs.textContent = "—";
    requireMultilingualForTranslate();
  </script>
</body>
</html>
