# Free HTML product landing page template with GSAP scroll animations — Hushkey

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02) ![Lighthouse mobile: 93](https://img.shields.io/badge/Lighthouse%20mobile-93-brightgreen)

**[Live demo](https://8bsite.github.io/product-landing-page-template/)** · **[Use this template](https://github.com/new?template_name=product-landing-page-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/product-landing-page-template/archive/refs/heads/main.zip)**

<img src="previews/scroll.gif" alt="Hushkey, a free HTML template: scrolling through the first sections on a desktop" width="74%"> <img src="previews/phone.png" alt="Hushkey, a free HTML template: first screen on a phone" width="24%">

A one-page launch site for a palm-sized smart-home remote with eleven soft keys. Grey, tactile, monochrome; the keys are drawn in HTML and CSS and press, swell and melt into each other as you scroll.

Good for: hardware or gadget launch; pre-order or waitlist page; smart-home or IoT product; any product with a handful of features shown one per section. Free for personal and commercial use (MIT), made by [8B](https://8b.com/).

## Quick start

Pick one:

- **No code.** Download the ZIP, unzip it, replace the contacts and texts in `index.html`, put `index.html` into an empty folder and drag that folder onto [Netlify Drop](https://app.netlify.com/drop). The page is online in a minute.
- **On GitHub.** Click **[Use this template](https://github.com/new?template_name=product-landing-page-template&template_owner=8bsite)** to get your own copy, then **Settings → Pages → Deploy from a branch → main**. Your site appears at `https://<you>.github.io/<repo>/`.
- **With an AI coding agent** (Claude Code, Codex, Cursor, Windsurf…). Download the files into your project:
  ```bash
  curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/index.html
  curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/AGENTS.md
  ```
  Then give your agent this prompt:
  ```text
  Read AGENTS.md, then edit index.html. Use this template as the base for a launch page for <your product: what it is, who it is for, price, how to buy>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, prices, links and contacts, and recolour it through the CSS variables if needed.
  ```
  Give the agent the downloaded file, not a link to the live page: agents read links as summaries and would rebuild a different page.

## What's on the page

- **Navigation** — top bar: wordmark, section links, Pre-order button; phone menu overlay
- **Eleven keys for the whole house.** — first screen: headline, two buttons, the eleven-key product panel drawn in HTML/CSS
- **Up is ready. Down is on.** — keyboard of eight toggle keys (Up is ready / Down is on)
- **One pad. Four moods of the house.** — sticky stage: D-pad drives four room photos (Morning, Desk, Evening, Away)
- **Hold plus. The light arrives slowly.** — fader + plus key over one room photo (grey to colour on scroll)
- **No screen to wake. Off** — short statement: no screen, no app
- **Press two at once. Get a third.** — two keys meet and their outlines melt into one (chords)
- **Made to be found in the dark.** — three material cards with texture photos
- **Two finishes. The same eleven keys.** — two finishes (Chalk, Graphite) with pre-order buttons and a switch
- **Before you press order.** — questions and answers (native &lt;details&gt;)
- **Ask someone who has pressed every key.** — email, phone and a contact form (placeholders)
- **Footer** — width-filling HUSHKEY wordmark, links, copyright and the Design: 8B credit

## Before you publish

- Replace everything marked `data-8b-placeholder` (email, phone, form, social preview image, favicon) and the invented demo facts — prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The contact form does not send anything yet: connect it to a form service (Formspree, Netlify Forms) or remove it.

## Customize

- **Colours and fonts**: CSS variables in the `:root` block at the top of `<head>`.
- **Text**: edit it in place. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.
- **Photos**: replace the image URLs (they come from Unsplash now) and the `alt` texts.
- **Animations**: each section's animation is one `<script data-8b-part="scene:<id>">` block at the end of the file. For native scroll, delete the Lenis block in `page-init`.

## For developers

- **Stack.** HTML and CSS (custom properties, cascade layers) with GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr. No build step, no framework, no npm. 115 KB.
- **Layout of the file.** `<head>`: CSS variables, shared classes, then one style block per section. Then the markup, one element per section with a one-line comment above it. End of `<body>`: small behaviour scripts, the libraries, smooth scroll (`page-init`), the effects, one animation script per section.
- **Browsers.** Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), container query units, cascade layers, small/dynamic viewport units).
- **Speed.** Lighthouse (mobile, measured by 8B before release): 93, LCP 2.7 s, CLS 0.
- **Accessibility.** Motion runs only when the visitor's system allows it; with "reduce motion" the page is complete and still. FAQ answers use native `<details>` and open without JavaScript. Every photo has alt text.
- **External requests.** fonts.gstatic.com, images.unsplash.com, cdn.jsdelivr.net. No analytics, no cookies. To self-host everything (offline use, or Google Fonts and GDPR in the EU), download those files and change the URLs.
- **Licences of the parts.** GSAP is free, commercial use included, under its own standard licence (not MIT); Lenis is MIT; fonts are SIL OFL; photos are under the Unsplash License. See [CREDITS.md](CREDITS.md).

## FAQ

**Can I use it for a client or a commercial site?** Yes. The code is MIT: use it, change it, sell the site you build with it.

**Do I have to keep the "Design: 8B" link?** No. It is welcome, not required.

**Can I use it in React, Next.js, Astro or Vue?** Yes. Move each section's markup and style block into a component and run its animation script in `useGSAP()` (React) or `onMounted` (Vue); start Lenis once. Or keep it as a separate static landing page next to your app (`example.com` for the landing, `app.example.com` for the app).

**Why doesn't the contact form send?** It is a demo. Connect it to Formspree, Netlify Forms or your backend; AGENTS.md has the steps.

**Where are the photos from?** Unsplash; they load from Unsplash's servers. Replace them with your own when you can.

## More free templates

[More 8B templates on GitHub](https://github.com/8bsite) · [8b.com](https://8b.com/)

## License

The template code is MIT licensed — see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences — see [CREDITS.md](CREDITS.md).
