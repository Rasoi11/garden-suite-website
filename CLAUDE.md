# Garden Suite Website

Marketing website for **Garden Suite**, a family-run countryside events venue in Pontlliw, Swansea.
Plain static HTML + CSS (no build step, no framework). Hosted on Manbir's server, which auto-deploys from the `main` branch of this GitHub repo: whatever is on `main` is the live site. SSL is set up on the server.

## Business details (use these exactly)

- **Name:** Garden Suite
- **Address:** Bryntirion Road, Pontlliw, Swansea SA4 9DY
- **Phone:** 01792 981444 (link as `tel:+441792981444`)
- **Email (website):** events@gardensuite.co.uk
- **Location notes:** just off M4 junctions 47 & 48, free on-site parking, ~15 minutes from Swansea city centre
- **Map coordinates:** 51.6895, -4.0319
- **Events:** weddings, birthdays, corporate, christenings, wakes, special occasions. Customised and bespoke menus.
- **Viewings:** by appointment, seven days a week

## Files

| File | Purpose |
|---|---|
| `index.html` | Home page (Nov 2026 redesign from the website deck): hero video, Weddings, From Intimate to Grand cards, Countryside Location, Make an enquiry. Self-contained styles in the `<style>` block |
| `video/hero.mp4`, `video/hero-720.mp4` | Hero video (1080p desktop, 720p phones), converted from the iPhone original. `images/hero-poster.jpg` shows while it loads |
| `images/` | Homepage photos. `picture-N-*.jpg` match the numbering in the website deck |
| `contact.html` | Contact page: phone, email, address, visiting info, map. Still the old design and not linked from the new homepage |
| `styles.css` | Styling for `contact.html` (old design). Imports `brand/tokens.css` and Google Fonts |
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
- The homepage follows the website deck's look (dark header with centred logo tab, Playfair Display italic headings, Cinzel caps, Great Vibes tagline), not the brand-kit Manrope/forest style. The owner chose this deliberately.

## Known to-dos

- **No enquiry form on the homepage.** Enquiries are by phone or email only. Add a form service (e.g. Formspree) if a form is wanted.
- **Pictures 3 to 6 are not Garden Suite** (stock-style wedding and birthday photos supplied by Rishabh). Replace with real photos from events at the venue. Picture 9 is a soft crop from a deck screenshot; replace with the original file.
- **Instagram and Facebook** are hidden on the homepage until the real account URLs are supplied. There is a marker comment in the enquiry section of `index.html`.
- The brand kit README lists `hello@gardensuite.wales`, while the website uses `events@gardensuite.co.uk`. Confirm which is correct.
