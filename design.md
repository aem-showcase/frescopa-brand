# Fréscopa — Design Reference
> Machine-readable design token and style guide for use when building Frescopa digital assets.
> Last updated: 2026 Edition

---

## Brand in One Line

**"Premium beverages and the artisan appliances that bring them to life."**

Fréscopa is a lifestyle brand for consumers (B2C) and an end-to-end beverage solutions partner for businesses (B2B). The café showroom bridges both.

---

## Color Tokens

These are the authoritative CSS custom properties from the live codebase. Always use these values — do not approximate.

```css
:root {
  --frescopa-color-background: #F4E9DC; /* Cream — page background */
  --frescopa-color-brand:      #A33532; /* Crimson — primary brand, CTAs */
  --frescopa-color-primary:    #00647D; /* Teal — B2B lead color, links */
  --frescopa-color-secondary:  #DC6E52; /* Terracotta — B2C lead color, headlines */
  --frescopa-color-tertiary:   #EBA439; /* Amber — badges, callouts, juice line */
  --frescopa-color-text:       #58181D; /* Burgundy — body text on light backgrounds */
  --frescopa-color-black:      #2C2C2C; /* Charcoal — dark backgrounds, nav */
}
```

### Named Palette

| Token | Hex | Name | Primary Use |
|---|---|---|---|
| `--frescopa-color-background` | #F4E9DC | Cream | Page background |
| `--frescopa-color-brand` | #A33532 | Crimson | Brand CTAs, key moments |
| `--frescopa-color-primary` | #00647D | Teal | B2B materials, links, secondary buttons |
| `--frescopa-color-secondary` | #DC6E52 | Terracotta | B2C materials, headlines, accents |
| `--frescopa-color-tertiary` | #EBA439 | Amber | Badges, callouts, juice & energy lines |
| `--frescopa-color-text` | #58181D | Burgundy | Body text on light backgrounds |
| `--frescopa-color-black` | #2C2C2C | Charcoal | Dark backgrounds, nav, footers |

### B2C vs B2B Color Rule

- **B2C surfaces**: Terracotta (`--frescopa-color-secondary`) leads. Cream background. Burgundy body text.
- **B2B surfaces**: Teal (`--frescopa-color-primary`) leads. Charcoal or Cream background. Crimson for emphasis.
- Both operate under the same unified Frescopa identity — color is the contextual signal, not a separate brand.

### Accessibility

| Combination | Rating | Use |
|---|---|---|
| Crimson on Cream | WCAG AA | Body text ✓ |
| Teal on Cream | WCAG AA | Body text ✓ |
| Charcoal on Cream | WCAG AAA | Body text ✓ |
| Terracotta on Cream | Below AA | Headlines only — never body text |
| Amber on Cream | Fails | Never use for text |

---

## Typography

### Typefaces

```css
--font-display: 'Playfair Display', Georgia, serif;
--font-body:    'DM Sans', sans-serif;
--font-mono:    'DM Mono', monospace;
```

Google Fonts import:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
```

### Type Hierarchy

| Role | Typeface | Weight | Size | Notes |
|---|---|---|---|---|
| Display | Playfair Display | Bold (700) | 28pt+ | Letter-spacing: -0.02em |
| Heading 1 | Playfair Display | Bold (700) | 22pt | |
| Heading 2 | Playfair Display | Bold (700) | 16pt | |
| Body | DM Sans | Regular (400) | 11pt / 16px | Line-height: 1.7 |
| Caption | DM Sans | Regular (400) | 9pt | |
| Labels / Mono | DM Mono | Regular (400) | 9–10pt | Uppercase, letter-spacing: 0.1–0.18em |

### Typography Rules

- Display and headings always use Playfair Display
- Body copy always uses DM Sans
- Mono is reserved for: labels, metadata, code tokens, section numbers, technical callouts
- Italic Playfair Display is used for quotes, promises, and brand statements
- Never use Arial, Inter, Roboto, or system fonts in brand-facing surfaces

---

## Spacing & Layout

```css
--nav-height:    64px;
--section-gap:   120px;   /* vertical padding between major sections */
--content-width: 1100px;  /* max content width */
--site-width:    1360px;  /* max site width */
```

### Layout Conventions

- Content max-width: 1100px, centered
- Section padding: 120px top/bottom, 10vw left/right
- Two-column grids: `1fr 1fr` or `1fr 2fr` (thirds)
- Card grids: `repeat(auto-fill, minmax(150px, 1fr))`
- Gap between grid items: 2px (flush panel style) or 20–24px (card style)

---

## Logo

### Variants

| Variant | When to use |
|---|---|
| Full lockup — light | Light/cream backgrounds |
| Full lockup — dark | Dark/charcoal backgrounds |
| Bean mark only | Small sizes (≤32px digital, ≤10mm print), established brand contexts only |

### Colors per Background

| Background | Wordmark color | Line color | Bean color |
|---|---|---|---|
| Light (Cream/White) | Burgundy `#58181D` | Burgundy `#58181D` | Amber `#EBA439` |
| Dark (Charcoal/Black) | Cream `#F4E9DC` | Cream `#F4E9DC` | Amber `#EBA439` |
| Brand (Crimson) | Cream `#F4E9DC` | Cream `#F4E9DC` | Amber `#EBA439` |

