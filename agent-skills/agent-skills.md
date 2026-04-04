---
marp: true
theme: default
paginate: false
backgroundColor: #fff
color: #3d3428
style: |
  section {
    font-family: 'Aporetic Serif', serif;
  }
  h1, h2, h3, h4, h5, h6,
  code,
  pre,
  pre code {
    font-family: 'Aporetic Sans Mono', monospace;
  }
  section.lead h1 {
    font-size: 2.5em;
  }
  section.quote {
    background: #2e2a1a;
    color: #f5f0e8;
  }
  section.quote blockquote {
    border-left: 4px solid #d4a050;
    padding-left: 1em;
    font-style: italic;
  }
  blockquote {
    border-left: 4px solid #d4a050;
    padding-left: 1em;
    margin: 1em 0;
  }
  code {
    background: #f5f0e8;
    padding: 0.2em 0.4em;
    border-radius: 4px;
    color: #3d3428;
  }
  pre {
    background: #f5f0e8 !important;
    color: #3d3428 !important;
  }
  pre code {
    background: transparent;
  }
  section::after {
    color: #7a6d5a;
  }
  section.video-slide {
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #000;
    overflow: hidden;
  }
  section.small-code pre {
    font-size: 0.6em;
    line-height: 1.2;
  }
---

<!-- _class: lead -->

# Agent Skills

**James Su**


---

# First, a demo

`jira` skill — work with Jira in natural language.

> "Summarize OA-28145"


---

<!-- _class: small-code -->

# What is a skill?

A skill is a markdown playbook the agent can discover and follow.

```text
---
name: skill-name
description: A description of what this skill does and when to use it.
---

# Step-by-step instructions
1. Do the first thing
2. Then do the next thing

# Examples of inputs and outputs
Input: "Help me investigate this issue"
Output: Summary, likely cause, next actions

# Common edge cases
- Missing credentials
- Ambiguous user request
- Required config not set
```



---

# Skills can be discovered or invoked

Usually, you describe the task and let the agent choose.

> You: `"Find production errors for OA-27793"`
> Agent: *reads `opensearch`* → searches logs and summarizes findings

If you want, you can also call the same skill directly.

> You: `"/opensearch Find production errors for OA-27793"`
> Agent: *runs `opensearch` directly* → searches logs and summarizes findings


---

<!-- _class: lead -->

# Skills in OpenApply


---

# Local setup

`oa-setup` — get OpenApply running on a new machine.

PM and QA now run OpenApply locally — no engineer needed.


---

# QA verify

`oa-qa-verify` — verify a parent-facing form end to end.

- Opens the form in `agent-browser` and captures an initial screenshot
- Fills required fields with realistic fake data
- Moves through each step, handling dynamic widgets and validation
- Produces a Markdown report with screenshots and issues found


---

# Dev lifecycle

`oa-commit-work` — craft commits with meaningful context

`oa-review-changes` — self-review before opening a PR

`oa-pr-create` — PR with correct template and Jira link

`oa-review-pr` — structured peer review

`oa-demo-update` — delegate complex demo updates to the agent so demo servers get refreshed more often

`oa-release-notify` — stakeholder notification on deploy


---

# Document early

`write-docs` — generate documentation from code and context.

Best run immediately after finishing a feature.

> "Document how reenrollment works."

The agent reads the code, understands the intent, writes the docs.


---

<!-- _class: lead -->

# Why it works

---

<!-- _class: quote -->

> "Many 'non-coding' tasks become tractable once they look like files, programs, tools, and outputs. That gives you leverage from the model's strongest priors instead of fighting them."

— Armin Ronacher, [*Leaning In to Find Out*](https://github.com/mitsuhiko/talks/tree/main/dynamic/leaning-in-to-find-out), 2026


---

<!-- _class: small-code -->

# Skills ❤️ certainty

```text
Files    →  Read · Write · Edit

Programs →  python3 -c "import json; print(json.dumps(results))"
            bash -c 'grep ERROR production.log | tail -20'

Tools    →  gh pr create --title "Fix login"
            curl "$API/issues/OA-123" | jq '.fields.summary'
            acli jira workitem view OA-123

Outputs  →  ## Summary
            - Root cause: null check missing in reenrollment
            - Fix: OA-28145, deployed to staging
```

> if `gh` works in your terminal, it works in the skill.


---

<!-- _class: lead -->

# Writing a skill

---

<!-- _class: small-code -->

# The skill specification

Agent Skills support a simple directory structure:

```text
skill-name/
├── SKILL.md          # Required: metadata + instructions
├── scripts/          # Optional: executable code
├── references/       # Optional: documentation
├── assets/           # Optional: templates, resources
└── ...               # Any additional files or directories
```

In `SKILL.md`, you can point to supporting files directly:

```text
See [the reference guide](references/REFERENCE.md) for details.

Run the extraction script:
scripts/extract.py
```

> <https://agentskills.io/specification>


---

# Write a skill manually

**Directory structure**

```text
opensearch/
├── SKILL.md
└── references/
    ├── fetch.md
    ├── debug.md
    └── schema.md
```

**SKILL.md**

```text
---
name: opensearch
description: >
  Query production logs. Use when investigating a bug,
  analysing slow requests, or debugging a Jira ticket.
---
# ...
```


---

# Write a skill with the agent

**Claude Web** — enable then use

1. Customize → Skills → enable `skill-creator`
2. `/skill-creator`

**Claude Code** — install then use

1. `npx skills add anthropic/skills -s skill-creator -a claude-code -g`
2. `/skill-creator`

**Other built-ins**

- Codex — `$skill creator`
- VS Code — `/create-skill`


---

# Install skills

**Manually** — copy the directory, or use [`vercel-labs/skills`](https://github.com/vercel-labs/skills):

```
~/.claude/skills/opensearch/SKILL.md
npx skills add eduvo/agent-skills -s jira -a claude-code -g
npx skills add eduvo/agent-skills -s opensearch -a claude-code -g
```

**Ask your agent** — just tell it to install a skill for you.

> "install the skill: https://github.com/anthropics/skills/tree/main/skills/frontend-design"


---

# Skills improve over time

Every failure is a gap in the spec.

When a skill misfires: run `skill-creator eval` → find the gaps → improve.

> A skill is never finished. It's a living document.


---

<!-- _class: lead -->

# What's next

---

# Write your expertise into skills

We all have workflows and tricks that took a while to figure out.

- Things you debug in a way others don't know yet
- Shortcuts that took you months to discover

**Write them as skills — so others don't have to figure them out the hard way.**


---

# Share common skills across teams

Upskill the whole team quickly.

Multiply productivity — not just yours, but everyone's.

A shared repo is the source of truth — [eduvo/agent-skills](https://github.com/eduvo/agent-skills)


---

<!-- _class: lead -->

# Q & A

