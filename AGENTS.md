# Hushkey — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger and SplitText, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Get the files
If you were given a link to this repository or to its demo, do not read the page (you would get a summary and rebuild a different page). Download the files:
```bash
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/AGENTS.md
```

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes: the animation scripts find elements by them. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`HUSHKEY` → 7).
- These neighbouring sections animate across their border: hero → states, editions → faq. Keep each pair next to each other, or that transition switches off.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, email, phone, form); remove the attribute once the real value is in.
- Pre-order buttons in the hero and the nav: link to #editions now; point them to your checkout, waitlist or store URL.
- Pre-order Chalk / Pre-order Graphite in editions: link to #contact now; point them to the checkout URL of each finish.
- **The form sends nothing.** `section-script:contact` shows the thank-you message (`data-sent` on the form) without sending. Connect it to a form service (Formspree, Netlify Forms) or the user's endpoint, or remove it.
- Invented demo facts:
  - The price €189 (hero button, editions) and the bundle "any two panels for €340" (editions).
  - "Ships in March" (hero note, the FAQ "When does it ship?").
  - Payment and returns: pre-orders "charged only when your panel leaves the studio", "thirty days to send it back" (editions, FAQ).
  - Product specs: a battery that lasts about two years, USB-C charging, the woven back and a cable in the box (editions, FAQ), and the mounting answer (FAQ "How does it mount?").
  - Compatibility: "joins the hub your home already has over the open smart-home standards", works when the internet drops (FAQ, hero note, contact topic "Setting up with my hub").
  - Service: "the studio answers within a working day" (contact text and the form's data-sent message).
  - Place and hours: "Rotterdam, open Thursdays by appointment" (contact) and "© 2026 Hushkey Studio, Rotterdam" (footer).
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Common edits
- Rebrand: search the old name (`Hushkey`) and replace every match except the header comment; change the favicon letter and colours in `<link rel="icon">`.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Publish `index.html` with LICENSE and CREDITS.md; leave README.md, AGENTS.md and the `previews` folder out.
