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
  strong {
    color: #000;
  }
  section.lead {
    background: #f7f3ea;
    color: #2f2a24;
  }
  section.lead h1, section.lead h2 {
    color: #201a14;
  }
  code {
    background: #efe4d1;
    color: #2f2a24;
    padding: 0.15em 0.35em;
    border-radius: 6px;
  }
  .transform-sentence {
    margin-top: 1.6em;
    font-size: 1.15em;
    line-height: 1.6;
    color: #2f2a24;
    text-align: center;
  }
  .transform-swap {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 24px;
    margin-top: 1em;
  }
  .swap-pill {
    border-radius: 99px;
    padding: 12px 28px;
    font-size: 2.2em;
    line-height: 1;
  }
  .swap-pill.before {
    background: #ede3d4;
    border: 1px solid #c9b899;
  }
  .swap-pill.after {
    background: #ede3d4;
    border: 1px solid #c9b899;
  }
  .swap-divider {
    font-size: 1.8em;
    color: #8a6a2f;
    font-weight: 300;
  }
  .research-list {
    margin-top: 1.6em;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .research-item {
    display: flex;
    align-items: center;
    gap: 20px;
    background: #ede3d4;
    border: 1px solid #c9b899;
    border-radius: 12px;
    padding: 18px 24px;
  }
  .research-label {
    font-size: 0.75em;
    font-weight: 800;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #8a6a2f;
    min-width: 90px;
  }
  .research-link {
    font-size: 1em;
    color: #2f2a24;
  }
  .research-link a {
    color: #2f2a24;
    text-decoration: none;
    border-bottom: 1.5px solid #a8872e;
  }
  blockquote {
    border-left: 4px solid #c9a85a;
    margin: 1.4em 0 0;
    padding: 0.6em 0 0.6em 1.2em;
    background: none;
    font-size: 1.5em;
    font-style: italic;
    color: #4a3f2f;
    line-height: 1.4;
  }
  blockquote p { margin: 0; }
---

<!-- _class: lead -->

# Delegate Support Q&A to my agent

James Su

---

<!-- _class: card -->

# Situation

Support asks me questions on Slack:

- Is it a bug?
- How does the feature work?
- If I change this, will that happen?

---

<!-- _class: card -->

# Solution

- I know the answer: typing the answer on Slack directly.
- I don't know the answer: run an agent on my machine and copy-paste the answer to Slack.

---

<!-- _class: card -->

# Problem

I'm happy to help, but context switching is expensive.

---

<!-- _class: card -->

# Idea

<div class="transform-sentence">Run an agent on my machine when <em>___</em> gets a message on Slack</div>
<div class="transform-swap">
  <div class="swap-pill before">👨‍💻</div>
  <div class="swap-divider">→</div>
  <div class="swap-pill after">🤖</div>
</div>

---

<!-- _class: card -->

# Research

- Slack: [Chat SDK](https://chat-sdk.dev/docs/adapters#messaging)
- Agent: [Pi SDK](https://pi.dev/docs/latest/sdk)

---

<!-- _class: card -->

# Why Chat SDK?

- Support various messaging platforms with [unified APIs](https://chat-sdk.dev/docs/api)
- Slack is fully supported according to [feature matrix](https://chat-sdk.dev/docs/adapters#feature-matrix)
- Easy to develop using the [chat-sdk skill](https://skills.sh/vercel/chat/chat-sdk)

---

<!-- _class: card -->

# Why Pi SDK?

- Already using Pi on my machine
- Pi exposes the same APIs it uses internally to build AI applications

---

<!-- _class: card -->

# Demo

https://github.com/goofansu/pi-chat

---

<!-- _class: card -->

# Q&A
