# AGENTS.md

This is a **historical repo on the `legacy` profile** (Node.js, December 2013). It is kept for the record, not maintained.

## Stack
- JavaScript (CommonJS), Node of the 0.10 era, `ripple-lib` (2013 `Remote` API). No `package.json`, no lockfile, no tests.

## Layout
- `trust_line.js`: the whole library (`TrustLine`).
- `docs/STATUS.md`: current truth about what works. `docs/readme/banner.svg`: README banner.

## Commands as they would have been
- Install: `npm install ripple-lib` (an old version). Test: none exist; `npm test` would have been added with a `package.json`.

## Rules
- Docs-only changes unless the repo is revived. Reviving means choosing a real profile (see the repo standard) as its own decision.
- Never commit secrets or key values. Secrets come from `RIPPLE_SECRET_KEY` in the environment.
- Use Conventional Commits (`docs: ...`, `fix: ...`).
- Update `docs/STATUS.md` whenever you learn something about what works.
