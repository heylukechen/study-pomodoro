# Study Pomodoro

A single-file focus timer: Pomodoro cycles, an insistent end-of-timer alarm with a
visual alert, generated focus soundscapes, an embedded lofi loop, and live internet
radio (SomaFM / Radio Paradise / Nightride FM).

Everything lives in `index.html` — no build step, no dependencies.

## Run locally
Just open `index.html` in a browser. For the embedded radio to stream reliably,
serve it over http rather than file:// :

    python3 -m http.server 8000
    # then open http://localhost:8000

## Deploy
Static host, output directory = project root (no build command).
- Cloudflare Pages: connect this repo, framework preset "None", build command empty,
  output directory `/`.
- Netlify: connect this repo, build command empty, publish directory `.`.

## Edit
Open this folder with Claude Code (`claude`) and ask for changes, then commit & push —
your connected host redeploys automatically.
