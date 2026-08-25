# AGENTS.md

## Cursor Cloud specific instructions

This repository (`roamspan-web`) is the **static marketing website** for the Roamspan iPhone app. It is plain HTML + CSS with static assets (images, SVGs). There is **no build step, no framework, no package manager, no lockfile, no backend, and no database**. The advertised iPhone app lives in a separate repository (`r3tr0eth/schengen-days-expo`) and is out of scope here.

### Layout / pages
- `index.html` — English home (canonical)
- `privacy/index.html` — English privacy policy (App Store Connect privacy URL)
- `es/index.html` — Spanish home
- `es/privacy/index.html` — Spanish privacy policy
- `styles.css` — shared styles; `vercel.json` — hosting config (`cleanUrls`, security + `Content-Language` headers)

### Run locally (dev)
Serve the static files with any static file server. The documented command (see `README.md` "Local"):
```bash
python3 -m http.server 4173
# open http://127.0.0.1:4173/
```
Python 3 is preinstalled. No install step is required. Note: with `python3 -m http.server`, `cleanUrls` from `vercel.json` is NOT applied, so open `/privacy/index.html` and `/es/privacy/index.html` explicitly (the trailing-slash directory form `/privacy/` also works because `index.html` is auto-served). On production Vercel, `/privacy/` etc. resolve via `cleanUrls`.

### Lint / test / build
There is **no lint, no automated test suite, and no build**. "Testing" means serving the files and clicking through `/`, `/es/`, `/privacy/`, and `/es/privacy/` to confirm they render.

### Deploy (do not run during setup)
Production is Vercel (project `roamspan-web`, production branch `main`); pushing `main` auto-deploys. Deploying requires Vercel auth and is not part of local development.
