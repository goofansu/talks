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
---

<!-- _class: lead -->

# pi-chat

James Su

---

<!-- _class: card -->

# Problem

- Support ask me **how does this feature work?**
- Support ask me **is this a bug?**

---

<!-- _class: card -->

# Solution 1

Run agent on my machine when **I** got a message on Slack

---

<!-- _class: card -->

# Solution 2

Run agent on my machine when **the bot** got a message on Slack

---

<!-- _class: card -->

# Research

- [Chat SDK](https://chat-sdk.dev)
- [Pi SDK](https://github.com/badlogic/pi-mono/blob/main/packages/coding-agent/docs/sdk.md)

---

<!-- _class: card -->

# Demo

---

<!-- _class: card -->

# Q&A

https://github.com/goofansu/pi-chat
