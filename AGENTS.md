## graphify

This project uses Graphify outputs in `graphify-out/`.

Rules:
- Before architecture/codebase answers, read `graphify-out/GRAPH_REPORT.md`.
- For cross-module relations, prefer graph traversal commands:
  - `graphify query "<question>"`
  - `graphify path "<A>" "<B>"`
  - `graphify explain "<concept>"`
- After code changes, run `graphify update .`.
- After documentation/content changes (`html/*.html`, `*.md`), run `/graphify --update` in the assistant.

Current project layout (for link/path checks):
- Main pages: `html/` (including `html/index.html`)
- Exercise/support files: `html/dados/`
