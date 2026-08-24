# roamspan.app

Marketing site for **Roamspan** — Schengen 90/180 on iPhone.

Live: [https://roamspan-web.vercel.app](https://roamspan-web.vercel.app)  
Custom domain (DNS pending): [https://roamspan.app](https://roamspan.app)  
Repo: [r3tr0eth/roamspan-web](https://github.com/r3tr0eth/roamspan-web)  
App: [r3tr0eth/schengen-days-expo](https://github.com/r3tr0eth/schengen-days-expo) · branch `v1/prep-testflight`

## Language

English is the **primary** language. There is no `Accept-Language` redirect.

| URL | Language |
| --- | --- |
| `/` | English (canonical, `hreflang=x-default`) |
| `/privacy/` | English — App Store Connect privacy URL |
| `/es/` | Spanish |
| `/es/privacy/` | Spanish |

`Content-Language` is set in `vercel.json` (`en` everywhere except `/es/*`).

## Stack

Static HTML + CSS. No build step, no framework. Vercel project `roamspan-web` (team `r3tr0eths-projects`, Hobby), GitHub production branch `main`.

App Store ID: **6804630253** (listing may 404 until Ready for Sale).  
Smart App Banner: `apple-itunes-app` meta on home and privacy.

## Conversion notes

Taken from App Store / landing research (English-speaking travelers: UK, US, AU, CA, nomads):

- One job: get an iPhone user to the App Store. One official badge in the hero; nav uses a text pill, not a second badge ([Apple badge guidelines](https://developer.apple.com/app-store/marketing/guidelines/): one badge per layout, do not modify or animate it).
- Headline is the outcome, not a feature: **Never overstay the Schengen 90.**
- Trust chips under the lede: free 90/180 count · no account · on-device only.
- Desktop: QR to `apps.apple.com/app/id6804630253` (non-iOS visits otherwise dead-end). Hidden on small screens.
- Product shot is a **full** iPhone screenshot (status bar included), not `object-fit: cover` that clips the HUD.
- Hero must paint visible. Do **not** start copy/mockup at `opacity: 0` — first paint and crawlers otherwise get a blank hero.
- On mobile, copy + official badge sit above the mockup.

## Assets

| File | What |
| --- | --- |
| `badge-en.svg` / `badge-es.svg` | Official Apple “Download on the App Store” **white** badges (alternative variant for dark layouts). Source: `tools.applemediaservices.com`. Do not recolor. Min on-screen height 40px (we use 52px). |
| `app-home.jpg` | iPhone 16 Pro sim, English UI, full frame including Dynamic Island. |
| `og.jpg` | 16:9 social: “Know your Schengen days.” |
| `qr.svg` | QR → App Store URL. |
| `icon.png` / `favicon.png` | App icon. |

Footer includes the Apple trademark line required when the badge is used.

## DNS (`roamspan.app`)

Domain is already attached to the Vercel project. At the registrar:

| Host | Type | Value |
| --- | --- | --- |
| `@` | A | `76.76.21.21` |
| `www` | CNAME | `cname.vercel-dns.com` |

Until that propagates, use the `vercel.app` URL. Privacy URL for ASC once DNS is live: `https://roamspan.app/privacy/`.

## Local

```bash
cd ~/Documents/Desarrollador/kai-projects/roamspan-web
python3 -m http.server 4173
# open http://127.0.0.1:4173/
```

Deploy: push `main` (GitHub integration) or `vercel --prod` from this directory (linked project `roamspan-web`).

## App Store copy alignment

- Free: unlimited trips, map, remaining days, history. Official 90/180 is never paywalled.
- Pro: planner + PDF · €14.99/year (7-day trial) · €3.99/month. Cancel in Apple Settings.
- iPhone only. No account. Itinerary stays on device.
- Planning tool, not legal advice.
