<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta http-equiv="Cache-Control" content="no-store, no-cache, must-revalidate, max-age=0" />
  <meta http-equiv="Pragma" content="no-cache" />
  <meta http-equiv="Expires" content="0" />
  <title>Ultra Listener — AutoFix A/B Adaptive (autofix-ab-adapt-1767924460)</title>
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
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // AUTOFIX A/B ADAPTIVE (autofix-ab-adapt-1767924460)</h1>

  <div class="grid">
    <div class="card">
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b></div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny" selected>whisper-tiny (multilingual) — recommended</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (English-only)</option>
          </select>
          <div class="small">Build: <b id="buildId">autofix-ab-adapt-1767924460</b> • CacheFix: <b id="fixState">pending</b></div>
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
        <button id="btnReset">Reset Site</button>
        <span class="pill" id="status">idle</span>
      </div>

      <div class="statusstrip">
        <span class="kv"><span id="dotModel" class="dot"></span><span class="key">MODEL</span><span id="modelState" class="val">NOT LOADED</span></span>
        <span class="kv"><span id="dotMic" class="dot"></span><span class="key">MIC</span><span id="micState" class="val">OFF</span></span>
        <span class="kv"><span class="key">LEVEL</span><span id="lvlDb" class="val">-inf dBFS</span></span>
        <span class="kv"><span class="key">ASR</span><span id="asrMs" class="val">—</span></span>
        <span class="kv"><span class="key">NEXT</span><span id="nextIn" class="val">—</span></span>
        <span class="kv"><span class="key">LAST</span><span id="lastState" class="val">—</span></span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>MODE</b></div>
          <label class="toggle" title="A=fast translation, B=EVP accurate">
            <input id="modeAB" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">B = Accurate / EVP</span>
          </label>
          <div class="small">A runs more often. B runs less often and uses longer window.</div>
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
          <input id="winSec" type="range" min="1.5" max="8" step="0.5" value="2.0" />
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>UPDATE</b> sec: <span id="updSecLabel">1.5</span></div>
          <input id="updSec" type="range" min="0.5" max="10" step="0.5" value="1.5" />
          <div class="small">Adaptive scheduler will override this upward if ASR is slow.</div>
        </div>
      </div>

      <div class="small" style="margin-top:10px">
        Your ASR time is ~9 seconds. This build will automatically wait long enough for a run to finish before starting the next one, so text can actually appear.
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT</b></div>
          <div class="small">Translated text appended continuously. If translation is empty, it falls back to [SRC] transcript so you still see words.</div>
        </div>
        <div class="row">
          <button id="btnCopy">Copy</button>
          <button id="btnClear">Clear</button>
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
        <button id="btnCloseOv">Close</button>
      </div>
    </div>
  </div>

  <script>
    // Basic cache defense: best-effort unregister SW + clear CacheStorage once per tab session (no forced reload loop).
    const fixState = document.getElementById("fixState");
    (async () => {
      try{
        if (sessionStorage.getItem("ul_fix_done") === "1"){
          fixState.textContent = "done";
          return;
        }
        sessionStorage.setItem("ul_fix_done","1");
        if ("serviceWorker" in navigator){
          const regs = await navigator.serviceWorker.getRegistrations();
          for (const r of regs) await r.unregister();
        }
        if (window.caches){
          const keys = await caches.keys();
          for (const k of keys) await caches.delete(k);
        }
        fixState.textContent = "done";
      }catch(e){
        fixState.textContent = "skipped";
      }
    })();

    function el(id){ return document.getElementById(id); }
    el("buildId").textContent = "autofix-ab-adapt-1767924460";
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
    el("btnCloseOv").addEventListener("click", () => el("overlay").classList.remove("show"));
    window.addEventListener("error", (e) => showOverlay("Script error", "JS crashed.", (e?.message||"") + "\n" + (e?.filename||"") + ":" + (e?.lineno||"")));
    window.addEventListener("unhandledrejection", (e) => showOverlay("Unhandled rejection", "Async error occurred.", e?.reason?.message || e?.reason || ""));

    const statusEl = el("status");
    const dotModel = el("dotModel");
    const dotMic = el("dotMic");
    const modelState = el("modelState");
    const micState = el("micState");
    const lvlDb = el("lvlDb");
    const asrMsEl = el("asrMs");
    const nextInEl = el("nextIn");
    const lastState = el("lastState");

    const modelSel = el("modelSel");
    const translateOn = el("translateOn");
    const modeAB = el("modeAB");
    const alwaysOn = el("alwaysOn");
    const winSec = el("winSec");
    const winSecLabel = el("winSecLabel");
    const updSec = el("updSec");
    const updSecLabel = el("updSecLabel");
    const out = el("out");

    const btnLoadModel = el("btnLoadModel");
    const btnStart = el("btnStart");
    const btnStop = el("btnStop");
    const btnHelp = el("btnHelp");
    const btnReset = el("btnReset");
    const btnCopy = el("btnCopy");
    const btnClear = el("btnClear");

    function setStatus(s){ statusEl.textContent = s; }
    function appendWords(s){
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }

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
      showOverlay("Reset complete", "Close this tab and reopen the page.", null);
    }

    // Audio capture
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

    // Meter
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

    // AI main engine
    let modelLoaded=false;
    let asrMain=null;
    function cleanTranscript(raw){
      if (!raw) return "";
      let t=String(raw);
      t = t.replace(/[♪♫]+/g," ");
      t = t.replace(/\[([^\]]+)\]/g, " ");
      t = t.replace(/\(([^\)]+)\)/g, " ");
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");
      t = t.replace(/\s+/g," ").trim();
      if (!/\p{L}/u.test(t)) return "";
      if (/\b(blank_audio|mus_audio|no_audio|music)\b/i.test(t)) return "";
      return t;
    }

    async function appLoadModel(){
      if (modelLoaded) return;
      if (!requireMultilingualForTranslate()) return;

      btnLoadModel.disabled = true;
      dotModel.classList.add("warn");
      modelState.textContent = "LOADING…";
      setStatus("loading model…");
      lastState.textContent = "loading";

      try{
        const mod = await import("https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2");
        const { pipeline, env } = mod;
        env.allowLocalModels = false;
        env.useBrowserCache = true;
        const t0 = performance.now();
        asrMain = await pipeline("automatic-speech-recognition", modelSel.value, { device: "wasm" });
        const dt = performance.now() - t0;
        asrMsEl.textContent = dt.toFixed(0) + "ms(load)";
        modelLoaded = true;

        dotModel.classList.remove("warn");
        dotModel.classList.add("on");
        modelState.textContent = "READY";
        setStatus("model loaded");
        lastState.textContent = "ready";
      } catch (e){
        btnLoadModel.disabled = false;
        dotModel.classList.remove("warn");
        modelState.textContent = "ERROR";
        setStatus("model load error");
        lastState.textContent = "load error";
        showOverlay("Model load failed", "Likely blocked CDN/model downloads (VPN/Private DNS/adblock).", e?.message || e);
      }
    }

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
      lastState.textContent = "request mic";

      try{
        stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
      } catch (e){
        btnStart.disabled = false;
        setStatus("mic error");
        lastState.textContent = "mic error";
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
      lastState.textContent = "listening";

      startInferenceLoop();
      startMeter();
    }

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
      lastState.textContent = "stopped";
    }

    function appHelp(){
      showOverlay("Help", "If ASR shows ~9000ms like yours, you MUST wait ~10s between runs. This build does that automatically. Use Mode A for faster, Mode B for EVP accuracy.", null);
    }
    function appClear(){ out.value=""; }
    async function appCopy(){
      try{ await navigator.clipboard.writeText(out.value||""); }
      catch{ showOverlay("Copy failed","Clipboard blocked. Select and copy manually."); }
    }

    // A/B presets
    function applyMode(){
      if (modeAB.checked){
        // B (EVP): longer window, slower base update
        if (Number(winSec.value) < 3.0) winSec.value = "3.0";
        if (Number(updSec.value) < 5.0) updSec.value = "5.0";
      } else {
        // A (fast): shorter window, smaller base (but adaptive will still wait)
        if (Number(winSec.value) > 2.0) winSec.value = "2.0";
        if (Number(updSec.value) > 2.0) updSec.value = "2.0";
      }
      winSecLabel.textContent = Number(winSec.value).toFixed(1);
      updSecLabel.textContent = Number(updSec.value).toFixed(1);
      if (audioCtx) startInferenceLoop();
    }

    modeAB.addEventListener("change", applyMode);
    winSec.addEventListener("input", () => { winSecLabel.textContent = Number(winSec.value).toFixed(1); });
    updSec.addEventListener("input", () => { updSecLabel.textContent = Number(updSec.value).toFixed(1); });

    // Non-overlap adaptive scheduler
    let inferTimer=null;
    let busy=false;
    let lastAsrMs=0;

    function stopInferenceLoop(){
      if (inferTimer){ clearTimeout(inferTimer); inferTimer=null; }
      busy = false;
    }

    function scheduleNext(ms){
      // show countdown
      const sec = Math.max(0, ms/1000);
      nextInEl.textContent = sec.toFixed(1) + "s";
      const start = Date.now();
      const tick = () => {
        const left = ms - (Date.now() - start);
        if (left <= 0){ nextInEl.textContent = "0.0s"; return; }
        nextInEl.textContent = (left/1000).toFixed(1) + "s";
        setTimeout(tick, 200);
      };
      setTimeout(tick, 200);
      inferTimer = setTimeout(loop, ms);
    }

    async function loop(){
      // If a run is still busy, wait a bit
      if (busy){ lastState.textContent = "busy"; inferTimer = setTimeout(loop, 250); return; }
      await runInferenceTick();
      // Adaptive next interval: at least base update, and at least ASR time + slack
      const base = Number(updSec.value) * 1000;
      const slack = modeAB.checked ? 900 : 300; // B waits more
      const next = Math.max(base, lastAsrMs + slack);
      scheduleNext(next);
    }

    function startInferenceLoop(){
      stopInferenceLoop();
      scheduleNext(800);
    }

    async function runInferenceTick(){
      if (!audioCtx || !rb || !modelLoaded || !asrMain){
        if (diagOn.checked) lastState.textContent = "waiting";
        return;
      }
      const sr = audioCtx.sampleRate;
      let windowSec = Number(winSec.value);
      if (rbFilled < Math.floor(sr*1.0)) return;

      const pcm = rbGetLast(windowSec, sr);
      const m = maxAbs(pcm);
      const thr = 0.0003;
      if (m < (alwaysOn.checked ? thr : 0.001)) { if (diagOn.checked) lastState.textContent = "silence"; return; }

      busy = true;
      setStatus("transcribing…");
      lastState.textContent = "transcribing";

      try{
        const t0 = performance.now();
        const res = await asrMain(pcm, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false, task: (translateOn.checked ? "translate" : undefined) });
        const dt = performance.now() - t0;
        lastAsrMs = dt;
        asrMsEl.textContent = dt.toFixed(0) + "ms";

        let rawText = (res?.text || "").trim();
        let cleaned = cleanTranscript(rawText);

        // Fallback for real-world audio:
        // Whisper "translate" often returns empty in noisy/overlapping speech. If that happens, try plain transcription once.
        if (!cleaned && translateOn.checked) {
          try {
            const res2 = await asrMain(pcm, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false });
            const raw2 = (res2?.text || "").trim();
            const cleaned2 = cleanTranscript(raw2);
            if (cleaned2) {
              cleaned = cleaned2;
              // mark as source-language (untranslated) so the user still gets words
              appendWords("[SRC] " + cleaned2);
              lastState.textContent = "src";
            }
          } catch (e2) {
            // ignore fallback errors
          }
        }

        if (cleaned) {
          // If we already appended [SRC], avoid double-appending
          if (lastState.textContent !== "src") {
            appendWords(cleaned);
            lastState.textContent = "ok";
          }
        } else {
          lastState.textContent = "empty";
        }
        setStatus("listening");
      } catch (e){
        lastState.textContent = "error";
        showOverlay("ASR error", "Inference failed.", e?.message || e);
        setStatus("error");
      } finally {
        busy = false;
      }
    }

    // Wire buttons
    btnLoadModel.addEventListener("click", appLoadModel);
    btnStart.addEventListener("click", appStartMic);
    btnStop.addEventListener("click", stopAll);
    btnHelp.addEventListener("click", appHelp);
    btnReset.addEventListener("click", appReset);
    btnCopy.addEventListener("click", appCopy);
    btnClear.addEventListener("click", appClear);
    translateOn.addEventListener("change", requireMultilingualForTranslate);

    // Init
    dotModel.classList.remove("on","warn");
    dotMic.classList.remove("on");
    modelState.textContent = "NOT LOADED";
    micState.textContent = "OFF";
    setStatus("idle");
    asrMsEl.textContent = "—";
    lastState.textContent = "—";
    nextInEl.textContent = "—";
    requireMultilingualForTranslate();
  </script>
</body>
</html>
