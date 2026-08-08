# Michael Lund — Personal Website

A fast, single-page personal portfolio built as static HTML/CSS/JS. No build step, no dependencies — just open `index.html`.

## Structure

```
.
├── index.html                                  # The entire site (styles + scripts inlined)
├── assets/
│   ├── Michael_Lund_Resume.pdf                 # Linked by the "Download résumé" buttons
│   ├── Wage_Garnishment_Case_Study_Michael_Lund.pdf  # Redacted case-study work sample
│   └── favicon.svg                             # Browser-tab icon (ML monogram)
└── README.md
```

## Editing

Everything lives in `index.html`. Common tweaks:

- **Copy / wording** — edit the text directly inside each `<section>`.
- **Colors** — change the CSS variables in the `:root` block near the top (e.g. `--accent` is the green highlight).
- **Résumé** — replace `assets/Michael_Lund_Resume.pdf` with a new file of the same name and every download link updates automatically.
- **Sections** — each block is clearly commented (`<!-- HERO -->`, `<!-- SELECTED TRADES -->`, etc.).

## Viewing locally

Just open the file, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying (free options)

**GitHub Pages**
1. Push to GitHub → repo **Settings → Pages**.
2. Source: *Deploy from a branch*, pick your branch, folder `/ (root)`.
3. Live at `https://<username>.github.io/<repo>/` within a minute.

**Vercel / Netlify**
- Import the repo (or drag-and-drop the folder). No build command needed — it's static. Both give you a free HTTPS URL and let you attach a custom domain (e.g. `michaellund.com`).

## Notes

- Projects lead the page (proof of work first), followed by Experience, Skills, Trades, About, and Contact.
- A **Build / Operate** filter at the top of Projects (mirrored in Experience) tags and toggles every project and role by the kind of work it was.
- The design is skimmable by default with detail on demand. Short summaries up front; the visitor pulls depth.
  - The hero is a full-bleed wordmark: the name is the only large element, with small corner text hugging the screen edges. On load the two name lines slide up from a mask; on scroll they slide apart to the sides and fade. Reduced-motion shows the name statically.
  - A second "statement" screen follows the hero: the one-line pitch (keywords bolded), an availability block, the CTAs, and a scrolling tag marquee (paused under reduced-motion).
  - Projects are flip cards (two highlighted "Featured" ones plus a grid). The front shows the title and meta; hover flips to the summary; a click opens the full dossier in a modal (content in `<template>` elements; closes on the button, overlay-click, or Esc). The Build/Operate filter applies to projects only.
  - Experience is an accordion: one role per line, bullets expand on click. Role titles and bullets follow the résumé's capitalization.
  - Selected trades are flip cards. The essentials sit on the front, the write-up on the back, revealed on hover or tap.
  - A cursor spotlight (radial glow) follows the pointer on fine-pointer devices, off under reduced-motion.
- `assets/ticket-drop-playbook.html` is a standalone, themed rendering of the ticket-drop operations playbook, linked from that project's dossier.
- Copy follows a set of anti-AI-writing rules: no em dashes, straight quotes, no emoji, plain verbs, specific facts, and a flat confident voice.
- Fully responsive, keyboard-accessible, and respects `prefers-reduced-motion`.
- The phone number from the résumé is intentionally **not** published on the site; contact routes through email and LinkedIn.
- The case-study PDF is a **redacted** version of the original: the two company names it referenced are blacked out and the underlying text removed (true redaction, not just an overlay), so nothing is recoverable by copy/paste or search.
