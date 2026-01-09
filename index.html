<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta http-equiv="Cache-Control" content="no-store" />
  <title>Ultra Listener — Prod Option1 16k (prod-opt1-16k-1767929561)</title>
  <style>
    :root{color-scheme:dark;--bg:#000;--panel:#050505;--border:#0f3a18;--green:#35ff6a;--green-dim:rgba(53,255,106,.78);--red:#ff4d4d;--font:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;}
    body{margin:0;padding:14px;background:var(--bg);color:var(--green);font-family:var(--font);letter-spacing:.2px}
    h1{margin:0 0 10px;font-size:16px;text-shadow:0 0 8px rgba(53,255,106,.25)}
    .grid{display:grid;gap:12px;grid-template-columns:1fr}
    @media (min-width:980px){.grid{grid-template-columns:1.2fr .8fr}}
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
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // PROD OPTION 1+ (16k + BOOST) (prod-opt1-16k-1767929561)</h1>

  <div class="grid">
    <div class="card">
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b></div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny" selected>whisper-tiny (multilingual, fastest)</option>
            <option value="Xenova/whisper-base">whisper-base (multilingual, better)</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (English-only, fastest)</option>
            <option value="Xenova/whisper-base.en">whisper-base.en (English-only, better)</option>
          </select>
          <div class="small">Fixes your “(empty)” loop by: (1) transcribing first (no translate task) (2) resampling to 16k before ASR.</div>
        </div>

        <div class="col" style="flex: 1 1 360px">
          <div class="small"><b>A/B</b></div>
          <div class="seg">
            <input type="radio" name="ab" id="modeA" checked><label for="modeA">A Fast</label>
            <input type="radio" name="ab" id="modeB"><label for="modeB">B EVP</label>
          </div>
          <div class="small">B = longer window + more spacing.</div>
        </div>

        <div class="col" style="flex: 1 1 360px">
          <div class="small"><b>Optional translation pass</b></div>
          <label class="toggle" title="Runs a second pass translate after transcript (does not block transcript output).">
            <input id="translatePass" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Also attempt [EN] translation</span>
          </label>
        </div>
      </div>

      <div class="row">
        <button id="btnLoad">Load AI Model</button>
        <button id="btnMic">Start Mic</button>
        <button id="btnStop" class="danger" disabled>Stop</button>
        <button id="btnTest">Test Output</button>
        <span class="pill">Model: <b id="mstate">NOT LOADED</b></span>
        <span class="pill">Mic: <b id="micstate">OFF</b></span>
        <span class="pill">Level: <b id="level">-inf</b></span>
        <span class="pill">ASR: <b id="asrms">—</b></span>
        <span class="pill">Next: <b id="next">—</b></span>
      </div>
      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>TIMED CAPTURE</b></div>
          <div class="row">
            <button id="btnCue" title="Starts a timed capture window">Start Countdown</button>
            <button id="btnCueStop" class="danger" disabled>Stop Countdown</button>
            <label class="toggle" title="Automatically repeat countdown/capture windows">
              <input id="cueLoop" type="checkbox" checked />
              <span class="track"><span class="thumb"></span></span>
              <span class="label">Loop</span>
            </label>
            <span class="pill">Speak in: <b id="cueIn">—</b></span>
            <span class="pill">Time left: <b id="cueLeft">—</b></span>
            <span class="pill">Mic cue: <b id="cueState">OFF</b></span>
          </div>
          <div class="small">Use this to capture exactly what you want. When Mic cue = ON, speak clearly into the mic.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Countdown</b> (seconds): <span id="countdownLabel">3</span></div>
          <input id="countdownSec" type="range" min="0" max="10" step="1" value="3" />
          <div class="small">Delay before the capture window opens.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Capture window</b> (seconds): <span id="captureLabel">6</span></div>
          <input id="captureSec" type="range" min="2" max="15" step="1" value="6" />
          <div class="small">How long you have to speak during the cue.</div>
        </div>
      </div>


      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Window</b> sec: <span id="winLabel">3.0</span></div>
          <input id="win" type="range" min="2" max="10" step="0.5" value="4.0" />
        </div>
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Base update</b> sec: <span id="updLabel">2.5</span></div>
          <input id="upd" type="range" min="1" max="10" step="0.5" value="3.0" />
        </div>
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Sensitivity</b>: <span id="sensLabel">0.0002</span></div>
          <input id="sens" type="range" min="0.00005" max="0.01" step="0.00005" value="0.0002" />
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 320px">
          <div class="small"><b>Monitoring</b> (headphones)</div>
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

        <div class="col" style="flex:1 1 320px">
          <div class="small"><b>Listening filter</b></div>
          <div class="seg">
            <input type="radio" name="listen" id="listenVoice" checked><label for="listenVoice">Voice-isolated</label>
            <input type="radio" name="listen" id="listenAll"><label for="listenAll">All sounds</label>
          </div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>Monitor volume</b>: <span id="monVolLabel">0.00</span></div>
          <input id="monVol" type="range" min="0" max="0.6" step="0.01" value="0" disabled />
        </div>
      </div>

      <div class="small" style="margin-top:10px">
        Your log showed translate returning empty. This build always runs transcription first, then optional translate. Expect output every ~ASR_time seconds.
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT</b></div>
          <div class="small">Always prints transcript. If translation pass is enabled, prints [EN] line after.</div>
        </div>
        <div class="row">
          <button id="btnCopy">Copy</button>
          <button id="btnClear">Clear</button>
        </div>
      </div>
      <textarea id="out" placeholder="(output appears here)"></textarea>
    </div>
  </div>

  <script type="module">
    import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";
    const el = (id) => document.getElementById(id);

    const out = el("out");
    const btnLoad = el("btnLoad");
    const btnMic = el("btnMic");
    const btnStop = el("btnStop");
    const btnTest = el("btnTest");
    const btnCopy = el("btnCopy");
    const btnClear = el("btnClear");

    const modelSel = el("modelSel");
    const translatePass = el("translatePass");
    const qualityBoost = el("qualityBoost");
    const modeA = el("modeA");
    const modeB = el("modeB");

    const mstate = el("mstate");
    const micstate = el("micstate");
    const levelEl = el("level");
    const asrmsEl = el("asrms");
    const nextEl = el("next");

    const monitorOn = el("monitorOn");
    const hpConfirm = el("hpConfirm");
    const listenVoice = el("listenVoice");
    const listenAll = el("listenAll");
    const monVol = el("monVol");
    const monVolLabel = el("monVolLabel");

    const win = el("win"); const winLabel = el("winLabel");
    const upd = el("upd"); const updLabel = el("updLabel");
    const sens = el("sens"); const sensLabel = el("sensLabel");
    const btnCue = el("btnCue");
    const btnCueStop = el("btnCueStop");
    const cueIn = el("cueIn");
    const cueLeft = el("cueLeft");
    const cueState = el("cueState");
    const countdownSec = el("countdownSec");
    const countdownLabel = el("countdownLabel");
    const captureSec = el("captureSec");
    const captureLabel = el("captureLabel");
    const cueLoop = el("cueLoop");


    function appendLine(s) {
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }

    // ===== 16k resampler (linear) =====
    function resampleLinear(input, inRate, outRate=16000) {
      if (inRate === outRate) return input;
      const ratio = outRate / inRate;
      const outLen = Math.max(1, Math.floor(input.length * ratio));
      const out = new Float32Array(outLen);
      const inv = inRate / outRate;
      for (let i=0; i<outLen; i++) {
        const x = i * inv;
        const x0 = Math.floor(x);
        const x1 = Math.min(input.length - 1, x0 + 1);
        const t = x - x0;
        out[i] = (1 - t) * input[x0] + t * input[x1];
      }
      return out;
    }

    // ===== Model =====
    let asr = null;
    let modelLoaded = false;

    async function loadModel() {
      if (modelLoaded) return;
      btnLoad.disabled = true;
      mstate.textContent = "LOADING…";
      env.allowLocalModels = false;
      env.useBrowserCache = true;
      const t0 = performance.now();
      try {
        asr = await pipeline("automatic-speech-recognition", modelSel.value, { device: "wasm" });
        modelLoaded = true;
        const dt = performance.now()-t0;
        asrmsEl.textContent = dt.toFixed(0) + "ms(load)";
        mstate.textContent = "READY";
        appendLine("[model] ready");
      } catch (e) {
        btnLoad.disabled = false;
        mstate.textContent = "ERROR";
        appendLine("[model] error: " + (e?.message || e));
      }
    }

    // ===== Audio + ring buffer =====
    let audioCtx=null, stream=null, source=null, captureNode=null;
    let monitorGain=null, speechBand=null;

    let rb=null, rbSize=0, rbWrite=0, rbFilled=0;
    function rbInit(sr) {
      rbSize = Math.max(1, Math.floor(sr * 12));
      rb = new Float32Array(rbSize);
      rbWrite=0; rbFilled=0;
    }
    function rbPush(block) {
      const n=block.length;
      for (let i=0;i<n;i++) {
        rb[rbWrite]=block[i];
        rbWrite=(rbWrite+1)%rbSize;
      }
      rbFilled=Math.min(rbSize, rbFilled+n);
    }
    function rbGetLast(seconds) {
      const sr = audioCtx.sampleRate;
      const need = Math.min(rbFilled, Math.floor(seconds*sr));
      const outArr = new Float32Array(need);
      const start = (rbWrite-need+rbSize)%rbSize;
      if (start+need <= rbSize) outArr.set(rb.subarray(start,start+need));
      else {
        const first = rbSize-start;
        outArr.set(rb.subarray(start),0);
        outArr.set(rb.subarray(0,need-first),first);
      }
      return outArr;
    }
    function maxAbs(pcm) {
      let m=0;
      for (let i=0;i<pcm.length;i++) {
        const a=Math.abs(pcm[i]); if (a>m) m=a;
      }
      return m;
    }

    async function ensureWorklet() {
      const code = `
        class Cap extends AudioWorkletProcessor {
          process(inputs) {
            const input = inputs[0];
            if (input && input[0]) this.port.postMessage(input[0].slice(0));
            return true;
          }
        }
        registerProcessor('cap', Cap);
      `;
      const url = URL.createObjectURL(new Blob([code], { type: "application/javascript" }));
      try { await audioCtx.audioWorklet.addModule(url); } finally { URL.revokeObjectURL(url); }
    }

    function updateMonitorLock() {
      const unlocked = monitorOn.checked && hpConfirm.checked;
      monVol.disabled = !unlocked;
      if (!unlocked) {
        monVol.value = "0";
        monVolLabel.textContent = "0.00";
        if (monitorGain) monitorGain.gain.value = 0;
      } else {
        monVolLabel.textContent = Number(monVol.value).toFixed(2);
        if (monitorGain) monitorGain.gain.value = Number(monVol.value);
      }
    }

    function buildMonitor() {
      if (!audioCtx || !source) return;
      try { monitorGain?.disconnect(); } catch {}
      try { speechBand?.disconnect(); } catch {}
      monitorGain = audioCtx.createGain();
      monitorGain.gain.value = 0;

      speechBand = audioCtx.createBiquadFilter();
      speechBand.type = "bandpass";
      speechBand.frequency.value = 1200;
      speechBand.Q.value = 0.6;

      if (listenVoice.checked) {
        source.connect(speechBand);
        speechBand.connect(monitorGain);
      } else {
        source.connect(monitorGain);
      }
      monitorGain.connect(audioCtx.destination);
      updateMonitorLock();
    }

    function rebuildMonitor() {
      if (!audioCtx || !source) return;
      try { source.disconnect(); } catch {}
      if (captureNode) source.connect(captureNode);
      buildMonitor();
    }

    async function startMic() {
      if (!navigator.mediaDevices?.getUserMedia) {
        appendLine("[mic] getUserMedia not supported");
        return;
      }
      if (!window.isSecureContext && location.hostname !== "localhost") {
        appendLine("[mic] requires https/github pages");
        return;
      }
      if (audioCtx) return;

      stream = await navigator.mediaDevices.getUserMedia({ audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false } });
      audioCtx = new (window.AudioContext||window.webkitAudioContext)();
      rbInit(audioCtx.sampleRate);
      source = audioCtx.createMediaStreamSource(stream);

      if (audioCtx.audioWorklet) {
        await ensureWorklet();
        captureNode = new AudioWorkletNode(audioCtx, "cap", { numberOfInputs:1, numberOfOutputs:0, channelCount:1 });
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

      buildMonitor();
      micstate.textContent = "LIVE";
      btnStop.disabled = false;
      appendLine("[mic] live");
      startMeter();
      startLoop();
    }

    function stopAll() {
      stopLoop();
      stopMeter();
      try { captureNode?.disconnect(); } catch {}
      try { source?.disconnect(); } catch {}
      if (stream) {
        for (const t of stream.getTracks()) t.stop();
      }
      if (audioCtx) audioCtx.close();
      audioCtx=null; stream=null; source=null; captureNode=null;
      rb=null; rbSize=rbWrite=rbFilled=0;
      micstate.textContent = "OFF";
      btnStop.disabled = true;
      appendLine("[stop] done");
    }

    // ===== Meter =====
    let meterTimer=null;
    function startMeter() {
      stopMeter();
      meterTimer = setInterval(() => {
        if (!audioCtx || !rb || rbFilled < Math.floor(audioCtx.sampleRate*0.2)) return;
        const pcm = rbGetLast(0.2);
        const m = maxAbs(pcm);
        const db = (m<=1e-9) ? "-inf" : (20*Math.log10(m)).toFixed(1);
        levelEl.textContent = db + " dBFS";
      }, 250);
    }
    function stopMeter() {
      if (meterTimer) { clearInterval(meterTimer); meterTimer=null; }
    }

    // ===== Loop (no overlap + adaptive) =====
    
    // Timed capture cue state
    let cueTimer = null;
    let cueActive = false;
    let cueEndsAt = 0;
    let cueStartsAt = 0;

let timer=null;
    let busy=false;
    let lastAsr=0;

    function stopLoop() {
      if (timer) { clearTimeout(timer); timer=null; }
      busy=false;
    }

    function cleanText(raw) {
      if (!raw) return "";
      let t = String(raw);

      // Remove common Whisper tags/captions
      t = t.replace(/\[([^\]]+)\]/g, " ");
      t = t.replace(/\(([^\)]+)\)/g, " ");
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");

      // Collapse whitespace
      t = t.replace(/\s+/g, " ").trim();

      // Must contain letters in any language
      if (!/\p{L}/u.test(t)) return "";

      const toks = t.split(" ").filter(Boolean);

      // Drop pathological repeated single-letter/short-token spam e.g. "r r r r r ..."
      // (This was your "train r r r ..." case)
      if (toks.length > 25) {
        const short = toks.filter(w => w.length <= 2).length;
        if (short / toks.length > 0.85) return "";
      }

      // Also drop if a single 1–2 char token dominates heavily (e.g., "r" repeated)
      if (toks.length > 40) {
        const counts = new Map();
        for (const w of toks) {
          const k = w.toLowerCase();
          counts.set(k, (counts.get(k) || 0) + 1);
        }
        let topK = null, topV = 0;
        for (const [k,v] of counts.entries()){
          if (v > topV){ topV=v; topK=k; }
        }
        if (topK && topK.length <= 2 && (topV / toks.length) > 0.7) return "";
      }

      // IMPORTANT: Do NOT drop repeated real words like "hello hello hello" — users may test like that.
      return t;
    }

      // Drop repeated-word spam like "hello hello hello" > 10 tokens
      if (toks.length > 12) {
        const uniq = new Set(toks.map(w => w.toLowerCase()));
        if (uniq.size <= 2) return "";
      }

      return t;
    }

    function mergeText(primary, secondary){
      const norm = (s) => String(s||"").toLowerCase().replace(/[^\p{L}0-9\s]/gu,"").replace(/\s+/g," ").trim();
      const A = norm(primary).split(" ").filter(Boolean);
      const B = norm(secondary).split(" ").filter(Boolean);
      const setA = new Set(A);
      const extras = [];
      for (const w of B){
        if (!setA.has(w)){
          setA.add(w);
          extras.push(w);
        }
      }
      if (!extras.length) return primary;
      return primary + " " + extras.join(" ");
    }



    async function transcribeOnce(windowSec) {
      
      const pcmRaw0 = rbGetLast(windowSec);

      function highpass(input, sr, cutoff=120){
        const out = new Float32Array(input.length);
        const rc = 1.0 / (2*Math.PI*cutoff);
        const dt = 1.0 / sr;
        const alpha = rc / (rc + dt);
        let y = 0;
        let prevX = input[0] || 0;
        for (let i=0;i<input.length;i++){
          const x = input[i];
          y = alpha * (y + x - prevX);
          out[i] = y;
          prevX = x;
        }
        return out;
      }

      function rmsNormalize(input, targetRms=0.08){
        let sum=0;
        for (let i=0;i<input.length;i++) sum += input[i]*input[i];
        const rms = Math.sqrt(sum / Math.max(1, input.length));
        if (rms < 1e-6) return input;
        const gain = Math.min(6.0, targetRms / rms);
        const out = new Float32Array(input.length);
        for (let i=0;i<input.length;i++) out[i] = input[i]*gain;
        return out;
      }

      const pcmHp = highpass(pcmRaw0, audioCtx.sampleRate, 120);
      const pcmRaw = rmsNormalize(pcmHp, 0.08);

      const m = maxAbs(pcmRaw);
      const thr = Number(sens.value);
      if (m < thr) return { kind:"silence" };

      // Resample to 16k
      const pcm16 = resampleLinear(pcmRaw, audioCtx.sampleRate, 16000);

      const t0 = performance.now();
      // ALWAYS transcribe first (no task)
      const r1 = await asr(pcm16, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false });
      const dt1 = performance.now() - t0;
      lastAsr = dt1;
      asrmsEl.textContent = dt1.toFixed(0) + "ms";
      let text1 = cleanText((r1?.text || "").trim());

      if (text1) {
        if (qualityBoost && qualityBoost.checked) {
          try {
            const extraWin = Math.min(10.0, windowSec + 1.5);
            const pcmRaw2 = rbGetLast(extraWin);
            const pcmHp2 = highpass(pcmRaw2, audioCtx.sampleRate, 120);
            const pcmNorm2 = rmsNormalize(pcmHp2, 0.08);
            const pcm16b = resampleLinear(pcmNorm2, audioCtx.sampleRate, 16000);
            const rExtra = await asr(pcm16b, { chunk_length_s: extraWin, stride_length_s: 0.2, return_timestamps:false });
            const tExtra = cleanText((rExtra?.text || "").trim());
            if (tExtra) { text1 = mergeText(text1, tExtra); }
          } catch (e) {}
        }
        appendLine(text1);
        if (translatePass.checked) {
          // translate pass on same 16k audio
          try {
            const t2 = performance.now();
            const r2 = await asr(pcm16, { chunk_length_s: windowSec, stride_length_s: 0.2, return_timestamps:false, task:"translate" });
            const text2 = cleanText((r2?.text || "").trim());
            if (text2) appendLine("[EN] " + text2);
          } catch(e) {}
        }
        return { kind:"ok" };
      } else {
        /* no output for empty */
        return { kind:"empty" };
      }
    }

    async function loop() {
      if (!audioCtx || !rb || !modelLoaded || !asr) return;
      if (busy) { timer = setTimeout(loop, 300); return; }
      busy=true;

      // A/B adjusts window and slack
      let windowSec = Number(win.value);
      if (modeB.checked) windowSec = Math.max(5.0, windowSec);
      else windowSec = Math.min(3.0, windowSec);
      winLabel.textContent = windowSec.toFixed(1);

      try {
        await transcribeOnce(windowSec);
      } catch(e) {
        appendLine("[asr] error: " + (e?.message || e));
      } finally {
        busy=false;
        const base = Number(upd.value) * 1000;
        const slack = modeB.checked ? 1600 : 800;
        const next = Math.max(base, lastAsr + slack);
        nextEl.textContent = (next/1000).toFixed(1) + "s";
        timer = setTimeout(loop, next);
      }
    }

    function startLoop() {
      stopLoop();
      timer = setTimeout(loop, 900);
    }

    
    async function runCueTranscription(){
      if (!audioCtx || !rb || !modelLoaded || !asr) { appendLine("[cue] not ready"); return; }
      // Use exact capture window length
      const windowSec = Number(captureSec.value);
      // Reuse the same pipeline as transcribeOnce, but label output
      try {
        await transcribeOnce(windowSec);
        appendLine("[cue] done");
      } catch(e) {
        appendLine("[cue] error: " + (e?.message || e));
      }
    }

    function stopCountdown(){
      if (cueTimer) { clearInterval(cueTimer); cueTimer = null; }
      cueActive = false;
      cueStartsAt = 0;
      cueEndsAt = 0;
      cueIn.textContent = "—";
      cueLeft.textContent = "—";
      cueState.textContent = "OFF";
      btnCueStop.disabled = true;
      btnCue.disabled = false;
    }

    function startCountdown(){
      stopCountdown();
      const delay = Number(countdownSec.value);
      const dur = Number(captureSec.value);
      const now = Date.now();
      cueStartsAt = now + delay*1000;
      cueEndsAt = cueStartsAt + dur*1000;
      btnCue.disabled = true;
      btnCueStop.disabled = false;

      cueTimer = setInterval(async () => {
        const t = Date.now();
        if (t < cueStartsAt){
          cueState.textContent = "OFF";
          cueIn.textContent = ((cueStartsAt - t)/1000).toFixed(1) + "s";
          cueLeft.textContent = (dur).toFixed(1) + "s";
        } else if (t >= cueStartsAt && t < cueEndsAt){
          cueState.textContent = "ON";
          cueIn.textContent = "0.0s";
          cueLeft.textContent = ((cueEndsAt - t)/1000).toFixed(1) + "s";
        } else {
          // cue finished
          cueState.textContent = "PROCESSING";
          cueIn.textContent = "—";
          cueLeft.textContent = "0.0s";
          clearInterval(cueTimer);
          cueTimer = null;
          // Force one transcription of exactly the cue window
          await runCueTranscription();
          // Loop immediately if enabled
          const doLoop = cueLoop && cueLoop.checked;
          stopCountdown();
          if (doLoop) {
            // slight pause to avoid back-to-back overlaps
            setTimeout(() => startCountdown(), 250);
          }
        }
      }, 100);
    }

