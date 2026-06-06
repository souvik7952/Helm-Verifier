<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Helm Verifier — README</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500&family=Geist:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #07080a;
    --surface: #0f1117;
    --surface2: #141720;
    --surface3: #1a1e2a;
    --border: #1c2030;
    --border2: #262d42;
    --text: #dde3f0;
    --text2: #7e8ba8;
    --text3: #414e6a;
    --accent: #4f7cff;
    --accent2: #7c52ff;
    --green: #1de9a2;
    --yellow: #f5c842;
    --red: #f0545a;
    --blue: #4b9eff;
    --helm: #c98bff;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Geist', system-ui, sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    font-size: 15px;
    line-height: 1.75;
    -webkit-font-smoothing: antialiased;
    padding: 48px 24px 80px;
  }

  .readme {
    max-width: 780px;
    margin: 0 auto;
  }

  /* ── Hero ── */
  .hero {
    text-align: center;
    padding: 56px 0 48px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 48px;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: .12em;
    text-transform: uppercase;
    color: var(--accent);
    background: rgba(79,124,255,.08);
    border: 1px solid rgba(79,124,255,.22);
    padding: 5px 14px;
    border-radius: 999px;
    margin-bottom: 28px;
  }
  .hero-badge::before {
    content: '';
    width: 5px; height: 5px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 6px var(--accent);
    animation: pulse 2.4s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; box-shadow: 0 0 4px var(--accent); }
    50%       { opacity: .5; box-shadow: 0 0 10px var(--accent); }
  }

  .hero-logo {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 64px; height: 64px;
    border-radius: 16px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    box-shadow: 0 0 40px rgba(79,124,255,.25), 0 0 0 1px rgba(255,255,255,.06);
    margin-bottom: 24px;
  }
  .hero-logo svg {
    width: 28px; height: 28px;
    fill: none;
    stroke: rgba(255,255,255,.95);
    stroke-width: 1.8;
    stroke-linecap: round;
    stroke-linejoin: round;
  }

  .hero h1 {
    font-size: 36px;
    font-weight: 700;
    letter-spacing: -.03em;
    color: var(--text);
    margin-bottom: 16px;
    line-height: 1.15;
  }
  .hero h1 span {
    background: linear-gradient(135deg, var(--accent), var(--helm));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-desc {
    font-size: 16px;
    color: var(--text2);
    max-width: 560px;
    margin: 0 auto 32px;
    line-height: 1.7;
    font-weight: 300;
  }

  /* Badge pills */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    font-family: var(--mono);
    font-size: 10.5px;
    font-weight: 500;
    padding: 4px 10px;
    border-radius: 6px;
    border: 1px solid;
    letter-spacing: .04em;
  }
  .badge-green  { color: var(--green);  background: rgba(29,233,162,.07);  border-color: rgba(29,233,162,.2); }
  .badge-blue   { color: var(--blue);   background: rgba(75,158,255,.07);  border-color: rgba(75,158,255,.2); }
  .badge-yellow { color: var(--yellow); background: rgba(245,200,66,.07);  border-color: rgba(245,200,66,.2); }
  .badge-helm   { color: var(--helm);   background: rgba(201,139,255,.07); border-color: rgba(201,139,255,.2); }
  .badge-gray   { color: var(--text2);  background: rgba(126,139,168,.07); border-color: rgba(126,139,168,.2); }

  /* ── Section headings ── */
  h2 {
    font-size: 13px;
    font-weight: 600;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--text3);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  h2::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  section { margin-bottom: 52px; }

  p {
    color: var(--text2);
    margin-bottom: 14px;
    font-weight: 300;
  }
  p strong { color: var(--text); font-weight: 500; }

  /* ── Feature grid ── */
  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 12px;
  }

  .feature-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 18px 16px;
    transition: border-color .2s ease, box-shadow .2s ease;
  }
  .feature-card:hover {
    border-color: var(--border2);
    box-shadow: 0 4px 24px rgba(0,0,0,.35);
  }

  .feature-icon {
    width: 34px; height: 34px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 12px;
    font-size: 16px;
  }
  .feature-icon.blue   { background: rgba(75,158,255,.1);  }
  .feature-icon.green  { background: rgba(29,233,162,.1);  }
  .feature-icon.yellow { background: rgba(245,200,66,.1);  }
  .feature-icon.helm   { background: rgba(201,139,255,.1); }
  .feature-icon.red    { background: rgba(240,84,90,.1);   }
  .feature-icon.gray   { background: rgba(126,139,168,.1); }

  .feature-card h3 {
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 6px;
    letter-spacing: -.01em;
  }
  .feature-card p {
    font-size: 12.5px;
    color: var(--text2);
    line-height: 1.6;
    margin: 0;
    font-weight: 300;
  }

  /* ── How it works ── */
  .steps {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .step {
    display: flex;
    gap: 18px;
    align-items: flex-start;
    padding: 18px 0;
    border-bottom: 1px solid var(--border);
  }
  .step:last-child { border-bottom: none; }

  .step-num {
    width: 28px; height: 28px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--mono);
    font-size: 11px;
    font-weight: 600;
    color: #fff;
    flex-shrink: 0;
    margin-top: 2px;
    box-shadow: 0 0 12px rgba(79,124,255,.3);
  }

  .step-body h3 {
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 5px;
    letter-spacing: -.01em;
  }
  .step-body p {
    font-size: 13px;
    color: var(--text2);
    margin: 0;
    font-weight: 300;
    line-height: 1.6;
  }

  /* ── Tech stack table ── */
  .tech-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
  }
  .tech-table th {
    text-align: left;
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--text3);
    padding: 0 16px 10px;
    border-bottom: 1px solid var(--border);
    font-weight: 500;
  }
  .tech-table td {
    padding: 11px 16px;
    border-bottom: 1px solid var(--border);
    color: var(--text2);
    vertical-align: top;
    font-weight: 300;
  }
  .tech-table td:first-child {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent);
    white-space: nowrap;
    font-weight: 400;
  }
  .tech-table tr:last-child td { border-bottom: none; }
  .tech-table tr:hover td { background: var(--surface); }

  /* ── Constraint pills ── */
  .constraints {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .constraint {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: var(--mono);
    font-size: 11.5px;
    color: var(--text2);
    background: var(--surface);
    border: 1px solid var(--border2);
    padding: 6px 12px;
    border-radius: 6px;
  }
  .constraint::before {
    content: '✓';
    color: var(--green);
    font-size: 11px;
  }

  /* ── YAML highlight demo block ── */
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
  }
  .code-block-header {
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .code-block-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--border2);
  }
  .code-block-title {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    letter-spacing: .06em;
    margin-left: 4px;
  }
  .code-block pre {
    font-family: var(--mono);
    font-size: 12.5px;
    line-height: 1.7;
    padding: 18px 20px;
    overflow-x: auto;
    color: var(--text2);
  }
  .yk  { color: #6fa3ff; }  /* key */
  .ys  { color: #9ec8ff; }  /* string */
  .yn  { color: #f0a84a; }  /* number */
  .yb  { color: #2ed8a0; }  /* bool */
  .yc  { color: #3d4d6a; font-style: italic; } /* comment */
  .yh  { color: #c98bff; }  /* helm expr */

  /* ── Footer ── */
  .footer {
    text-align: center;
    padding-top: 40px;
    border-top: 1px solid var(--border);
    font-size: 12px;
    color: var(--text3);
    font-family: var(--mono);
    letter-spacing: .04em;
  }
  .footer a { color: var(--accent); text-decoration: none; }
  .footer a:hover { text-decoration: underline; }
</style>
</head>
<body>
<div class="readme">

  <!-- ═══════ HERO ═══════ -->
  <div class="hero">
    <div class="hero-badge">Browser-Based DevTools &nbsp;·&nbsp; Zero Dependencies</div>
    <div><div class="hero-logo">
      <svg viewBox="0 0 24 24">
        <polyline points="4,18 4,6 12,2 20,6 20,18"/>
        <line x1="4" y1="12" x2="20" y2="12"/>
        <line x1="9" y1="6" x2="9" y2="18"/>
        <line x1="15" y1="6" x2="15" y2="18"/>
      </svg>
    </div></div>
    <h1><span>Helm Verifier</span></h1>
    <p class="hero-desc">
      A self-contained, browser-based tool for validating and rendering Helm chart templates —
      no installation, no backend, no build step required.
    </p>
    <div class="badges">
      <span class="badge badge-green">✦ Zero Dependencies</span>
      <span class="badge badge-blue">Single HTML File</span>
      <span class="badge badge-helm">Helm Template Support</span>
      <span class="badge badge-yellow">Live Syntax Highlighting</span>
      <span class="badge badge-gray">Dark &amp; Light Mode</span>
    </div>
  </div>

  <!-- ═══════ OVERVIEW ═══════ -->
  <section>
    <h2>Overview</h2>
    <p>
      <strong>Helm Verifier</strong> is a fully offline, single-file HTML application designed for
      engineers who work with Kubernetes Helm charts. It provides instant feedback on template
      correctness without requiring a local Helm installation, a Kubernetes cluster, or any
      external tooling whatsoever.
    </p>
    <p>
      Simply open the file in any modern browser, paste your <strong>template YAML</strong> and
      <strong>values YAML</strong> into the respective editor panels, then hit
      <strong>Render</strong> or <strong>Verify</strong> to get immediate, color-coded output
      with detailed validation messages.
    </p>
    <p>
      Built to run on locked-down corporate laptops where only local HTML files can be
      executed — no npm, no internet, no permissions needed.
    </p>
  </section>

  <!-- ═══════ FEATURES ═══════ -->
  <section>
    <h2>Features</h2>
    <div class="feature-grid">

      <div class="feature-card">
        <div class="feature-icon blue">⚡</div>
        <h3>Instant Template Rendering</h3>
        <p>Resolves <code>.Values.*</code>, <code>.Release.*</code>, and <code>.Chart.*</code> expressions and outputs the fully rendered YAML immediately.</p>
      </div>

      <div class="feature-card">
        <div class="feature-icon green">✔</div>
        <h3>Deep Validation</h3>
        <p>Detects unclosed <code>{{ }}</code> expressions, flags missing <code>.Values</code> paths, and warns on unsupported Helm control-flow directives.</p>
      </div>

      <div class="feature-card">
        <div class="feature-icon helm">◈</div>
        <h3>Live Syntax Highlighting</h3>
        <p>All three panels — Template, Values, and Output — render real-time YAML and Helm expression syntax colouring as you type.</p>
      </div>

      <div class="feature-card">
        <div class="feature-icon yellow">⟳</div>
        <h3>Pipe Filter Support</h3>
        <p>Evaluates common Helm filters including <code>upper</code>, <code>lower</code>, <code>quote</code>, <code>trim</code>, <code>title</code>, <code>default</code>, <code>indent</code>, and more.</p>
      </div>

      <div class="feature-card">
        <div class="feature-icon gray">◐</div>
        <h3>Dark &amp; Light Mode</h3>
        <p>Toggle between a deep dark theme and a clean light theme. Both are carefully tuned for readability and YAML token contrast.</p>
      </div>

      <div class="feature-card">
        <div class="feature-icon red">↓</div>
        <h3>Copy &amp; Download Output</h3>
        <p>Copy the rendered YAML to clipboard or download it directly as <code>rendered-output.yaml</code> with a single click.</p>
      </div>

    </div>
  </section>

  <!-- ═══════ HOW IT WORKS ═══════ -->
  <section>
    <h2>How It Works</h2>
    <div class="steps">

      <div class="step">
        <div class="step-num">1</div>
        <div class="step-body">
          <h3>Paste Your Template</h3>
          <p>Enter your Helm chart template YAML — including <code>{{ .Values.* }}</code>, <code>{{ .Release.* }}</code>, pipe filters, and <code>index</code> expressions — into the left panel. Syntax highlighting activates immediately.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-num">2</div>
        <div class="step-body">
          <h3>Paste Your Values</h3>
          <p>Enter your <code>values.yaml</code> content into the centre panel. The built-in YAML parser handles nested mappings, sequences, scalars, booleans, and null types.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-num">3</div>
        <div class="step-body">
          <h3>Verify or Render</h3>
          <p><strong>Verify</strong> checks expression syntax, bracket balance, unsupported directives, and missing <code>.Values</code> keys — all reported in the Validation Console below. <strong>Render</strong> runs verification first, then substitutes all resolvable expressions and displays the final highlighted YAML.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-num">4</div>
        <div class="step-body">
          <h3>Review &amp; Export</h3>
          <p>Inspect the rendered output with full YAML syntax highlighting. Copy it to your clipboard or download it as a <code>.yaml</code> file ready for <code>kubectl apply</code>.</p>
        </div>
      </div>

    </div>
  </section>

  <!-- ═══════ SYNTAX HIGHLIGHTING DEMO ═══════ -->
  <section>
    <h2>Syntax Highlighting</h2>
    <p>All editor panels render tokens using a layered backdrop-highlight technique — a transparent <code>&lt;textarea&gt;</code> overlaid on a syntax-coloured <code>&lt;div&gt;</code> that scrolls in perfect sync.</p>
    <div class="code-block">
      <div class="code-block-header">
        <div class="code-block-dot"></div>
        <div class="code-block-dot"></div>
        <div class="code-block-dot"></div>
        <span class="code-block-title">template.yaml — highlighted preview</span>
      </div>
      <pre><span class="yc"># Kubernetes Service manifest</span>
<span class="yk">apiVersion</span>: <span class="ys">v1</span>
<span class="yk">kind</span>: <span class="ys">Service</span>
<span class="yk">metadata</span>:
  <span class="yk">name</span>: <span class="yh">{{ .Values.app.name }}</span>
  <span class="yk">namespace</span>: <span class="yh">{{ .Values.global.namespace | default .Release.Namespace }}</span>
<span class="yk">spec</span>:
  <span class="yk">selector</span>:
    <span class="yk">app</span>: <span class="yh">{{ .Values.app.name }}</span>
  <span class="yk">ports</span>:
    - <span class="yk">port</span>: <span class="yh">{{ (index .Values.service.ports 0).port }}</span>
      <span class="yk">targetPort</span>: <span class="yn">8080</span>
      <span class="yk">protocol</span>: <span class="ys">TCP</span>
  <span class="yk">type</span>: <span class="yh">{{ .Values.service.type }}</span></pre>
    </div>
  </section>

  <!-- ═══════ SUPPORTED HELM EXPRESSIONS ═══════ -->
  <section>
    <h2>Supported Expressions</h2>
    <table class="tech-table">
      <thead>
        <tr>
          <th>Expression</th>
          <th>Support</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>.Values.a.b.c</td>
          <td>Full resolution via dot-path traversal through nested mappings and sequences</td>
        </tr>
        <tr>
          <td>.Release.Name / .Namespace / .Service</td>
          <td>Resolved to sensible mock values (<code>release-name</code>, <code>default</code>, etc.)</td>
        </tr>
        <tr>
          <td>.Chart.Name / .Version / .AppVersion</td>
          <td>Resolved to placeholder chart metadata values</td>
        </tr>
        <tr>
          <td>index .Values.list N</td>
          <td>Array index access for sequences defined in values</td>
        </tr>
        <tr>
          <td>(expr).field</td>
          <td>Parenthesised sub-expression with field access</td>
        </tr>
        <tr>
          <td>expr | default fallback</td>
          <td>Fallback to literal or another expression when value is empty</td>
        </tr>
        <tr>
          <td>upper · lower · quote · trim · title · toString · toYaml · indent</td>
          <td>String transformation pipe filters</td>
        </tr>
        <tr>
          <td>range · if · include · tpl · printf</td>
          <td>Detected and flagged as unsupported — left verbatim in output</td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- ═══════ TECHNICAL CONSTRAINTS ═══════ -->
  <section>
    <h2>Technical Design</h2>
    <p>Built under strict constraints that make it universally portable:</p>
    <div class="constraints">
      <span class="constraint">Single self-contained HTML file</span>
      <span class="constraint">Vanilla HTML, CSS &amp; JavaScript only</span>
      <span class="constraint">No frameworks, no npm, no build step</span>
      <span class="constraint">No backend, no server, no APIs</span>
      <span class="constraint">No external CDN dependencies</span>
      <span class="constraint">Works fully offline</span>
      <span class="constraint">Custom YAML parser (no library)</span>
      <span class="constraint">Custom Helm expression evaluator</span>
      <span class="constraint">Responsive across screen sizes</span>
      <span class="constraint">Dark &amp; light theme via CSS variables</span>
    </div>
  </section>

  <!-- ═══════ GETTING STARTED ═══════ -->
  <section>
    <h2>Getting Started</h2>
    <div class="code-block">
      <div class="code-block-header">
        <div class="code-block-dot"></div>
        <span class="code-block-title">usage</span>
      </div>
      <pre><span class="yc"># No installation required.</span>
<span class="yc"># Download the file and open it directly in your browser.</span>

<span class="yk">1.</span> <span class="ys">Download</span>  helm-verifier.html
<span class="yk">2.</span> <span class="ys">Open</span>      File → Open  (or double-click the file)
<span class="yk">3.</span> <span class="ys">Paste</span>     your template.yaml  →  left panel
<span class="yk">4.</span> <span class="ys">Paste</span>     your values.yaml    →  centre panel
<span class="yk">5.</span> <span class="ys">Click</span>     Render  or  Verify</pre>
    </div>
  </section>

  <!-- ═══════ FOOTER ═══════ -->
  <div class="footer">
    <p>Built with pure HTML · CSS · JavaScript &nbsp;·&nbsp; No dependencies &nbsp;·&nbsp; Open in any modern browser</p>
  </div>

</div>
</body>
</html>
