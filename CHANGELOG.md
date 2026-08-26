# Changelog — roamspan.app

## 2026-08-26

### Auditoría, copy y SEO

- Fix: `/es/privacy/` ganó `meta description` y Smart App Banner (faltaban frente a la versión EN); el FAQ legal en ES recupera la frase sobre visados y normas bilaterales; enlaces de idioma con `lang` + `aria-label`.
- Copy: home EN/ES pulida — lede orientado a beneficio, «ventana móvil» en vez de «ventana rolling», «Planificador» en vez de «Planner», CTAs finales más claros. EN y ES equivalentes.
- SEO: titles y descriptions únicos por página, Open Graph/Twitter completos (og.jpg 1280×720 existente), JSON-LD `MobileApplication` en ambas homes, `theme-color`, `lastmod` en `sitemap.xml`. Canonical/hreflang y `robots.txt` ya eran correctos.

## 2026-08-24

### Landing V1

- English primary (`/`, `/privacy/`). Spanish at `/es/`, `/es/privacy/`. No geo/language redirect.
- Hero: “Never overstay the Schengen 90.” Official Apple badge (white, EN/ES), desktop QR, trust chips.
- Mockup: full sim screenshot in a CSS bezel (`height: auto`, no `object-fit: cover` crop).
- Ambient dark field: green/gold orbs + grain (HUD palette). Reduced-motion respected.
- Nav CTA is an outline pill (`Get the app`). A filled white button inherited muted text from `.nav-links a` and rendered blank.
- Hero animation does **not** use `opacity: 0` (first paint was empty).
- Mobile: copy + badge above the phone.
- Privacy pages for App Store Connect. Smart App Banner `app-id=6804630253`.
- Vercel project `roamspan-web`, production alias `roamspan-web.vercel.app`. Domain `roamspan.app` added; registrar A/CNAME still pending.
