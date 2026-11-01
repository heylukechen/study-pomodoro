# Project: Study Pomodoro

A single-file focus-timer web app. Everything is in `index.html` — no build step,
no framework, no dependencies. Keep it that way unless a feature truly requires more.

## Structure (all inside index.html)
- One `<style>` block with CSS custom properties; supports light/dark via tokens.
- Timer logic (focus / short break / long break; long break every 4th round).
- End-of-timer alarm: repeating Web Audio tone + full-screen visual alert + tab-title flash.
- Focus soundscapes: generated in-browser (brown/rain/ocean/drone) + an embedded
  lofi loop (data: URI) + internet radio via <audio> (SomaFM / Radio Paradise / Nightride).
- State persists per-browser in localStorage (wrapped in try/catch).

## Conventions
- Vanilla JS, no libraries. Keep it a single self-contained file.
- Audio only plays during focus; it pauses on breaks and during the alarm.
- Serve over http(s) for radio to stream reliably (python3 -m http.server 8000).

## Deploy
Static host, output = repo root, no build command (Cloudflare Pages / Netlify).
Every push auto-redeploys.

## Working style
Explain tradeoffs and offer alternatives rather than one forced answer; back claims
with sources where it matters.
