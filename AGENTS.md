# AGENTS.md

## Working with slides
- Always `cd` into the slide directory before running any `make` command.
- To build HTML: `make html`
- Always use `make open` — never `open <file>.html` directly. Video and WebGL effects require HTTP.
- If a Markdown file is updated in a turn, rebuild HTML with `make html`.
