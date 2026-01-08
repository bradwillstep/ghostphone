<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <title>Ultra Listener — Android Pro (VAD + Spectrogram + Logs + A/B)</title>
  <style>
    :root{
      color-scheme: dark;
      --bg:#000;
      --panel:#050505;
      --border:#0f3a18;
      --green:#35ff6a;
      --green-dim: rgba(53,255,106,.78);
      --green-faint: rgba(53,255,106,.28);
      --yellow:#ffd740;
      --red:#ff4d4d;
      --font: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
    }
    body{ margin:0; padding:14px; background:var(--bg); color:var(--green); font-family:var(--font); letter-spacing:.2px; }
    h1{ margin:0 0 10px; font-size:16px; text-shadow:0 0 8px rgba(53,255,106,.25); }
    .grid{ display:grid; gap:12px; grid-template-columns:1fr; }
    @media (min-width: 980px){ .grid{ grid-template-columns: 1.25fr 0.75fr; } }
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
    button.yellow{ border-color: rgba(255,215,64,.55); color: rgba(255,231,140,.95); }
    .pill{
      display:inline-flex; align-items:center; gap:8px;
      padding:4px 8px; border-radius:999px;
      border:1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      font-size:12px; white-space:nowrap;
    }
    .small{ font-size:12px; color:var(--green-dim); line-height:1.35; }
    .banner{
      display:none;
      border-radius:10px; padding:10px;
      border:1px solid var(--border);
      background: rgba(53,255,106,.04);
      color: var(--green-dim);
      margin-bottom: 12px;
      font-size:12px; line-height:1.35;
    }
    .banner.show{ display:block; }

    canvas{ width:100%; border-radius:10px; border:1px solid var(--border); background:#000; }
    #spec{ height:140px; }
    #specgram{ height:190px; image-rendering: pixelated; }

    textarea{
      width:100%; min-height: 260px; resize: vertical;
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
      margin-top:10px;
      padding: 8px 10px;
      border-radius:10px;
      border:1px solid var(--border);
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

    /* Toggle */
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

    /* Segmented */
    .seg{ display:inline-flex; border:1px solid var(--border); border-radius:999px; overflow:hidden; background: rgba(53,255,106,.04); }
    .seg input{ display:none; }
    .seg label{
      padding: 8px 10px;
      font-size: 12px;
      color: var(--green-dim);
      cursor:pointer;
      border-right: 1px solid rgba(53,255,106,.18);
    }
    .seg label:last-child{ border-right:0; }
    .seg input:checked + label{ color: var(--bg); background: rgba(53,255,106,.85); }

    details{ border:1px solid var(--border); border-radius:10px; padding:10px; background: rgba(53,255,106,.04); }
    summary{ cursor:pointer; font-weight: 800; color: rgba(53,255,106,.9); }
    .tiny{ font-size:12px; }

    /* Overlay */
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
    .steps{ display:grid; gap:10px; grid-template-columns:1fr; }
    @media (min-width: 760px){ .steps{ grid-template-columns:1fr 1fr; } }
    .step{ border:1px solid var(--border); background: rgba(53,255,106,.04); border-radius:10px; padding:10px; }
    .step b{ font-size: 12px; }
    .muted{ font-size:12px; color: var(--green-dim); line-height:1.35; }
    .actions{ display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end; margin-top:10px; }
    .codepill{ display:inline-block; padding:2px 6px; border-radius:8px; border:1px solid var(--border); background: rgba(53,255,106,.04); }
  
    /* Study mode highlight */
    #studyPanel.unlocked{
      border-color: rgba(255,215,64,.95) !important;
      box-shadow: 0 0 0 1px rgba(255,215,64,.35) inset, 0 0 18px rgba(255,215,64,.18);
    }

  </style>
</head>
<body>
  <h1>ULTRA LISTENER // ANDROID PRO</h1>

  <div id="envBanner" class="banner"></div>

  <div class="grid">
    <div class="card">
      <!-- Model + Translate -->
      <div class="row" style="justify-content: space-between; margin-bottom:10px">
        <div class="col" style="flex: 1 1 520px">
          <div class="small"><b>WHISPER MODEL</b> (locks after load)</div>
          <select id="modelSel">
            <option value="Xenova/whisper-tiny">whisper-tiny (fast, multilingual) — recommended</option>
            <option value="Xenova/whisper-tiny.en">whisper-tiny.en (fastest, English-only)</option>
            <option value="Xenova/whisper-base.en">whisper-base.en (better, English-only)</option>
          </select>
          <div class="small">Android Chrome: keep model small for less lag.</div>
        </div>

        <div class="col" style="flex: 1 1 320px">
          <div class="small"><b>TRANSLATE</b></div>
          <label class="toggle" title="Translate detected speech to English">
            <input id="translateOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Translate to English</span>
          </label>
          <div class="small">Requires multilingual model (whisper-tiny).</div>
        </div>
      </div>

      <!-- Mic + model load -->
      <div class="row">
        <button id="btnStart">Start Mic</button>
        <button id="btnStop" class="danger" disabled>Stop</button>
        <button id="btnLoadModel">Load AI Model</button>
        <button id="btnHelp">Mic Help</button>
        <button id="btnBaseline" class="yellow">Calibrate Baseline</button>
        <button id="btnInstall" class="yellow" disabled>Install App</button>
        <span class="pill" id="status">idle</span>
      </div>

      <div class="statusstrip" aria-label="Status indicators">
        <span class="kv"><span id="dotModel" class="dot"></span><span class="key">MODEL</span><span id="modelState" class="val">NOT LOADED</span></span>
        <span class="kv"><span id="dotMic" class="dot"></span><span class="key">MIC</span><span id="micState" class="val">OFF</span></span>
        <span class="kv"><span id="dotVad" class="dot"></span><span class="key">VAD</span><span id="vadState" class="val">IDLE</span></span>
        <span class="kv"><span class="key">ENT</span><span id="entVal" class="val">n/a</span></span>
        <span class="kv"><span class="key">FORM</span><span id="formVal" class="val">n/a</span></span>
        <span class="kv"><span class="key">LEVEL</span><span id="lvlDb" class="val">-inf dBFS</span></span>
        <span class="kv"><span class="key">VU</span><span class="vu"><div id="vuFill"></div></span></span>
      </div>

      <div style="margin-top:10px">
        <canvas id="spec" width="1200" height="260"></canvas>
      </div>

      <div style="margin-top:10px">
        <canvas id="specgram" width="1200" height="320"></canvas>
        <div class="small">Spectrogram (waterfall). Brighter = more energy. (Optimized for mobile: lower refresh.)</div>
      </div>

      <div class="row small" style="margin-top:8px">
        <span class="pill">sampleRate: <span id="sr">-</span> Hz</span>
        <span class="pill">nyquist: <span id="ny">-</span> Hz</span>
        <span class="pill">peak: <span id="pk">-</span> Hz</span>
        <span class="pill">noise floor: <span id="floorDb">n/a</span> dBFS</span>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>MODE</b></div>
          <div class="seg" aria-label="Mode">
            <input type="radio" name="mode" id="modeNormal" checked>
            <label for="modeNormal">Normal Speech</label>
            <input type="radio" name="mode" id="modeShift">
            <label for="modeShift">Band + Hz Shift</label>
          </div>
          <div class="small">Shift mode = band-isolate then heterodyne shift before AI (better than raw shift).</div>
        </div>

        <div class="col" style="flex:1 1 320px">
          <div class="small"><b>VOICE</b></div>
          <label class="toggle" title="Toggle audible voice">
            <input id="voiceOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Speak detected words</span>
          </label>
          <div class="small">If off, words still appear in output.</div>
        </div>

        <div class="col" style="flex:1 1 320px">
          <div class="small"><b>MONITOR SHIFTED AUDIO</b> (headphones)</div>
          <label class="toggle" title="Play shifted audio to headphones (can cause feedback)">
            <input id="monitorOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Monitor shifted audio</span>
          </label>
          <div class="small">Use headphones. Default off.</div>
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>SHIFT PRESET</b></div>
          <select id="shiftPreset">
            <option value="8000">8 kHz</option>
            <option value="12000" selected>12 kHz</option>
            <option value="16000">16 kHz</option>
          </select>
          <div class="small">Use with band isolate.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>BANDPASS CENTER</b> (Hz): <span id="bpCenterLabel">12000</span></div>
          <input id="bpCenter" type="range" min="2000" max="20000" value="12000" step="100" />
          <div class="small">Isolate a band before shifting (reduces junk).</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>BAND WIDTH</b> (Q): <span id="bpQLabel">12</span></div>
          <input id="bpQ" type="range" min="2" max="30" value="12" step="1" />
          <div class="small">Higher Q = narrower band.</div>
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>NOTCH</b> (hum removal)</div>
          <label class="toggle" title="Notch out 60 Hz and harmonics">
            <input id="notchOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Enable notch filters</span>
          </label>
          <div class="small">Reduces 50/60Hz hum & harmonics.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>WINDOW</b> seconds: <span id="winSecLabel">2.5</span></div>
          <input id="winSec" type="range" min="1" max="8" step="0.5" value="2.5" />
          <div class="small">How much recent audio gets transcribed each run.</div>
        </div>

        <div class="col" style="flex:1 1 340px">
          <div class="small"><b>UPDATE</b> every seconds: <span id="updSecLabel">1.0</span></div>
          <input id="updSec" type="range" min="0.5" max="3" step="0.5" value="1.0" />
          <div class="small">Android default: 1.0s for stability.</div>
        </div>
      </div>

      <div class="row" style="margin-top:10px">
        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>VAD (VOICE ACTIVITY) GATING</b></div>
          <label class="toggle" title="Only transcribe when voice-likely">
            <input id="vadOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Use VAD gating</span>
          </label>
          <div class="small">Reduces false positives. (VAD-lite: energy + ZCR + band ratios)</div>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>STABILITY RULE</b> (anti-hallucination)</div>
          <label class="toggle" title="Only print phrases that repeat/stabilize">
            <input id="stableOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Require stability</span>
          </label>
          <div class="small">Phrase must appear similarly in 2 updates.</div>
        </div>

        <div class="col" style="flex:1 1 360px">
          <div class="small"><b>DEDUPLICATE</b></div>
          <label class="toggle" title="Avoid repeating identical lines">
            <input id="dedupeOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Skip exact repeats</span>
          </label>
          <div class="small">Keeps output clean.</div>
        </div>
      </div>

      <details style="margin-top:10px">
        <summary>Session Tools (Logs + Export + A/B)</summary>
        <div class="row" style="margin-top:10px">
          <button id="btnMarkA" class="yellow">Mark A</button>
          <button id="btnMarkB" class="yellow">Mark B</button>
          <button id="btnCompare" class="yellow">Compare A/B</button>
          <button id="btnExportJson" class="yellow">Export Session JSON</button>
          <button id="btnExportWav" class="yellow">Export Last Clip WAV</button>
          <button id="btnScanToggle" class="yellow">Start Band Scan</button>
          <label class="toggle" title="Limit scan to target frequency range (e.g., 12k–18k)">
            <input id="scanTargetsOnly" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Scan targets only</span>
          </label>
          <span class="pill">Min <input id="scanMinHz" type="number" value="12000" min="2000" max="20000" style="width:92px;background:#000;color:#35ff6a;border:1px solid #0f3a18;border-radius:8px;padding:6px 8px;font-family:ui-monospace,monospace"></span>
          <span class="pill">Max <input id="scanMaxHz" type="number" value="18000" min="2000" max="20000" style="width:92px;background:#000;color:#35ff6a;border:1px solid #0f3a18;border-radius:8px;padding:6px 8px;font-family:ui-monospace,monospace"></span>
          <button id="btnLoadModel2" class="yellow">Load 2nd Model</button>
          <label class="toggle" title="Require 2 models to agree before printing">
            <input id="voteOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">2-model voting</span>
          </label>
          <label class="toggle" title="Only apply 2-model voting while band scan is running (recommended for Android)">
            <input id="voteOnlyScan" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Vote only during scan</span>
          </label>
          <label class="toggle" title="Show entropy/formant scoring in log and status">
            <input id="scoreOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Entropy/formant scoring</span>
          </label>
          <span class="pill">Last clip: <span id="clipInfo">n/a</span></span>
        </div>
        <div class="small" style="margin-top:10px">
          A/B workflow: record baseline, then toggle settings and press Mark A / Mark B during the same environment.
          Compare shows what repeated/stabilized in each mode.
        </div>
        
        <div class="row" style="margin-top:10px">
          <button id="btnMemRefresh" class="yellow">Refresh Memory Dashboard</button>
          <button id="btnMemClear" class="yellow">Clear Memory</button>
          <label class="toggle" title="Store repeat stats on this device (localStorage)">
            <input id="memoryOn" type="checkbox" checked />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Memory ON</span>
          </label>
          <label class="toggle" title="Blind A/B mode hides condition labels until reveal">
            <input id="blindOn" type="checkbox" />
            <span class="track"><span class="thumb"></span></span>
            <span class="label">Blind A/B</span>
          </label>
          <button id="btnReveal" class="yellow" disabled>Reveal</button>
        </div>
        
        <details id="studyPanel" style="margin-top:10px; border-color: rgba(255,215,64,.55);">
          <summary>Study Mode (Double-blind forced protocol)</summary>
          <div class="warn" style="margin-top:10px">
            <b>Warning:</b> Study mode locks all settings until the selected study time is over.
          </div>

          <div class="row" style="margin-top:10px">
            <label class="toggle" title="Unlock study controls">
              <input id="studyUnlock" type="checkbox" />
              <span class="track"><span class="thumb"></span></span>
              <span class="label">Unlock study controls</span>
            </label>

            <span class="pill">Study time
              <select id="studyMinutes" style="margin-left:8px">
                <option value="5">5 min</option>
                <option value="10" selected>10 min</option>
                <option value="15">15 min</option>
                <option value="20">20 min</option>
              </select>
            </span>

            <span class="pill">Block length
              <select id="studyBlock" style="margin-left:8px">
                <option value="30">30s</option>
                <option value="45" selected>45s</option>
                <option value="60">60s</option>
              </select>
            </span>

            <button id="btnStartStudy" class="yellow" disabled>Start Study</button>
            <button id="btnStopStudy" class="yellow" disabled>Stop Study</button>

            <span class="pill">Condition: <span id="studyCond">—</span></span>
            <span class="pill">Time left: <span id="studyLeft">—</span></span>
          </div>

          <div class="small" style="margin-top:10px">
            <b>A (control):</b> Normal Speech (no shift).<br>
            <b>B (experimental):</b> Scan+Shift targets 12k–18k (internal), Voting enabled (only during B).<br>
            Output labels are hidden as <b>[SAMPLE]</b> until Reveal.
          </div>
        </details>

        <div class="small" style="margin-top:10px">
          <b>Memory dashboard</b> shows top repeating phrases across sessions on this device (bands + dates).
          Blind A/B hides whether outputs are from NORMAL vs SCAN+VOTE until you press Reveal.
        </div>
        <textarea id="memDash" placeholder="(memory dashboard)"></textarea>

        <textarea id="log" placeholder="(debug log)"></textarea>
      </details>
    </div>

    <div class="card">
      <div class="row" style="justify-content: space-between">
        <div>
          <div class="small"><b>OUTPUT // WORDS ONLY</b></div>
          <div class="small">Only prints words (filters tags/captions like BLANK_AUDIO).</div>
        </div>
        <div class="row">
          <button id="btnCopy">Copy</button>
          <button id="btnClear">Clear</button>
        </div>
      </div>

      <textarea id="out" placeholder="(detected words will appear here)"></textarea>

      <div class="small" style="margin-top:10px">
        Recommendation: Calibrate Baseline in a quiet room for 5–10 seconds. Then run Normal Speech and Shift modes and compare A/B.
      </div>
    </div>
  </div>

  <!-- Overlay -->
  <div id="permOverlay" class="overlay" role="dialog" aria-modal="true">
    <div class="modal">
      <h2 id="permTitle">Help</h2>
      <p class="sub" id="permSubtitle">.</p>
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
          <b>3) Android performance</b>
          <div class="muted">Use whisper-tiny, keep Update at 1.0s. Turn off Monitor and Stability if you need speed.</div>
        </div>
        <div class="step">
          <b>4) False positives</b>
          <div class="muted">Keep VAD + Stability on. Only trust phrases that repeat across time and settings.</div>
        </div>
      </div>
      <div class="actions">
        <button id="btnCloseOverlay">Close</button>
      </div>
    </div>
  </div>

  <script type="module">
    import { pipeline, env } from "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2";

    const $ = (id) => document.getElementById(id);

    // Buttons
    const btnStart = $("btnStart");
    const btnStop = $("btnStop");
    const btnLoadModel = $("btnLoadModel");
    const btnHelp = $("btnHelp");
    const btnBaseline = $("btnBaseline");
    const btnInstall = $("btnInstall");

    const btnCopy = $("btnCopy");
    const btnClear = $("btnClear");

    const btnMarkA = $("btnMarkA");
    const btnMarkB = $("btnMarkB");
    const btnCompare = $("btnCompare");
    const btnExportJson = $("btnExportJson");
    const btnExportWav = $("btnExportWav");
    const btnMemRefresh = $("btnMemRefresh");
    const btnMemClear = $("btnMemClear");
    const memoryOn = $("memoryOn");
    const blindOn = $("blindOn");
    const btnReveal = $("btnReveal");
    const memDash = $("memDash");
    const studyPanel = $("studyPanel");
    const studyUnlock = $("studyUnlock");
    const studyMinutes = $("studyMinutes");
    const studyBlock = $("studyBlock");
    const btnStartStudy = $("btnStartStudy");
    const btnStopStudy = $("btnStopStudy");
    const studyCond = $("studyCond");
    const studyLeft = $("studyLeft");
    const btnScanToggle = $("btnScanToggle");
    const btnLoadModel2 = $("btnLoadModel2");
    const voteOn = $("voteOn");
    const voteOnlyScan = $("voteOnlyScan");
    const scoreOn = $("scoreOn");
    const scanTargetsOnly = $("scanTargetsOnly");
    const scanMinHz = $("scanMinHz");
    const scanMaxHz = $("scanMaxHz");

    // UI controls
    const modelSel = $("modelSel");
    const translateOn = $("translateOn");

    const modeNormal = $("modeNormal");
    const modeShift = $("modeShift");

    const voiceOn = $("voiceOn");
    const monitorOn = $("monitorOn");

    const shiftPreset = $("shiftPreset");
    const bpCenter = $("bpCenter");
    const bpCenterLabel = $("bpCenterLabel");
    const bpQ = $("bpQ");
    const bpQLabel = $("bpQLabel");
    const notchOn = $("notchOn");

    const winSec = $("winSec");
    const winSecLabel = $("winSecLabel");
    const updSec = $("updSec");
    const updSecLabel = $("updSecLabel");

    const vadOn = $("vadOn");
    const stableOn = $("stableOn");
    const dedupeOn = $("dedupeOn");

    // Output areas
    const out = $("out");
    const log = $("log");
    const clipInfo = $("clipInfo");

    // Indicators
    const statusEl = $("status");
    const dotModel = $("dotModel");
    const dotMic = $("dotMic");
    const dotVad = $("dotVad");
    const modelState = $("modelState");
    const micState = $("micState");
    const vadState = $("vadState");
    const entVal = $("entVal");
    const formVal = $("formVal");
    const lvlDb = $("lvlDb");
    const vuFill = $("vuFill");

    // Readouts
    const srEl = $("sr");
    const nyEl = $("ny");
    const pkEl = $("pk");
    const floorDbEl = $("floorDb");

    // Canvases
    const spec = $("spec");
    const specCtx = spec.getContext("2d");
    const specgram = $("specgram");
    const gramCtx = specgram.getContext("2d");

    // Overlay
    const overlay = $("permOverlay");
    const overlayTitle = $("permTitle");
    const overlaySubtitle = $("permSubtitle");
    const overlayErr = $("permErrorBox");
    const btnCloseOverlay = $("btnCloseOverlay");

    // ====== State ======
    let audioCtx = null;
    let stream = null;
    let source = null;
    let analyser = null;
    let freqData = null;
    let timeData = null;

    let captureNode = null;

    // monitor chain for shifted audio
    let bpFilter = null;
    let notch1 = null; let notch2 = null; let notch3 = null; let notch4 = null;
    let monitorGain = null;
    let shifter = null; // ScriptProcessor for monitoring shift

    // ring buffer (raw mic)
    let rb = null, rbSize=0, rbWrite=0, rbFilled=0;

    // last clip (raw PCM) around a detection
    let lastClipPcm = null;
    let lastClipSr = 48000;
    let lastClipMeta = null;

    // baseline/noise floor calibration
    let floorDb = null; // dBFS baseline
    let baselineSamples = [];

    // ASR
    let asr = null;
    let asr2 = null;
    let model2Loaded = false;
    let loadedModelId2 = null;
    let modelLoaded = false;
    let loadedModelId = null;
    let busy = false;

    // inference loop
    let inferTimer = null;

    // stability / dedupe memory
    let lastEmitted = "";
    let prevCandidate = "";
    let prevCandidateTime = 0;

    // session log for export
    const session = {
      started_at: new Date().toISOString(),
      device_hint: navigator.userAgent,
      settings: {},
      events: [],
      ab: { A: [], B: [] },
      baseline_dbfs: null,
    };

    // ====== Cross-session Memory (localStorage) ======
    const SESSION_ID = (crypto?.randomUUID ? crypto.randomUUID() : (Date.now().toString(36) + Math.random().toString(36).slice(2)));
    const MEM_KEY = "ultra_listener_memory_v1";

    function loadMemory(){
      try{
        const raw = localStorage.getItem(MEM_KEY);
        if (!raw) return { phrases: {}, sessions: {} };
        return JSON.parse(raw);
      }catch{
        return { phrases: {}, sessions: {} };
      }
    }
    function saveMemory(mem){
      try{ localStorage.setItem(MEM_KEY, JSON.stringify(mem)); }catch{}
    }
    function normPhrase(s){
      return String(s||"").toLowerCase().replace(/[^a-z0-9\s]/g,"").replace(/\s+/g," ").trim();
    }
    function bandBucket(centerHz){
      // bucket to nearest 100 Hz
      return String(Math.round(Number(centerHz||0)/100)*100);
    }
    function updateMemoryForDetection(text, meta){
      if (!memoryOn.checked) return;
      const mem = loadMemory();
      const key = normPhrase(text);
      if (!key) return;

      if (!mem.phrases[key]){
        mem.phrases[key] = {
          first_seen: Date.now(),
          last_seen: Date.now(),
          total: 0,
          sessions: {},
          bands: {},
          last_mode: meta.mode || "unknown",
          last_conf: meta.conf || 0,
        };
      }
      const p = mem.phrases[key];
      p.total += 1;
      p.last_seen = Date.now();
      p.last_mode = meta.mode || p.last_mode;
      p.last_conf = meta.conf ?? p.last_conf;

      p.sessions[SESSION_ID] = (p.sessions[SESSION_ID] || 0) + 1;
      // record band bucket if available
      if (meta.bandCenter){
        const b = bandBucket(meta.bandCenter);
        p.bands[b] = (p.bands[b] || 0) + 1;
      }

      mem.sessions[SESSION_ID] = { t: Date.now() };
      // cap memory to avoid huge localStorage: keep top 500 by total (prune)
      const keys = Object.keys(mem.phrases);
      if (keys.length > 600){
        keys.sort((a,b)=>mem.phrases[b].total - mem.phrases[a].total);
        const keep = new Set(keys.slice(0, 500));
        for (const k of keys.slice(500)){
          if (!keep.has(k)) delete mem.phrases[k];
        }
      }
      saveMemory(mem);
    }

    function formatDate(ts){
      const d = new Date(ts);
      return d.toLocaleString();
    }

    function memoryDashboard(){
      const mem = loadMemory();
      const entries = Object.entries(mem.phrases || {});
      entries.sort((a,b)=> (b[1].total||0) - (a[1].total||0));

      const top = entries.slice(0, 30);
      let out = "";
      out += "MEMORY DASHBOARD (this device)\n";
      out += `sessions stored: ${Object.keys(mem.sessions||{}).length}\n`;
      out += `phrases stored: ${entries.length}\n\n`;
      out += "TOP REPEATING PHRASES:\n";
      for (const [phrase, v] of top){
        const sessCount = Object.keys(v.sessions||{}).length;
        // most common band
        let topBand = "n/a";
        const bands = Object.entries(v.bands||{});
        if (bands.length){
          bands.sort((x,y)=>y[1]-x[1]);
          topBand = `${bands[0][0]}Hz (${bands[0][1]}x)`;
        }
        out += `• ${v.total}x / ${sessCount} sessions  | band: ${topBand}\n`;
        out += `  "${phrase}"\n`;
        out += `  last: ${formatDate(v.last_seen)}  first: ${formatDate(v.first_seen)}\n`;
      }
      memDash.value = out;
      memDash.scrollTop = 0;
    }

    function clearMemory(){
      try{ localStorage.removeItem(MEM_KEY); }catch{}
      memDash.value = "Memory cleared.\n";
    }

    // ====== Blind A/B mode ======
    // When enabled, the app hides whether a line came from NORMAL or SCAN+VOTE.
    // It stores hidden labels and reveals them later.
    let blindReveal = false;
    const blindMap = {
      // lineId -> actualTag
      lines: {}
    };
    function blindTag(actualTag){
      if (!blindOn.checked) return actualTag;
      // hide until reveal
      if (blindReveal) return actualTag;
      return "[SAMPLE]";
    }
    function setBlindState(on){
      blindReveal = false;
      blindMap.lines = {};
      btnReveal.disabled = !on;
      btnReveal.textContent = "Reveal";
    }

    // ====== Double-blind forced protocol (Study Mode) ======
    let studyActive = false;
    let studyEndAt = 0;
    let studyTimer = null;
    let blockTimer = null;
    let currentCond = null; // 'A' or 'B'
    let lockedControls = [];

    function setStudyUnlocked(unlocked){
      if (unlocked){
        studyPanel.classList.add("unlocked");
        btnStartStudy.disabled = false;
      } else {
        studyPanel.classList.remove("unlocked");
        btnStartStudy.disabled = true;
      }
      // stop study if user locks it back while running
      if (!unlocked && studyActive) stopStudy();
    }

    function lockSettings(){
      // Lock all interactive settings (controls + mode toggles) until study ends
      const ids = [
        "modelSel","translateOn","modeNormal","modeShift","voiceOn","monitorOn","shiftPreset","bpCenter","bpQ",
        "notchOn","winSec","updSec","vadOn","stableOn","dedupeOn","scanTargetsOnly","scanMinHz","scanMaxHz",
        "voteOn","voteOnlyScan","scoreOn","btnScanToggle","btnLoadModel2","btnBaseline","btnLoadModel","btnStart","btnStop","btnHelp"
      ];
      lockedControls = [];
      for (const id of ids){
        const el = document.getElementById(id);
        if (!el) continue;
        lockedControls.push({ el, disabled: el.disabled });
        el.disabled = true;
      }
      // Keep Stop Study enabled
      btnStopStudy.disabled = false;
    }

    function unlockSettings(){
      for (const item of lockedControls){
        try{ item.el.disabled = item.disabled; }catch{}
      }
      lockedControls = [];
      btnStopStudy.disabled = true;
    }

    function applyCondition(cond){
      currentCond = cond;
      // Hide actual condition indicator on screen (double-blind): show em dash.
      studyCond.textContent = "HIDDEN";
      // Internally apply: A = normal, no scan/vote. B = shift+scan-range+vote.
      if (cond === "A"){
        // control
        // force internal flags via variables, not UI. We'll set a global override.
        studyOverrides = {
          mode: "normal",
          vote: false,
          scan: false,
          bandMin: null,
          bandMax: null
        };
      } else {
        // experimental
        const minHz = 12000;
        const maxHz = 18000;
        studyOverrides = {
          mode: "shift",
          vote: true,
          scan: true,
          bandMin: minHz,
          bandMax: maxHz
        };
      }
      session.events.push({ t: Date.now(), type:"study_block", cond, overrides: studyOverrides });
    }

    let studyOverrides = null;

    function startRandomizedBlocks(blockSec){
      if (blockTimer) clearInterval(blockTimer);
      // Randomize blocks: swap condition each block in random order but roughly balanced
      // We'll generate a simple alternation with random flips.
      // Start with random condition
      applyCondition(Math.random() < 0.5 ? "A" : "B");
      blockTimer = setInterval(() => {
        if (!studyActive) return;
        // flip most of the time, occasionally repeat
        const flip = Math.random() < 0.75;
        let next = currentCond;
        if (flip) next = (currentCond === "A") ? "B" : "A";
        applyCondition(next);
      }, blockSec * 1000);
    }

    function startStudy(){
      if (!audioCtx || !rb){
        showOverlay({ title:"Start mic first", subtitle:"Study mode requires microphone running and model loaded." });
        return;
      }
      if (!modelLoaded){
        showOverlay({ title:"Load model first", subtitle:"Click Load AI Model before starting study." });
        return;
      }
      // Force blind mode ON, and prevent reveal until study ends
      blindOn.checked = true;
      setBlindState(true);
      blindReveal = false;
      btnReveal.disabled = true;

      studyActive = true;
      const mins = Number(studyMinutes.value || 10);
      const blockSec = Number(studyBlock.value || 45);
      studyEndAt = Date.now() + mins * 60 * 1000;

      // Lock everything
      lockSettings();

      // Start blocks
      startRandomizedBlocks(blockSec);

      // Tick timer
      if (studyTimer) clearInterval(studyTimer);
      studyTimer = setInterval(() => {
        const left = Math.max(0, studyEndAt - Date.now());
        const s = Math.ceil(left/1000);
        const mm = Math.floor(s/60);
        const ss = String(s % 60).padStart(2,"0");
        studyLeft.textContent = `${mm}:${ss}`;
        if (left <= 0){
          stopStudy(true);
        }
      }, 500);

      btnStartStudy.disabled = true;
      btnStopStudy.disabled = false;
      setStatus("study running");
      session.events.push({ t: Date.now(), type:"study_start", minutes: mins, blockSec });
      logLine(`[study] started: ${mins} min, blocks ${blockSec}s. Labels hidden until end.`);
    }

    function stopStudy(auto=false){
      if (!studyActive) return;
      studyActive = false;

      if (studyTimer) { clearInterval(studyTimer); studyTimer = null; }
      if (blockTimer) { clearInterval(blockTimer); blockTimer = null; }

      unlockSettings();

      // Allow reveal now
      btnReveal.disabled = false;
      btnReveal.textContent = "Reveal";

      studyCond.textContent = "—";
      studyLeft.textContent = "—";
      studyOverrides = null;

      btnStartStudy.disabled = !studyUnlock.checked;
      btnStopStudy.disabled = true;

      setStatus("listening");
      session.events.push({ t: Date.now(), type:"study_stop", auto });
      logLine(auto ? "[study] finished. You can now press Reveal." : "[study] stopped early. You can now press Reveal.");
      showOverlay({ title:"Study complete", subtitle:"Study mode ended. Press Reveal to see which condition produced which lines." });
    }



    let currentMark = null; // 'A' | 'B' | null

    // spectrogram buffer (downsampled bins)
    let gramX = 0;
    let gramThrottle = 0;

    // Band scan automation
    let scanOnState = false;
    let scanTimer = null;
    let scanDir = 1;
    let scanCenter = 2000;
    let scanStepHz = 400;
    let scanDwellMs = 900;
    let scanBest = [];

    // ====== Helpers ======
    function setStatus(s){ statusEl.textContent = s; }
    function logLine(s){
      const prefix = log.value.length && !log.value.endsWith("\n") ? "\n" : "";
      log.value += prefix + s;
      log.scrollTop = log.scrollHeight;
    }
    function appendWords(s){
      const prefix = out.value.length && !out.value.endsWith("\n") ? "\n" : "";
      out.value += prefix + s;
      out.scrollTop = out.scrollHeight;
    }
    function showOverlay({title, subtitle, errorHtml}={}){
      overlayTitle.textContent = title || "Help";
      overlaySubtitle.textContent = subtitle || "";
      if (errorHtml){
        overlayErr.style.display = "block";
        overlayErr.innerHTML = errorHtml;
      } else {
        overlayErr.style.display = "none";
        overlayErr.textContent = "";
      }
      overlay.classList.add("show");
    }
    function hideOverlay(){ overlay.classList.remove("show"); overlayErr.style.display="none"; overlayErr.textContent=""; }

    function environmentChecks(){
      const isSecure = window.isSecureContext || location.hostname === "localhost";
      const isFile = location.protocol === "file:";
      const isGithubBlob = location.hostname === "github.com" && location.pathname.includes("/blob/");
      const msgs = [];
      if (isFile) msgs.push("Opened as file:// — mic is usually blocked. Use GitHub Pages (https://) or localhost.");
      if (isGithubBlob) msgs.push("github.com blob view — mic will not work. Open the github.io Pages URL.");
      if (!isSecure) msgs.push("Not a secure context — mic requires https:// or http://localhost.");
      const banner = $("envBanner");
      if (msgs.length){
        banner.classList.add("show");
        banner.innerHTML = "<b>HEADS UP</b><br>" + msgs.map(m => "• " + m).join("<br>");
      } else banner.classList.remove("show");
    }

    function maxAbs(pcm){
      let m=0;
      for (let i=0;i<pcm.length;i++){
        const a = Math.abs(pcm[i]);
        if (a>m) m=a;
      }
      return m;
    }

    function dbfsFromTimeDomainByte(arr){
      let sumSq=0;
      for (let i=0;i<arr.length;i++){
        const v = (arr[i]-128)/128;
        sumSq += v*v;
      }
      const rms = Math.sqrt(sumSq/arr.length);
      if (rms <= 1e-9) return "-inf";
      return (20*Math.log10(rms)).toFixed(1);
    }

    function modelIsEnglishOnly(modelId){ return String(modelId||"").toLowerCase().includes(".en"); }

    function requireMultilingualForTranslate(){
      const modelId = modelSel.value;
      if (translateOn.checked && modelIsEnglishOnly(modelId)){
        showOverlay({
          title:"Translation needs multilingual model",
          subtitle:"Choose whisper-tiny (multilingual).",
          errorHtml:"You selected an English-only model (.en). Select <b>whisper-tiny</b> and reload to load it."
        });
        translateOn.checked = false;
        return false;
      }
      return true;
    }

    // ====== Words-only cleaning (aggressive) ======
    const NON_WORD_CUES = [
      "blank_audio","mus_audio","no_audio","music",
      "wind","wind howling","howling","static","buzz","hiss","hum",
      "sigh","sighs","sniff","sniffling","snore","snoring","cough","coughing",
      "laugh","laughter","applause","clapping","silence","background noise","noise",
      "crying","sobbing","yawn","yawning","clears throat","lip smack"
    ];
    function looksLikeCue(s){
      const raw = String(s||"").trim();
      const t = raw.toLowerCase();
      if (!t) return true;
      if (/^[A-Z0-9_]+$/.test(raw) && raw.length >= 4) return true;
      if (t.includes("blank_audio") || t.includes("mus_audio") || t.includes("no_audio")) return true;
      if (t.startsWith("sound of ") || t.startsWith("sounds of ")) return true;
      const letters = (t.match(/[a-z]/g)||[]).length;
      if (letters===0) return true;
      for (const cue of NON_WORD_CUES){
        if (t===cue) return true;
        if (t.includes(cue) && t.length <= cue.length+14) return true;
      }
      if (t.split(/\s+/).length <= 3 && /^(wind|door|rain|thunder|footsteps|breathing|snoring|sigh|sniff|music|static|silence)\b/.test(t)) return true;
      return false;
    }
    function cleanTranscript(raw){
      if (!raw) return "";
      let t = String(raw);
      t = t.replace(/[♪♫]+/g, " ");
      t = t.replace(/\[([^\]]+)\]/g, (m, inner) => looksLikeCue(inner) ? " " : m);
      t = t.replace(/\(([^\)]+)\)/g, (m, inner) => looksLikeCue(inner) ? " " : m);
      t = t.replace(/\b(BLANK_AUDIO|MUS_AUDIO|NO_AUDIO|MUSIC)\b/gi, " ");
      if (looksLikeCue(t.trim())) return "";
      t = t.replace(/\s+/g, " ").trim();
      if (!/[A-Za-z]/.test(t)) return "";
      if (/\b(blank_audio|mus_audio|no_audio|music)\b/i.test(t)) return "";
      return t;
    }

    // ====== Similarity for stability rule ======
    function normText(s){ return String(s||"").toLowerCase().replace(/[^a-z0-9\s]/g,"").replace(/\s+/g," ").trim(); }
    function similarity(a,b){
      a = normText(a); b = normText(b);
      if (!a || !b) return 0;
      if (a===b) return 1;
      // simple token overlap
      const A = new Set(a.split(" ")), B = new Set(b.split(" "));
      let inter=0;
      for (const x of A) if (B.has(x)) inter++;
      const union = A.size + B.size - inter;
      return union ? inter/union : 0;
    }

    // ====== Confidence badge (entropy + formant + vote agreement) ======
    function clamp01(x){ return Math.max(0, Math.min(1, x)); }

    function confidenceBadge(entropyNorm, formantNorm, agreeNorm){
      // entropyNorm in [0..1] (higher=noisier). formantNorm [0..1] (higher=speech-like). agreeNorm [0..1]
      const conf = clamp01(0.45*clamp01(formantNorm) + 0.35*clamp01(1 - entropyNorm) + 0.20*clamp01(agreeNorm));
      let label = "LOW";
      if (conf >= 0.75) label = "HIGH";
      else if (conf >= 0.55) label = "MED";
      return { conf, label };
    }



    // ====== Ring buffer ======
    function rbInit(sampleRate){
      rbSize = Math.max(1, Math.floor(sampleRate * 12)); // keep 12s
      rb = new Float32Array(rbSize);
      rbWrite = 0; rbFilled = 0;
    }
    function rbPush(block){
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
      if (start + need <= rbSize) outArr.set(rb.subarray(start, start+need));
      else {
        const firstLen = rbSize - start;
        outArr.set(rb.subarray(start), 0);
        outArr.set(rb.subarray(0, need-firstLen), firstLen);
      }
      return outArr;
    }
    function rbGetWindowCentered(secondsBefore, secondsAfter, sampleRate){
      // clip around "now": last (before+after) seconds, with detection assumed near end of before
      const total = secondsBefore + secondsAfter;
      return rbGetLast(total, sampleRate);
    }

    // ====== Band isolate + shift ======
    function applyBandpass(pcm, sampleRate, centerHz, Q){
      // simple biquad IIR bandpass (direct form I) - single-pass
      // coefficients from RBJ cookbook
      const w0 = 2*Math.PI*centerHz/sampleRate;
      const alpha = Math.sin(w0)/(2*Q);
      const b0 = alpha, b1 = 0, b2 = -alpha;
      const a0 = 1 + alpha, a1 = -2*Math.cos(w0), a2 = 1 - alpha;
      const out = new Float32Array(pcm.length);
      let x1=0,x2=0,y1=0,y2=0;
      for (let i=0;i<pcm.length;i++){
        const x0 = pcm[i];
        const y0 = (b0/a0)*x0 + (b1/a0)*x1 + (b2/a0)*x2 - (a1/a0)*y1 - (a2/a0)*y2;
        out[i] = y0;
        x2=x1; x1=x0; y2=y1; y1=y0;
      }
      return out;
    }
    let heteroPhase = 0;
    function applyHeterodyne(pcm, sampleRate, shiftHzVal){
      const out = new Float32Array(pcm.length);
      const twoPi = 2*Math.PI;
      let ph = heteroPhase;
      const inc = twoPi * shiftHzVal / sampleRate;
      for (let i=0;i<pcm.length;i++){
        out[i] = pcm[i] * Math.cos(ph);
        ph += inc;
        if (ph > 1e9) ph = ph % twoPi;
      }
      heteroPhase = ph;
      return out;
    }

    // ====== VAD-lite ======
    function zcr(pcm){
      let z=0;
      for (let i=1;i<pcm.length;i++){
        const a=pcm[i-1], b=pcm[i];
        if ((a>=0 && b<0) || (a<0 && b>=0)) z++;
      }
      return z / pcm.length;
    }
    function bandEnergy(pcm, sampleRate, loHz, hiHz){
      // very cheap: goertzel-ish not feasible; use biquad bandpass then RMS as proxy
      const center = Math.sqrt(loHz*hiHz);
      const Q = center / (hiHz - loHz);
      const filtered = applyBandpass(pcm, sampleRate, center, Math.max(2, Math.min(18, Q)));
      let sum=0;
      for (let i=0;i<filtered.length;i++) sum += filtered[i]*filtered[i];
      return Math.sqrt(sum/filtered.length);
    }
    function vadLite(pcm, sampleRate){
      const m = maxAbs(pcm);
      if (m < 0.0010) return { speech:false, reason:"quiet", score:0 };

      // baseline aware threshold
      if (floorDb !== null){
        // approximate max->dBFS
        const db = 20*Math.log10(Math.max(1e-9, m));
        if (db < (floorDb + 8)) return { speech:false, reason:"below floor", score:0.2 };
      }

      const z = zcr(pcm);
      // speech usually mid zcr (not too low like hum, not too high like hiss)
      const zScore = (z > 0.02 && z < 0.18) ? 1 : 0.4;

      // energy in "speech band" vs "very low" band
      const eSpeech = bandEnergy(pcm, sampleRate, 300, 3400);
      const eLow = bandEnergy(pcm, sampleRate, 40, 160);
      const ratio = eLow > 1e-9 ? (eSpeech / eLow) : eSpeech;

      const rScore = ratio > 1.6 ? 1 : 0.5;
      const score = 0.55*zScore + 0.45*rScore;

      return { speech: score > 0.72, reason:`zcr=${z.toFixed(3)} ratio=${ratio.toFixed(2)}`, score };
    }

    // ====== Export helpers ======
    function downloadBlob(blob, filename){
      const url = URL.createObjectURL(blob);
      const a = document.createElement("a");
      a.href = url; a.download = filename;
      document.body.appendChild(a); a.click(); a.remove();
      URL.revokeObjectURL(url);
    }
    function pcmToWavBlob(pcm, sampleRate){
      // 16-bit PCM WAV
      const n = pcm.length;
      const buffer = new ArrayBuffer(44 + n*2);
      const view = new DataView(buffer);
      function writeStr(off, s){ for (let i=0;i<s.length;i++) view.setUint8(off+i, s.charCodeAt(i)); }

      writeStr(0,"RIFF");
      view.setUint32(4, 36 + n*2, true);
      writeStr(8,"WAVE");
      writeStr(12,"fmt ");
      view.setUint32(16, 16, true);
      view.setUint16(20, 1, true); // PCM
      view.setUint16(22, 1, true); // mono
      view.setUint32(24, sampleRate, true);
      view.setUint32(28, sampleRate*2, true);
      view.setUint16(32, 2, true);
      view.setUint16(34, 16, true);
      writeStr(36,"data");
      view.setUint32(40, n*2, true);
      let o=44;
      for (let i=0;i<n;i++){
        let x = Math.max(-1, Math.min(1, pcm[i]));
        view.setInt16(o, (x<0 ? x*32768 : x*32767), true);
        o+=2;
      }
      return new Blob([buffer], { type: "audio/wav" });
    }

    // ====== AudioWorklet capture ======
    async function ensureCaptureWorklet(){
      const code = `
        class CaptureProcessor extends AudioWorkletProcessor {
          process(inputs, outputs, parameters) {
            const input = inputs[0];
            if (input && input[0]) {
              const ch0 = input[0];
              this.port.postMessage(ch0.slice(0));
            }
            return true;
          }
        }
        registerProcessor('capture-processor', CaptureProcessor);
      `;
      const url = URL.createObjectURL(new Blob([code], { type: "application/javascript" }));
      try{ await audioCtx.audioWorklet.addModule(url); }
      finally{ URL.revokeObjectURL(url); }
    }

    // ====== Model load ======
    async function loadModel(){
      if (modelLoaded) return;
      if (!requireMultilingualForTranslate()) return;

      btnLoadModel.disabled = true;
      dotModel.classList.add("warn");
      modelState.textContent = "LOADING…";
      setStatus("loading model…");

      env.allowLocalModels = false;
      env.useBrowserCache = true;

      const modelId = modelSel.value;

      // Android Chrome: WebGPU may be present but flaky; prefer wasm for stability unless GPU exists
      const device = (navigator.gpu ? "webgpu" : "wasm");

      try{
        asr = await pipeline("automatic-speech-recognition", modelId, { device });
        modelLoaded = true;
        loadedModelId = modelId;
        modelSel.disabled = true;

        dotModel.classList.remove("warn");
        dotModel.classList.add("on");
        modelState.textContent = "READY";
        setStatus("model loaded");
        session.events.push({ t: Date.now(), type:"model_loaded", model: modelId, device });
        logLine(`[model] loaded: ${modelId} (${device})`);
      } catch (e){
        btnLoadModel.disabled = false;
        dotModel.classList.remove("warn");
        modelState.textContent = "ERROR";
        setStatus("model load error");
        showOverlay({ title:"Model load failed", subtitle:"Could not load Whisper model.", errorHtml: String(e?.message || e) });
      }
    }

    // ====== Mic start/stop ======
    async function startMic(){
      if (!navigator.mediaDevices?.getUserMedia){
        showOverlay({ title:"Mic not supported", subtitle:"This browser doesn't support getUserMedia()." });
        return;
      }
      if (!window.isSecureContext && location.hostname !== "localhost"){
        showOverlay({ title:"Mic needs HTTPS", subtitle:"Browsers require a secure origin.", errorHtml:"Use <b>https://</b> (GitHub Pages) or <b>http://localhost</b>." });
        return;
      }
      if (location.hostname==="github.com" && location.pathname.includes("/blob/")){
        showOverlay({ title:"Open GitHub Pages", subtitle:"Mic won't work on github.com blob view.", errorHtml:"Open your <b>https://username.github.io/repo/</b> URL instead." });
        return;
      }
      if (audioCtx) return;

      setStatus("requesting mic…");
      btnStart.disabled = true;

      try{
        stream = await navigator.mediaDevices.getUserMedia({
          audio: { echoCancellation:false, noiseSuppression:false, autoGainControl:false }
        });
      } catch (e){
        btnStart.disabled = false;
        setStatus("mic error");
        showOverlay({ title:"Microphone error", subtitle:"Browser couldn't access microphone.", errorHtml: String(e?.message || e) });
        return;
      }

      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      srEl.textContent = audioCtx.sampleRate.toFixed(0);
      nyEl.textContent = (audioCtx.sampleRate/2).toFixed(0);

      rbInit(audioCtx.sampleRate);
      heteroPhase = 0;

      source = audioCtx.createMediaStreamSource(stream);

      analyser = audioCtx.createAnalyser();
      analyser.fftSize = 1024;
      analyser.smoothingTimeConstant = 0.65;
      freqData = new Uint8Array(analyser.frequencyBinCount);
      timeData = new Uint8Array(analyser.fftSize);
      source.connect(analyser);

      // Capture node
      if (audioCtx.audioWorklet){
        await ensureCaptureWorklet();
        captureNode = new AudioWorkletNode(audioCtx, "capture-processor", { numberOfInputs:1, numberOfOutputs:0, channelCount:1 });
        captureNode.port.onmessage = (ev) => { const block = ev.data; if (block && block.length) rbPush(block); };
        source.connect(captureNode);
      } else {
        const sp = audioCtx.createScriptProcessor(2048,1,1);
        sp.onaudioprocess = (e) => { rbPush(e.inputBuffer.getChannelData(0)); };
        source.connect(sp);
        const zero = audioCtx.createGain(); zero.gain.value = 0;
        sp.connect(zero); zero.connect(audioCtx.destination);
        captureNode = sp;
      }

      // Build monitor chain (muted by default)
      buildMonitorChain();

      btnStop.disabled = false;
      btnStart.disabled = true;
      dotMic.classList.add("on");
      micState.textContent = "LIVE";

      setStatus("listening");
      session.events.push({ t: Date.now(), type:"mic_started", sampleRate: audioCtx.sampleRate });
      logLine(`[mic] started @ ${audioCtx.sampleRate} Hz`);

      startInferenceLoop();
      requestAnimationFrame(drawLoop);
    }

    function stopAll(){
      stopInferenceLoop();

      try{ captureNode?.disconnect(); }catch{}
      captureNode = null;

      try{ source?.disconnect(); }catch{}
      source = null; analyser = null;

      try{ monitorGain?.disconnect(); }catch{}
      monitorGain = null; shifter = null; bpFilter = null;
      notch1 = notch2 = notch3 = notch4 = null;

      if (stream){
        for (const t of stream.getTracks()) t.stop();
        stream = null;
      }
      if (audioCtx){
        audioCtx.close();
        audioCtx = null;
      }
      rb = null; rbSize=rbWrite=rbFilled=0;

      btnStart.disabled = false;
      btnStop.disabled = true;

      dotMic.classList.remove("on");
      micState.textContent = "OFF";
      dotVad.classList.remove("on");
      vadState.textContent = "IDLE";
    entVal.textContent = "n/a";
    formVal.textContent = "n/a";

      setStatus("stopped");
      session.events.push({ t: Date.now(), type:"mic_stopped" });
      logLine("[mic] stopped");
    }

    // ====== Monitor chain (headphones) ======
    function buildMonitorChain(){
      if (!audioCtx || !source) return;
      try{ monitorGain?.disconnect(); }catch{}
      monitorGain = audioCtx.createGain();
      monitorGain.gain.value = 0; // keep silent unless monitorOn

      // notch filters (60Hz, 120, 180, 240)
      notch1 = audioCtx.createBiquadFilter(); notch1.type="notch"; notch1.frequency.value=60; notch1.Q.value=20;
      notch2 = audioCtx.createBiquadFilter(); notch2.type="notch"; notch2.frequency.value=120; notch2.Q.value=20;
      notch3 = audioCtx.createBiquadFilter(); notch3.type="notch"; notch3.frequency.value=180; notch3.Q.value=20;
      notch4 = audioCtx.createBiquadFilter(); notch4.type="notch"; notch4.frequency.value=240; notch4.Q.value=20;

      // bandpass isolate
      bpFilter = audioCtx.createBiquadFilter();
      bpFilter.type="bandpass";
      bpFilter.frequency.value = Number(bpCenter.value);
      bpFilter.Q.value = Number(bpQ.value);

      // shifter for monitor path only (script processor)
      shifter = audioCtx.createScriptProcessor(2048, 1, 1);
      let ph = 0;
      shifter.onaudioprocess = (e) => {
        const input = e.inputBuffer.getChannelData(0);
        const output = e.outputBuffer.getChannelData(0);
        const shiftHzVal = Number(shiftPreset.value);
        const sr = audioCtx.sampleRate;
        const inc = 2*Math.PI*shiftHzVal/sr;
        for (let i=0;i<input.length;i++){
          output[i] = input[i] * Math.cos(ph);
          ph += inc;
          if (ph > 1e9) ph = ph % (2*Math.PI);
        }
      };

      // Connect: source -> (optional notch chain) -> bp -> shifter -> monitorGain -> destination
      let node = source;
      if (notchOn.checked){
        node.connect(notch1); notch1.connect(notch2); notch2.connect(notch3); notch3.connect(notch4);
        node = notch4;
      }
      node.connect(bpFilter);
      bpFilter.connect(shifter);
      shifter.connect(monitorGain);
      monitorGain.connect(audioCtx.destination);

      applyMonitorToggle();
    }

    function applyMonitorToggle(){
      if (!monitorGain) return;
      if (!monitorOn.checked){
        monitorGain.gain.value = 0;
      } else {
        // very low by default for safety
        monitorGain.gain.value = 0.12;
      }
    }

    // ====== Baseline calibration ======
    function startBaseline(){
      if (!audioCtx || !rb || rbFilled < Math.floor(audioCtx.sampleRate*1.0)){
        showOverlay({ title:"Baseline needs mic", subtitle:"Start mic first, then calibrate in a quiet room." });
        return;
      }
      baselineSamples = [];
      floorDb = null;
      floorDbEl.textContent = "…";
      setStatus("calibrating…");
      logLine("[baseline] calibrating 6 seconds… keep quiet");

      const sr = audioCtx.sampleRate;
      const startT = Date.now();
      const timer = setInterval(() => {
        const pcm = rbGetLast(0.4, sr);
        const m = maxAbs(pcm);
        const db = 20*Math.log10(Math.max(1e-9, m));
        baselineSamples.push(db);
        if (Date.now() - startT > 6000){
          clearInterval(timer);
          baselineSamples.sort((a,b)=>a-b);
          // median
          floorDb = baselineSamples[Math.floor(baselineSamples.length/2)];
          session.baseline_dbfs = floorDb;
          floorDbEl.textContent = floorDb.toFixed(1);
          setStatus("listening");
          logLine(`[baseline] noise floor ≈ ${floorDb.toFixed(1)} dBFS`);
        }
      }, 400);
    }

    // ====== Inference loop (Android optimized) ======
    function stopInferenceLoop(){ if (inferTimer){ clearInterval(inferTimer); inferTimer=null; } busy=false; }
    function startInferenceLoop(){
      stopInferenceLoop();
      const intervalMs = Math.max(450, Number(updSec.value)*1000); // Android: keep >=450ms
      inferTimer = setInterval(runInferenceTick, intervalMs);
    }

    async function runInferenceTick(){
      if (!audioCtx || !rb || !modelLoaded || !asr) return;
      if (busy) return;

      const sr = audioCtx.sampleRate;
      const windowSec = Number(winSec.value);
      if (rbFilled < Math.floor(sr * 1.0)) return;

      let pcm = rbGetLast(windowSec, sr);

      // VAD gating
      if (vadOn.checked){
        const vad = vadLite(pcm, sr);
        if (vad.speech){
          dotVad.classList.add("on");
          vadState.textContent = "SPEECH";
        } else {
          dotVad.classList.remove("on");
          vadState.textContent = "IDLE";
          // skip inference if no speech-likely
          return;
        }
      }

      // blank audio guard
      const rawMax = maxAbs(pcm);
      if (rawMax < 0.0009) return;

      busy = true;
      setStatus("transcribing…");

      try{
        // pre-process: notch (optional) + shift mode with band isolate
        if (notchOn.checked){
          // quick notch via monitor chain not possible here; cheap alternative: ignore (kept for monitor + spectrum)
          // leave pcm as-is (notch is mostly for listening and display)
        }

        const effectiveModeShift = (studyActive && studyOverrides) ? (studyOverrides.mode === "shift") : modeShift.checked;
        if (effectiveModeShift){
          // isolate band then shift
          pcm = applyBandpass(pcm, sr, Number(bpCenter.value), Number(bpQ.value));
          pcm = applyHeterodyne(pcm, sr, Number(shiftPreset.value));
        }

        // Normalize quiet audio slightly
        const m = maxAbs(pcm);
        if (m > 0 && m < 0.003){
          const gain = Math.min(18, 0.05/m);
          const outN = new Float32Array(pcm.length);
          for (let i=0;i<pcm.length;i++) outN[i] = pcm[i]*gain;
          pcm = outN;
        }

        const result = await asr(pcm, {
          chunk_length_s: windowSec,
          stride_length_s: 0.2,
          return_timestamps: false,
          task: (translateOn.checked ? "translate" : undefined)
        });

        const rawText = (result?.text || "").trim();
        const cleaned = cleanTranscript(rawText);
        if (!cleaned) return;

        // Optional multi-model voting (Android warning: slower)
        let cleaned2 = "";
        const effectiveScanOn = (studyActive && studyOverrides) ? !!studyOverrides.scan : scanOnState;
        const effectiveVoting = (studyActive && studyOverrides) ? !!studyOverrides.vote : voteOn.checked;
        const effectiveVoteOnlyScan = (studyActive && studyOverrides) ? true : voteOnlyScan.checked;
        const useVoting = effectiveVoting && (!effectiveVoteOnlyScan || effectiveScanOn);
        if (useVoting) {
          if (!model2Loaded || !asr2) {
            // If voting is enabled but 2nd model not loaded, disable voting automatically
            voteOn.checked = false;
            logLine("[vote] 2nd model not loaded — voting turned off.");
          } else {
            try {
              const r2 = await asr2(pcm, {
                chunk_length_s: windowSec,
                stride_length_s: 0.2,
                return_timestamps: false,
                task: (translateOn.checked ? "translate" : undefined)
              });
              cleaned2 = cleanTranscript((r2?.text || "").trim());
            } catch (e) {
              cleaned2 = "";
            }
            // Require agreement by similarity
            const sim = similarity(cleaned, cleaned2);
            if (!cleaned2 || sim < 0.55) {
              // Do not print if models disagree
              logLine(`[vote] disagree (sim=${sim.toFixed(2)}): A="${cleaned}"  B="${cleaned2||"(empty)"}"`);
              return;
            }
          }
        }

        // stability rule (require similar phrase twice)
        let ok = true;
        if (stableOn.checked){
          const now = Date.now();
          if (!prevCandidate){
            prevCandidate = cleaned;
            prevCandidateTime = now;
            ok = false; // wait for next tick
          } else {
            const sim = similarity(prevCandidate, cleaned);
            const within = (now - prevCandidateTime) < 4500;
            if (within && sim >= 0.55){
              ok = true;
            } else {
              prevCandidate = cleaned;
              prevCandidateTime = now;
              ok = false;
            }
          }
        }

        if (!ok) return;

        // Dedupe
        if (dedupeOn.checked && cleaned === lastEmitted) return;

        lastEmitted = cleaned;

        // If scanning, record hit with current band center and scores
        if (effectiveScanOn && scoreOn.checked && audioCtx) {
          const ent = spectralEntropy(freqData);
          const fsc = formantScoreApprox(freqData, audioCtx.sampleRate);
          const composite = (0.55*fsc + 0.45*(1-ent)); // prefer formant-y and low entropy
          scanBest.push({ t: Date.now(), center: Number(bpCenter.value), ent, formant: fsc, score: composite, text: cleaned });
          scanBest.sort((a,b)=>b.score-a.score);
          scanBest = scanBest.slice(0, 30);
        }

        // Build label + confidence badge
        let tag = "[NORMAL]";
        if (effectiveScanOn && useVoting) tag = "[SCAN+VOTE]";
        // Scores
        let ent = 0.0, fsc = 0.0;
        if (scoreOn.checked && audioCtx && freqData) {
          ent = spectralEntropy(freqData);
          fsc = formantScoreApprox(freqData, audioCtx.sampleRate);
        }
        // Vote agreement score
        let agree = 0.6;
        if (voteOn.checked && (!voteOnlyScan.checked || scanOnState)) {
          agree = similarity(cleaned, cleaned2 || "");
        }
        const cb = confidenceBadge(ent, fsc, agree);
        const badge = `[CONF:${cb.label} ${cb.conf.toFixed(2)}]`;
        const lineId = (Date.now().toString(36) + Math.random().toString(36).slice(2,8));
        const displayTag = blindTag(tag);
        blindMap.lines[lineId] = { actual: tag, badge, text: cleaned, t: Date.now() };
        const line = `${displayTag} ${badge} ${cleaned}`;
        appendWords(line);
        // Update cross-session memory
        updateMemoryForDetection(cleaned, { mode: tag, bandCenter: Number(bpCenter.value||0), conf: cb.conf });
        if (voiceOn.checked){
          if ("speechSynthesis" in window){
            const u = new SpeechSynthesisUtterance(cleaned);
            u.rate=1.0; u.pitch=1.0; u.volume=1.0;
            window.speechSynthesis.cancel();
            window.speechSynthesis.speak(u);
          }
        }

        // Save last clip around detection for export/review (A/B and logging)
        const clip = rbGetWindowCentered(2.0, 1.0, sr); // 3s window
        lastClipPcm = clip;
        lastClipSr = sr;
        lastClipMeta = {
          t: Date.now(),
          mode: modeShift.checked ? "shift" : "normal",
          translate: translateOn.checked,
          model: loadedModelId,
          shiftHz: Number(shiftPreset.value),
          bandCenter: Number(bpCenter.value),
          bandQ: Number(bpQ.value),
          baseline_dbfs: floorDb,
        };
        clipInfo.textContent = `${(clip.length/sr).toFixed(1)}s @ ${sr}Hz`;

        // Session event
        const ev = {
          t: Date.now(),
          text: cleaned,
          mode: lastClipMeta.mode,
          translate: lastClipMeta.translate,
          settings: snapshotSettings()
        };
        session.events.push(ev);

        if (currentMark === "A") session.ab.A.push(ev);
        if (currentMark === "B") session.ab.B.push(ev);

      } catch (err){
        const msg = String(err?.message || err);
        if (msg.toLowerCase().includes("blank_audio")){
          // ignore
        } else {
          showOverlay({ title:"Transcription error", subtitle:"Something went wrong.", errorHtml: msg });
        }
      } finally {
        busy = false;
        setStatus("listening");
      }
    }

    function snapshotSettings(){
      return {
        mode: modeShift.checked ? "shift" : "normal",
        translate: translateOn.checked,
        shiftHz: Number(shiftPreset.value),
        bandCenter: Number(bpCenter.value),
        bandQ: Number(bpQ.value),
        notch: notchOn.checked,
        winSec: Number(winSec.value),
        updSec: Number(updSec.value),
        vad: vadOn.checked,
        stable: stableOn.checked,
        dedupe: dedupeOn.checked,
        monitor: monitorOn.checked,
        model: loadedModelId || modelSel.value,
        baseline_dbfs: floorDb
      };
    }

    
    // ====== Spectral entropy + formant-ish scoring (lightweight) ======
    function spectralEntropy(freqBytes){
      // Shannon entropy of normalized magnitude distribution (0..1), higher = flatter/noise
      let sum = 0;
      const n = freqBytes.length;
      const mags = new Float32Array(n);
      for (let i=0;i<n;i++){
        const v = freqBytes[i] / 255;
        mags[i] = v;
        sum += v;
      }
      if (sum <= 1e-9) return 0;
      let H = 0;
      for (let i=0;i<n;i++){
        const p = mags[i] / sum;
        if (p > 1e-9) H -= p * Math.log2(p);
      }
      // Normalize by log2(n)
      return H / Math.log2(n);
    }

    function formantScoreApprox(freqBytes, sampleRate){
      // Rough "speech formant" heuristic:
      // Look for energy bumps in 300–900 (F1-ish) and 900–2600 (F2-ish) vs very-low and very-high bands.
      const ny = sampleRate / 2;
      const n = freqBytes.length;
      const band = (lo, hi) => {
        const a = Math.max(0, Math.floor((lo/ny)*n));
        const b = Math.min(n-1, Math.floor((hi/ny)*n));
        let s = 0;
        for (let i=a;i<=b;i++) s += freqBytes[i]/255;
        return s / Math.max(1, (b-a+1));
      };
      const low = band(40, 160);
      const f1  = band(300, 900);
      const f2  = band(900, 2600);
      const high= band(6000, 12000);

      // Speech-like: f1 and f2 moderate, low not dominating, high not dominating
      const score = (0.55*(f1 + f2) - 0.25*low - 0.20*high);
      // Map to 0..1-ish
      return Math.max(0, Math.min(1, (score + 0.2) / 0.8));
    }

