# Stringer Electrical Ltd — Website

A single-page site for Stringer Electrical Ltd (director: Zayne Stringer). Built by OpenFlow.

## Folder layout

```
Stringer Electrical Ltd/
├── index.html                  ← the whole site (HTML + CSS + JS in one file)
├── README.md
├── assets/                     ← web-optimised files the site uses
│   ├── brand/
│   │   ├── logo.jpg            ← original logo (white on black)
│   │   ├── logo-full.png       ← exact logo, transparent (preloader, footer, menu)
│   │   ├── logo-mark.png       ← bolt + circle only (nav, marquee)
│   │   ├── logo-wordmark.png   ← "STRINGER — ELECTRICAL LTD" only (nav)
│   │   └── favicon.png
│   ├── hero/
│   │   ├── hero-video.mp4      ← hero background (compressed from Hero-Vid.mp4)
│   │   ├── hero-poster.jpg     ← shown while the video loads
│   │   └── hero-van-shed.jpg   ← About section photo
│   ├── partner/openflow-wordmark.png  ← footer "Digitally powered by" credit
│   └── projects/               ← project slideshow photos (01–09, graded for web)
└── source-files/
    ├── openflow-wordmark.png   ← full-size OpenFlow wordmark
    └── original-photos/        ← untouched originals, kept for future use
```

`assets/projects/09-hallway-lighting.jpg` is prepared but not in the slideshow, since it's very close to slide 08. You can add it in if you'd like.

## Going live

Upload `index.html` and the `assets/` folder to any static host (Netlify, Vercel, Cloudflare Pages, cPanel and so on). The `source-files/` folder doesn't need to be uploaded. Fonts, GSAP and Lenis load from CDNs.

## Common edits

**Add or swap a project photo:** put the image in `assets/projects/`, then in `index.html` copy one `<figure class="slide">` block in the Projects section. Update the `src`, the `alt`, and the `figcaption` (`data-cat`, `data-title`, plus the description text). The thumbnail, blurred backdrop, caption and counter are all generated automatically.

**Google reviews:** near the bottom of `index.html`, `const REVIEWS = [...]` holds the reviews shown in the slider (3 seconds each). Add a line to add a review, and update `GOOGLE_REVIEW_TOTAL` when the Google count changes. The "+N more" link updates itself.

**Quote form:** every "Get a Quote" button opens the form as a pop-up (it reuses the Contact section form). Right now it opens the visitor's email app with the request filled in, addressed to info@stringerelectrical.co.nz. To receive submissions straight to your inbox instead, create a free form at formspree.io and swap the `mailto` line in the form script for a `fetch()` POST to your Formspree endpoint.
