<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta http-equiv="Cache-Control" content="no-store, no-cache, must-revalidate, max-age=0" />
  <meta http-equiv="Pragma" content="no-cache" />
  <meta http-equiv="Expires" content="0" />
  <title>Ultra Listener — Hardwired Stable (hardwired-stable-1767932752-cj0ui)</title>
  <style>
    :root{color-scheme:dark;--bg:#000;--panel:#050505;--border:#0f3a18;--green:#35ff6a;--green-dim:rgba(53,255,106,.78);--red:#ff4d4d;--font:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;}
    body{margin:0;padding:14px;background:var(--bg);color:var(--green);font-family:var(--font);letter-spacing:.2px}
    h1{margin:0 0 10px;font-size:16px;text-shadow:0 0 8px rgba(53,255,106,.25)}
    .card{background:linear-gradient(180deg, rgba(53,255,106,.05), transparent 35%), var(--panel);border:1px solid var(--border);border-radius:12px;padding:12px}
    .row{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
    .col{display:flex;flex-direction:column;gap:6px}
    button{background:transparent;color:var(--green);border:1px solid var(--border);padding:10px 12px;border-radius:10px;font-weight:800;cursor:pointer}
    button:disabled{opacity:.55;cursor:not-allowed}
    button.danger{border-color:rgba(255,77,77,.7);color:var(--red)}
    .pill{display:inline-flex;align-items:center;gap:8px;padding:4px 8px;border-radius:999px;border:1px solid var(--border);background:rgba(53,255,106,.04);color:var(--green-dim);font-size:12px;white-space:nowrap}
    textarea{width:100%;min-height:320px;resize:vertical;border-radius:10px;border:1px solid var(--border);background:#000;color:var(--green);padding:12px;font-family:var(--font);font-size:14px;line-height:1.45}
    .small{font-size:12px;color:var(--green-dim);line-height:1.35}
    .toggle{display:inline-flex;align-items:center;gap:10px;border:1px solid var(--border);background:rgba(53,255,106,.04);padding:8px 10px;border-radius:999px;user-select:none}
    .toggle input{display:none}
    .toggle .track{width:42px;height:22px;border-radius:999px;border:1px solid var(--border);background:rgba(0,0,0,.7);position:relative}
    .toggle .thumb{width:18px;height:18px;border-radius:999px;position:absolute;top:1px;left:1px;background:rgba(53,255,106,.25);border:1px solid rgba(53,255,106,.6);transition:transform .18s ease}
    .toggle input:checked + .track .thumb{transform:translateX(20px);background:rgba(53,255,106,.85)}
    .toggle .label{font-size:12px;color:var(--green-dim)}
    .overlay{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(0,0,0,.8);padding:14px;z-index:9999}
    .overlay.show{display:flex}
    .modal{width:min(900px,100%);border-radius:14px;background:#000;border:1px solid var(--border);padding:12px}
    .err{border:1px solid rgba(255,77,77,.55);background:rgba(255,77,77,.08);border-radius:10px;padding:10px;color:rgba(255,150,150,.95);white-space:pre-wrap}
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // HARDWIRED STABLE</h1>

  <div class="card">
    <div class="row">
      <button onclick="app.loadModel()">Load AI Model</button>
      <button onclick="app.startMic()">Start Mic</button>
      <button class="danger" onclick="app.stop()" id="btnStop" disabled>Stop</button>
      <button onclick="app.startCountdown()">Start Countdown</button>
      <button class="danger" onclick="app.stopCountdown()" id="btnStopCd" disabled>Stop Countdown</button>
      <label class="toggle" title="Loop the countdown automatically">
        <input id="loopOn" type="checkbox" checked />
        <span class="track"><span class="thumb"></span></span>
        <span class="label">Loop</span>
      </label>
      <button onclick="app.test()">Test Output</button>
      <button onclick="app.reset()">Reset Site</button>
      <span class="pill">Build: <b id="build">hardwired-stable-1767932752-cj0ui</b></span>
      <span class="pill">JS: <b id="jsok">YES</b></span>
    </div>

    <div class="row" style="margin-top:10px">
      <span class="pill">Model: <b id="mstate">NOT LOADED</b></span>
      <span class="pill">Mic: <b id="micstate">OFF</b></span>
      <span class="pill">Level: <b id="level">-inf</b></span>
      <span class="pill">ASR: <b id="asrms">—</b></span>
      <span class="pill">Cue: <b id="cuestate">OFF</b></span>
      <span class="pill">Speak in: <b id="cuein">—</b></span>
      <span class="pill">Left: <b id="cueleft">—</b></span>
    </div>

    <div class="row" style="margin-top:10px">
      <div class="col" style="flex:1 1 220px">
        <div class="small"><b>Countdown</b> sec: <span id="cdLbl">3</span></div>
        <input id="cd" type="range" min="0" max="10" step="1" value="3" />
      </div>
      <div class="col" style="flex:1 1 220px">
        <div class="small"><b>Capture</b> sec: <span id="capLbl">6</span></div>
        <input id="cap" type="range" min="2" max="15" step="1" value="6" />
      </div>
      <div class="col" style="flex:1 1 220px">
        <div class="small"><b>Window</b> sec: <span id="winLbl">4.0</span></div>
        <input id="win" type="range" min="2" max="10" step="0.5" value="4.0" />
      </div>
      <div class="col" style="flex:1 1 220px">
        <div class="small"><b>Update</b> sec: <span id="updLbl">3.0</span></div>
        <input id="upd" type="range" min="1" max="10" step="0.5" value="3.0" />
      </div>
      <div class="col" style="flex:1 1 220px">
        <div class="small"><b>Sensitivity</b>: <span id="sensLbl">0.0002</span></div>
        <input id="sens" type="range" min="0.00005" max="0.01" step="0.00005" value="0.0002" />
      </div>
    </div>

    <div class="small" style="margin-top:10px">
      Hardwired buttons + on-screen errors. If model/CDN is blocked, you'll get a visible error instead of dead UI.
    </div>

    <div style="margin-top:10px">
      <textarea id="out" placeholder="(output will appear here)"></textarea>
    </div>
  </div>

  <div id="overlay" class="overlay">
    <div class="modal">
      <div class="err" id="errBox"></div>
      <div class="row" style="justify-content:flex-end;margin-top:10px">
        <button onclick="document.getElementById('overlay').classList.remove('show')">Close</button>
      </div>
    </div>
  </div>

  <script>
    const el = (id) => document.getElementById(id);
    const out = el("out");
    const errBox = el("errBox");
    const overlay = el("overlay");

    function log(line) {
      out.value += (out.value && !out.value.endsWith("\n") ? "\n" : "") + line;
      out.scrollTop = out.scrollHeight;
    }
    function showErr(msg) {
      errBox.textContent = String(msg);
      overlay.classList.add("show");
    }
    window.addEventListener("error", (e)=>showErr((e?.message||"")+"\n"+(e?.filename||"")+":"+e?.lineno));
    window.addEventListener("unhandledrejection", (e)=>showErr(e?.reason?.message || e?.reason || "unhandled rejection"));

    const state = {
      audioCtx:null, stream:null, source:null, capNode:null,
      rb:null, rbSize:0, rbWrite:0, rbFilled:0,
      meter:null,
      asr:null, modelLoaded:false,
      timer:null, busy:false, lastAsrMs:0,
      cueTimer:null, cueStartsAt:0, cueEndsAt:0
    };

    function rbInit(sr) {
      state.rbSize = Math.max(1, Math.floor(sr*12));
      state.rb = new Float32Array(state.rbSize);
      state.rbWrite = 0; state.rbFilled = 0;
    }
    function rbPush(block) {
      const n = block.length;
      for (let i=0;i<n;i++) {
        state.rb[state.rbWrite] = block[i];
        state.rbWrite = (state.rbWrite + 1) % state.rbSize;
      }
      state.rbFilled = Math.min(state.rbSize, state.rbFilled + n);
    }
    function rbGetLast(seconds) {
      const sr = state.audioCtx.sampleRate;
      const need = Math.min(state.rbFilled, Math.floor(seconds*sr));
      const outArr = new Float32Array(need);
      const start = (state.rbWrite - need + state.rbSize) % state.rbSize;
      if (start + need <= state.rbSize) outArr.set(state.rb.subarray(start, start+need));
      else {
        const first = state.rbSize - start;
        outArr.set(state.rb.subarray(start), 0);
        outArr.set(state.rb.subarray(0, need-first), first);
      }
      return outArr;
    }
    function maxAbs(pcm) {
      let m=0;
      for (let i=0;i<pcm.length;i++) {
        const a = Math.abs(pcm[i]);
        if (a>m) m=a;
      }
      return m;
    }
    function resampleLinear(input, inRate, outRate=16000) {
      if (inRate === outRate) return input;
      const outLen = Math.max(1, Math.floor(input.length * (outRate/inRate)));
      const out = new Float32Array(outLen);
      const inv = inRate / outRate;
      for (let i=0;i<outLen;i++) {
        const x = i * inv;
        const x0 = Math.floor(x);
        const x1 = Math.min(input.length-1, x0+1);
        const t = x - x0;
        out[i] = (1-t)*input[x0] + t*input[x1];
      }
      return out;
    }
    function highpass(input, sr, cutoff=120) {
      const out = new Float32Array(input.length);
      const rc = 1.0 / (2*Math.PI*cutoff);
      const dt = 1.0 / sr;
      const alpha = rc / (rc + dt);
      let y=0;
      let prevX = input[0] || 0;
      for (let i=0;i<input.length;i++) {
        const x = input[i];
        y = alpha * (y + x - prevX);
        out[i] = y;
        prevX = x;
      }
      return out;
    }
    function rmsNormalize(input, targetRms=0.08) {
      let sum=0;
      for (let i=0;i<input.length;i++) sum += input[i]*input[i];
      const rms = Math.sqrt(sum/Math.max(1,input.length));
      if (rms < 1e-6) return input;
      const gain = Math.min(6.0, targetRms/rms);
      const out = new Float32Array(input.length);
      for (let i=0;i<input.length;i++) out[i] = input[i]*gain;
      return out;
    }

    async function ensureWorklet() {
      const code = `
        class Cap extends AudioWorkletProcessor {
          process(inputs){
            const input = inputs[0];
            if (input && input[0]) this.port.postMessage(input[0].slice(0));
            return true;
          }
        }
        registerProcessor('cap', Cap);
      `;
      const url = URL.createObjectURL(new Blob([code], { type:"application/javascript" }));
      try{ await state.audioCtx.audioWorklet.addModule(url); } finally{ URL.revokeObjectURL(url); }
    }

    function updateLabels() {
      el("cdLbl").textContent = el("cd").value;
      el("capLbl").textContent = el("cap").value;
      el("winLbl").textContent = Number(el("win").value).toFixed(1);
      el("updLbl").textContent = Number(el("upd").value).toFixed(1);
      el("sensLbl").textContent = Number(el("sens").value).toFixed(4);
    }
    ["cd","cap","win","upd","sens"].forEach(id => el(id).addEventListener("input", updateLabels));
    updateLabels();

    function startMeter() {
      stopMeter();
      state.meter = setInterval(()=>{
        if (!state.audioCtx || !state.rb || state.rbFilled < Math.floor(state.audioCtx.sampleRate*0.2)) return;
        const pcm = rbGetLast(0.2);
        const m = maxAbs(pcm);
        const db = (m<=1e-9) ? "-inf" : (20*Math.log10(m)).toFixed(1);
        el("level").textContent = db + " dBFS";
      }, 250);
    }
    function stopMeter() {
      if (state.meter){ clearInterval(state.meter); state.meter=null; }
    }

    function stopCountdown() {
      if (state.cueTimer){ clearInterval(state.cueTimer); state.cueTimer=null; }
      state.cueStartsAt = 0; state.cueEndsAt = 0;
      el("cuestate").textContent = "OFF";
      el("cuein").textContent = "—";
      el("cueleft").textContent = "—";
      el("btnStopCd").disabled = true;
    }
    async function runCueTranscription() {
      if (!state.asr || !state.modelLoaded || !state.audioCtx) { log("[cue] not ready"); return; }
      const cap = Number(el("cap").value);
      await transcribeOnce(cap, true);
      log("[cue] done");
    }
    function startCountdown() {
      stopCountdown();
      el("btnStopCd").disabled = false;
      const delay = Number(el("cd").value);
      const cap = Number(el("cap").value);
      const now = Date.now();
      state.cueStartsAt = now + delay*1000;
      state.cueEndsAt = state.cueStartsAt + cap*1000;

      state.cueTimer = setInterval(async ()=>{
        const t = Date.now();
        if (t < state.cueStartsAt) {
          el("cuestate").textContent = "OFF";
          el("cuein").textContent = ((state.cueStartsAt - t)/1000).toFixed(1)+"s";
          el("cueleft").textContent = cap.toFixed(1)+"s";
        } else if (t < state.cueEndsAt) {
          el("cuestate").textContent = "ON";
          el("cuein").textContent = "0.0s";
          el("cueleft").textContent = ((state.cueEndsAt - t)/1000).toFixed(1)+"s";
        } else {
          el("cuestate").textContent = "PROCESS";
          clearInterval(state.cueTimer);
          state.cueTimer = null;
          await runCueTranscription();
          stopCountdown();
          if (el("loopOn").checked) {
            setTimeout(()=>startCountdown(), 250);
          }
        }
      }, 100);
    }

    function cleanText(raw) {
      if (!raw) return "";
      let t = String(raw);
      t = t.replace(/\[([^\]]+)\]/g," ");
      t = t.replace(/\(([^\)]+)\)/g," ");
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi," ");
      t = t.replace(/\s+/g," ").trim();
      if (!/\p{L}/u.test(t)) return "";
      const toks = t.split(" ").filter(Boolean);
      if (toks.length > 25) {
        const short = toks.filter(w=>w.length<=2).length;
        if (short/toks.length > 0.85) return "";
      }
      return t;
    }

    async function transcribeOnce(windowSec, tagCue) {
      const pcm0 = rbGetLast(windowSec);
      const m = maxAbs(pcm0);
      const thr = Number(el("sens").value);
      if (m < thr) return;

      const pcm = rmsNormalize(highpass(pcm0, state.audioCtx.sampleRate, 120), 0.08);
      const pcm16 = resampleLinear(pcm, state.audioCtx.sampleRate, 16000);

      const t0 = performance.now();
      const r1 = await state.asr(pcm16, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false });
      const dt = performance.now()-t0;
      state.lastAsrMs = dt;
      el("asrms").textContent = dt.toFixed(0)+"ms";
      const text = cleanText((r1?.text||"").trim());
      if (text) {
        log((tagCue?"[CUE] ":"") + text);
      }
    }

    function stopLoop() {
      if (state.timer){ clearTimeout(state.timer); state.timer=null; }
      state.busy=false;
    }
    function startLoop() {
      stopLoop();
      const tick = async ()=>{
        if (!state.audioCtx || !state.rb || !state.modelLoaded || !state.asr) { state.timer=setTimeout(tick, 800); return; }
        if (state.busy) { state.timer=setTimeout(tick, 250); return; }
        const pcm = rbGetLast(0.4);
        if (pcm.length < 1000) { state.timer=setTimeout(tick, 400); return; }
        if (maxAbs(pcm) < Number(el("sens").value)) { state.timer=setTimeout(tick, 500); return; }

        state.busy=true;
        try {
          const windowSec = Number(el("win").value);
          await transcribeOnce(windowSec, false);
        } catch(e) {
          log("[asr] ERROR: " + (e?.message||e));
        } finally {
          state.busy=false;
          const base = Number(el("upd").value)*1000;
          const next = Math.max(base, state.lastAsrMs + 800);
          state.timer=setTimeout(tick, next);
        }
      };
      state.timer=setTimeout(tick, 1200);
    }

    async function loadModel() {
      if (state.modelLoaded) return;
      el("mstate").textContent = "LOADING…";
      log("[load] clicked");
      try {
        const mod = await import("https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2");
        const pipeline = mod.pipeline;
        const env = mod.env;
        env.allowLocalModels = false;
        env.useBrowserCache = true;
        const t0 = performance.now();
        state.asr = await pipeline("automatic-speech-recognition", el("modelSel").value, { device:"wasm" });
        const dt = performance.now()-t0;
        state.modelLoaded = true;
        el("mstate").textContent = "READY";
        el("asrms").textContent = dt.toFixed(0)+"ms(load)";
        log("[load] READY ("+dt.toFixed(0)+"ms)");
      } catch(e) {
        el("mstate").textContent = "ERROR";
        log("[load] ERROR: " + (e?.message||e));
        showErr(e?.message||e);
      }
    }

    async function startMic() {
      log("[mic] clicked");
      if (!navigator.mediaDevices?.getUserMedia){ showErr("getUserMedia not supported"); return; }
      if (!window.isSecureContext && location.hostname !== "localhost"){ showErr("Mic requires HTTPS (GitHub Pages) or localhost"); return; }
      if (state.audioCtx) return;
      try {
        state.stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
        state.audioCtx = new (window.AudioContext||window.webkitAudioContext)();
        rbInit(state.audioCtx.sampleRate);
        state.source = state.audioCtx.createMediaStreamSource(state.stream);

        if (state.audioCtx.audioWorklet) {
          await ensureWorklet();
          state.capNode = new AudioWorkletNode(state.audioCtx, "cap", { numberOfInputs:1, numberOfOutputs:0, channelCount:1 });
          state.capNode.port.onmessage = (ev)=>{ const b=ev.data; if (b && b.length) rbPush(b); };
          state.source.connect(state.capNode);
        } else {
          const sp = state.audioCtx.createScriptProcessor(2048,1,1);
          sp.onaudioprocess = (e)=>rbPush(e.inputBuffer.getChannelData(0));
          state.source.connect(sp);
          const zero = state.audioCtx.createGain(); zero.gain.value=0;
          sp.connect(zero); zero.connect(state.audioCtx.destination);
          state.capNode = sp;
        }

        el("micstate").textContent = "LIVE";
        el("btnStop").disabled = false;
        log("[mic] LIVE");
        startMeter();
        startLoop();
      } catch(e) {
        log("[mic] ERROR: " + (e?.message||e));
        showErr(e?.message||e);
      }
    }

    function stop() {
      stopLoop();
      stopMeter();
      stopCountdown();
      try{ state.capNode?.disconnect(); }catch(e){}
      try{ state.source?.disconnect(); }catch(e){}
      if (state.stream){ state.stream.getTracks().forEach(t=>t.stop()); }
      if (state.audioCtx){ state.audioCtx.close(); }
      state.audioCtx=null; state.stream=null; state.source=null; state.capNode=null;
      state.rb=null; state.rbSize=state.rbWrite=state.rbFilled=0;
      el("micstate").textContent = "OFF";
      el("btnStop").disabled = true;
      log("[stop] done");
    }

    function test(){ log("[TEST] output append works"); }
    async function copy(){ try{ await navigator.clipboard.writeText(out.value||""); }catch(e){ showErr(e); } }
    function clear(){ out.value=""; }
    function help(){ log("[HELP] Increase Window/Update for better accuracy. Use Countdown to capture a controlled phrase."); }

    async function reset() {
      try{ if ("serviceWorker" in navigator){ const regs=await navigator.serviceWorker.getRegistrations(); for (const r of regs) await r.unregister(); } }catch(e){}
      try{ if (window.caches){ const keys=await caches.keys(); for (const k of keys) await caches.delete(k); } }catch(e){}
      try{ localStorage.clear(); sessionStorage.clear(); }catch(e){}
      showErr("Reset complete. Close this tab and reopen the page.");
    }

    window.app = {
      loadModel, startMic, stop, test, copy, clear, help, reset,
      startCountdown, stopCountdown
    };
  </script>
</body>
</html>
