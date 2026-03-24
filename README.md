# StartIQ.ai — Frontend Website

**AI-Powered Startup Intelligence Platform**
Founder: Shashwat Sharma | shashwatdogra13@gmail.com

---

## How to Run in VS Code

### Option 1 — Live Server (Recommended)
1. Open this folder in VS Code
2. Install the **Live Server** extension (ritwickdey.LiveServer)
3. Right-click `index.html` → **Open with Live Server**
4. Site opens at `http://127.0.0.1:5500`

### Option 2 — Simple HTTP Server
```bash
# Python 3
python3 -m http.server 3000

# Then open: http://localhost:3000
```

---

## File Structure

```
startiq/
│
├── index.html              ← MAIN HOMEPAGE (start here)
│
├── css/
│   ├── variables.css       ← All design tokens (colours, fonts, spacing)
│   ├── global.css          ← Reset, base styles, buttons, layout
│   ├── animations.css      ← All keyframes + scroll reveal system
│   ├── navbar.css          ← Navigation bar styles
│   ├── components.css      ← Reusable UI: cards, tabs, stats, ticker
│   └── sections.css        ← Every page section: hero, about, problem...
│
├── js/
│   ├── main.js             ← Cursor, navbar, reveal, counters, tabs, scroll
│   └── blobs.js            ← Canvas blob animation engine
│
├── pages/
│   ├── about.html          ← About Us page
│   ├── privacy.html        ← Privacy Policy
│   └── terms.html          ← Terms of Use
│
└── assets/
    ├── images/             ← Add your images here (logo PNG, OG image, etc.)
    └── icons/              ← Add favicon files here
```

---

## CSS Architecture

| File | Purpose |
|------|---------|
| `variables.css` | Every colour, font, spacing token. Change things here to reskin the whole site. |
| `global.css` | Base reset, body, container, headings, buttons. Never put page-specific styles here. |
| `animations.css` | All `@keyframes` and the `.rv` / `.rv.in` scroll reveal system. |
| `navbar.css` | Nav only. Sticky behaviour, mobile menu, hamburger. |
| `components.css` | Feature cards, stat boxes, role tabs, problem cells, insight cards. |
| `sections.css` | Layout and spacing for every section: `#hero`, `#about`, `#problem`, `#platform`, `#how`, `#impact`, `#insights`, `#cta`, `footer`. |

---

## JS Architecture

| File | What it does |
|------|-------------|
| `main.js` | Page loader, custom cursor, navbar sticky + active link, scroll reveal (IntersectionObserver), counter animations, role tab switching, smooth anchor scroll. |
| `blobs.js` | `BlobCanvas` class — draws organic animated shapes on `<canvas>` elements. Each section has its own canvas. Automatically initialised on window load. |

---

## Adding New Pages

1. Copy `pages/about.html` as a template
2. Update `<title>` and content
3. CSS/JS paths use `../css/` and `../js/` (one level up)
4. Add a link in `footer-col` inside `index.html`

---

## Customisation Quick Reference

### Change brand colour (rose/pink)
In `css/variables.css`:
```css
--rose:   #ff2d6b;   /* Main accent */
--rose-2: #ff6b95;   /* Lighter variant */
```

### Change fonts
In `css/variables.css`:
```css
--font-display: 'Playfair Display', Georgia, serif;
--font-mono:    'Orbitron', monospace;
--font-body:    'Outfit', sans-serif;
```
Also update the Google Fonts `<link>` in `index.html`.

### Add a new section
1. Add HTML section in `index.html`
2. Add section styles in `css/sections.css`
3. Add a blob canvas if you want animated background
4. Register the blob in `js/blobs.js` configs array

---

## Next Steps (Backend Integration)

The backend runs on **n8n automation**. When ready to connect:

- `POST /api/validate-idea` — Idea Validation AI form
- `POST /api/contact` — CTA contact form
- `POST /api/register` — Founder registration

Add fetch() calls in `js/main.js` under a new `initForms()` function.

---

## Browser Support
Chrome 90+ | Firefox 88+ | Safari 14+ | Edge 90+

---

*© 2026 StartIQ.ai — Built for serious founders.*
