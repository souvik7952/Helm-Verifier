<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

<h1>Helm Verifier</h1>

<p>
A simple browser-based tool for validating and rendering Helm chart templates.
No installation, backend, or external dependencies required.
</p>

<hr>

<section>
<h2>Overview</h2>

<p>
Helm Verifier helps engineers validate Helm templates directly in the browser.
Paste your template YAML and values YAML, then verify or render the output.
</p>

<p>
Works completely offline using a single HTML file.
</p>
</section>

<section>
<h2>Features</h2>

<ul>
<li>Instant Template Rendering</li>
<li>Helm Expression Validation</li>
<li>YAML Syntax Highlighting</li>
<li>Pipe Filter Support</li>
<li>Dark and Light Mode</li>
<li>Copy and Download Output</li>
</ul>

</section>

<section>
<h2>How It Works</h2>

<ol>
<li>Paste Helm Template YAML</li>
<li>Paste values.yaml</li>
<li>Click Verify or Render</li>
<li>Review and Export Output</li>
</ol>

</section>

<section>
<h2>Example Template</h2>

<pre>
apiVersion: v1
kind: Service
metadata:
  name: {{ .Values.app.name }}

spec:
  type: {{ .Values.service.type }}
</pre>

</section>

<section>
<h2>Supported Expressions</h2>

<table>
<tr>
<th>Expression</th>
<th>Description</th>
</tr>

<tr>
<td>.Values.*</td>
<td>Access values.yaml properties</td>
</tr>

<tr>
<td>.Release.*</td>
<td>Release information</td>
</tr>

<tr>
<td>.Chart.*</td>
<td>Chart metadata</td>
</tr>

<tr>
<td>index</td>
<td>Array access</td>
</tr>

<tr>
<td>default</td>
<td>Fallback value</td>
</tr>

<tr>
<td>upper, lower, quote</td>
<td>Common pipe filters</td>
</tr>
</table>

</section>

<section>
<h2>Technical Design</h2>

<ul>
<li>Single HTML File</li>
<li>HTML, CSS, JavaScript Only</li>
<li>No Frameworks</li>
<li>No Backend</li>
<li>No External Libraries</li>
<li>Works Offline</li>
</ul>

</section>

<section>
<h2>Getting Started</h2>

<pre>
1. Download helm-verifier.html
2. Open in browser
3. Paste template.yaml
4. Paste values.yaml
5. Click Verify or Render
</pre>

</section>

<div class="footer">
Built with HTML, CSS and JavaScript
</div>

</body>
</html>
