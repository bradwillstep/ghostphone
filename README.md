<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <title>Ultra Listener — Mic + Spectrum + Shift + AI + Speak</title>
  <style>
    :root { font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; color-scheme: dark; }
    body { margin: 0; padding: 14px; background: #0b0d10; color: #e8eef6; }
    h1 { font-size: 18px; margin: 0 0 10px; }
    .grid { display: grid; gap: 12px; grid-template-columns: 1fr; }
    @media (min-width: 980px) { .grid { grid-template-columns: 1.2fr 0.8fr; } }
    .card { background: #12161c; border: 1px solid #222a35; border-radius: 14px; padding: 12px; }
    .row { display: flex; gap: 10px; flex-wrap: wrap; align-items: center; }
    .col { display:flex; flex-direction: column; gap: 6px; }
    button {
      background: #1f6feb; border: 0; color: white; padding: 10px 12px; border-radius: 12px;
      font-weight: 700; cursor: pointer;
    }
    button.secondary { background: #2b3442; }
    button.danger { background: #b42318; }
    button:disabled { opacity: 0.55; cursor: not-allowed; }
    label { font-size: 12px; opacity: 0.92; }
    input[type="range"] { width: min(560px, 100%); }
    select {
      background: #0a0c0f; border: 1px solid #222a35; border-radius: 10px; color: #e8eef6;
      padding: 8px 10px;
    }
    .mono { font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; }
    .small { font-size: 12px; opacity: 0.86; line-height: 1.35; }
    .pill { padding: 4px 8px; border-radius: 999px; background: #0a0c0f; border: 1px solid #222a35; }
    canvas { width: 100%; height: 190px; background: #0a0c0f; border-radius: 12px; border: 1px solid #222a35; }
    textarea {
      width: 100%; min-height: 220px; resize: vertical; border-radius: 12px;
      border: 1px solid #222a35; background: #0a0c0f; color: #e8eef6; padding: 10px;
    }
    .warn { border: 1px solid #4a2b15; background: #16110c; border-radius: 12px; padding: 10px; }
    .ok { border: 1px solid #1f3a2a; background: #0e1612; border-radius: 12px; padding: 10px; }
    hr { border: 0; border-top: 1px solid #222a35; opacity: .7; margin: 10px 0; }

    /* Permission overlay */
    .overlay {
      position: fixed; inset: 0; display: none; align-items: center; justify-content: center;
      background: rgba(0,0,0,0.65); padding: 14px; z-index: 50;
    }
    .overlay.show { display: flex; }
    .modal {
      width: min(820px, 100%); border-radius: 16px; background: #10151c; border: 1px solid #2a3341;
      box-shadow: 0 10px 35px rgba(0,0,0,.55);
      padding: 14px;
    }
    .modal h2 { margin: 0 0 8px; font-size: 16px; }
    .modal .sub { margin: 0 0 12px; opacity: 0.9; font-size: 12px; line-height: 1.35; }
    .steps { display: grid; gap: 10px; grid-template-columns: 1fr; }
    @media (min-width: 760px) { .steps { grid-template-columns: 1fr 1fr; } }
    .step { background: #0a0c0f; border: 1px solid #222a35; border-radius: 12px; padding: 10px; }
    .step b { font-size: 12px; }
    .muted { opacity: 0.85; font-size: 12px; line-height: 1.35; }
    .codepill { display:inline-block; padding: 2px 6px; border-radius: 8px; border: 1px solid #222a35; background:#0a0c0f; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; font-size: 12px; }
    .modal .actions { display:flex; gap:10px; flex-wrap: wrap; align-items:center; justify-content: flex-end; margin-top: 10px; }
    .banner {
      display:none; border-radius: 12px; padding: 10px; border: 1px solid #2a3341; background: #0a0c0f;
    }
    .banner.show { display:block; }
    a { color: #7db1ff; }
  </style>
</head>
<body>
  <h1>Ultra Listener — Mic → (Shift/Scan) → AI Transcribe → Speak</h1>

  <!-- Top banner for environment warnings -->
  <div id="envBanner" class="banner small"></div>

  <div class="grid">
    <div class="card">
      <div class="row">
        <button id="btnStart">Start Mic</button>
        <button id="btnStop" class="danger" disabled>Stop</button>
        <button id="btnLoadModel" class="secondary">Load AI Model</button>
        <button id="btnHelp" class="secondary">Mic Help</button>
        <span class="pill mono" id="status">idle</span>
      </div>

      <div class="warn small" style="margin-top:10px">
        <b>Safety:</b> Monitoring audio to speakers can cause feedback. Use headphones.
        Monitoring volume is locked to <span class="mono">0.00</span> unless you enable <b>Headphone Safe</b>.
      </div>

      <div style="margin-top:10px">
        <canvas id="spec" width="1200" height="360"></canvas>
      </div>

      <div class="row small" style="margin-top:8px">
        <span class="pill mono">sampleRate: <span id="sr">-</span> Hz</span>
        <span class="pill mono">nyquist: <span id="ny">-</span> Hz</span>
        <span class="pill mono">peak: <span id="pk">-</span> Hz</span>
        <span class="pill mono">centroid: <span id="cent">-</span> Hz</span>
        <span class="pill mono">level: <span id="lvl">-</span> dBFS</span>
        <span class="pill mono">anomaly: <span id="anom">off</span></span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex: 1 1 320px;">
          <label>
            <input type="checkbox" id="lowPower" checked />
            Low-power mode (recommended on phones)
          </label>
          <div class="small">
            Uses smaller FFT + slower redraw + prefers a smaller Whisper model.
          </div>
        </div>

        <div class="col" style="flex: 1 1 240px;">
          <label>AI model</label>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (fastest, English)</option>
            <option value="Xenova/whisper-tiny">whisper-tiny (fast, multilingual)</option>
            <option value="Xenova/whisper-base.en">whisper-base.en (better, slower)</option>
          </select>
          <div class="small">Runs locally in your browser (no paid API).</div>
        </div>
      </div>

      <hr />

      <div class="row">
        <div class="col" style="flex: 1 1 320px;">
          <label>
            <input type="checkbox" id="shiftOn" />
            Enable frequency shift (heterodyne / “bat detector”)
          </label>
          <div class="small">Shifts higher-frequency energy down into audible range.</div>
        </div>

        <div class="col" style="flex: 1 1 280px;">
          <label>
            <input type="checkbox" id="transcribeShifted" />
            Transcribe shifted audio (experimental)
          </label>
          <div class="small">May reduce normal speech accuracy.</div>
        </div>
      </div>

      <div class="row">
        <div class="col" style="flex: 1 1 340px;">
          <label>Shift amount (Hz): <span class="mono" id="shiftHzLabel">12000</span></label>
          <input id="shiftHz" type="range" min="1000" max="20000" value="12000" />
          <div class="small">Example: set 12000 Hz, energy near ~18 kHz shifts down near ~6 kHz.</div>
        </div>

        <div class="col" style="flex: 1 1 340px;">
          <label>
            <input type="checkbox" id="headphoneSafe" />
            Headphone Safe monitoring (requires confirmation)
          </label>
          <label class="small">
            <input type="checkbox" id="iHaveHeadphones" disabled />
            I am wearing headphones (unlock monitoring volume)
          </label>
          <div class="small">When enabled, adds a limiter and unlocks monitor volume.</div>
        </div>
      </div>

      <div class="row">
        <div class="col" style="flex: 1 1 340px;">
          <label>Monitor volume: <span class="mono" id="monVolLabel">0.00</span></label>
          <input id="monVol" type="range" min="0" max="1" step="0.01" value="0" disabled />
          <div class="small">Locked unless Headphone Safe + “I am wearing headphones” are enabled.</div>
        </div>

        <div class="col" style="flex: 1 1 340px;">
          <label>Transcription chunk (seconds): <span class="mono" id="chunkSecLabel">2.5</span></label>
          <input id="chunkSec" type="range" min="1" max="6" step="0.5" value="2.5" />
          <div class="small">Smaller chunks update faster but can be less accurate.</div>
        </div>
      </div>

      <hr />

      <div class="row">
        <div class="col" style="flex: 1 1 340px;">
          <label>
            <input type="checkbox" id="ttsOn" checked />
            Speak recognized text out loud (SpeechSynthesis)
          </label>
          <div class="small">Uses your browser’s built-in voice.</div>
        </div>

        <div class="col" style="flex: 1 1 340px;">
          <label>
            <input type="checkbox" id="anomalyOn" />
            Anomaly detection (spectral flux) + notify
          </label>
          <div class="small">Flags sudden spectral changes (clicks, beeps, bursts).</div>
        </div>
      </div>

      <div class="row">
        <div class="col" style="flex: 1 1 520px;">
          <label>
            <input type="checkbox" id="scanOn" />
            Band-scan mode (band-pass sweep) + peak list
          </label>
          <div class="small">Sweeps a band-pass filter and logs strongest bands.</div>
        </div>

        <div class="col" style="flex: 1 1 220px;">
          <label>Sweep speed</label>
          <select id="scanSpeed">
            <option value="slow">Slow</option>
            <option value="med" selected>Medium</option>
            <option value="fast">Fast</option>
          </select>
        </div>

        <div class="col" style="flex: 1 1 220px;">
          <label>Scan band (Hz)</label>
          <select id="scanBand">
            <option value="wide" selected>Wide</option>
            <option value="narrow">Narrow</option>
          </select>
        </div>
      </div>

      <div class="ok small" style="margin-top:10px">
        <b>Tip (GitHub Pages):</b> Use the Pages URL (starts with <span class="codepill">https://</span>), not the
        GitHub file viewer (<span class="codepill">github.com/.../blob/...</span>).
      </div>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between;">
        <div>
          <div class="mono">Live Output</div>
          <div class="small">Transcripts + hints + scan/anomaly logs.</div>
        </div>
        <div class="row">
          <button id="btnCopy" class="secondary">Copy</button>
          <button id="btnClear" class="secondary">Clear</button>
        </div>
      </div>

      <textarea id="out" placeholder="(output appears here)"></textarea>

      <div class="small warn" style="margin-top:10px">
        <b>Reality check:</b> Most microphones cannot capture true ultrasound reliably, and human speech doesn’t
        contain “secret words” above hearing. This tool is best for detecting high-frequency <i>noise</i>, shifting it
        to audible range, and transcribing whatever speech is actually present.
      </div>
    </div>
  </div>

  <!-- Permission / help overlay -->
  <div id="permOverlay" class="overlay" role="dialog" aria-modal="true" aria-label="Microphone help">
    <div class="modal">
      <h2 id="permTitle">Microphone permission needed</h2>
      <p class="sub" id="permSubtitle">
        Your browser must allow microphone access. This app will never auto-enable the mic — you must click Allow.
      </p>

      <div id="permErrorBox" class="warn small" style="display:none"></div>

      <div class="steps">
        <div class="step">
          <b>1) Make sure you are on a secure URL</b>
          <div class="muted">
            Must be <span class="codepill">https://</span> (GitHub Pages) or <span class="codepill">http://localhost</span>.
            The mic will not work reliably on <span class="codepill">file://</span> or GitHub’s <span class="codepill">blob</span> view.
          </div>
        </div>

        <div class="step">
          <b>2) Allow microphone for this site</b>
          <div class="muted">
            On Chrome/Edge: tap the <span class="codepill">🔒</span> icon → <span class="codepill">Site settings</span> →
            <span class="codepill">Microphone</span> → <span class="codepill">Allow</span>, then refresh.
          </div>
        </div>

        <div class="step">
          <b>3) If you hit “Block” by accident</b>
          <div class="muted">
            Open site settings and change Microphone to Allow. You may need to refresh the page after changing it.
          </div>
        </div>

        <div class="step">
          <b>4) If there is no mic on the device</b>
          <div class="muted">
            Plug in a headset/mic or check OS permissions. Some browsers also block mic in private browsing modes.
          </div>
        </div>
      </div>

      <div class="actions">
        <button id="btnTryAgain">Try Start Mic Again</button>
        <button id="btnCloseOverlay" class="secondary">Close</button>
      </div>

      <div class="small" style="margin-top:10px; opacity:.88">
        <b>Debug hint:</b> If it fails instantly with “NotAllowedError”, the mic is blocked in browser/site settings.
        If it says “NotFoundError”, no microphone device is available.
      </div>
    </div>
  </div>

  <script type="module">
    import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";

    const $ = (id) => document.getElementById(id);

    // Buttons & status
    const btnStart = $("btnStart");
    const btnStop = $("btnStop");
    const btnLoadModel = $("btnLoadModel");
    const btnClear = $("btnClear");
    const btnCopy = $("btnCopy");
    const btnHelp = $("btnHelp");
    const statusEl = $("status");

    // Overlay
    const permOverlay = $("permOverlay");
    const permTitle = $("permTitle");
    const permSubtitle = $("permSubtitle");
    const permErrorBox = $("permErrorBox");
    const btnTryAgain = $("btnTryAgain");
    const btnCloseOverlay = $("btnCloseOverlay");
    const envBanner = $("envBanner");

    // Visuals
    const spec = $("spec");
    const ctx2d = spec.getContext("2d");

    // Readouts
    const srEl = $("sr");
    const nyEl = $("ny");
    const pkEl = $("pk");
    const centEl = $("cent");
    const lvlEl = $("lvl");
    const anomEl = $("anom");

    // Controls
    const lowPower = $("lowPower");
    const modelSel = $("modelSel");

    const shiftOn = $("shiftOn");
    const transcribeShifted = $("transcribeShifted");
    const shiftHz = $("shiftHz");
    const shiftHzLabel = $("shiftHzLabel");

    const headphoneSafe = $("headphoneSafe");
    const iHaveHeadphones = $("iHaveHeadphones");
    const monVol = $("monVol");
    const monVolLabel = $("monVolLabel");

    const chunkSec = $("chunkSec");
    const chunkSecLabel = $("chunkSecLabel");

    const ttsOn = $("ttsOn");

    const anomalyOn = $("anomalyOn");

    const scanOn = $("scanOn");
    const scanSpeed = $("scanSpeed");
    const scanBand = $("scanBand");

    const out = $("out");

    // ======= Audio state =======
    let audioCtx = null;
    let stream = null;
    let source = null;

    // analysis
    let analyser = null;
    let freqData = null;
    let timeData = null;

    // monitor chain
    let monitorGain = null;
    let compressor = null;

    // heterodyne
    let shifterNode = null;
    let phase = 0;

    // scan filter (monitor only)
    let scanFilter = null;
    let scanPhase = 0;

    // ======= Recorder / ASR state =======
    let mediaRecorder = null;
    let chunkTimer = null;

    // Whisper
    let asr = null;
    let modelLoaded = false;
    let busy = false;

    // anomaly detection
    let prevSpectrum = null;
    let anomScore = 0;
    let lastPeakLog = 0;

    // ======= UX helpers =======
    function setStatus(s) { statusEl.textContent = s; }

    function appendLine(line) {
      const prefix = out.value.length && !out.value.endsWith("\\n") ? "\\n" : "";
      out.value += prefix + line;
      out.scrollTop = out.scrollHeight;
    }

    function nowTime() {
      const d = new Date();
      return d.toLocaleTimeString([], { hour12: true });
    }

    function showOverlay({ title, subtitle, errorHtml } = {}) {
      permTitle.textContent = title || "Microphone permission needed";
      permSubtitle.textContent = subtitle || "Your browser must allow microphone access. This app will never auto-enable the mic — you must click Allow.";
      if (errorHtml) {
        permErrorBox.style.display = "block";
        permErrorBox.innerHTML = errorHtml;
      } else {
        permErrorBox.style.display = "none";
        permErrorBox.textContent = "";
      }
      permOverlay.classList.add("show");
    }

    function hideOverlay() {
      permOverlay.classList.remove("show");
      permErrorBox.style.display = "none";
      permErrorBox.textContent = "";
    }

    function environmentChecks() {
      const isSecure = window.isSecureContext || location.hostname === "localhost";
      const isFile = location.protocol === "file:";
      const isGithubBlob = location.hostname === "github.com" && location.pathname.includes("/blob/");
      const isPages = location.hostname.endsWith(".github.io") || location.hostname.endsWith("github.io");

      const msgs = [];
      if (isFile) msgs.push("You're opening this as a local file (file://). Most browsers block mic access here. Use GitHub Pages (https://) or localhost.");
      if (isGithubBlob) msgs.push("You're viewing the file on github.com (blob view). Mic will not work there. Open the GitHub Pages URL instead.");
      if (!isSecure) msgs.push("This page is not a secure context. Mic requires https:// or http://localhost.");

      if (msgs.length) {
        envBanner.classList.add("show");
        envBanner.innerHTML = "<b>Heads up:</b><br>" + msgs.map(m => "• " + m).join("<br>");
      } else if (isPages) {
        envBanner.classList.add("show");
        envBanner.innerHTML = "<b>GitHub Pages detected:</b> When you press <span class='codepill'>Start Mic</span>, your browser should prompt for microphone permission.";
      } else {
        envBanner.classList.remove("show");
      }
    }

    function micSupportChecks() {
      if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
        showOverlay({
          title: "Microphone not supported",
          subtitle: "This browser doesn't support microphone capture (getUserMedia). Try Chrome/Edge/Firefox.",
          errorHtml: "<b>Missing API:</b> navigator.mediaDevices.getUserMedia is not available."
        });
        return false;
      }
      return true;
    }

    async function queryPermissionIfPossible() {
      // Not all browsers support Permissions API for microphone.
      try {
        if (!navigator.permissions || !navigator.permissions.query) return null;
        const p = await navigator.permissions.query({ name: "microphone" });
        return p.state; // 'granted' | 'prompt' | 'denied'
      } catch {
        return null;
      }
    }

    function speak(text) {
      if (!ttsOn.checked) return;
      if (!("speechSynthesis" in window)) return;

      const u = new SpeechSynthesisUtterance(text);
      u.rate = 1.0;
      u.pitch = 1.0;
      u.volume = 1.0;

      window.speechSynthesis.cancel();
      window.speechSynthesis.speak(u);
    }

    // ======= Audio math =======
    function dbfsFromTimeDomain(arr) {
      let sumSq = 0;
      for (let i = 0; i < arr.length; i++) {
        const v = (arr[i] - 128) / 128;
        sumSq += v * v;
      }
      const rms = Math.sqrt(sumSq / arr.length);
      if (rms <= 1e-9) return "-inf";
      return (20 * Math.log10(rms)).toFixed(1);
    }

    function spectralCentroid(freqBytes, nyquist) {
      let num = 0, den = 0;
      const n = freqBytes.length;
      for (let i = 0; i < n; i++) {
        const mag = freqBytes[i] / 255;
        const hz = (i / n) * nyquist;
        num += hz * mag;
        den += mag;
      }
      return den > 0 ? (num / den) : 0;
    }

    function findPeakHz(freqBytes, nyquist) {
      let peakIdx = 0;
      for (let i = 1; i < freqBytes.length; i++) {
        if (freqBytes[i] > freqBytes[peakIdx]) peakIdx = i;
      }
      const hz = (peakIdx / freqBytes.length) * nyquist;
      return { peakIdx, hz };
    }

    function phonemeHint(freqBytes, nyquist) {
      // conservative "vowel-ish" hints (not words)
      const n = freqBytes.length;
      const bandEnergy = (loHz, hiHz) => {
        const lo = Math.max(0, Math.floor((loHz / nyquist) * n));
        const hi = Math.min(n - 1, Math.floor((hiHz / nyquist) * n));
        let s = 0;
        for (let i = lo; i <= hi; i++) s += (freqBytes[i] / 255);
        return s;
      };

      const low = bandEnergy(80, 300);
      const f1 = bandEnergy(300, 900);
      const f2 = bandEnergy(900, 2600);
      const high = bandEnergy(2600, 6000);

      const total = low + f1 + f2 + high + 1e-9;
      const rLow = low / total, rF1 = f1 / total, rF2 = f2 / total, rHigh = high / total;

      let hint = "unknown";
      if (rLow > 0.30 && rHigh < 0.10) hint = "vowel-ish: 'oo' (rough)";
      else if (rF2 > 0.38 && rHigh > 0.12) hint = "vowel-ish: 'ee' (rough)";
      else if (rF1 > 0.32 && rF2 < 0.33) hint = "vowel-ish: 'ah' (rough)";
      else if (rF1 > 0.25 && rF2 > 0.25) hint = "vowel-ish: 'eh/ih' (rough)";

      const activity = total / n;
      if (activity < 0.02) return null;
      return hint;
    }

    function applyHeterodyneToPCM(pcm, sampleRate, shiftHzVal) {
      const outArr = new Float32Array(pcm.length);
      const twoPi = 2 * Math.PI;
      let ph = 0;
      const inc = twoPi * shiftHzVal / sampleRate;
      for (let i = 0; i < pcm.length; i++) {
        outArr[i] = pcm[i] * Math.cos(ph);
        ph += inc;
        if (ph > 1e9) ph = ph % twoPi;
      }
      return outArr;
    }

    function buildShifter(inputNode) {
      const bufferSize = lowPower.checked ? 2048 : 1024;
      const sp = audioCtx.createScriptProcessor(bufferSize, 1, 1);

      sp.onaudioprocess = (e) => {
        const input = e.inputBuffer.getChannelData(0);
        const output = e.outputBuffer.getChannelData(0);
        const fShift = Number(shiftHz.value);
        const sr = audioCtx.sampleRate;
        const twoPi = 2 * Math.PI;

        for (let i = 0; i < input.length; i++) {
          output[i] = input[i] * Math.cos(phase);
          phase += twoPi * fShift / sr;
          if (phase > 1e9) phase = phase % twoPi;
        }
      };

      inputNode.connect(sp);
      return sp;
    }

    function setupMonitorChain() {
      try { if (monitorGain) monitorGain.disconnect(); } catch {}
      try { if (compressor) compressor.disconnect(); } catch {}
      try { if (scanFilter) scanFilter.disconnect(); } catch {}
      try { if (shifterNode) shifterNode.disconnect(); } catch {}

      monitorGain = audioCtx.createGain();
      monitorGain.gain.value = Number(monVol.value);

      compressor = audioCtx.createDynamicsCompressor();
      compressor.threshold.value = -24;
      compressor.knee.value = 20;
      compressor.ratio.value = 12;
      compressor.attack.value = 0.003;
      compressor.release.value = 0.25;

      scanFilter = audioCtx.createBiquadFilter();
      scanFilter.type = "bandpass";
      scanFilter.frequency.value = 2000;
      scanFilter.Q.value = (scanBand.value === "narrow") ? 18 : 6;

      let node = source;

      if (shiftOn.checked) {
        shifterNode = buildShifter(node);
        node = shifterNode;
      }

      if (scanOn.checked) {
        node.connect(scanFilter);
        node = scanFilter;
      }

      if (headphoneSafe.checked) {
        node.connect(compressor);
        compressor.connect(monitorGain);
      } else {
        node.connect(monitorGain);
      }

      monitorGain.connect(audioCtx.destination);
    }

    function enforceHeadphoneSafetyUI() {
      if (headphoneSafe.checked) iHaveHeadphones.disabled = false;
      else {
        iHaveHeadphones.checked = false;
        iHaveHeadphones.disabled = true;
      }

      const unlocked = headphoneSafe.checked && iHaveHeadphones.checked;
      monVol.disabled = !unlocked;

      if (!unlocked) {
        monVol.value = "0";
        monVolLabel.textContent = "0.00";
        if (monitorGain) monitorGain.gain.value = 0;
      }
    }

    // ======= AI model =======
    async function loadModel() {
      if (modelLoaded) return;
      btnLoadModel.disabled = true;

      env.allowLocalModels = false;
      env.useBrowserCache = true;

      const modelId = modelSel.value;
      setStatus("loading model…");
      appendLine(`[${nowTime()}] Loading model: ${modelId}`);

      const device = (navigator.gpu ? "webgpu" : "wasm");
      appendLine(`[${nowTime()}] Backend: ${device}`);

      asr = await pipeline("automatic-speech-recognition", modelId, { device });
      modelLoaded = true;
      setStatus("model loaded");
      appendLine(`[${nowTime()}] Model loaded.`);
    }

    // ======= Recording / transcription loop =======
    function startChunkedTranscription() {
      if (!stream) return;

      const seconds = Number(chunkSec.value);
      const mime = MediaRecorder.isTypeSupported("audio/webm;codecs=opus")
        ? "audio/webm;codecs=opus"
        : "audio/webm";

      if (chunkTimer) { clearInterval(chunkTimer); chunkTimer = null; }
      if (mediaRecorder && mediaRecorder.state !== "inactive") mediaRecorder.stop();
      mediaRecorder = null;

      mediaRecorder = new MediaRecorder(stream, { mimeType: mime });
      const chunks = [];

      mediaRecorder.ondataavailable = (e) => {
        if (e.data && e.data.size > 0) chunks.push(e.data);
      };

      mediaRecorder.onstop = async () => {
        if (!chunks.length) return;
        const blob = new Blob(chunks.splice(0, chunks.length), { type: mime });
        await transcribeBlob(blob);
      };

      const cycle = () => {
        if (!mediaRecorder) return;
        if (mediaRecorder.state === "recording") return;

        mediaRecorder.start();
        setTimeout(() => {
          if (mediaRecorder && mediaRecorder.state === "recording") mediaRecorder.stop();
        }, Math.max(600, seconds * 1000));
      };

      cycle();
      chunkTimer = setInterval(cycle, Math.max(700, seconds * 1000 + 200));
    }

    async function transcribeBlob(blob) {
      if (!modelLoaded || !asr) return;
      if (busy) return;

      busy = true;
      setStatus("transcribing…");

      try {
        const arrayBuffer = await blob.arrayBuffer();
        const tmpCtx = new (window.AudioContext || window.webkitAudioContext)();
        const audioBuf = await tmpCtx.decodeAudioData(arrayBuffer);
        const pcm = audioBuf.getChannelData(0);
        const sr = audioBuf.sampleRate;

        let pcmToUse = pcm;
        if (shiftOn.checked && transcribeShifted.checked) {
          pcmToUse = applyHeterodyneToPCM(pcm, sr, Number(shiftHz.value));
        }

        await tmpCtx.close();

        const result = await asr(pcmToUse, {
          chunk_length_s: Number(chunkSec.value),
          stride_length_s: 0.2,
          return_timestamps: false
        });

        const text = (result?.text || "").trim();
        if (text) {
          appendLine(`[${nowTime()}] ${text}`);
          speak(text);
        }
      } catch (err) {
        console.error(err);
        appendLine(`[${nowTime()}] [error] ${err?.message || String(err)}`);
      } finally {
        busy = false;
        setStatus("listening");
      }
    }

    // ======= Stop =======
    function stopAll() {
      if (chunkTimer) { clearInterval(chunkTimer); chunkTimer = null; }
      if (mediaRecorder && mediaRecorder.state !== "inactive") mediaRecorder.stop();
      mediaRecorder = null;

      try { if (shifterNode) shifterNode.disconnect(); } catch {}
      shifterNode = null;

      try { if (scanFilter) scanFilter.disconnect(); } catch {}
      scanFilter = null;

      try { if (source) source.disconnect(); } catch {}
      source = null;

      try { if (analyser) analyser.disconnect(); } catch {}
      analyser = null;

      try { if (monitorGain) monitorGain.disconnect(); } catch {}
      monitorGain = null;

      try { if (compressor) compressor.disconnect(); } catch {}
      compressor = null;

      if (stream) {
        for (const track of stream.getTracks()) track.stop();
        stream = null;
      }

      if (audioCtx) {
        audioCtx.close();
        audioCtx = null;
      }

      btnStart.disabled = false;
      btnStop.disabled = true;
      setStatus("stopped");
    }

    // ======= Scan/anomaly =======
    function updateScanFilter() {
      if (!scanFilter || !audioCtx) return;

      const nyquist = audioCtx.sampleRate / 2;
      const minHz = 60;
      const maxHz = Math.max(500, Math.min(nyquist - 200, 20000));

      const speed = scanSpeed.value;
      const step =
        speed === "slow" ? 0.002 :
        speed === "fast" ? 0.010 :
        0.005;

      scanPhase += step;
      if (scanPhase > 1) scanPhase -= 1;

      const logMin = Math.log(minHz);
      const logMax = Math.log(maxHz);
      const f = Math.exp(logMin + (logMax - logMin) * scanPhase);

      scanFilter.frequency.value = f;
      scanFilter.Q.value = (scanBand.value === "narrow") ? 18 : 6;
    }

    function logTopPeaks(freqBytes, nyquist) {
      const t = performance.now();
      if (t - lastPeakLog < 1200) return;
      lastPeakLog = t;

      const n = freqBytes.length;
      const peaks = [];
      for (let i = 2; i < n - 2; i++) {
        const a = freqBytes[i - 1], b = freqBytes[i], c = freqBytes[i + 1];
        if (b > a && b > c && b > 140) {
          const hz = (i / n) * nyquist;
          peaks.push({ hz, mag: b });
        }
      }
      peaks.sort((p, q) => q.mag - p.mag);
      const top = peaks.slice(0, 5);
      if (!top.length) return;

      const list = top.map(p => `${p.hz.toFixed(0)}Hz`).join(", ");
      appendLine(`[${nowTime()}] [scan peaks] ${list}`);
    }

    function anomalyDetect(freqBytes) {
      if (!prevSpectrum) return 0;
      let flux = 0;
      for (let i = 0; i < freqBytes.length; i++) {
        const v = freqBytes[i] / 255;
        const d = v - prevSpectrum[i];
        if (d > 0) flux += d;
        prevSpectrum[i] = v;
      }
      return flux;
    }

    // ======= Draw loop =======
    function drawLoop() {
      if (!analyser || !audioCtx) return;

      if (scanOn.checked) updateScanFilter();

      analyser.getByteFrequencyData(freqData);
      analyser.getByteTimeDomainData(timeData);

      const nyquist = audioCtx.sampleRate / 2;

      const { peakIdx, hz: peakHz } = findPeakHz(freqData, nyquist);
      const centroid = spectralCentroid(freqData, nyquist);
      const db = dbfsFromTimeDomain(timeData);

      pkEl.textContent = peakHz.toFixed(0);
      centEl.textContent = centroid.toFixed(0);
      lvlEl.textContent = db;

      if (anomalyOn.checked) {
        const flux = anomalyDetect(freqData);
        anomScore = 0.85 * anomScore + 0.15 * flux;
        anomEl.textContent = anomScore.toFixed(2);

        if (anomScore > (lowPower.checked ? 2.2 : 2.0)) {
          appendLine(`[${nowTime()}] [anomaly] spectral change detected (score=${anomScore.toFixed(2)})`);
          anomScore = 0.6 * anomScore;
        }
      } else {
        anomEl.textContent = "off";
      }

      const hint = phonemeHint(freqData, nyquist);
      if (hint && (!busy) && Math.random() < 0.02) {
        appendLine(`[${nowTime()}] [hint] ${hint}`);
      }

      if (scanOn.checked) logTopPeaks(freqData, nyquist);

      // Draw spectrum
      ctx2d.clearRect(0, 0, spec.width, spec.height);
      const w = spec.width, h = spec.height;
      const n = freqData.length;
      const barW = w / n;

      for (let i = 0; i < n; i++) {
        const v = freqData[i] / 255;
        const barH = v * (h - 20);
        ctx2d.fillStyle = `rgba(125, 177, 255, ${0.10 + v * 0.85})`;
        ctx2d.fillRect(i * barW, h - barH, barW, barH);
      }

      // Peak marker
      const x = peakIdx * barW;
      ctx2d.fillStyle = "rgba(255,255,255,0.9)";
      ctx2d.fillRect(x, 0, 2, h);

      // Scan marker (center frequency)
      if (scanOn.checked && scanFilter) {
        const fx = (scanFilter.frequency.value / nyquist) * w;
        ctx2d.fillStyle = "rgba(255, 230, 160, 0.9)";
        ctx2d.fillRect(fx, 0, 2, h);
      }

      const delay = lowPower.checked ? 60 : 0;
      if (delay) setTimeout(() => requestAnimationFrame(drawLoop), delay);
      else requestAnimationFrame(drawLoop);
    }

    function reconnectAudioGraphIfRunning() {
      if (!audioCtx || !source) return;

      if (analyser) {
        analyser.fftSize = lowPower.checked ? 1024 : 2048;
        freqData = new Uint8Array(analyser.frequencyBinCount);
        timeData = new Uint8Array(analyser.fftSize);
        prevSpectrum = new Float32Array(analyser.frequencyBinCount);
      }

      setupMonitorChain();
      enforceHeadphoneSafetyUI();
    }

    // ======= Mic start with better UX =======
    function formatMicError(e, permState) {
      const name = e?.name || "Error";
      const msg = e?.message || String(e);

      let title = "Microphone error";
      let subtitle = "Your browser blocked or could not access the microphone.";
      let html = `<b>${name}:</b> ${msg}<br><br>`;

      if (name === "NotAllowedError" || name === "SecurityError") {
        title = "Microphone blocked";
        subtitle = "The site is not allowed to use your microphone (permission denied).";
        html += "• Open the 🔒 site settings and set <b>Microphone</b> to <b>Allow</b>.<br>";
        html += "• If you previously tapped <b>Block</b>, you must change it in site settings and refresh.<br>";
        if (permState) html += `• Permission state: <span class="codepill">${permState}</span><br>`;
      } else if (name === "NotFoundError" || name === "DevicesNotFoundError") {
        title = "No microphone found";
        subtitle = "No audio input device is available.";
        html += "• Plug in a headset mic or ensure your device mic is available.<br>";
      } else if (name === "NotReadableError" || name === "TrackStartError") {
        title = "Microphone busy";
        subtitle = "Another app might be using the microphone.";
        html += "• Close other apps/tabs that might be using the mic (calls, recorders, voice chat).<br>";
        html += "• Then try again.<br>";
      } else if (name === "OverconstrainedError") {
        title = "Mic constraints not supported";
        subtitle = "The browser couldn’t satisfy requested audio settings.";
        html += "• Try again; or use a different browser/device.<br>";
      } else {
        html += "• Try Chrome/Edge on Android or desktop.<br>";
      }

      return { title, subtitle, html };
    }

    async function startMic() {
      if (!micSupportChecks()) return;

      // Quick environment warning before we even ask
      if (!window.isSecureContext && location.hostname !== "localhost") {
        showOverlay({
          title: "Mic needs HTTPS (or localhost)",
          subtitle: "Browsers require a secure origin for microphone access.",
          errorHtml: "You're on an insecure page. Use <b>https://</b> (GitHub Pages) or <b>http://localhost</b>."
        });
        return;
      }
      if (location.hostname === "github.com" && location.pathname.includes("/blob/")) {
        showOverlay({
          title: "Open the GitHub Pages URL",
          subtitle: "The GitHub file viewer cannot request mic permission.",
          errorHtml: "You're on <b>github.com</b> blob view. Open your <b>https://username.github.io/repo/</b> page instead."
        });
        return;
      }

      if (audioCtx) return;

      // Check permission state (if possible) so the overlay can be more specific
      const permState = await queryPermissionIfPossible();
      if (permState === "denied") {
        showOverlay({
          title: "Microphone is blocked",
          subtitle: "Your browser/site settings are set to Block.",
          errorHtml: "Permission state is <b>denied</b>. Tap the 🔒 icon → Site settings → Microphone → <b>Allow</b>, then refresh."
        });
        return;
      }

      setStatus("requesting mic…");

      try {
        // Note: using minimal constraints increases compatibility
        stream = await navigator.mediaDevices.getUserMedia({
          audio: { echoCancellation: false, noiseSuppression: false, autoGainControl: false }
        });
      } catch (e) {
        const info = formatMicError(e, permState);
        setStatus("mic error");
        showOverlay({ title: info.title, subtitle: info.subtitle, errorHtml: info.html });
        appendLine(`[${nowTime()}] [mic error] ${info.title} — ${e?.name || e}`);
        return;
      }

      // Success: hide overlay if it was open
      hideOverlay();

      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      srEl.textContent = audioCtx.sampleRate.toFixed(0);
      nyEl.textContent = (audioCtx.sampleRate / 2).toFixed(0);

      source = audioCtx.createMediaStreamSource(stream);

      analyser = audioCtx.createAnalyser();
      analyser.fftSize = lowPower.checked ? 1024 : 2048;
      analyser.smoothingTimeConstant = 0.6;

      freqData = new Uint8Array(analyser.frequencyBinCount);
      timeData = new Uint8Array(analyser.fftSize);
      prevSpectrum = new Float32Array(analyser.frequencyBinCount);

      source.connect(analyser);

      setupMonitorChain();
      enforceHeadphoneSafetyUI();

      startChunkedTranscription();

      btnStart.disabled = true;
      btnStop.disabled = false;

      setStatus("listening");
      appendLine(`[${nowTime()}] Mic started. sampleRate=${audioCtx.sampleRate}Hz`);
      requestAnimationFrame(drawLoop);
    }

    // ======= Events =======
    btnStart.addEventListener("click", startMic);

    btnStop.addEventListener("click", () => {
      appendLine(`[${nowTime()}] Stopping…`);
      stopAll();
    });

    btnLoadModel.addEventListener("click", async () => {
      try {
        await loadModel();
      } catch (e) {
        console.error(e);
        alert("Model load failed: " + (e?.message || e));
        setStatus("model load error");
        btnLoadModel.disabled = false;
      }
    });

    btnHelp.addEventListener("click", async () => {
      const permState = await queryPermissionIfPossible();
      showOverlay({
        title: "Microphone help",
        subtitle: "Follow these steps to enable the mic.",
        errorHtml: permState ? `Permissions API reports: <span class="codepill">${permState}</span>` : null
      });
    });

    btnTryAgain.addEventListener("click", async () => {
      hideOverlay();
      await startMic();
    });

    btnCloseOverlay.addEventListener("click", hideOverlay);

    btnClear.addEventListener("click", () => { out.value = ""; });

    btnCopy.addEventListener("click", async () => {
      try {
        await navigator.clipboard.writeText(out.value || "");
        appendLine(`[${nowTime()}] (copied to clipboard)`);
      } catch {
        alert("Copy failed (clipboard permissions). You can manually select/copy.");
      }
    });

    shiftHz.addEventListener("input", () => { shiftHzLabel.textContent = shiftHz.value; });

    chunkSec.addEventListener("input", () => {
      chunkSecLabel.textContent = chunkSec.value;
      if (stream) startChunkedTranscription();
    });

    lowPower.addEventListener("change", () => reconnectAudioGraphIfRunning());

    shiftOn.addEventListener("change", () => { if (audioCtx) reconnectAudioGraphIfRunning(); });
    scanOn.addEventListener("change", () => { if (audioCtx) reconnectAudioGraphIfRunning(); });

    scanBand.addEventListener("change", () => {
      if (scanFilter) scanFilter.Q.value = (scanBand.value === "narrow") ? 18 : 6;
    });

    headphoneSafe.addEventListener("change", () => {
      enforceHeadphoneSafetyUI();
      if (audioCtx) reconnectAudioGraphIfRunning();
    });

    iHaveHeadphones.addEventListener("change", () => {
      enforceHeadphoneSafetyUI();
      if (audioCtx) reconnectAudioGraphIfRunning();
    });

    monVol.addEventListener("input", () => {
      monVolLabel.textContent = Number(monVol.value).toFixed(2);
      if (monitorGain) monitorGain.gain.value = Number(monVol.value);
    });

    modelSel.addEventListener("change", () => {
      if (modelLoaded) appendLine(`[${nowTime()}] Model already loaded. Reload the page to load a different model.`);
    });

    // Init labels and checks
    shiftHzLabel.textContent = shiftHz.value;
    chunkSecLabel.textContent = chunkSec.value;
    monVolLabel.textContent = Number(monVol.value).toFixed(2);
    enforceHeadphoneSafetyUI();
    environmentChecks();

    // If permissions are denied, proactively show help (no mic prompt)
    (async () => {
      const permState = await queryPermissionIfPossible();
      if (permState === "denied") {
        showOverlay({
          title: "Microphone is blocked",
          subtitle: "Your browser/site settings are set to Block.",
          errorHtml: "Tap the 🔒 icon → Site settings → Microphone → <b>Allow</b>, then refresh."
        });
      }
    })();

    setStatus("idle (Start Mic, then Load AI Model)");
    appendLine(`[${nowTime()}] Ready. Use HTTPS (GitHub Pages) or localhost for mic access.`);
  </script>
</body>
</html>
