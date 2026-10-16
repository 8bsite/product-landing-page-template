# Hushkey — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger and SplitText, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
  - `section-script:nav`: `.nav__open` `.nav__close`
  - `section-script:states`: `.m-key-2`
  - `section-script:contact`: `.contact__form` `.contact__status` `data-sent` `data-invalid`
  - `scene:hero`: `.hero__stage` `.hero__panel` `.states__slot` `.hero__k-up` `.hero__k-left` `.hero__k-ok` `.hero__k-right` `.hero__k-down` `.hero__seg` `.m-key` `.hero__k-play` `.hero__k-pause` `.hero__steps` `.is-on`
  - `scene:states`: `.states__keys` `.m-key-2`
  - `scene:modes`: `.modes__track` `.modes__item` `.modes__k-` `data-dir`
  - `scene:dimmer`: `.dimmer__rig` `.dimmer__photo` `.dimmer__groove` `.dimmer__thumb` `.dimmer__plus`
  - `scene:chords`: `.chords__track` `.chords__art` `.chords__a` `.chords__b` `.chords__contour` `.chords__result` `.m-key__dent` `.m-key__cap`
  - `scene:editions`: `.editions__item` `.editions__panel` `.editions__key`
  - `scene:faq`: `.faq__flood` `.editions__key`
  - `scene:footer`: `.footer__mark`
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`HUSHKEY` → 7).
- These neighbouring sections animate across their border: hero → states, editions → faq. Keep each pair next to each other, or that transition switches off.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, email, phone, form); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Pre-order buttons in the hero and the nav: link to #editions now; point them to your checkout, waitlist or store URL.
- Pre-order Chalk / Pre-order Graphite in editions: link to #contact now; point them to the checkout URL of each finish.
- **The form sends nothing.** `section-script:contact` checks the fields and shows a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
  - The price €189 (hero button, editions) and the bundle "any two panels for €340" (editions).
  - "Ships in March" (hero note, the FAQ "When does it ship?").
  - Payment and returns: pre-orders "charged only when your panel leaves the studio", "thirty days to send it back" (editions, FAQ).
  - Product specs: a battery that lasts about two years, USB-C charging, the woven back and a cable in the box (editions, FAQ), and the mounting answer (FAQ "How does it mount?").
  - Compatibility: "joins the hub your home already has over the open smart-home standards", works when the internet drops (FAQ, hero note, contact topic "Setting up with my hub").
  - Service: "the studio answers within a working day" (contact text and the form's data-sent message).
  - Place and hours: "Rotterdam, open Thursdays by appointment" (contact) and "© 2026 Hushkey Studio, Rotterdam" (footer).
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The product panel, the keys and the switches are HTML and CSS (with SVG outlines), not images: restyle them through the CSS variables and the .m-key* classes.
- Lighthouse lists gsap and ScrollTrigger as render-blocking (about 0.8–0.95 s); they sit at the end of body and the motion scripts after them need them loaded.
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the hero and the footer.
- Mid-wipe frames in modes show two half captions; it resolves within the wipe.
- Resizing across 900 px keeps the previous order of the states wave until reload (cosmetic).

## Common edits
- Rebrand: search the old name (`Hushkey`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
