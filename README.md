# Free HTML product landing page template with GSAP scroll animations — Hushkey

**Product launch and pre-order page for a physical device: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02) ![Lighthouse mobile: 93](https://img.shields.io/badge/Lighthouse%20mobile-93-brightgreen)

**[Live demo](https://8bsite.github.io/product-landing-page-template/)** · **[Use this template](https://github.com/new?template_name=product-landing-page-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/product-landing-page-template/archive/refs/heads/main.zip)** · **[Template page on 8b.com](https://8b.com/templates/hushkey/)**

<a href="https://8bsite.github.io/product-landing-page-template/"><img src="previews/desktop.png" alt="Hushkey, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/product-landing-page-template/"><img src="previews/phone.png" alt="Hushkey, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/product-landing-page-template/"><img src="previews/scroll.gif" alt="Hushkey, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page launch site for a palm-sized smart-home remote with eleven soft keys. Grey, tactile, monochrome; the keys are drawn in HTML and CSS and press, swell and melt into each other as you scroll.

Good for: hardware or gadget launch; pre-order or waitlist page; smart-home or IoT product; any product with a handful of features shown one per section.

## Use it with an AI coding agent

Download the files into your project (in Windows PowerShell type `curl.exe`):

```bash
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/product-landing-page-template/main/CREDITS.md
```

Then give your agent this prompt:

```text
Read AGENTS.md, then edit index.html. Use this template as the base for a launch page for <your product: what it is, who it is for, price, how to buy>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, prices, links and contacts, and recolour it through the CSS variables if needed.
```

Give the agent the downloaded file, not a link: from a link it would rebuild a different page. No agent? Click **[Use this template](https://github.com/new?template_name=product-landing-page-template&template_owner=8bsite)**, edit `index.html` and turn on **Settings → Pages**.

## What's on the page

- **Navigation** — top bar: wordmark, section links, Pre-order button; phone menu overlay
- **Eleven keys for the whole house.** — first screen: headline, two buttons, the eleven-key product panel drawn in HTML/CSS
- **Up is ready. Down is on.** — keyboard of eight toggle keys (Up is ready / Down is on)
- **One pad. Four moods of the house.** — sticky stage: D-pad drives four room photos (Morning, Desk, Evening, Away)
- **Hold plus. The light arrives slowly.** — fader + plus key over one room photo (grey to colour on scroll)
- **No screen to wake.** — short statement: no screen, no app
- **Press two at once. Get a third.** — two keys meet and their outlines melt into one (chords)
- **Made to be found in the dark.** — three material cards with texture photos
- **Two finishes. The same eleven keys.** — two finishes (Chalk, Graphite) with pre-order buttons and a switch
- **Before you press order.** — questions and answers (native &lt;details&gt;)
- **Ask someone who has pressed every key.** — email, phone and a contact form (placeholders)
- **Footer** — width-filling HUSHKEY wordmark, links, copyright and the Design: 8B credit

## Design

Palette: ![#e4e5e8](https://img.shields.io/badge/-%23e4e5e8-e4e5e8?style=flat-square) ![#232427](https://img.shields.io/badge/-%23232427-232427?style=flat-square) ![#fbfbfc](https://img.shields.io/badge/-%23fbfbfc-fbfbfc?style=flat-square) ![#8d8e93](https://img.shields.io/badge/-%238d8e93-8d8e93?style=flat-square) ![#55565b](https://img.shields.io/badge/-%2355565b-55565b?style=flat-square) ![#b4b5b9](https://img.shields.io/badge/-%23b4b5b9-b4b5b9?style=flat-square) ![#2c2d31](https://img.shields.io/badge/-%232c2d31-2c2d31?style=flat-square) ![#a9abb0](https://img.shields.io/badge/-%23a9abb0-a9abb0?style=flat-square) ![#121315](https://img.shields.io/badge/-%23121315-121315?style=flat-square)  
Fonts: Mozilla Headline, Mozilla Text (Google Fonts). Change both through the CSS variables in the `:root` block at the top of `<head>`. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.

- The product panel, the keys and the switches are HTML and CSS (with SVG outlines), not images: restyle them through the CSS variables and the .m-key* classes.

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, email, phone, form) and the invented demo facts: prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr, 115 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), container query units, cascade layers, small/dynamic viewport units). Lighthouse (mobile, measured by 8B before release): 93, LCP 2.7 s, CLS 0. With "reduce motion" on, the page is complete and still.

## License

MIT, see [LICENSE](LICENSE); the "Design: 8B" footer link is welcome, not required. Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [8b.com/templates](https://8b.com/templates/) · [github.com/8bsite](https://github.com/8bsite).
