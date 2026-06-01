# Oasis Nails & Spa — Website

Marketing and booking website for **Oasis Nails & Spa**, a luxury nail studio located in Wake Forest, NC.

---

## Overview

Single-page static website built with plain HTML, CSS, and vanilla JavaScript — no frameworks, no build tools, no dependencies beyond a Google Fonts import. The entire site lives in one file (`index.html`) for simplicity and fast deployment.

---

## Structure

```
oasis-nails-and-spa-website/
├── index.html                # Complete site — HTML + CSS + JS in one file
└── Assets/
    ├── manicure.jpg          # Services section — Manicures card background
    ├── pedicure.jpg          # Services section — Pedicures card background
    ├── waxing.jpg            # Services section — Waxing card background
    ├── temp nail polish pic.jpg  # Hero image
    ├── temp inside spa.jpg   # About section image
    ├── Angie.jpg             # Artist photo
    ├── Anne.jpg
    ├── Diana.jpg
    ├── Helen.jpg
    ├── Janice.jpg
    ├── Jenna.jpg
    ├── Jimmie.jpg
    ├── Lee.jpg
    ├── Linette.jpg
    ├── Lynn.jpg
    ├── Nancy.jpg
    ├── Ngoc.jpg
    ├── Rose.jpg
    └── Thery.jpg
```

---

## Sections

| Section | Description |
|---|---|
| **Nav** | Fixed top nav with smooth-scroll links and a Book Now CTA. Collapses to a hamburger menu on mobile. |
| **Hero** | Full-width intro with headline, subtext, book button, and phone CTA. |
| **Marquee** | Scrolling ticker of service names. |
| **About** | Studio story and brand pillars. |
| **Services** | Interactive three-category menu (Manicures, Pedicures, Waxing) with a slide-out detail panel and full price list. |
| **Artists** | Horizontally scrollable carousel of artist cards with name and skills. |
| **Reviews** | Horizontally scrollable carousel of Google reviews with rating display. |
| **Booking Policy** | Cancellation, refund, and touch-up policy. |
| **Contact** | Embedded Google Map, address, hours, and Instagram link. |
| **Footer** | Logo, copyright, and footer links. |

---

## Features

- **Booking modal** — opens from any Book CTA; optionally pre-fills a selected service and artist. Calls are placed via the phone link inside the modal.
- **Services menu** — tap a category card to expand a detailed price list panel with scroll-snap navigation.
- **Artist carousel** — scroll-snap carousel with dot indicators and prev/next arrow buttons on desktop. Mobile shows swipe-only with dots.
- **Reviews carousel** — same carousel pattern as artists. Dots visible on mobile; hidden on desktop where all cards are visible at once.
- **Scroll reveal** — `.reveal` elements animate in as they enter the viewport via `IntersectionObserver`.
- **Sticky mobile book button** — fixed bottom bar with a Book Appointment button, visible only on mobile.
- **Directional touch lock** — artist carousel (`pan-x pan-y`) and reviews carousel handle horizontal swipes for navigation while passing vertical swipes through to the page scroll.

---

## Updating Content

### Phone number
Search for `+19196992667` — appears in the hero section and the booking modal CTA.

### Address
Search for `2808 Rogers Rd` — appears in the contact section address block and the Google Maps link.

### Hours
Edit the `<ul class="hours-list">` block inside `#contact`.

### Artists
Edit the `ARTISTS` array in `initCarousel()` inside the `<script>` tag. Each entry takes:
```js
{ name: 'FirstName', ext: 'jpg', skills: ['Skill One', 'Skill Two'] }
```
The corresponding photo must exist at `Assets/FirstName.jpg` (or `.png`, matching the `ext` field).

### Service prices
Edit the `MENU_DATA` object in `initMenu()`. Each item takes:
```js
{ name: 'Service Name', desc: 'Optional description', price: '$XX', note: 'Optional fine print' }
```

### Reviews
Edit the `.review-card` blocks inside `#reviews-track` in the HTML.

### Hero / About images
Replace the files in `Assets/` — filenames are referenced directly in the HTML (`temp nail polish pic.jpg`, `temp inside spa.jpg`).

---

## Deployment

The site is a static file and can be hosted anywhere that serves HTML:

- **GitHub Pages** — push to `main`, enable Pages in repo settings, set source to root.
- **Netlify / Vercel** — drag and drop the repo folder or connect the GitHub repo.
- **Any web host** — upload `oasis-nails-spa.html` and the `Assets/` folder to the server root.

No build step required.

---

## Browser Support

Targets modern evergreen browsers (Chrome, Safari, Firefox, Edge). Uses CSS custom properties, `IntersectionObserver`, scroll snap, and `backdrop-filter` — all widely supported in current browser versions.
