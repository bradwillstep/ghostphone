<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta http-equiv="Cache-Control" content="no-store" />
  <title>Ultra Listener — Output Fix (fixout-1767926144-djbla)</title>
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
    textarea{width:100%;min-height:320px;resize:vertical;border-radius:10px;border:1px solid var(--border);background:#000;color:var(--green);padding:12px;font-family:var(--font);font-size:14px;line-height:1.45;box-shadow:0 0 0 1px rgba(53,255,106,.08) inset}
    textarea::placeholder{color:rgba(53,255,106,.35)}
    select{background:#000;color:var(--green);border:1px solid var(--border);border-radius:10px;padding:8px 10px;font-family:var(--font)}
    input[type="range"]{width:min(520px,100%);accent-color:#35ff6a}
    .statusstrip{display:flex;gap:10px;flex-wrap:wrap;align-items:center;margin-top:10px;padding:8px 10px;border-radius:10px;border:1px solid var(--border);background:rgba(53,255,106,.04);color:var(--green-dim);font-size:12px}
    .dot{width:8px;height:8px;border-radius:999px;display:inline-block;border:1px solid rgba(53,255,106,.45);background:rgba(53,255,106,.15);box-shadow:0 0 10px rgba(53,255,106,.12);margin-right:6px;vertical-align:middle}
    .dot.on{background:rgba(53,255,106,.95);border-color:rgba(53,255,106,.95)}
    .dot.warn{background:rgba(255,215,64,.9);border-color:rgba(255,215,64,.9)}
    .kv{display:inline-flex;align-items:center;gap:8px}
    .key{color:rgba(53,255,106,.9);font-weight:800}
    .toggle{display:inline-flex;align-items:center;gap:10px;border:1px solid var(--border);background:rgba(53,255,106,.04);padding:8px 10px;border-radius:999px;user-select:none}
    .toggle input{display:none}
    .toggle .track{width:42px;height:22px;border-radius:999px;border:1px solid var(--border);background:rgba(0,0,0,.7);position:relative}
    .toggle .thumb{width:18px;height:18px;border-radius:999px;position:absolute;top:1px;left:1px;background:rgba(53,255,106,.25);border:1px solid rgba(53,255,106,.6);transition:transform .18s ease}
    .toggle input:checked + .track .thumb{transform:translateX(20px);background:rgba(53,255,106,.85)}
    .toggle .label{font-size:12px;color:var(--green-dim)}
    .seg{display:inline-flex;border:1px solid var(--border);border-radius:999px;overflow:hidden;background:rgba(53,255,106,.04)}
    .seg input{display:none}
    .seg label{padding:8px 10px;font-size:12px;color:var(--green-dim);cursor:pointer;border-right:1px solid rgba(53,255,106,.18)}
    .seg label:last-child{border-right:0}
    .seg input:checked + label{color:var(--bg);background:rgba(53,255,106,.85)}
    .overlay{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(0,0,0,.75);padding:14px;z-index:50}
    .overlay.show{display:flex}
    .modal{width:min(860px,100%);border-radius:14px;background:#000;border:1px solid var(--border);padding:12px}
    .modal .err{border:1px solid rgba(255,77,77,.55);background:rgba(255,77,77,.08);border-radius:10px;padding:10px;color:rgba(255,150,150,.95);font-size:12px;white-space:pre-wrap}
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // OUTPUT FIX (fixout-1767926144-djbla)</h1>

  <div class="grid">
    <div class="card">
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b></div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny" selected>whisper-tiny (multilingual)</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (English-only)</option>
          </select>
          <div class="small">Build: <b>fixout-1767926144-djbla</b></div>
        </div>

        <div class="col" style="flex: 1 1 340px">
          <div class="small"><b>MODE</b></div>
          <div class="seg">
            <input type="radio" name="ab" id="modeA" checked><label for="modeA">A Fast</label>
            <input type="radio" name="ab" id="modeB"><label for="modeB">B EVP</label>
          </div>
          <div class="small">A: shorter window. B: longer window + more spacing.</div>
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
        <button id="btnTest">Test Output</button>
        <span class="pill" id="status">idle</span>
      </div>

      <div class="statusstrip">
        <span class="kv"><span id="dotModel" class="dot"></span><span class="key">MODEL</span><span id="modelState" class="val">NOT LOADED</span></span>
        <span class="kv"><span id="dotMic" class="dot"></span><span class="key">MIC</span><span id="micState" class="val">OFF</span></span>
        <span class="kv"><span class="key">LEVEL</span><span id="lvlDb" class="val">-inf dBFS</span></span>
        <span class="kv"><span class="key">ASR</span><span id="asrMs" class="val">—</span></span>
        <span class="kv"><span class="key">LAST</span><span id="lastState" class="val">—</span></span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <label class="toggle" title="If on, we will print raw text even when filtering removes everything">
            <input id="showRaw" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Show RAW when empty</span>
          </label>
        </div>
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>Sensitivity</b>: <span id="sensLabel">0.0002</span></div>
          <input id="sens" type="range" min="0.00005" max="0.01" step="0.00005" value="0.0002" />
          <div class="small">Lower = more sensitive.</div>
        </div>
      </div>

      <div class="small" style="margin-top:10px">
        If ASR is ~9000ms, you won't see words instantly. This build waits for each run to finish and always logs RAW text when empty.
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT</b></div>
          <div class="small">This should always populate if ASR returns anything.</div>
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
      <div class="err" id="ovErr"></div>
      <div class="actions"><button id="btnCloseOv">Close</button></div>
    </div>
  </div>

  <script type="module">
    import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";

    const el = (id) => document.getElementById(id);
    const out = el("out");

    const btnLoadModel = el("btnLoadModel");
    const btnStart = el("btnStart");
    const btnStop = el("btnStop");
    const btnTest = el("btnTest");
    const btnCopy = el("btnCopy");
    const btnClear = el("btnClear");

    const modelSel = el("modelSel");
    const translateOn = el("translateOn");
    const modeA = el("modeA");
    const modeB = el("modeB");
    const showRaw = el("showRaw");

    const sens = el("sens");
    const sensLabel = el("sensLabel");

    const statusEl = el("status");
    const dotModel = el("dotModel");
    const dotMic = el("dotMic");
    const modelState = el("modelState");
    const micState = el("micState");
    const lvlDb = el("lvlDb");
    const asrMs = el("asrMs");
    const lastState = el("lastState");

    const overlay = el("overlay");
    const ovErr = el("ovErr");
    el("btnCloseOv").addEventListener("click", () => overlay.classList.remove("show"));

    function setStatus(s){ statusEl.textContent = s; }
    function appendLine(s){
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }
    function showError(err){
      ovErr.textContent = String(err);
      overlay.classList.add("show");
    }

    window.addEventListener("error", (e)=>showError((e?.message||"")+"\n"+(e?.filename||"")+":"+e?.lineno));
    window.addEventListener("unhandledrejection", (e)=>showError(e?.reason?.message||e?.reason||"unhandled"));

    // Model
    let asr = null;
    let modelLoaded = false;

    // Audio
    let audioCtx=null, stream=null, source=null, captureNode=null;
    let rb=null, rbSize=0, rbWrite=0, rbFilled=0;

    function rbInit(sr){
      rbSize = Math.max(1, Math.floor(sr*12));
      rb = new Float32Array(rbSize);
      rbWrite=0; rbFilled=0;
    }
    function rbPush(block){
      const n=block.length;
      for (let i=0;i<n;i++){ rb[rbWrite]=block[i]; rbWrite=(rbWrite+1)%rbSize; }
      rbFilled = Math.min(rbSize, rbFilled+n);
    }
    function rbGetLast(seconds, sr){
      const need = Math.min(rbFilled, Math.floor(seconds*sr));
      const outArr = new Float32Array(need);
      const start = (rbWrite-need+rbSize)%rbSize;
      if (start+need <= rbSize) outArr.set(rb.subarray(start,start+need));
      else {
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

    function cleanTranscript(raw){
      if (!raw) return "";
      let t=String(raw);
      t = t.replace(/[♪♫]+/g," ");
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");
      t = t.replace(/\s+/g," ").trim();
      // accept any language letters
      if (!/\p{L}/u.test(t)) return "";
      return t;
    }

    // Scheduler (no overlap)
    let inferTimer=null;
    let busy=false;
    let lastAsr=0;

    function stopInfer(){
      if (inferTimer){ clearTimeout(inferTimer); inferTimer=null; }
      busy=false;
    }

    function scheduleNext(ms){
      inferTimer = setTimeout(loop, ms);
    }

    async function loop(){
      if (!audioCtx || !rb || !modelLoaded || !asr) return;
      if (busy) return;

      let windowSec = Number(el("winSecLabel").textContent || "2");
      // derive from mode + slider values
      windowSec = modeB.checked ? Math.max(Number(windowSec), 3.0) : Math.min(Number(windowSec), 2.0);
      const sr = audioCtx.sampleRate;
      if (rbFilled < Math.floor(sr*1.0)){ scheduleNext(300); return; }

      const pcm = rbGetLast(windowSec, sr);
      const m = maxAbs(pcm);
      const thr = Number(sens.value);
      if (m < thr){ lastState.textContent="silence"; scheduleNext(300); return; }

      busy=true;
      setStatus("transcribing…");
      lastState.textContent="transcribing";

      try{
        const t0 = performance.now();
        const res = await asr(pcm, {
          chunk_length_s: windowSec,
          stride_length_s: 0.2,
          return_timestamps:false,
          task: (translateOn.checked ? "translate" : undefined)
        });
        const dt = performance.now() - t0;
        lastAsr = dt;
        asrMs.textContent = dt.toFixed(0) + "ms";

        const raw = (res?.text || "").trim();
        const cleaned = cleanTranscript(raw);

        if (cleaned) {
          appendLine(cleaned);
          lastState.textContent="ok";
        } else if (showRaw.checked) {
          // always show what model returned, even if it's junk, so you never get "nothing"
          appendLine("[RAW] " + (raw || "(empty)"));
          lastState.textContent="raw";
        } else {
          lastState.textContent="empty";
        }
      } catch(e) {
        lastState.textContent="error";
        showError(e?.message || e);
      } finally {
        busy=false;
        setStatus("listening");
      }

      // adaptive spacing: at least slider update or ASR time + slack
      const base = modeB.checked ? 6000 : 2500;
      const next = Math.max(base, lastAsr + (modeB.checked ? 1200 : 400));
      scheduleNext(next);
    }

    async function loadModel(){
      if (modelLoaded) return;
      btnLoadModel.disabled = true;
      dotModel.classList.add("warn");
      modelState.textContent = "LOADING…";
      setStatus("loading model…");
      lastState.textContent="loading";
      try{
        env.allowLocalModels = false;
        env.useBrowserCache = true;
        const t0=performance.now();
        asr = await pipeline("automatic-speech-recognition", modelSel.value, { device:"wasm" });
        const dt=performance.now()-t0;
        asrMs.textContent = dt.toFixed(0) + "ms(load)";
        modelLoaded=true;
        dotModel.classList.remove("warn");
        dotModel.classList.add("on");
        modelState.textContent="READY";
        setStatus("model loaded");
        lastState.textContent="ready";
      } catch(e) {
        btnLoadModel.disabled = false;
        dotModel.classList.remove("warn");
        modelState.textContent="ERROR";
        setStatus("model load error");
        showError(e?.message || e);
      }
    }

    async function startMic(){
      if (!navigator.mediaDevices?.getUserMedia){ showError("getUserMedia not supported"); return; }
      if (!window.isSecureContext && location.hostname !== "localhost"){ showError("Mic requires HTTPS or localhost"); return; }
      if (audioCtx) return;

      setStatus("requesting mic…");
      btnStart.disabled=true;
      try{
        stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
      } catch(e) {
        btnStart.disabled=false;
        showError(e?.message || e);
        return;
      }

      audioCtx = new (window.AudioContext||window.webkitAudioContext)();
      rbInit(audioCtx.sampleRate);
      source = audioCtx.createMediaStreamSource(stream);

      if (audioCtx.audioWorklet) {
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

      btnStop.disabled=false;
      dotMic.classList.add("on");
      micState.textContent="LIVE";
      setStatus("listening");
      startMeter();
      stopInfer();
      scheduleNext(800);
    }

    function stopAll(){
      stopInfer();
      stopMeter();
      try{ captureNode?.disconnect(); }catch{}
      captureNode=null;
      try{ source?.disconnect(); }catch{}
      source=null;
      if (stream){ for (const t of stream.getTracks()) t.stop(); stream=null; }
      if (audioCtx){ audioCtx.close(); audioCtx=null; }
      rb=null; rbSize=rbWrite=rbFilled=0;
      btnStart.disabled=false;
      btnStop.disabled=true;
      dotMic.classList.remove("on");
      micState.textContent="OFF";
      setStatus("stopped");
      lastState.textContent="stopped";
    }

    // UI wiring
    btnLoadModel.addEventListener("click", loadModel);
    btnStart.addEventListener("click", startMic);
    btnStop.addEventListener("click", stopAll);
    btnTest.addEventListener("click", () => appendLine("[TEST] output append works"));
    btnClear.addEventListener("click", () => { out.value=""; });
    btnCopy.addEventListener("click", async () => {
      try{ await navigator.clipboard.writeText(out.value||""); }catch(e){ showError(e); }
    });
    sens.addEventListener("input", ()=> sensLabel.textContent = Number(sens.value).toFixed(4));
    modeA.addEventListener("change", ()=>{ winSec.value="2.0"; winSecLabel.textContent="2.0"; updSec.value="2.0"; updSecLabel.textContent="2.0"; });
    modeB.addEventListener("change", ()=>{ winSec.value="4.0"; winSecLabel.textContent="4.0"; updSec.value="6.0"; updSecLabel.textContent="6.0"; });
    translateOn.addEventListener("change", ()=>{ /* keep */ });

    // init
    setStatus("idle");
    modelState.textContent="NOT LOADED";
    micState.textContent="OFF";
    lastState.textContent="—";
  </script>
</body>
</html>
