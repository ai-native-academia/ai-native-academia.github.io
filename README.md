# AI-Native Academia @ NeurIPS 2026 — Workshop Website

Single-page static site for the NeurIPS 2026 Workshop on AI-Native Academia.

## Files

- `index.html` — full single-page site (CSS embedded). No build step, no JS framework, no external assets beyond Google Fonts.
- `assets/` — speaker, panelist, and organizer headshots (copied from `../6a0536626a192630b63f8071/figure/`, already face-cropped to square).

## Local preview

```bash
cd website
python3 -m http.server 8000
# open http://localhost:8000
```

Or just open `index.html` in a browser (Google Fonts will load over the network).

## Deploy to GitHub Pages

1. Create a new GitHub repo, e.g. `ai-native-academia`.
2. Push the contents of this `website/` folder to the repo root (so `index.html` is at the top level).
3. In repo settings → Pages → choose `Deploy from a branch` → `main` → `/` (root) → Save.
4. Site is live at `https://<your-org>.github.io/ai-native-academia/`.

If you'd prefer a `<org>.github.io` URL (e.g. `ai-native-academia.github.io`), name the repo `ai-native-academia.github.io` and push to `main`.

## Design

Style follows [curateddata.github.io](https://curateddata.github.io) (ECCV 2026 workshop): numbered single-page sections, generous whitespace, Fraunces (serif) for display + Inter for body, warm-paper background, photo-grid for speakers and organizers, sticky top nav.

## Updating the cast

When the speaker / panel / organizer list changes in the LaTeX proposal:

1. Update the corresponding `<div class="person">` block in `index.html`.
2. Drop the new headshot into `assets/` (square JPG/PNG, ≥150×150).

If the proposal's `figure/` folder changes, re-copy:

```bash
cp ../6a0536626a192630b63f8071/figure/{zou,cho,su,sharonli,raffel,peng,yisongyue,humphreyshi,dudik,atlas,denghui,kezia}.* assets/ 2>/dev/null
```

## Layout / sections

| # | Section       | Source in proposal |
| - | ------------- | ------------------ |
| - | Hero          | Workshop title + Tagline |
| 01 | Overview     | Why now + The concept + Convergence point |
| 02 | Call for Papers | 8-topic table + Submission tracks |
| 03 | Important Dates | Submission \& Timeline |
| 04 | Invited Speakers | Cast table (top 6) |
| 05 | All-PC-Chair Panel | Cast table (bottom 5 + moderator) |
| 06 | Organizers  | Organizer Information section |