// ===== Wiring =====
    btnLoad.addEventListener("click", loadModel);
    btnMic.addEventListener("click", startMic);
    btnStop.addEventListener("click", stopAll);
    btnTest.addEventListener("click", () => appendLine("[TEST] output append works"));

    btnCue.addEventListener("click", startCountdown);
    btnCueStop.addEventListener("click", stopCountdown);
    countdownSec.addEventListener("input", () => countdownLabel.textContent = String(countdownSec.value));
    captureSec.addEventListener("input", () => captureLabel.textContent = String(captureSec.value));

    btnClear.addEventListener("click", () => out.value="");
    btnCopy.addEventListener("click", async () => {
      try { await navigator.clipboard.writeText(out.value||""); } catch {}
    });

    monitorOn.addEventListener("change", updateMonitorLock);
    hpConfirm.addEventListener("change", updateMonitorLock);
    monVol.addEventListener("input", updateMonitorLock);
    listenVoice.addEventListener("change", rebuildMonitor);
    listenAll.addEventListener("change", rebuildMonitor);

    win.addEventListener("input", () => winLabel.textContent = Number(win.value).toFixed(1));
    upd.addEventListener("input", () => updLabel.textContent = Number(upd.value).toFixed(1));
    sens.addEventListener("input", () => sensLabel.textContent = Number(sens.value).toFixed(4));

    modeA.addEventListener("change", () => { win.value="4.0"; winLabel.textContent="4.0"; upd.value="3.0"; updLabel.textContent="3.0"; if (audioCtx) startLoop(); });
    modeB.addEventListener("change", () => { win.value="8.0"; winLabel.textContent="8.0"; upd.value="10.0"; updLabel.textContent="10.0"; if (audioCtx) startLoop(); });

    // Init labels
    winLabel.textContent = Number(win.value).toFixed(1);
    updLabel.textContent = Number(upd.value).toFixed(1);
    sensLabel.textContent = Number(sens.value).toFixed(4);
    countdownLabel.textContent = String(countdownSec.value);
    captureLabel.textContent = String(captureSec.value);

  </script>
</body>
</html>
