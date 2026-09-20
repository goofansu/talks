---
marp: true
theme: default
paginate: false
backgroundColor: #f7f3ea
color: #2f2a24
style: |
  section {
    font-family: 'Avenir Next', 'Helvetica Neue', Arial, sans-serif;
    padding: 56px;
  }
  h1, h2, h3 {
    color: #201a14;
    margin-bottom: 0.4em;
  }
  section.card {
    background: linear-gradient(180deg, #fffdf8 0%, #f4ecdf 100%);
  }
  section.card::before {
    content: '';
    position: absolute;
    inset: 24px;
    border: 1px solid #d8c9ae;
    border-radius: 18px;
    pointer-events: none;
  }
  .eyebrow {
    color: #8a6a2f;
    font-size: 0.85em;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 0.8em;
    font-weight: 700;
  }
  ul {
    font-size: 1.1em;
    line-height: 1.45;
  }
  strong { color: #000; }
  section.lead {
    background: #f7f3ea;
    color: #2f2a24;
  }
  section.lead h1, section.lead h2 { color: #201a14; }
  code {
    background: #efe4d1;
    color: #2f2a24;
    padding: 0.15em 0.35em;
    border-radius: 6px;
  }
  .lead-sub {
    margin-top: 0.6em;
    font-size: 1.3em;
    color: #5a4d39;
  }
  .pipeline {
    display: flex;
    flex-wrap: wrap;
    align-items: stretch;
    justify-content: center;
    gap: 6px;
    margin-top: 1.6em;
  }
  .pipe-step {
    background: #ede3d4;
    border: 1px solid #c9b899;
    border-radius: 10px;
    padding: 10px 12px;
    text-align: center;
    min-width: 80px;
  }
  .pipe-step.human {
    background: #f3e7c9;
    border-color: #c9a85a;
  }
  .step-num {
    display: block;
    font-size: 0.68em;
    font-weight: 800;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #8a6a2f;
    margin-bottom: 4px;
  }
  .step-name {
    font-weight: 700;
    color: #201a14;
    font-size: 0.95em;
  }
  .step-out {
    display: block;
    font-size: 0.72em;
    color: #6b5c45;
    margin-top: 4px;
    line-height: 1.3;
  }
  .pipe-arrow {
    align-self: center;
    color: #8a6a2f;
    font-size: 1.4em;
    font-weight: 300;
    padding: 0 2px;
  }
  .cols {
    display: flex;
    gap: 24px;
    margin-top: 0.4em;
  }
  .col { flex: 1; }
  .col h3 { font-size: 1.1em; }
  .step-list {
    display: flex;
    flex-direction: column;
    gap: 6px;
    margin-top: 0.2em;
  }
  .step-item {
    background: #ede3d4;
    border: 1px solid #c9b899;
    border-radius: 10px;
    padding: 8px 12px;
  }
  .step-item .name { font-weight: 700; color: #201a14; }
  .step-item .out { color: #5a4d39; font-size: 0.88em; }
  .guard-list {
    list-style: none;
    padding: 0;
    margin: 0.2em 0 0;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .guard-list li {
    background: #f3e7c9;
    border: 1px solid #c9a85a;
    border-radius: 10px;
    padding: 6px 12px;
    font-size: 0.9em;
  }
  .brain {
    margin-top: 8px;
    background: #efe4d1;
    border-left: 4px solid #c9a85a;
    border-radius: 0 10px 10px 0;
    padding: 8px 12px;
    font-size: 0.9em;
  }
  .bottom-note {
    margin-top: 0.7em;
    font-size: 0.98em;
    color: #2f2a24;
  }
  section.spaced-copy p {
    margin: 0.8em 0 0.35em;
  }
  section.spaced-copy ul {
    margin-top: 0.35em;
    margin-bottom: 0.8em;
  }
  section.spaced-copy li {
    margin-bottom: 0.35em;
  }
  section.station-slide h1 {
    margin-bottom: 0.2em;
  }
  .station-summary {
    color: #5a4d39;
    font-size: 1.25em;
    margin-bottom: 0.9em;
  }
  .station-grid {
    display: grid;
    grid-template-columns: 1.35fr 1fr;
    gap: 20px;
    align-items: stretch;
  }
  .station-stack {
    display: flex;
    flex-direction: column;
    gap: 14px;
  }
  .station-panel {
    background: #ede3d4;
    border: 1px solid #c9b899;
    border-radius: 14px;
    padding: 18px 22px;
  }
  .station-panel h3 {
    color: #8a6a2f;
    font-size: 0.85em;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin: 0 0 0.55em;
  }
  .station-panel p {
    font-size: 1.08em;
    line-height: 1.45;
    margin: 0 0 0.65em;
  }
  .station-panel p:last-child { margin-bottom: 0; }
  .artifact-panel {
    background: #f3e7c9;
    border-color: #c9a85a;
  }
  .boundary-panel {
    background: #efe4d1;
    border-left: 4px solid #c9a85a;
  }
  section.prompt-slide pre {
    background: #201a14;
    border: 1px solid #4b4035;
    border-radius: 14px;
    padding: 22px 24px;
    margin-top: 0.8em;
    white-space: pre-wrap;
    overflow-wrap: anywhere;
    font-size: 0.9em;
    line-height: 1.55;
  }
  section.prompt-slide pre code {
    background: transparent;
    color: #fffdf8;
    padding: 0;
    display: block;
    white-space: pre-wrap;
    font-size: 1em;
    line-height: 1.55;
  }
  section.prompt-slide pre code span {
    color: inherit !important;
  }
  .prompt-note {
    color: #5a4d39;
    font-size: 1.05em;
    margin-top: 0.35em;
  }
  .demo-steps {
    margin-top: 0.3em;
    counter-reset: demo;
    list-style: none;
    padding: 0;
  }
  .demo-steps li {
    counter-increment: demo;
    padding: 8px 0 8px 48px;
    position: relative;
    display: flex;
    align-items: center;
    min-height: 48px;
    font-size: 1.05em;
    line-height: 1.4;
    border-bottom: 1px solid #e2d5c0;
  }
  .demo-steps li:last-child { border-bottom: none; }
  .demo-steps li::before {
    content: counter(demo);
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 30px;
    height: 30px;
    background: #ede3d4;
    border: 1px solid #c9b899;
    border-radius: 50%;
    text-align: center;
    line-height: 28px;
    font-weight: 800;
    color: #8a6a2f;
  }
---

<!-- _class: lead -->

# Foreman Software Factory

<div class="lead-sub">Bug report to reviewed draft PR</div>

---

<!-- _class: card -->

<div class="eyebrow">What is a software factory</div>

# A pipeline that turns an issue into a draft PR

A `factory`-labeled issue flows through a fixed sequence of specialized steps. Each step has **one job** and produces **one artifact** — unattended, from intake to draft pull request. A human only appears at the end.

<div class="pipeline">
  <div class="pipe-step human">
    <span class="step-num">in</span>
    <span class="step-name">Issue</span>
    <span class="step-out">labeled <code>factory</code></span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">1</span>
    <span class="step-name">Foreman</span>
    <span class="step-out">reads issue</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">2</span>
    <span class="step-name">Classifier</span>
    <span class="step-out">type · priority</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">3</span>
    <span class="step-name">Analyst</span>
    <span class="step-out">plan + criteria</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">4</span>
    <span class="step-name">Implementer</span>
    <span class="step-out">code + checks</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">5</span>
    <span class="step-name">Reviewer</span>
    <span class="step-out">different vendor</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step">
    <span class="step-num">out</span>
    <span class="step-name">Draft PR</span>
    <span class="step-out">the ceiling</span>
  </div>
  <div class="pipe-arrow">→</div>
  <div class="pipe-step human">
    <span class="step-num">you</span>
    <span class="step-name">Human</span>
    <span class="step-out">review · merge</span>
  </div>
</div>

---

<!-- _class: card spaced-copy -->

<div class="eyebrow">What it solves</div>

# Automating the bug-fix workflow

**The problem**

- Bug reports interrupt planned development work
- Developers must stop current work to investigate and fix them

**The solution**

- The `factory` label sends the bug report through Foreman
- The pipeline returns a reviewed draft PR for approval and merge
- **Current scope: bug fixes only**

---

<!-- _class: card station-slide -->

<div class="eyebrow">How it solves · station 1 of 4</div>

# Classifier

<div class="station-summary">Decides whether the task is ready to build.</div>

<div class="station-grid">
  <div class="station-panel">
    <h3>Job</h3>
    <p>Assigns the task's type, priority, and complexity.</p>
    <p>If the issue is not actionable, Foreman asks the requester and stops.</p>
  </div>
  <div class="station-panel artifact-panel">
    <h3>Artifact</h3>
    <p>A classification with an explicit <strong>actionable</strong> or <strong>not actionable</strong> decision.</p>
  </div>
</div>

---

<!-- _class: card station-slide -->

<div class="eyebrow">How it solves · station 2 of 4</div>

# Analyst

<div class="station-summary">Turns the classified task into a plan the next station can execute.</div>

<div class="station-grid">
  <div class="station-panel">
    <h3>Job</h3>
    <p>Reads from its own live checkout of the repository.</p>
    <p>Defines the implementation approach and the conditions for success.</p>
  </div>
  <div class="station-panel artifact-panel">
    <h3>Artifact</h3>
    <p>An implementation plan with concrete acceptance criteria.</p>
  </div>
</div>

---

<!-- _class: card station-slide -->

<div class="eyebrow">How it solves · station 3 of 4</div>

# Implementer

<div class="station-summary">Executes the plan in an isolated sandbox.</div>

<div class="station-grid">
  <div class="station-panel">
    <h3>Job</h3>
    <p>Writes the code and runs the repository's own checks.</p>
    <p>Pushes a validated <code>factory/&lt;type&gt;-&lt;slug&gt;</code> branch.</p>
  </div>
  <div class="station-stack">
    <div class="station-panel artifact-panel">
      <h3>Artifact</h3>
      <p>Code, check results, and a pushed branch.</p>
    </div>
    <div class="station-panel boundary-panel">
      <h3>Boundary</h3>
      <p><code>main</code> and <code>master</code> are refused in code.</p>
    </div>
  </div>
</div>

---

<!-- _class: card station-slide -->

<div class="eyebrow">How it solves · station 4 of 4</div>

# Reviewer

<div class="station-summary">Judges the implementation independently.</div>

<div class="station-grid">
  <div class="station-panel">
    <h3>Job</h3>
    <p>Reads the real diff and judges every acceptance criterion with evidence.</p>
    <p>Returns <code>approve</code>, <code>request_changes</code>, or <code>reject</code>.</p>
  </div>
  <div class="station-stack">
    <div class="station-panel artifact-panel">
      <h3>Artifact</h3>
      <p>An evidence-backed review verdict.</p>
    </div>
    <div class="station-panel boundary-panel">
      <h3>Revision loop</h3>
      <p>At most two revisions before the draft pull request.</p>
    </div>
  </div>
</div>

---

<!-- _class: card -->

<div class="eyebrow">Demo</div>

# Label an issue, watch it build

<ol class="demo-steps">
  <li>Add the <code>factory</code> label to an issue</li>
  <li>Foreman → classifier → analyst → implementer → reviewer</li>
  <li>Draft PR appears, progress on the issue</li>
  <li>A person reviews, marks ready, merges</li>
</ol>

---

<!-- _class: card prompt-slide -->

<div class="eyebrow">Get started</div>

# How to build the factory

<div class="prompt-note">Paste this prompt into your coding agent:</div>

```
I want to build a software factory with the eve framework,
using the Foreman template. Read the setup instructions at
https://ask-foreman.dev/docs/getting-started and follow them.
They cover deploying the template, connecting GitHub and Linear,
running it locally, and how the pipeline works overall.
```

---

<!-- _class: lead -->

# Q & A
