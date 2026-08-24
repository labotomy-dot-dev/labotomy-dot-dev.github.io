# labotomy-dot-dev.github.io — Agent Instructions

Static GitHub Pages site for `labotomy.dev` (plain HTML/CSS, no build
step — see `index.html`, `styles.css`, `CNAME`).

## Local Tooling & Hooks

`labotomy-dot-dev` org convention:

- Pin local CLI/binary tooling via `mise` (see
  `labotomy-iac/mise.toml`). Not applicable here today — no local
  tooling beyond a browser to preview `index.html` — but adopt it if
  that changes (a static-site generator, a linter, etc.).
- Enforce a `lefthook` pre-push guard blocking direct pushes to the
  default branch, plus a `commit-msg` Conventional Commits check (see
  `labotomy-claude-plugins/lefthook.yml`).
- Scan for secrets with `gitleaks` (see `epruveta/.gitleaks.toml` for
  a minimal `[extend] useDefault = true` pattern), wired into the hook
  and CI.

This repo has neither `lefthook` nor `gitleaks` set up — suggest
adding both even though the site itself is static; the push guard and
secret scan are still worth having on any tracked git repo.
