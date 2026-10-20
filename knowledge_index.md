# Knowledge Index

## Observations

- 2026-10-20 homepage rebuilt as a simplified, video-first page (user asked for a professional UI/UX pass, simple style). Structure: sticky header (logo · How it works · Privacy · "Get it free" pill) → hero ("Focus with *intent*." + lede + App Store CTA above the video + 16:9 promo `assets/anchor-promo.mp4` with pause and sound buttons and a captions track `assets/anchor-promo.vtt`) → How it works (3 steps: start / watches / pulls you back, WebP stills in `assets/web/`) → Real stakes (score + pet) → one-line privacy statement → closing CTA → footer with developer credits ("Made by Haichao Li and Kexin Le", linking to https://www.linkedin.com/in/haichaol/ and https://www.linkedin.com/in/jessica-le-a72a5b2a9/). Removed: problem cards, blockers-vs-Anchor comparison, willpower essay, 5-step flow, section dividers. `styles.css` was rewritten as a token-based system (6 text styles, one section rhythm, no borders) and still covers `privacy.html`/`support.html` (`.page.article`, `.back`, `.updated`). App Store link: https://apps.apple.com/us/app/anchor-ai-focus/id6774340728?mt=12 (only found in search by the full name "Anchor: AI Focus"). Stylesheet cache-bust `?v=20261020c`. `assets/newdesign/notification.png` shows a real YouTube creator's face — it is no longer referenced and must not be reused.
    - importance: yellow
    - review_state: informed

- 2026-06-05 corrected homepage pet-feature language: proctors are the entities that watch/check sessions, while pets are collectible rewards earned from sufficiently high session scores.
    - importance: yellow
    - review_state: informed
- 2026-06-05 updated the public homepage for the new pet feature: hero copy now frames Anchor around proctor check-ins and earned pets, the landing hero uses `assets/session-set-up-view.mov` with `assets/newdesign/setup.png` as poster, the flow uses the new setup/during-session/notification/result/history screenshots, and the bottom Companion section shows the pet collection. Renamed new asset files to URL-safe names: `during-session.png`, `pet-collection.png`, and `result-pet-gone.png`.
    - importance: green
    - review_state: informed
- 2026-06-05 GitHub Pages live check showed `/index.html`, `/styles.css`, and `/app-icon.png` all serving 200 with the correct MIME types. Added `?v=20260605` stylesheet cache-busting query to `index.html`, `privacy.html`, and `support.html` because browsers/CDN edges can temporarily show an unstyled page after seeing a stale or missing stylesheet during deploy.
    - importance: green
    - review_state: informed
- 2026-06-04 rebuilt the public homepage into a fuller static marketing page matching the macOS app's minimal native style: warm off-white canvas, system typography, green/deep-green AnchorTheme accents, pill CTAs, real app icon asset, and a CSS-rendered focus-session preview with proctor-eye motif.
    - importance: green
    - review_state: informed
- 2026-06-04 updated public contact email on the static website privacy and support pages to haichaoli616@gmail.com.
    - importance: green
    - review_state: informed

- This repository is the public static website for Anchor. It is separate from the private app source repository so GitHub Pages can serve public App Store metadata pages.
    - importance: red
    - review_state: informed
- GitHub Pages is configured to publish from the `main` branch root. Expected public URLs are `https://haichaolihc.github.io/anchor-website/`, `/privacy.html`, and `/support.html`.
    - importance: yellow
    - review_state: informed
- (superseded 2026-10-20 by the simplified video-first page) 2026-06-06 rewrote `index.html` around ANTI-BLOCKER positioning (hero "Delete your blockers. For good."). New section order: hero → problem ("Nobody's brain was built for the feed" + 3 cards) → blockers-vs-Anchor contrast (✕/✓ columns) → how-it-works flow (reframed, reuses existing screenshots) → "A score you'll want to beat" (scoring + foot-in-the-door psychology) → pets as real stakes → privacy → closing CTA. Added a "Download for Mac" pill linking to `https://github.com/HaichaoLihc/anchor-website/releases/latest` and "Requires macOS 14.1 on Apple silicon". New CSS classes: `.button`/`.cta-row`/`.cta-note`, `.section-head(.center)`, `.problem(-grid/-card)`, `.contrast(-grid/-col.is-anchor)`, `.score-band`, `.how-head`. Cache-bust bumped to `?v=20260606-blocker`.
    - importance: yellow
    - review_state: approved
- The homepage privacy section was made HONEST about telemetry: it no longer claims "no analytics/telemetry" (false now that the app ships Sentry + Aptabase). It states the screen analysis runs on-device and screenshots are never uploaded, and that only anonymous aggregate usage + crash data is collected. `privacy.html` (the App Store policy) still says Anchor "does not collect personal data on developer-operated servers" and likely needs the same correction.
    - importance: yellow
    - review_state: approved
- 2026-06-06 added `appcast.xml` here to host the Anchor macOS app's Sparkle auto-update feed at `https://haichaolihc.github.io/anchor-website/appcast.xml` (referenced by the app's `SUFeedURL`). It currently has zero `<item>` entries (valid "no update" state) plus a commented item template. New releases are appended (newest first) using `make_appcast_item.sh` in the app repo, which signs the GitHub-Release DMG with the EdDSA key.
    - importance: yellow
    - review_state: approved
- `privacy.html` is the App Store Connect privacy policy URL. It discloses on-device screenshot processing plus Aptabase usage analytics and Sentry diagnostics; it must remain aligned with the app's actual collection, sharing, and retention behavior.
    - importance: yellow
    - review_state: informed
- 2026-07-27 updated the public privacy policy and homepage to match the on-device-only App Store build: Anchor has no camera or API-key/cloud-AI feature; periodic still screenshots are processed locally during active focus sessions, are never uploaded/shared/used for training, and temporary files are deleted after each check/intervention. The policy separately and specifically discloses Aptabase product-usage event fields and Sentry diagnostics.
    - importance: red
    - review_state: informed

## Child Indexes
