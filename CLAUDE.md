# Garden Suite Website

Marketing website for **Garden Suite**, a family-run countryside events venue in Pontlliw, Swansea.
Plain static HTML + CSS (no build step, no framework). Hosted on Manbir's server, which auto-deploys from the `main` branch of this GitHub repo: whatever is on `main` is the live site. SSL is set up on the server.

## Business details (use these exactly)

- **Name:** Garden Suite
- **Address:** Bryntirion Road, Pontlliw, Swansea SA4 9DY
- **Phone:** 01792 882409 (link as `tel:+441792882409`)
- **Email (website):** events@gardensuite.co.uk
- **Location notes:** just off M4 junctions 47 & 48, free on-site parking, ~15 minutes from Swansea city centre
- **Map coordinates:** 51.6895, -4.0319
- **Events:** weddings, birthdays, corporate, christenings, wakes, special occasions. Customised and bespoke menus.
- **Viewings:** by appointment, seven days a week

## Files

| File | Purpose |
|---|---|
| `index.html` | Home page: hero, "What we do", "Find us" (Leaflet map), enquiry form, footer |
| `contact.html` | Contact page: phone, email, address, visiting info, map |
| `styles.css` | All site styling. Imports `brand/tokens.css` and Google Fonts |
| `brand/tokens.css` | Brand design tokens (colours, fonts, spacing) as CSS variables (`--gs-*`) |
| `brand/tokens.json` | Same tokens, machine-readable |
| `brand/README.txt` | Brand kit summary: colours, typography, logo rules |
| `brand/logo/` | Logo files (SVG + PNG exports, favicons) |

## Brand rules

**Colours.** Always use the `--gs-*` variables from `brand/tokens.css`, never hard-coded hex.
- Forest `#3E4A2E` (logo, headings, buttons), Leaf `#8FA078`, Paper `#FAF7F0` (page background), Ink `#1F1B16`
- Support: Olive `#6B7A55` (labels/meta), Taupe `#A89882` (secondary text)
- Sage `#E5E8DC` and Cream `#F5F0E6` are **backgrounds only, never text**

**Typography**
- Manrope for headings and body (weights 300/500/600)
- JetBrains Mono for small labels/nav: UPPERCASE, 0.32em letter-spacing (`.gs-label` style)

**Logo**
- Primary logo on Paper/Cream/Sage backgrounds; Reverse or mono-white logo on Ink/Forest backgrounds
- Never stretch, rotate, recolour the leaves, or add shadows/glows
- Use the sprig mark alone below 120px wide

**Tone of voice.** Warm, friendly, plain-spoken, a little understated. Short sentences. British English
(e.g. "colour", "personalised"). Headlines are short and confident ("Events, Done Properly.").

## Working on the site

- Preview locally: `python3 -m http.server 4173`, then open http://localhost:4173 (also set up in `.claude/launch.json`).
- Keep both pages consistent: header, footer, phone and email appear on **both** `index.html` and `contact.html`, so update both.
- Check changes on mobile width as well as desktop.
- To publish: commit and push to `main`. Manbir's server picks it up automatically.
- **Site reverted to its original state (Nov 2026)** at the owner's request: old phone number 01792 882409 and the Leaflet map are back. A phone update to 01792 981444 (commit f65f502) and a keyless Google Maps fix (commit 01ff607) are in history if wanted again.
- **Saved redesign:** a deck-style homepage (dark header with centred logo tab, hero video, Playfair Display / Cinzel / Great Vibes) is saved in git history at commit `999a922` ("Launch new homepage from the website deck"); restore with `git checkout 999a922 -- index.html images video`. It was live briefly in Nov 2026, then the owner chose to go back to this original homepage. Restore it from that tag if asked.

## Known to-dos

- **Enquiry form doesn't send anything yet.** It only shows a thank-you message. It needs a form service (e.g. Formspree) or an email link to actually deliver enquiries.
- **Photos are stock placeholders** from Unsplash. Replace with real photos of the venue.
- **Instagram link** in the footer points to `instagram.com/`, so it needs the real account URL.
- The brand kit README lists `hello@gardensuite.wales`, while the website uses `events@gardensuite.co.uk`. Confirm which is correct.