// ====== Drawing (Android optimized) ======
    function drawLoop(){
      if (!analyser || !audioCtx) return;

      analyser.getByteFrequencyData(freqData);
      analyser.getByteTimeDomainData(timeData);

      // Indicators
      const db = dbfsFromTimeDomainByte(timeData);
      lvlDb.textContent = db + " dBFS";
      if (scoreOn.checked) {
        const ent = spectralEntropy(freqData);
        const fsc = formantScoreApprox(freqData, audioCtx.sampleRate);
        entVal.textContent = ent.toFixed(2);
        formVal.textContent = fsc.toFixed(2);
      } else {
        entVal.textContent = "n/a";
        formVal.textContent = "n/a";
      }
      let dbNum = (db === "-inf") ? -99 : Number(db);
      if (!Number.isFinite(dbNum)) dbNum = -99;
      const pct = Math.max(0, Math.min(100, ((dbNum + 60) / 50) * 100));
      vuFill.style.width = pct.toFixed(0) + "%";

      // Peak Hz
      let peakIdx=0;
      for (let i=1;i<freqData.length;i++) if (freqData[i] > freqData[peakIdx]) peakIdx=i;
      const peakHz = (peakIdx / freqData.length) * (audioCtx.sampleRate/2);
      pkEl.textContent = peakHz.toFixed(0);

      // Spectrum bars (lower-res)
      specCtx.clearRect(0,0,spec.width,spec.height);
      const w=spec.width, h=spec.height;
      const n=freqData.length;
      const step = 2; // downsample bins for speed
      const bars = Math.floor(n/step);
      const barW = w / bars;

      let bi=0;
      for (let i=0;i<n;i+=step){
        const v = Math.max(freqData[i], freqData[i+1]||0) / 255;
        const barH = v*(h-12);
        const a = 0.08 + v*0.85;
        specCtx.fillStyle = `rgba(53,255,106,${a})`;
        specCtx.fillRect(bi*barW, h-barH, barW, barH);
        bi++;
      }

      // Spectrogram (waterfall) - throttle for Android
      gramThrottle = (gramThrottle + 1) % 3; // draw every 3 frames
      if (gramThrottle === 0){
        // scroll left by 1 column (cheap) by drawing into itself
        const gw = specgram.width, gh = specgram.height;
        const img = gramCtx.getImageData(1,0, gw-1, gh);
        gramCtx.putImageData(img, 0, 0);

        // draw newest column at far right
        const col = gramCtx.createImageData(1, gh);
        // map frequency bins to pixels (log-ish)
        for (let y=0;y<gh;y++){
          const p = 1 - (y/(gh-1));
          // log mapping
          const hz = 20 * Math.pow((audioCtx.sampleRate/2)/20, p);
          const idx = Math.min(n-1, Math.max(0, Math.floor((hz/(audioCtx.sampleRate/2))*n)));
          const v = freqData[idx] / 255;
          const g = Math.floor(20 + v*235);
          const o = y*4;
          col.data[o+0]=0;
          col.data[o+1]=g;
          col.data[o+2]=0;
          col.data[o+3]=255;
        }
        gramCtx.putImageData(col, gw-1, 0);
      }

      requestAnimationFrame(drawLoop);
    }


    // ====== Manual band scan automation ======
    function updateScanParams(){
      // Android-friendly: coarse scan, moderate dwell
      scanStepHz = 500;
      scanDwellMs = 950;
      scanDir = 1;
      scanBest = [];
      // Target range
      const minHz = scanTargetsOnly.checked ? Number(scanMinHz.value || 12000) : 2000;
      const maxHz = scanTargetsOnly.checked ? Number(scanMaxHz.value || 18000) : 20000;
      session.events.push({ t: Date.now(), type:"scan_range", minHz, maxHz, targetsOnly: scanTargetsOnly.checked });
      // clamp + sanitize
      const lo = Math.max(2000, Math.min(20000, Math.min(minHz, maxHz)));
      const hi = Math.max(2000, Math.min(20000, Math.max(minHz, maxHz)));
      scanMinHz.value = String(Math.round(lo));
      scanMaxHz.value = String(Math.round(hi));
      // start near current band center but within bounds
      const cur = Math.max(lo, Math.min(hi, Number(bpCenter.value)));
      scanCenter = cur;
    }

    function startBandScan(){
      if (!audioCtx || !rb){ showOverlay({ title:"Start mic first", subtitle:"Band scan needs mic input." }); return; }
      // Force shift mode during scan
      modeShift.checked = true;
      modeNormal.checked = false;
      updateScanParams();
      scanOnState = true;
      btnScanToggle.textContent = "Stop Band Scan";
      logLine("[scan] started (bandpass+shift). Watching for stable phrases + scores…");
      session.events.push({ t: Date.now(), type:"scan_start", settings: snapshotSettings() });

      // Sweep center frequency
      scanTimer = setInterval(() => {
        if (!scanOnState) return;
        const lo = scanTargetsOnly.checked ? Number(scanMinHz.value || 12000) : 2000;
        const hi = scanTargetsOnly.checked ? Number(scanMaxHz.value || 18000) : 20000;
        const minHz = Math.max(2000, Math.min(20000, Math.min(lo, hi)));
        const maxHz = Math.max(2000, Math.min(20000, Math.max(lo, hi)));
        // step
        scanCenter += scanDir * scanStepHz;
        if (scanCenter > maxHz){ scanCenter = maxHz; scanDir = -1; }
        if (scanCenter < minHz){ scanCenter = minHz; scanDir = 1; }

        bpCenter.value = String(Math.round(scanCenter));
        bpCenterLabel.textContent = bpCenter.value;
        if (bpFilter) bpFilter.frequency.value = Number(bpCenter.value);

        // adjust Q slightly during scan
        bpQ.value = String(Math.max(8, Math.min(18, Number(bpQ.value))));
        bpQLabel.textContent = bpQ.value;
        if (bpFilter) bpFilter.Q.value = Number(bpQ.value);

        setStatus("scanning…");
      }, scanDwellMs);
    }

    function stopBandScan(){
      scanOnState = false;
      if (scanTimer){ clearInterval(scanTimer); scanTimer = null; }
      btnScanToggle.textContent = "Start Band Scan";
      setStatus("listening");
      session.events.push({ t: Date.now(), type:"scan_stop", settings: snapshotSettings(), best: scanBest.slice(0,10) });
      logLine("[scan] stopped.");
      if (scanBest.length){
        logLine("[scan] top hits (rough):");
        for (const item of scanBest.slice(0,8)){
          logLine(`  ${item.score.toFixed(2)} @ ${item.center}Hz  —  ${item.text}`);
        }
      }
    }

    // ====== A/B tools ======
    function mark(label){
      currentMark = label;
      session.events.push({ t: Date.now(), type:"mark", label, settings: snapshotSettings() });
      logLine(`[AB] Mark ${label} active`);
      setStatus(`mark ${label}`);
      setTimeout(() => setStatus("listening"), 650);
    }
    function compareAB(){
      const A = session.ab.A.map(e => e.text);
      const B = session.ab.B.map(e => e.text);

      function summarize(list){
        const counts = new Map();
        for (const t of list){
          const k = normText(t);
          if (!k) continue;
          counts.set(k, (counts.get(k)||0)+1);
        }
        const arr = [...counts.entries()].sort((a,b)=>b[1]-a[1]).slice(0,12);
        return arr.map(([k,c])=>`${c}×  ${k}`).join("\n");
      }

      const aSum = summarize(A);
      const bSum = summarize(B);

      logLine("\n=== A/B COMPARE ===");
      logLine("[A] top phrases:\n" + (aSum || "(none)"));
      logLine("\n[B] top phrases:\n" + (bSum || "(none)"));
      logLine("===================\n");
    }

    // ====== Exports ======
    function exportJson(){
      session.settings = snapshotSettings();
      const blob = new Blob([JSON.stringify(session, null, 2)], { type:"application/json" });
      downloadBlob(blob, `ultra_listener_session_${Date.now()}.json`);
    }
    function exportWav(){
      if (!lastClipPcm){
        showOverlay({ title:"No clip yet", subtitle:"Wait until a phrase is detected, then export." });
        return;
      }
      const blob = pcmToWavBlob(lastClipPcm, lastClipSr);
      downloadBlob(blob, `ultra_listener_clip_${Date.now()}.wav`);
    }

    // ====== UI wiring ======
    btnStart.addEventListener("click", startMic);
    btnStop.addEventListener("click", stopAll);
    btnLoadModel.addEventListener("click", loadModel);

    async function loadSecondModel(){
      if (model2Loaded) { logLine("[model2] already loaded."); return; }
      if (!modelLoaded) { showOverlay({ title:"Load primary model first", subtitle:"Load AI model, then load 2nd model." }); return; }
      btnLoadModel2.disabled = true;
      logLine("[model2] loading… (this may lag on Android)");
      const primary = loadedModelId || modelSel.value;
      // Choose a second model that differs a bit. If primary is multilingual, use tiny.en as a second opinion; else use multilingual tiny.
      const second = primary.includes(".en") ? "Xenova/whisper-tiny" : "Xenova/whisper-tiny.en";
      const device = (navigator.gpu ? "webgpu" : "wasm");
      try {
        asr2 = await pipeline("automatic-speech-recognition", second, { device });
        model2Loaded = true;
        loadedModelId2 = second;
        logLine(`[model2] loaded: ${second} (${device})`);
        session.events.push({ t: Date.now(), type:"model2_loaded", model: second, device });
      } catch (e) {
        btnLoadModel2.disabled = false;
        showOverlay({ title:"2nd model load failed", subtitle:"Could not load second model.", errorHtml: String(e?.message || e) });
        logLine("[model2] failed to load.");
        return;
      }
      btnLoadModel2.disabled = false;
    }

    btnHelp.addEventListener("click", () => showOverlay({ title:"Help", subtitle:"Quick checklist + Android tuning tips." }));
    btnCloseOverlay.addEventListener("click", hideOverlay);

    btnBaseline.addEventListener("click", startBaseline);

    btnCopy.addEventListener("click", async () => {
      try{ await navigator.clipboard.writeText(out.value || ""); }
      catch{ showOverlay({ title:"Copy failed", subtitle:"Clipboard blocked.", errorHtml:"Manually select & copy." }); }
    });
    btnClear.addEventListener("click", () => { out.value=""; lastEmitted=""; prevCandidate=""; });

    btnMarkA.addEventListener("click", () => mark("A"));
    btnMarkB.addEventListener("click", () => mark("B"));
    btnCompare.addEventListener("click", compareAB);
    btnExportJson.addEventListener("click", exportJson);
    btnExportWav.addEventListener("click", exportWav);

    // Memory + blind UI
    btnMemRefresh.addEventListener("click", memoryDashboard);
    btnMemClear.addEventListener("click", clearMemory);

    blindOn.addEventListener("change", () => {
      setBlindState(blindOn.checked);
      if (blindOn.checked){
        logLine("[blind] ON — labels hidden until Reveal.");
      } else {
        logLine("[blind] OFF.");
      }
    });

    
    // Study mode UI
    studyUnlock.addEventListener("change", () => {
      setStudyUnlocked(studyUnlock.checked);
    });

    btnStartStudy.addEventListener("click", () => {
      if (!studyUnlock.checked) return;
      startStudy();
    });

    btnStopStudy.addEventListener("click", () => {
      stopStudy(false);
    });

