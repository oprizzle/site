# Instructions for Claude (Claude Code / any Claude instance working in this repo)

## What this repo is
Static marketing site for figabl.com. Source in `src/`, built to `dist/` by
`node build.mjs`. Netlify builds from `main`; `dist/` is NOT committed.

## Rules
1. Never edit `dist/` by hand — it is generated. Edit `src/` and rebuild.
2. Copy changes -> `src/sections/<name>.html`. Colors -> `src/styles/tokens.css`.
   Section layout -> `src/sections/<name>.css`. Meta/SEO -> `src/meta.json`.
   Page order -> `src/sections/manifest.json`.
3. After ANY edit: run `node build.mjs` and confirm it exits cleanly before committing.
4. Work on a branch (`feat/...` or `copy/...`), never commit directly to `main`.
   Open a PR; Netlify posts a Deploy Preview URL on the PR for visual review.
5. Update `CHANGELOG.md` under [Unreleased] in the same commit as the change.
6. Do not add dependencies without being asked — the build is intentionally zero-dep.
7. Do not touch DNS, Netlify settings, or GitHub settings from this repo.

## Known gaps (see README) 
Contact form has no backend yet; no mobile nav below 1020px; og.png missing.
