<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta http-equiv="Cache-Control" content="no-store" />
  <title>Ultra Listener — Minimal Fix (minfix-1767927367-d5bsdx)</title>
  <style>
    :root{color-scheme:dark;--bg:#000;--panel:#050505;--border:#0f3a18;--green:#35ff6a;--green-dim:rgba(53,255,106,.78);--red:#ff4d4d;--font:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;}
    body{margin:0;padding:14px;background:var(--bg);color:var(--green);font-family:var(--font);letter-spacing:.2px}
    h1{margin:0 0 10px;font-size:16px}
    .card{background:var(--panel);border:1px solid var(--border);border-radius:12px;padding:12px}
    .row{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
    button{background:transparent;color:var(--green);border:1px solid var(--border);padding:10px 12px;border-radius:10px;font-weight:800;cursor:pointer}
    button:disabled{opacity:.55;cursor:not-allowed}
    .pill{display:inline-flex;align-items:center;gap:8px;padding:4px 8px;border-radius:999px;border:1px solid var(--border);background:rgba(53,255,106,.04);color:var(--green-dim);font-size:12px;white-space:nowrap}
    textarea{width:100%;min-height:260px;resize:vertical;border-radius:10px;border:1px solid var(--border);background:#000;color:var(--green);padding:12px;font-family:var(--font);font-size:13px;line-height:1.4}
    .err{border:1px solid rgba(255,77,77,.55);background:rgba(255,77,77,.08);border-radius:10px;padding:10px;color:rgba(255,150,150,.95);white-space:pre-wrap;display:none}
  </style>
</head>
<body>
  <h1>ULTRA LISTENER // MINIMAL FIX</h1>
  <div class="card">
    <div class="row">
      <button id="btnLoad" onclick="app.loadModel()">Load AI Model</button>
      <button id="btnMic" onclick="app.startMic()">Start Mic</button>
      <button id="btnStop" onclick="app.stop()" disabled>Stop</button>
      <button id="btnTest" onclick="app.test()">Test Output</button>
      <button id="btnHelp" onclick="app.help()">Help</button>
      <span class="pill">Build: <b id="build">minfix-1767927367-d5bsdx</b></span>
      <span class="pill">JS: <b id="js">YES</b></span>
      <span class="pill">Model: <b id="mstate">NOT LOADED</b></span>
      <span class="pill">Mic: <b id="micstate">OFF</b></span>
    </div>
    <div id="err" class="err"></div>
    <div style="margin-top:10px">
      <textarea id="log" placeholder="(log output)"></textarea>
    </div>
  </div>

  <script>
    const logEl = document.getElementById("log");
    const errEl = document.getElementById("err");
    const mstate = document.getElementById("mstate");
    const micstate = document.getElementById("micstate");
    const btnStop = document.getElementById("btnStop");
    const btnLoad = document.getElementById("btnLoad");
    const btnMic = document.getElementById("btnMic");

    function log(line){
      logEl.value += (logEl.value && !logEl.value.endsWith("\n") ? "\n" : "") + line;
      logEl.scrollTop = logEl.scrollHeight;
    }
    function showErr(e){
      errEl.style.display = "block";
      errEl.textContent = String(e);
    }

    window.addEventListener("error", (e)=>showErr((e?.message||"") + "\n" + (e?.filename||"") + ":" + (e?.lineno||"")));
    window.addEventListener("unhandledrejection", (e)=>showErr(e?.reason?.message || e?.reason || "unhandled rejection"));

    const app = {
      // audio
      audioCtx: null,
      stream: null,
      source: null,
      rb: null,
      rbSize: 0,
      rbWrite: 0,
      rbFilled: 0,
      captureNode: null,

      // model
      asr: null,
      pipeline: null,
      env: null,
      modelLoaded: false,
      busy: false,
      timer: null,

      test(){
        log("[TEST] button works and log appends");
      },

      help(){
        log("[HELP] If Test Output doesn't append, JS isn't running or you're not on GitHub Pages.");
        log("[HELP] If Load AI Model hangs, your network/VPN/Private DNS may be blocking cdn.jsdelivr.net or huggingface.");
      },

      async loadModel(){
        try{
          log("[load] clicked");
          mstate.textContent = "LOADING…";
          btnLoad.disabled = true;

          // Dynamic import (main thread, most compatible)
          const mod = await import("https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2");
          this.pipeline = mod.pipeline;
          this.env = mod.env;
          this.env.allowLocalModels = false;
          this.env.useBrowserCache = true;

          const t0 = performance.now();
          this.asr = await this.pipeline("automatic-speech-recognition", "Xenova/whisper-tiny", { device: "wasm" });
          const dt = performance.now() - t0;

          this.modelLoaded = true;
          mstate.textContent = "READY";
          log("[load] model READY (" + dt.toFixed(0) + "ms)");
        } catch(e){
          btnLoad.disabled = false;
          mstate.textContent = "ERROR";
          log("[load] ERROR: " + (e?.message || e));
          showErr(e?.message || e);
        }
      },

      rbInit(sr){
        this.rbSize = Math.max(1, Math.floor(sr * 10));
        this.rb = new Float32Array(this.rbSize);
        this.rbWrite = 0;
        this.rbFilled = 0;
      },

      rbPush(block){
        const n = block.length;
        for (let i=0;i<n;i++) {
          this.rb[this.rbWrite] = block[i];
          this.rbWrite = (this.rbWrite + 1) % this.rbSize;
        }
        this.rbFilled = Math.min(this.rbSize, this.rbFilled + n);
      },

      rbGetLast(seconds){
        const sr = this.audioCtx.sampleRate;
        const need = Math.min(this.rbFilled, Math.floor(seconds * sr));
        const out = new Float32Array(need);
        const start = (this.rbWrite - need + this.rbSize) % this.rbSize;
        if (start + need <= this.rbSize) out.set(this.rb.subarray(start, start+need));
        else {
          const first = this.rbSize - start;
          out.set(this.rb.subarray(start), 0);
          out.set(this.rb.subarray(0, need-first), first);
        }
        return out;
      },

      maxAbs(pcm){
        let m=0;
        for (let i=0;i<pcm.length;i++) {
          const a = Math.abs(pcm[i]);
          if (a > m) m = a;
        }
        return m;
      },

      async ensureWorklet(){
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
        try { await this.audioCtx.audioWorklet.addModule(url); } finally { URL.revokeObjectURL(url); }
      },

      async startMic(){
        try{
          log("[mic] clicked");
          if (!navigator.mediaDevices?.getUserMedia) {
            throw new Error("getUserMedia not supported");
          }
          if (!window.isSecureContext && location.hostname !== "localhost") {
            throw new Error("Mic requires HTTPS (GitHub Pages) or localhost");
          }
          if (this.audioCtx) return;

          this.stream = await navigator.mediaDevices.getUserMedia({ audio: true });
          this.audioCtx = new (window.AudioContext || window.webkitAudioContext)();
          this.rbInit(this.audioCtx.sampleRate);

          this.source = this.audioCtx.createMediaStreamSource(this.stream);

          if (this.audioCtx.audioWorklet) {
            await this.ensureWorklet();
            this.captureNode = new AudioWorkletNode(this.audioCtx, "cap", { numberOfInputs:1, numberOfOutputs:0, channelCount:1 });
            this.captureNode.port.onmessage = (ev) => {
              const b = ev.data;
              if (b && b.length) this.rbPush(b);
            };
            this.source.connect(this.captureNode);
          } else {
            const sp = this.audioCtx.createScriptProcessor(2048,1,1);
            sp.onaudioprocess = (e) => this.rbPush(e.inputBuffer.getChannelData(0));
            this.source.connect(sp);
            const zero = this.audioCtx.createGain(); zero.gain.value = 0;
            sp.connect(zero); zero.connect(this.audioCtx.destination);
            this.captureNode = sp;
          }

          micstate.textContent = "LIVE";
          btnStop.disabled = false;
          log("[mic] LIVE");

          this.startLoop();
        } catch(e){
          log("[mic] ERROR: " + (e?.message || e));
          showErr(e?.message || e);
        }
      },

      startLoop(){
        if (this.timer) clearTimeout(this.timer);
        const tick = async () => {
          try {
            if (!this.modelLoaded || !this.asr) {
              this.timer = setTimeout(tick, 800);
              return;
            }
            if (!this.audioCtx || !this.rb) {
              this.timer = setTimeout(tick, 800);
              return;
            }
            if (this.busy) {
              this.timer = setTimeout(tick, 300);
              return;
            }
            const pcm = this.rbGetLast(3.0);
            if (pcm.length < 16000) {
              this.timer = setTimeout(tick, 500);
              return;
            }
            if (this.maxAbs(pcm) < 0.0002) {
              this.timer = setTimeout(tick, 500);
              return;
            }
            this.busy = true;
            const t0 = performance.now();
            const res = await this.asr(pcm, { chunk_length_s: 3.0, stride_length_s: 0.2, return_timestamps:false, task:"translate" });
            const dt = performance.now()-t0;
            const text = (res?.text || "").trim();
            log("[asr] " + dt.toFixed(0) + "ms -> " + (text ? text : "(empty)"));
          } catch(e) {
            log("[asr] ERROR: " + (e?.message || e));
          } finally {
            this.busy = false;
            this.timer = setTimeout(tick, 2500);
          }
        };
        this.timer = setTimeout(tick, 1200);
      },

      stop(){
        try{
          if (this.timer) clearTimeout(this.timer);
          this.timer = null;
          this.busy = false;
          if (this.captureNode) try{ this.captureNode.disconnect(); }catch(e){}
          this.captureNode = null;
          if (this.source) try{ this.source.disconnect(); }catch(e){}
          this.source = null;
          if (this.stream) {
            for (const t of this.stream.getTracks()) t.stop();
            this.stream = null;
          }
          if (this.audioCtx) {
            this.audioCtx.close();
            this.audioCtx = null;
          }
          micstate.textContent = "OFF";
          btnStop.disabled = true;
          btnMic.disabled = false;
          log("[stop] done");
        } catch(e){
          showErr(e?.message||e);
        }
      }
    };

    window.app = app;
  </script>
</body>
</html>