btnReveal.addEventListener("click", () => {
      if (!blindOn.checked) return;
      blindReveal = true;
      btnReveal.textContent = "Revealed";
      btnReveal.disabled = true;

      // Print a reveal report in the log
      logLine("\n=== BLIND REVEAL ===");
      const items = Object.values(blindMap.lines).sort((a,b)=>a.t-b.t);
      for (const it of items.slice(-40)){
        logLine(`${it.actual} ${it.badge} ${it.text}`);
      }
      logLine("====================\n");
      showOverlay({ title:"Revealed", subtitle:"Blind labels are now revealed in the Debug Log." });
    });



    btnLoadModel2.addEventListener("click", loadSecondModel);

    btnScanToggle.addEventListener("click", () => {
      if (!scanOnState) startBandScan();
      else stopBandScan();
    });



    // Controls
    shiftPreset.addEventListener("change", () => { /* affects shift */ });
    bpCenter.addEventListener("input", () => { bpCenterLabel.textContent = bpCenter.value; if (bpFilter) bpFilter.frequency.value = Number(bpCenter.value); });
    bpQ.addEventListener("input", () => { bpQLabel.textContent = bpQ.value; if (bpFilter) bpFilter.Q.value = Number(bpQ.value); });

    function sanitizeScanRange(){
      const lo = Number(scanMinHz.value || 12000);
      const hi = Number(scanMaxHz.value || 18000);
      const minHz = Math.max(2000, Math.min(20000, Math.min(lo, hi)));
      const maxHz = Math.max(2000, Math.min(20000, Math.max(lo, hi)));
      scanMinHz.value = String(Math.round(minHz));
      scanMaxHz.value = String(Math.round(maxHz));
    }
    scanMinHz.addEventListener("change", sanitizeScanRange);
    scanMaxHz.addEventListener("change", sanitizeScanRange);
    scanTargetsOnly.addEventListener("change", () => { sanitizeScanRange(); });



    notchOn.addEventListener("change", () => { if (audioCtx) buildMonitorChain(); });
    monitorOn.addEventListener("change", () => { applyMonitorToggle(); });

    winSec.addEventListener("input", () => { winSecLabel.textContent = Number(winSec.value).toFixed(1); if (audioCtx) startInferenceLoop(); });
    updSec.addEventListener("input", () => { updSecLabel.textContent = Number(updSec.value).toFixed(1); if (audioCtx) startInferenceLoop(); });

    modeNormal.addEventListener("change", () => { lastEmitted=""; prevCandidate=""; });
    modeShift.addEventListener("change", () => { lastEmitted=""; prevCandidate=""; });

    translateOn.addEventListener("change", () => {
      if (translateOn.checked && modelIsEnglishOnly(modelSel.value)){
        showOverlay({ title:"Need multilingual model", subtitle:"Translation requires whisper-tiny (multilingual)." });
        translateOn.checked = false;
      }
      lastEmitted=""; prevCandidate="";
    });

    modelSel.addEventListener("change", () => {
      if (modelLoaded && loadedModelId){
        // lock: revert, no popup
        modelSel.value = loadedModelId;
        setStatus("model locked");
        setTimeout(() => setStatus("listening"), 650);
      }
    });


    // ====== PWA (install button + offline cache) ======
    let deferredInstallPrompt = null;

    function setupPwa(){
      // Create a manifest on the fly (single-file build)
      const manifest = {
        name: "Ultra Listener",
        short_name: "UltraListener",
        start_url: "./",
        display: "standalone",
        background_color: "#000000",
        theme_color: "#000000",
        icons: [
          {
            // Simple inline SVG icon (green terminal)
            src: "data:image/svg+xml;charset=utf-8," + encodeURIComponent(`
              <svg xmlns="http://www.w3.org/2000/svg" width="192" height="192" viewBox="0 0 192 192">
                <rect width="192" height="192" rx="24" fill="#000"/>
                <rect x="20" y="28" width="152" height="136" rx="14" fill="#050505" stroke="#0f3a18" stroke-width="4"/>
                <path d="M52 82 L78 96 L52 110" fill="none" stroke="#35ff6a" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/>
                <rect x="86" y="104" width="56" height="10" rx="5" fill="#35ff6a"/>
              </svg>
            `),
            sizes: "192x192",
            type: "image/svg+xml",
            purpose: "any"
          }
        ]
      };
      const manifestBlob = new Blob([JSON.stringify(manifest)], { type: "application/manifest+json" });
      const manifestUrl = URL.createObjectURL(manifestBlob);
      const link = document.createElement("link");
      link.rel = "manifest";
      link.href = manifestUrl;
      document.head.appendChild(link);

      // Minimal service worker to cache this page for offline open
      const swCode = `
        const CACHE = "ultra-listener-cache-v1";
        self.addEventListener("install", (e) => {
          e.waitUntil((async () => {
            const cache = await caches.open(CACHE);
            await cache.addAll([self.location.origin + self.location.pathname]);
            self.skipWaiting();
          })());
        });
        self.addEventListener("activate", (e) => {
          e.waitUntil(self.clients.claim());
        });
        self.addEventListener("fetch", (e) => {
          e.respondWith((async () => {
            const cache = await caches.open(CACHE);
            const cached = await cache.match(e.request, { ignoreSearch: true });
            if (cached) return cached;
            try{
              const res = await fetch(e.request);
              if (e.request.method === "GET" && res && res.status === 200) cache.put(e.request, res.clone());
              return res;
            }catch{
              return cached || Response.error();
            }
          })());
        });
      `;
      if ("serviceWorker" in navigator){
        const swUrl = URL.createObjectURL(new Blob([swCode], { type: "text/javascript" }));
        navigator.serviceWorker.register(swUrl).catch(()=>{});
      }

      window.addEventListener("beforeinstallprompt", (e) => {
        e.preventDefault();
        deferredInstallPrompt = e;
        btnInstall.disabled = false;
        btnInstall.textContent = "Install App";
      });

      btnInstall.addEventListener("click", async () => {
        if (!deferredInstallPrompt) {
          showOverlay({ title:"Install", subtitle:"If you don't see install, use Chrome menu → Add to Home screen." });
          return;
        }
        deferredInstallPrompt.prompt();
        try { await deferredInstallPrompt.userChoice; } catch {}
        deferredInstallPrompt = null;
        btnInstall.disabled = true;
        btnInstall.textContent = "Install App";
      });
    }

    // Init labels
    bpCenterLabel.textContent = bpCenter.value;
    bpQLabel.textContent = bpQ.value;
    winSecLabel.textContent = Number(winSec.value).toFixed(1);
    updSecLabel.textContent = Number(updSec.value).toFixed(1);

    modelState.textContent = "NOT LOADED";
    micState.textContent = "OFF";
    vadState.textContent = "IDLE";
    dotModel.classList.remove("on","warn");
    dotMic.classList.remove("on");
    dotVad.classList.remove("on");
    floorDbEl.textContent = "n/a";

    setStatus("idle");
    environmentChecks();
    setBlindState(false);
    setStudyUnlocked(false);

    memoryDashboard();
    setupPwa();

    // Warm hint for Android Chrome
    logLine("[tip] Android Chrome: Load model first, then Start Mic. Calibrate Baseline for best VAD gating.");
  </script>
</body>
</html>
