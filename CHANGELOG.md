# Changelog — roamspan.app

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
