<h1>RIS Benchmark Reports</h1>

<p>
  The RIS Benchmark Reports page provides a consolidated view of completed Reasoning Integrity Standard (RIS)
  evaluations. Each run includes a human-readable scorecard and a machine-readable JSON artifact produced by
  the RIS Evaluator and LCAC reference implementation.
</p>

<hr />

<section id="reports-overview">
  <h2>Reports Overview</h2>
  <p>
    The current published reports represent early evaluations of a single model configuration and a multi-model
    suite. As you expand the RIS Evaluator pipeline, additional runs will appear here with the same structure.
  </p>

  <ul>
    <li>Single-model runs for <code>alpha-test-model</code></li>
    <li>Multi-model suite runs from <code>ris_multi_config.json</code></li>
    <li>Both Markdown scorecards and JSON artifacts for each run</li>
  </ul>
</section>

<hr />

<section id="latest-reports">
  <h2>Latest Reports</h2>

  <table>
    <thead>
      <tr>
        <th>Run ID</th>
        <th>Type</th>
        <th>Model / Suite</th>
        <th>Scorecard</th>
        <th>JSON</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>RUN-573B4CBFDEB3</code></td>
        <td>Single Model</td>
        <td>alpha-test-model</td>
        <td><a href="RUN-573B4CBFDEB3.md">RUN-573B4CBFDEB3.md</a></td>
        <td><a href="RUN-573B4CBFDEB3.json">RUN-573B4CBFDEB3.json</a></td>
      </tr>
      <tr>
        <td><code>RUN-9E847492F186</code></td>
        <td>Single Model</td>
        <td>alpha-test-model</td>
        <td><a href="RUN-9E847492F186.md">RUN-9E847492F186.md</a></td>
        <td><a href="RUN-9E847492F186.json">RUN-9E847492F186.json</a></td>
      </tr>
      <tr>
        <td><code>RUN-E39B22CC19C6</code></td>
        <td>Single Model</td>
        <td>alpha-test-model</td>
        <td><a href="RUN-E39B22CC19C6.md">RUN-E39B22CC19C6.md</a></td>
        <td><a href="RUN-E39B22CC19C6.json">RUN-E39B22CC19C6.json</a></td>
      </tr>
      <tr>
        <td><code>MULTI-ris_multi_config.json-1959911</code></td>
        <td>Multi-Model Suite</td>
        <td>ris_multi_config.json</td>
        <td><a href="MULTI-ris_multi_config.json-1959911.md">MULTI-ris_multi_config.json-1959911.md</a></td>
        <td><a href="MULTI-ris_multi_config.json-1959911.json">MULTI-ris_multi_config.json-1959911.json</a></td>
      </tr>
    </tbody>
  </table>
</section>

<hr />

<section id="report-usage">
  <h2>How These Reports Are Used</h2>
  <p>RIS reports are typically used in:</p>
  <ul>
    <li>
      <strong>Governance &amp; Audit:</strong> Attaching RIS evidence to risk registers, audit packages,
      and change-management tickets.
    </li>
    <li>
      <strong>Release &amp; Regression Management:</strong> Comparing model behaviour before and after upgrades
      to detect drift or instability.
    </li>
    <li>
      <strong>Model &amp; Vendor Evaluation:</strong> Benchmarking different providers or architectures using a
      consistent reasoning integrity metric.
    </li>
    <li>
      <strong>Research:</strong> Studying chain stability, semantic coherence, drift, and variance across models.
    </li>
  </ul>
</section>

<hr />

<section id="repository-layout">
  <h2>Repository Layout</h2>
  <p>
    Report files are stored following a predictable pattern to support both human review and automation:
  </p>

  <pre>
docs/
  reports/
    RUN-573B4CBFDEB3.md
    RUN-573B4CBFDEB3.json
    RUN-9E847492F186.md
    RUN-9E847492F186.json
    RUN-E39B22CC19C6.md
    RUN-E39B22CC19C6.json
    MULTI-ris_multi_config.json-1959911.md
    MULTI-ris_multi_config.json-1959911.json
    index.md  (this page)
  </pre>

  <p>
    This simple layout keeps the system compatible with future automation, including report index generators,
    leaderboard builders, and API endpoints.
  </p>
</section>

<hr />

<section id="adding-reports">
  <h2>Adding New Reports</h2>
  <p>
    To publish a new RIS evaluation:
  </p>
  <ol>
    <li>Generate the Markdown and JSON artifacts using the RIS Evaluator / LCAC pipeline.</li>
    <li>Place both files into <code>docs/reports/</code> on the main branch.</li>
    <li>Optionally, add a new row to the table above for manual indexing.</li>
    <li>Rebuild and deploy the portal from the server:</li>
  </ol>

  <pre>
cd /opt/ris-standard
mkdocs build
mkdocs gh-deploy --clean --force
  </pre>

  <p>
    Once deployed, the new reports will be available under the Analytics &rarr; Reports section of the RIS Portal.
  </p>
</section>

<hr />

<section id="future-enhancements">
  <h2>Future Enhancements</h2>
  <p>The following enhancements are planned for the RIS Reports experience:</p>
  <ul>
    <li>Sortable tables (by model, RIS level, drift, stability, date)</li>
    <li>Visual charts and trend lines based on composite scores</li>
    <li>Filters for model family, provider, domain, and run tag</li>
    <li>Integration with LCAC Governor and Redis-backed telemetry</li>
    <li>Export endpoints (CSV / JSON) for BI tools</li>
  </ul>

  <p>
    The objective is to evolve this page into a full Reasoning Integrity Observatory for models evaluated under RIS.
  </p>
</section>
