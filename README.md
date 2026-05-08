# 🏡 Virtual_home_photography — Real-Estate Photography Studio (Arquito-themed Static Front-End)

> **A modern, three-page static marketing site for the Brampton, Ontario real-estate photography studio "Virtual Home Photography". Built on top of the *Arquito* HTML theme by paul-themes — featuring an Animsition page-transition layer, a parallax Rellax hero, an off-canvas dark menu panel, a TwentyTwenty before/after slider showing the studio's retouching quality, a Swiper testimonials carousel, an embedded live 360° virtual tour, and a Google-Maps contact page. No backend, no build step — pure HTML/CSS/JS, ready to drop on any static host.**

[![HTML5](https://img.shields.io/badge/HTML5-Static-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-BEM-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-4-7952B3?logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![jQuery](https://img.shields.io/badge/jQuery-3.5.1-0769AD?logo=jquery&logoColor=white)](https://jquery.com/)
[![Swiper](https://img.shields.io/badge/Swiper-Carousel-6332F6?logo=swiper&logoColor=white)](https://swiperjs.com/)
[![Animsition](https://img.shields.io/badge/Animsition-Page_FX-FF8A65)](https://github.com/blivesta/animsition)
[![Rellax](https://img.shields.io/badge/Rellax-Parallax-2ECC71)](https://dixonandmoe.com/rellax/)
[![TwentyTwenty](https://img.shields.io/badge/TwentyTwenty-Before/After-9B59B6)](https://zurb.com/playground/twentytwenty)
[![GSAP](https://img.shields.io/badge/GSAP-TweenMax-88CE02?logo=greensock&logoColor=white)](https://greensock.com/gsap/)
[![Magnific Popup](https://img.shields.io/badge/Magnific_Popup-Lightbox-1ABC9C)](https://dimsemenov.com/plugins/magnific-popup/)
[![Isotope](https://img.shields.io/badge/Isotope-Masonry-2980B9)](https://isotope.metafizzy.co/)
[![Google Maps](https://img.shields.io/badge/Google_Maps-Embedded-4285F4?logo=googlemaps&logoColor=white)](https://developers.google.com/maps)

---

## 🌟 Overview

**Virtual Home Photography** is a Brampton, Ontario real-estate photography studio that has been producing high-definition photos and **360° virtual tours** for Realtors and Brokerages — Remax, Century 21, HomeLife, King Realty Inc. and many more — **since 2013**. They specialise in same-day-delivery virtual tours that work on both desktop and mobile, so listings can hit MLS as quickly as possible.

This repository is the **second iteration** of their public-facing website. Where the sister repo [`Virtual_Home_photo`](https://github.com/abdullahek/Virtual_Home_photo) was a PHP/Bootstrap-3 site built on the older "GoArch" theme with PHPMailer for the contact form, this build is a **modern, JS-only static site** based on the **Arquito** premium HTML theme by paul-themes.com. Three pages — `home.html`, `service.html`, `contact.html` — share an off-canvas dark hamburger menu, a Roboto + Teko Google-Fonts type system, and a single `assets/` bundle of JS plugins.

The site showcases:
- The studio's "Best Solutions for Photography" hero with Rellax parallax.
- A *"Get to know us"* about block.
- Four service tiles with a hover zoom effect (Photos, Virtual Tour, Aerial, 3D Tour).
- A live **TwentyTwenty before/after slider** demonstrating their retouching ("Our Quality Work").
- A Swiper-driven **testimonials carousel** featuring real client quotes ("Ontario Driving", "Sarita Kaushal", "TEAM GTA HOUSE GUIDE") with 5-star ratings — naming the studio's principal photographer **Mr Vishal**.
- A *Services* page that embeds the studio's own live 360° virtual tour from `virtualhomephotography.com/tour/Panos/2200LS/tour.html`.
- A *Contact* page with an embedded Google Map of the studio's location, contact form, and direct dial-link to **647-390-6555**.

---

## ✨ Core Pages & Features

### 🏠 `home.html` — Landing page
- **Animsition** page-load fade.
- Fixed black header with a 420×100 logo (`img/logo_virtual.png`) and an off-canvas dark hamburger menu containing six items (Home, Services, Pricing, Samples, Recent Projects, Contact Us). The hamburger toggle uses an orange `#f24a00` accent.
- **Hero "Main Slide"** with a Rellax parallax background (`img/bg_home.jpg`):
  - Subtitle: *OUR SPECIALIZATION*
  - Title: *Best Solutions for Photography*
  - Body: *Always happy, enthusiastic and creative…*
- **About block "Get to know us"** — long-form story of the studio paired with a `bg_right.jpg` image at 90 % size.
- **Zoom Services grid** — four hover-to-expand service tiles:
  - *Photos* (`icon-picture`)
  - *Virtual Tour* (`icon-camera`)
  - *Aerial* (`icon-magnifier`)
  - *3D Tour with MatterPort* (`icon-car`)
- **TwentyTwenty before/after slider** ("Our Quality Work") — drag handle compares `img/before.jpg` vs `img/after.jpg`.
- **Swiper testimonials carousel** — three real 5-star reviews with synced reviewer-button slider:
  - *Ontario Driving* — *"I know Mr Vishal since many years…"*
  - *Sarita Kaushal* — *"Excellent quality work!…"*
  - *TEAM GTA HOUSE GUIDE* — *"Professional, honest and very understanding guy…"*

### 🎥 `service.html` — Services
- Re-uses the same dark header + off-canvas menu.
- Two large `article-listing-item` cards in a 1-column masonry layout:
  - **Photos** — *"It is rightly said that 'A picture is worth a thousand words'."* with `bg_right.jpg` cover and an *Order Now* CTA.
  - **Virtual Tour** — describes how a 360° panorama is stitched from many photos. The cover area is a **live `<iframe>` embed of an actual virtual tour** at `virtualhomephotography.com/tour/Panos/2200LS/tour.html`.

### ✉️ `contact.html` — Contact
- Original HTTrack provenance comment in the file (line 4) reveals the source theme: *"Mirrored from paul-themes.com/html/arquito/demo/page-contact.html"*.
- Full-width **Google Map** (`#map` with `data-lat="-37.816248" data-lng="144.965981"` — coordinates point to **Melbourne, Australia**, leftover from the Arquito demo).
- Studio info card: *Canada · Brampton, Ontario · 647-390-6555 (`tel:` link) · virtualhomephotography@gmail.com*.
- "Get in touch" form with Name, Subject and Message fields and a *Send Message* button — but the form has **no `action` and no JS handler**, so submissions go nowhere (see [Tech-Debt](#-tech-debt--known-issues)).

### 🎨 Shared chrome on every page
- **Animsition `.page__inner`** wrapper for soft cross-fade page transitions.
- Inline SVG sprite definition (`#icon_ion-icon-apps`) for ionicon-style iconography.
- Off-canvas right-side menu panel with social row (Twitter / Facebook / Google Plus icofont icons).
- Footer with three columns: company / quick links / socials, and a *© 2020 Virtual Home Photography* line.
- Footer brand link still points to `http://paul-themes.com/` — leftover theme attribution.

---

## 🏗️ Architecture

```
                           ┌──────────────────────────────────────────────────────────┐
                           │                       VISITOR (browser)                  │
                           └────────────────────────────┬─────────────────────────────┘
                                                        │ static GET *.html
                                                        ▼
                ┌──────────────────────────────────────────────────────────────────────┐
                │                        STATIC FILE HOST                              │
                │            (any web server — Apache, Nginx, GitHub Pages,            │
                │             Netlify, Vercel, S3, Cloudflare Pages…)                  │
                │                                                                      │
                │       ┌──────────────┐   ┌──────────────┐   ┌──────────────┐        │
                │       │  home.html   │   │ service.html │   │ contact.html │        │
                │       └──────┬───────┘   └──────┬───────┘   └──────┬───────┘        │
                │              │                  │                  │                 │
                │              └────────── shared assets/ ───────────┘                 │
                │                                 │                                    │
                │   ┌─────────────────────────────┴────────────────────────────────┐  │
                │   │  assets/css/  (Bootstrap 4, theme, responsive, swiper,        │  │
                │   │                animsition, magnific-popup, twentytwenty,      │  │
                │   │                icofont, linearicons, dark, …)                 │  │
                │   │                                                                │  │
                │   │  assets/js/   (jQuery 3.5.1, Bootstrap bundle, Swiper,         │  │
                │   │                Animsition, Rellax, Magnific Popup, Isotope,    │  │
                │   │                TweenMax, TimelineLite, typed.js, vivus.js,     │  │
                │   │                TwentyTwenty, viewport, Slider Revolution +     │  │
                │   │                9 extensions + panorama/slicey add-ons,         │  │
                │   │                theme.js, gmap.js)                              │  │
                │   │                                                                │  │
                │   │  assets/img/, assets/fonts/, img/, favicons/                   │  │
                │   └─────────────────────────────┬──────────────────────────────────┘  │
                └─────────────────────────────────┼─────────────────────────────────────┘
                                                  │
                                                  ▼
                                      ┌─────────────────────────────────────┐
                                      │     External integrations           │
                                      │ ─ Google Fonts (Roboto + Teko)      │
                                      │ ─ jQuery 3.5.1 from googleapis CDN  │
                                      │ ─ Google Maps JS API (contact page) │
                                      │ ─ Live virtual-tour iframe          │
                                      │   (virtualhomephotography.com)      │
                                      └─────────────────────────────────────┘
```

---

## 📦 Project Structure

```
Virtual_home_photography/
├── home.html               # Landing page — hero, about, services grid, before/after, testimonials
├── service.html            # Services — 2 large article cards + embedded live virtual-tour iframe
├── contact.html            # Contact — Google Map + studio info + "Get in touch" form
│
├── img/                    # Page-level images referenced directly from the HTML files
│   ├── logo_virtual.png    # Studio logo (header)
│   ├── bg_home.jpg         # Rellax parallax hero background
│   ├── bg_right.jpg        # About-block + Photos service cover
│   ├── before.jpg          # TwentyTwenty "before" image
│   └── after.jpg           # TwentyTwenty "after" image
│
├── favicons/               # Full favicon kit (Apple, Android, MS, SVG)
│   ├── favicon.ico
│   ├── favicon-16x16.png + favicon-32x32.png
│   ├── apple-touch-icon.png
│   ├── safari-pinned-tab.svg
│   ├── browserconfig.xml
│   └── site.html           # (originally site.webmanifest — see Tech-Debt)
│
├── assets/
│   ├── css/
│   │   ├── theme.css                   # Master Arquito theme styles (BEM-style classes)
│   │   ├── responsive.css              # Mobile / tablet breakpoint overrides
│   │   ├── bootstrap.min.css           # Bootstrap 4 grid + components
│   │   ├── dark.css                    # Optional dark colour palette
│   │   ├── icofont.min.css             # Icofont icon font
│   │   ├── linearicons.min.css         # Linearicons icon font
│   │   ├── magnific-popup.min.css      # Lightbox styling
│   │   ├── animsition.min.css          # Page-transition styles
│   │   ├── swiper.min.css              # Swiper carousel
│   │   ├── twentytwenty.css            # Before/After comparison slider
│   │   ├── jquery.pagepiling.css       # PagePiling full-screen sections (vendored, unused)
│   │   ├── revolution-addons/panorama/revolution.addon.panorama.css
│   │   ├── revolution/                 # Slider Revolution stylesheets
│   │   │   ├── settings.css + layers.css
│   │   │   ├── openhand.html / closedhand.html  # cursor PNGs (mis-named .html)
│   │   ├── fonts/revicons/             # Slider Revolution icon font (cache-busted .html dupes)
│   │   └── assets/                     # Reference HTML snippets (gridtile, coloredbg, loader.gif)
│   │
│   ├── js/
│   │   ├── theme.js                    # Site bootstrap (very small — most logic is in plugins)
│   │   ├── gmap.js                     # Tiny Google Map initialiser used by contact.html
│   │   ├── jquery.min.js               # Bundled jQuery (also loaded from googleapis CDN)
│   │   ├── bootstrap.bundle.min.js     # Bootstrap 4 JS + Popper bundle
│   │   ├── animsition.min.js           # Page transitions
│   │   ├── swiper.min.js               # Carousels (testimonials)
│   │   ├── jquery.magnific-popup.min.js   # Lightbox
│   │   ├── isotope.pkgd.min.js         # Masonry layout (unused on current pages)
│   │   ├── jquery.twentytwenty.js      # Before/After image slider
│   │   ├── jquery.event.move.js        # TwentyTwenty's event helper
│   │   ├── rellax.min.js               # Parallax hero
│   │   ├── jQuerySimpleCounter.min.js  # Number counter (unused on current pages)
│   │   ├── jquery.pagepiling.min.js    # Full-screen page sections (unused)
│   │   ├── jquery.viewport.min.js      # Viewport detection
│   │   ├── smoothscroll.js
│   │   ├── polyfill.min.js
│   │   ├── svg4everybody.legacy.min.js # SVG <use> polyfill for IE
│   │   ├── TweenMax.min.js + TimelineLite.min.js   # GSAP animation engine
│   │   ├── typed.min.js                # Typewriter text effect (unused)
│   │   ├── vivus.min.js                # SVG line drawing (unused)
│   │   └── revolution/                 # Slider Revolution core + 9 extensions
│   │       └── revolution-addons/{panorama, slicey}/  # 360° + slicey effects (unused)
│   │
│   ├── img/                # Theme decoration images
│   │   ├── before.jpg + after.jpg + dummy.png + error-image.jpg
│   │   ├── distortion.jpg + dot.jpg + dot-dark.jpg + dot-gray.jpg
│   │   ├── icon_building.svg + icon_factory.svg + icon_house.svg
│   │   ├── quote.png
│   │   └── zoom-count-bg.jpg + zoom-image-head-bg.jpg + zoom-image-head-bg2.png
│   │
│   └── fonts/              # Webfonts
│       ├── Icofont.woff (+ .html companion)
│       └── Linearicons.woff (+ .html companion)
│
└── README.md
```

> ⚠️ Several files in the bundle are named `*.html` even though they should be `*.svg`, `*.woff2` or `*.webmanifest`. They're artifacts of an HTTrack mirror dump — see [Tech-Debt](#-tech-debt--known-issues).

---

## 🚀 Tech Stack

| Layer | Technology / Version | Notes |
|-------|----------------------|-------|
| Markup | HTML5 (3 standalone pages, no template engine) | BEM-style classes throughout (`menu-panel__menu-item`, `studio-reviews__title`, etc.) |
| Layout | **Bootstrap 4** | grid + utilities; bundle includes Popper |
| Styles | Custom Arquito theme (`assets/css/theme.css`) + `responsive.css` + `dark.css` | Roboto (300/400/500/700) + Teko (300/400) from Google Fonts |
| JS framework | **jQuery 3.5.1** | Loaded twice on `home.html` / `service.html` (CDN + bundled local copy) |
| Animations | **GSAP** (`TweenMax.min.js`, `TimelineLite.min.js`) + **Animsition** | Page transitions and motion |
| Carousel | **Swiper** | Testimonials + reviewer thumbnails (synced) |
| Lightbox | **Magnific Popup** | Loaded but not invoked on current pages |
| Masonry | **Isotope.pkgd** | Loaded but not invoked on current pages |
| Parallax | **Rellax** | Hero background on `home.html` |
| Before/After | **TwentyTwenty** + `jquery.event.move.js` | "Our Quality Work" slider on `home.html` |
| Other vendored (unused on current pages) | PagePiling, jQuerySimpleCounter, typed.js, vivus.js, Slider Revolution + 9 extensions + panorama / slicey addons | Carried over from the Arquito theme |
| Maps | **Google Maps JavaScript API** | API key is hard-coded in `contact.html` (see Tech-Debt) |
| Icons | **Icofont** + **Linearicons** + an inline SVG sprite | Twitter / Facebook / Google Plus icofont icons in nav + footer |
| Polyfills | `polyfill.min.js`, `svg4everybody.legacy.min.js` | For IE 11 compatibility |

### Brand colours

| Token | Hex | Used for |
|-------|-----|----------|
| Black | `#000000` | Header background, menu panel background |
| Orange accent | `#f24a00` | Hamburger/close button background in the off-canvas menu |
| White | `#ffffff` | Logo, hamburger bar inside the orange button |

---

## 🛠️ Local Setup

There is no build step. You just need to serve the static files.

### Option 1 — Open directly
```bash
git clone https://github.com/abdullahek/Virtual_home_photography.git
cd Virtual_home_photography
xdg-open home.html      # Linux
open home.html          # macOS
start home.html         # Windows
```

> ⚠️ Some plugins (Animsition, the live-tour `<iframe>`, Google Maps) won't load reliably from `file://` because of mixed-content / origin restrictions. For best results use a local web server (next section).

### Option 2 — Local HTTP server

```bash
# Python 3
python3 -m http.server 8080

# Node
npx http-server -p 8080

# PHP
php -S localhost:8080
```

Then open <http://localhost:8080/home.html>.

### Deploying as a static site
Drop the entire repo into:
- **GitHub Pages** — point to `master` / root.
- **Netlify / Vercel / Cloudflare Pages** — no build command, no output directory. (Set the *Default file* to `home.html`, since there's no `index.html`.)
- **Any S3 / Nginx / Apache** — same idea.

### Configure the Google Map
`contact.html` currently contains a **publicly committed Google Maps JS API key** (line 179). Before deploying:
1. Revoke that key in the Google Cloud console.
2. Provision a new key restricted to your production domain.
3. Replace the `<script src="https://maps.google.com/maps/api/js?key=…">` in `contact.html` with the new key (ideally injected at build/deploy time, not committed).
4. Update the `data-lat` / `data-lng` on `<div id="map">` to the studio's actual Brampton coordinates (currently set to Melbourne, Australia).

---

## 🔄 Site Map

```
                            ┌──────────────────┐
                            │   home.html  🏠  │ ◀── default landing
                            │   (Landing)      │
                            └────────┬─────────┘
                                     │ off-canvas hamburger menu
                ┌────────────────────┼────────────────────┐
                ▼                    ▼                    ▼
         service.html          contact.html        (Pricing / Samples /
       (Services + live      (Map + studio info     Recent Projects
       virtual-tour iframe)   + contact form)        ─ menu items exist
                                                     but link to #submenu*
                                                     anchors only — no real
                                                     pages have been built)
```

---

## 📝 Page Reference Table

| File | `<title>` | Hero / Intro | Primary content | External / heavy embeds |
|------|-----------|--------------|-----------------|--------------------------|
| `home.html` | Virtual Home Photography | Rellax parallax hero (`img/bg_home.jpg`) — *Best Solutions for Photography* | About block, 4-tile Zoom-Services grid (Photos / Virtual Tour / Aerial / 3D Tour), TwentyTwenty before/after, Swiper testimonials | Roboto + Teko Google Fonts, jQuery CDN, Cloudflare email-decode (referenced via broken relative path) |
| `service.html` | Virtual Home Photography | Static "Services" heading | Two `article-listing-item` masonry cards (Photos with `bg_right.jpg` cover, Virtual Tour with live tour iframe) | Live iframe to `virtualhomephotography.com/tour/Panos/2200LS/tour.html` |
| `contact.html` | Virtual Home Photography | Full-width Google Map (currently centred on Melbourne, Australia) | Studio info column (address, `tel:` link, email) + 3-field "Get in touch" form (Name / Subject / Message) | Google Maps JavaScript API (with a hard-coded API key) |

---

## 🐛 Tech-Debt / Known Issues

The site renders cleanly, but here's what needs cleanup before it's production-grade:

### 🔴 Critical — Security & secrets
- **Google Maps API key is committed to source.** `contact.html` line 179 hard-codes a key. Anyone who clones / browses this repo can read it. Revoke that key in the Google Cloud console **today** and provision a new domain-restricted one that you inject at deploy time (e.g. an environment-substitution step in Netlify/Vercel).
- **The contact form is non-functional.** `<form class="contact-block__form">` on `contact.html` has no `action`, no `method`, no JavaScript handler — clicking *Send Message* refreshes the page and silently discards everything the visitor typed. Wire it up to a real form-handler service (Formspree, Netlify Forms, AWS SES + Lambda, or an SMTP-backed PHP endpoint like the sister repo's `handler.php`). When you do, also add **CSRF protection**, a **honeypot / reCAPTCHA**, and **server-side validation**.

### 🟠 High — Broken / dead navigation
- **Off-canvas menu items "Services / Pricing / Samples / Recent Projects" all link to `#submenu*` anchors that don't exist** on any page. The only real navigation that works is Home → `home.html`, Services → `service.html` (only on home.html — on service.html and contact.html the Services menu item still points to `#submenu2`!), and Contact Us → `contact.html`. Fix the hrefs.
- **Footer "Quick Links" point Pricing / Samples / Recent Projects / Services to `href="#"`** — every link is a dead self-anchor.
- **The "Order Now" CTAs in `service.html` link to `href="#"`** — should link to a pricing page (which doesn't exist yet).
- **Email links use `<a href="">`** instead of `mailto:` — clicking does nothing.
- **Footer brand link still says `http://paul-themes.com/`** — leftover Arquito theme attribution. Replace with the studio's own homepage URL.
- **`contact.html` footer brand text still says "Arquito"** (`<a href="http://paul-themes.com/" class="logo">Arquito</a>`) — change to "Virtual Home Photography".

### 🟠 High — Site bugs
- **HTTrack provenance comment leaks the source theme.** `contact.html` line 4 still contains *"Mirrored from paul-themes.com/html/arquito/demo/page-contact.html by HTTrack Website Copier/3.x [XR&CO'2014], Tue, 21 Jul 2020 10:25:56 GMT"*. Remove it (and audit other files for similar comments).
- **HTTrack also renamed every non-HTML resource to `.html`.** `favicons/site.html` should be `site.webmanifest`, `assets/fonts/Icofont.html` and `Linearicons.html` should be `.woff2`/`.svg`, and `assets/css/fonts/revicons/revicons90c6.html` (+ `-2.html`, `-3.html`, `-4.html`) should all be Slider Revolution icon-font binaries (`.eot`, `.svg`, `.ttf`, `.woff`). Restore the correct extensions or those resources will return wrong MIME types from your server.
- **`apple-touch-icon` link tags point to `favicons/...` on `contact.html`** but are *missing entirely* on `home.html` / `service.html`. Add them everywhere.
- **`<link rel="manifest" href="favicons/site.html">`** — should be `site.webmanifest` (and the file itself should contain JSON, not HTML).
- **Cloudflare email-decoder script is loaded from a broken relative path** (`../../../cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js`) — also a leftover from the HTTrack mirror. Either drop the script or load it from Cloudflare's CDN.
- **jQuery is loaded twice on `home.html` / `service.html`** — once from `ajax.googleapis.com` in the `<head>` and once locally before `theme.js`. Pick one source.
- **Inline `<style>` overrides in the HTML.** `style="background-color: black;"` and `style="background-color: #f24a00;"` etc. are scattered across the markup. Promote them to classes in `theme.css`.
- **Hero alt attributes are empty** on every `<img>` (logo, bg_right, before/after). Bad for SEO and screen readers. Fill them in.
- **Footer copyright stuck on `© 2020`** — outdated. Render it dynamically with a tiny script: `document.getElementById('year').textContent = new Date().getFullYear();`
- **Google Map placeholder coordinates** — `data-lat="-37.816248" data-lng="144.965981"` is **Melbourne, Australia**. The studio is in Brampton, Ontario, Canada (≈ `43.7315, -79.7624`).
- **Side-menu hamburger toggle is left wide open by default** in some browsers because of the `class="collapsed collapsed"` (collapsed listed twice) duplication on the *Pricing* link. Remove the duplicate.
- **The page-load Animsition fade can leave the page invisible** if `animsition.min.js` fails to load (e.g. on slow networks). Add a JS-disabled fallback `<noscript>` style that forces `.page__inner.animsition { opacity: 1 !important; }`.

### 🟡 Medium — Performance & dead code
- **Massive vendored bundle, most of it unused.** Slider Revolution + 9 extensions + 2 add-ons (panorama, slicey), PagePiling, Isotope, jQuerySimpleCounter, typed.js and vivus.js are all loaded on every page even though none of them are actually invoked by `theme.js`. Removing them will cut ~1 MB from the page weight.
- **No `<meta name="description">`** — the existing tag is empty (`content=""`). Each page should have a unique 150-character description.
- **No Open Graph or Twitter Card meta tags** — listings shared on social media will look bare.
- **No image optimisation** — `bg_home.jpg`, `bg_right.jpg`, `before.jpg`, `after.jpg` are large desktop JPEGs served at full size to mobile too. Consider modern formats (WebP/AVIF) and `srcset` / `<picture>`.
- **Google Fonts import is render-blocking** (synchronous `<link>` in `<head>`). Add `media="print" onload="this.media='all'"` or a `display=swap` query param to mitigate FOIT.

### 🟢 Low — Cleanup
- **`assets/css/assets/`** contains reference HTML snippets (`gridtile.html`, `coloredbg.html`, `loader.gif`) that are not used by the site. Move them to a `docs/` folder or delete.
- **Inline SVG sprite (`#icon_ion-icon-apps`)** is defined on every page but never `<use>`d. Remove or actually use it.
- **Dead file `assets/js/jquery.viewport.min.js`** is loaded but its functionality isn't invoked anywhere.
- **No `index.html`.** Most static hosts will 404 on `/`. Either rename `home.html` → `index.html` or add a tiny `index.html` that does `<meta http-equiv="refresh" content="0; url=home.html">`.
- **No SEO-friendly URL structure** — visitors see `.html` extensions in the address bar.

---

## 🌱 Suggested Next Steps

If you want to take this from a working brochure site to something *maintainable and production-ready*:

1. ✅ **Revoke the committed Google Maps API key**, provision a new domain-restricted one, and inject it at deploy time instead of committing.
2. ✅ **Wire the contact form to a real backend** (Formspree, Netlify Forms, or an SMTP endpoint), with CSRF, honeypot, and server-side validation.
3. ✅ **Fix the navigation.** All the menu items currently point to `#submenu*` placeholders — either build the missing pages (Pricing, Samples, Recent Projects) or hide the links until they exist.
4. ✅ **Remove HTTrack artefacts** — strip the *"Mirrored from paul-themes.com…"* comment, restore correct extensions on all `*.html` files that are actually icon fonts / SVG / webmanifest, and remove the Cloudflare email-decoder script.
5. ✅ **Strip the unused vendor bundle** (Slider Revolution + add-ons, PagePiling, Isotope, jQuerySimpleCounter, typed, vivus) — instant ~1 MB win.
6. ✅ **Fix Google Map placeholder data** in both `contact.html` (`data-lat`/`data-lng`) and `assets/js/gmap.js` (centre, marker title, info-window).
7. ✅ **Replace the dead `href="#"` and `href=""` links** in the footer + service-page CTAs with real targets.
8. ✅ **Add meta descriptions, Open Graph and Twitter Card tags** to every page for SEO and richer social previews.
9. ✅ **Render the footer copyright year dynamically** so it's never out of date.
10. ✅ **Add `index.html`** (or rename `home.html`) so visiting the site root doesn't 404.
11. ✅ **Convert hero / before/after images to WebP + `srcset`** so mobile visitors don't download desktop-sized JPEGs.
12. ✅ **Add ARIA labels and `alt` text** for the hamburger button, off-canvas menu, every `<img>`, and the TwentyTwenty handles.
13. ✅ **Migrate to a tiny SSG** (Eleventy, Astro, or even plain `gulp-include`) so the off-canvas menu / footer / `<head>` block can live in a single partial instead of being copy-pasted across three files.
14. ✅ **Replace the *Arquito* footer logo text** (`contact.html`) with "Virtual Home Photography" and remove the `paul-themes.com` link.

---

## 📄 License

The studio's website content (copy, photography, brand) is © Virtual Home Photography. The underlying **Arquito** HTML theme is the property of **paul-themes.com** and was licensed for use on this project. The hand-written code in this repository is provided as-is for educational / portfolio purposes; all rights reserved by the author unless otherwise noted.

---

## 👤 Author / Maintainer

**Abdullah EK** — [@abdullahek](https://github.com/abdullahek)

> A modern, three-page static front-end for a Brampton, Ontario real-estate photography studio — built on the Arquito theme with Animsition page transitions, a Rellax parallax hero, a TwentyTwenty before/after slider, Swiper testimonials, and a live embedded 360° virtual tour.

---

<p align="center">
  Bringing every corner of every home to life — same-day HD photos and 360° virtual tours 🏠📸
</p>
