# Branding and Visual Direction

Visual specification for the SF Pacific War Archives Infrastructure Project.

Use this folder as the default reference for:

- public-facing web apps
- internal HTML reports
- slide decks and one-page briefs
- prototype UI work
- future design-system or front-end implementation

## Folder Contents

- `brand-tokens.css`: reusable CSS variables and a small set of brand utility
  classes
- `brand-preview.html`: local visual preview for quick reference
- `assets/memorial-hall-logo.png`: primary Memorial Hall logo for reports, hero
  blocks, navigation, and title pages

## Brand Qualities

- commemorative
- bilingual
- scholarly
- calm
- structured
- modern
- warm without nostalgia effects

## Palette

| Token | Hex | Use |
| --- | --- | --- |
| Paper | `#F7F1E6` | Main page background |
| Warm Paper | `#ECE1D0` | Alternate surfaces, blocks, infoboxes |
| Stone | `#CDBCA0` | Borders, dividers, subdued labels |
| Ink | `#1E1A17` | Primary body text |
| Soft Ink | `#51473F` | Secondary text, captions |
| Memorial Navy | `#21374D` | Primary structural color |
| Archive Blue | `#2B4762` | Hero surfaces, charts, secondary UI |
| Royal Slate | `#3B5B78` | Lighter blue support tone |
| Antique Brass | `#B58A42` | Highlights, keylines, small accents |
| Deep Brass | `#846229` | Hover, section markers, engraved details |
| Seal Red | `#8B3C35` | Rare emphasis, alerts, editorial markers |
| Sage Grey | `#6D796E` | Secondary series, quiet success states |
| Mist | `#D6DDE2` | Tables, report grids, cool neutral support |

### Recommended color balance

- 55% to 65% paper and warm-paper surfaces
- 20% to 25% navy/blue structural fields
- 10% to 15% ink typography
- 5% to 8% brass accents
- 2% to 4% seal red or sage support

### Color usage rules

- Navy should carry structure, not every accent.
- Brass should guide attention, not flood the interface.
- Seal red should be rare and intentional.
- Body text should almost never be gold.
- Large fields should prefer paper, stone, or navy instead of saturated color.

## Typography

### Primary serif voice

Use for page titles, exhibit headings, cover treatments, and quoted text:

- `Cormorant Garamond`
- `Source Han Serif SC`
- `Noto Serif SC`

Fallback stack in `brand-tokens.css` also supports system serif rendering when
those fonts are unavailable.

### Primary sans voice

Use for body copy, filters, metadata tables, navigation, and UI components:

- `IBM Plex Sans`
- `Source Han Sans SC`
- `Noto Sans SC`

### Monospaced support voice

Use for identifiers, accession numbers, technical metadata, and code-like
labels:

- `IBM Plex Mono`

### Typography rules

- Serif for titles and moments of memory.
- Sans for navigation, UI clarity, and metadata density.
- Chinese should use serious text faces, not faux-calligraphy.
- Avoid extremely tight tracking in Chinese.
- Do not set long paragraphs in decorative serif display cuts.

## Form Language

### Memorial Hall logo

Recommended treatment:

- official WWII Pacific War Memorial Hall mark
- clear, high-contrast placement
- used at title-page, divider, or navigation-mark scale
- reserved for one primary mark treatment per surface

Avoid:

- ornamental floral motifs
- unrelated substitute marks
- repeating the logo on every card or button

### Architectural framing

Use these framing moves in interface form:

- arched hero frames
- plaque-like panels
- stone-border insets
- axial section openings
- colonnade rhythm in grids and card spacing

### Editorial detailing

- fine dividers
- measured spacing
- slightly asymmetrical reading compositions
- restrained red editorial marks

### Avoid decorative overload

- brushstroke effects
- fake rice-paper textures
- loud seal-stamp gimmicks
- dense ornamental borders
- crowded hero sections

## Product Translation

### Apps

- Use paper as the default background.
- Use navy for headers, section anchors, and major contrast zones.
- Keep cards soft, pale, and minimally bordered.
- Prefer one strong hero moment over many competing decorative elements.

### HTML reports

- Use a title block with serif headline and small brass kicker.
- Allow one restrained badge treatment per opening page.
- Tables should be quiet and highly readable.
- Charts should use navy first, brass second, sage third, and seal red only for
  exceptional emphasis.

### Slide decks

- Favor strong opening titles and disciplined margins.
- Let photography or documents carry emotional weight.
- Keep ornament concentrated in cover/opening slides and section breaks.

## Imagery Rules

- Prefer archival photographs, documents, maps, and exhibition material.
- Use subtle warm or neutral correction instead of heavy sepia.
- Keep crops clean and dignified.
- Caption blocks can sit on navy or warm-paper panels.
- Avoid military-game visual tropes, explosions, distressed textures, and
  dramatic red-black posterization unless a specific exhibit demands it.

## What Not To Do

- Do not overuse bright red, bright gold, or patriotic iconography.
- Do not use dragons, clouds, scrollwork, or generic "Chinese style" ornaments.
- Do not use faux-handwritten fonts.
- Do not bury interfaces under paper texture and nostalgia filters.
- Do not make everything look antique; the project is historical, but the
  product should still feel current.
- Do not use rainbow dashboard palettes for reports.

## Implementation Notes

If a future app or report wants a starting point, load:

```html
<link rel="stylesheet" href="../../docs/standards/branding/brand-tokens.css">
```

For quick visual review, open:

- `docs/standards/branding/brand-preview.html`