### Minimum Sizes

- Print: 25mm / 1 inch — full lockup
- Digital: 120px wide — full lockup; 32px — bean mark only

### Clear Space

Minimum clear space on all sides = height of the accent on the 'é' character.

### Misuse — Never

- Stretch or distort the logo
- Change logo colors outside the approved palette
- Place on busy or cluttered backgrounds
- Add drop shadows, outlines, or gradients
- Rotate or skew
- Use the wordmark without the bean mark
- Use the standalone bean mark at large scale without the wordmark nearby

---

## Component Conventions

### Buttons / CTAs

- Use sentence case: "Shop now", "Find a location" — never ALL CAPS beyond 3 letters
- Primary: Crimson background, Cream text
- Secondary: Teal background, Cream text (B2B contexts)
- Outline: Terracotta border, Terracotta text (B2C contexts)
- Border radius: 4–6px (refined, not pill-shaped)

### Cards

- Background: white or Cream (`#F4E9DC`)
- Border radius: 10–12px
- Box shadow: `0 2px 16px rgba(44,44,44,0.06)`
- Hover: deepen shadow or lighten background slightly
- Internal padding: 32–40px

### Dividers / Rules

- Color: Terracotta (`#DC6E52`) for B2C, Teal (`#00647D`) for B2B
- Weight: 2px for section dividers, 1px for inline rules
- Never use tables as visual dividers

### Highlight / Callout Blocks

- Brand promise / quote: left border 4px Terracotta, background `rgba(220,110,82,0.07)`
- B2B promise: left border 4px Teal, background `rgba(0,100,125,0.07)`
- Warning / note: left border 3px Amber, background `rgba(235,164,57,0.1)`
- Restriction / error: background `rgba(163,53,50,0.05)`, border `rgba(163,53,50,0.15)`

### Section Labels (Eyebrows)

```css
font-family: var(--font-mono);
font-size: 0.7rem;
letter-spacing: 0.18em;
text-transform: uppercase;
color: var(--frescopa-color-secondary); /* Terracotta for B2C */
```

### Navigation

- Background: Charcoal `#2C2C2C`
- Bottom border: 2px Terracotta
- Link style: DM Sans, 0.72rem, uppercase, letter-spacing 0.08em
- Grouped dropdowns preferred over flat link lists
- Dropdown background: `#1a1a1a`, border `rgba(244,233,220,0.08)`, border-radius 8px

---

## Motion & Animation

- Page load: `fadeUp` stagger — `opacity: 0 → 1`, `translateY: 24px → 0`, duration 0.8s
- Scroll reveal: IntersectionObserver, threshold 0.08, `translateY: 32px → 0`, duration 0.7s
- Hover transitions: 0.2s ease for color and background
- Dropdown reveal: 0.18s opacity + translateY(-6px → 0)
- Pulsing elements (e.g. flywheel hub): 3s ease-in-out infinite box-shadow animation
- Principle: Frescopa moves smoothly and intentionally — never rushed, never bouncy

---

## Photography Style

### Approved

- Warm, natural lighting — golden hour preferred
- Outdoor café scenes, morning rituals, relaxed lifestyle moments
- People at ease, not posed — genuine enjoyment or quiet contemplation
- Color palette: warm browns, creams, ambers, earthy terracottas
- For juice/energy lines: fresh greens, warm ambers, vibrant fruit hues

### Not Approved

- Cold, desaturated, or high-contrast editorial tones
- Adventure, sport, or utility contexts
- Staged stock-photo compositions
- Heavy filters distorting natural colors
- Cluttered or busy backgrounds
- Harsh flash or artificial studio lighting

---

## File Structure (for deployment)

```
/
├── index.html
├── photo-cafe.jpeg        # Lifestyle — outdoor café
├── photo-golden.jpeg      # Lifestyle — golden hour hero
├── photo-mug.jpeg         # Still life — seasonal atmosphere (supporting only)
└── Frescopa_Logotype.svg  # Master logo file
```

All images referenced relatively — no CDN or absolute paths required.
