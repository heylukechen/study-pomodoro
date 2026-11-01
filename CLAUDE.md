# Project: Study Pomodoro

A single-file focus-timer web app. Everything is in `index.html` — no build step,
no framework, no dependencies. Keep it that way unless a feature truly requires more.

## Structure (all inside index.html)
- One `<style>` block with CSS custom properties; supports light/dark via tokens.
- Timer logic (focus / short break / long break; long break every 4th round).
- End-of-timer alarm: repeating Web Audio tone + full-screen visual alert + tab-title flash.
- Focus radio: internet radio via <audio> (SomaFM / Radio Paradise / Nightride), Off/On
  toggle + station picker + volume; each station has a fallback stream URL.
- State persists per-browser in localStorage (wrapped in try/catch).

## Conventions
- Vanilla JS, no libraries. Keep it a single self-contained file.
- Radio only plays during focus; it stops on breaks and during the alarm.
- Serve over http(s) for radio to stream reliably (python3 -m http.server 8000).
- SomaFM returns 403 when the Referer is `localhost`, so its stations only play on the
  deployed site; test radio locally with Radio Paradise or Nightride.

## Deploy
Cloudflare Workers, static assets only (no Worker script), connected to GitHub via
Workers Builds. `wrangler.jsonc` serves the repo root; `.assetsignore` keeps repo-only
files (CLAUDE.md, README.md, config) out of the published site. No build command.
Every push to `main` auto-redeploys; other branches get preview URLs.

## Working style
Explain tradeoffs and offer alternatives rather than one forced answer; back claims
with sources where it matters.
