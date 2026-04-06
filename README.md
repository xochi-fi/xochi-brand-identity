# xochi-brand-identity

Brand assets and visual identity for [Xochi](https://xochi.fi), ETH's Friendly Dark Pool.

Named after Lake Xochimilco, home of the axolotl. The mascot is an axolotl -- soft-bodied, completely observable, regenerative. The metaphor: your spawn point shouldn't determine whether you get privacy. The water doesn't care who's swimming.

## Palette

The palette inverts typical dark-mode convention. Where most dark themes use cool grays with blue accents, Xochi uses warm cream text and muted gold accents over cold near-black backgrounds. The feel is a private members' club, not a SaaS dashboard.

### Core

| Name         | Hex       | Role                    |
| ------------ | --------- | ----------------------- |
| Obsidian     | `#0a0a0c` | Page canvas             |
| Deep Night   | `#12121a` | Panel base              |
| Pearl Cream  | `#e8e4dc` | Primary text            |
| Crypto Frost | `#fdfff9` | Emphasis text           |
| Muted Gold   | `#a89a80` | Primary accent, borders |

### Brand accents

| Name                | Hex       | Role                          |
| ------------------- | --------- | ----------------------------- |
| Axol Coral          | `#ffcd9c` | CTAs, positive values, warmth |
| Decentralized Coral | `#e58476` | Errors, negative values       |
| CryptoWave Sky      | `#58a1c6` | Success states, confirmations |
| Node Indigo         | `#28338b` | Depth, verified tier accent   |

### Trust tier colors

Tier colors are semantic. Only use them for their designated tier -- never decoratively.

| Tier          | Text      | Background               |
| ------------- | --------- | ------------------------ |
| Standard      | `#a89a80` | `rgba(168,154,128,0.15)` |
| Trusted       | `#58a1c6` | `rgba(88,161,198,0.15)`  |
| Verified      | `#7b8ad9` | `rgba(40,51,139,0.15)`   |
| Premium       | `#ffcd9c` | `rgba(255,205,156,0.15)` |
| Institutional | `#e58476` | `rgba(229,132,118,0.15)` |

### Muted Gold opacity scale

Consistent opacity steps for borders, backgrounds, and interaction states:

```
 8%  -- subtle backgrounds
10%  -- light backgrounds, hover states
15%  -- badge backgrounds, borders
25%  -- medium emphasis borders
30%  -- hover borders, active backgrounds
40%  -- glow effects, focus rings
```

### Text opacity scale (Pearl Cream base)

| Level     | Opacity | Use                    |
| --------- | ------- | ---------------------- |
| Primary   | 100%    | Body text, headings    |
| Emphasis  | 80%     | Strong emphasis        |
| Strong    | 70%     | Secondary emphasis     |
| Secondary | 60%     | Labels, descriptions   |
| Muted     | 50%     | Metadata, timestamps   |
| Faint     | 40%     | Placeholders, disabled |
| Hint      | 35%     | Subtle guides          |
| Dim       | 30%     | Decorative elements    |
| Ghost     | 20%     | Barely visible         |
| Barely    | 10%     | Background texture     |

## Typography

All monospace, all the time. Three variants from the [Monaspace](https://github.com/githubnext/monaspace) family by GitHub Next:

| Variant         | Semantic role | Character           |
| --------------- | ------------- | ------------------- |
| Monaspace Argon | Code, numbers | Clean, neutral      |
| Monaspace Neon  | Body text     | Classic, readable   |
| Monaspace Xenon | Headings, UI  | Soft, rounded edges |

No sans-serif. No serif. The terminal/Bloomberg aesthetic is deliberate -- financial data should look like financial data.

### Sizing (fluid, clamp-based)

```
xs:   0.55rem -> 0.65rem    (fine print)
sm:   0.70rem -> 0.75rem    (labels)
base: 0.85rem -> 0.95rem    (body)
lg:   1.00rem -> 1.15rem    (subheads)
xl:   1.25rem -> 1.50rem    (section heads)
2xl:  1.50rem -> 2.00rem    (page titles)
3xl:  2.00rem -> 3.00rem    (hero)
```

### Spacing

Letter spacing runs wider than default for monospace readability:

- Body: `0.01em`
- Headings: `0.05em`
- Wide labels: `0.1em`
- Widest (tier badges, status): `0.15em`

Line heights: tight (1.2) for headings, normal (1.5) for UI, relaxed (1.7) for body text.

Tabular figures (`font-variant-numeric: tabular-nums`) on all numeric values -- amounts, prices, balances, fees.

## Visual language

**Dark-native.** Designed for darkness from the start, not a light theme with colors inverted. Near-black backgrounds are the canvas. Information appears through controlled luminance.

**Glassmorphism.** Panels use semi-transparent backgrounds (`rgba(18,18,26,0.85)`) with backdrop blur. Borders at low-opacity muted gold. Three elevation levels: subtle (0.7), standard (0.85), elevated (0.9).

**Atmospheric depth.** Layered backgrounds -- film grain, pearl gradients, floating orbs, water ripples, hexagonal grid patterns. These reinforce the "dark pool" metaphor. Functional, not decorative.

**ASCII only.** No emojis in the interface, documentation, or communications. Status indicators, labels, tier badges -- all rendered as text.

## Logo

Formats needed:

| Format   | Sizes                         | Use                       |
| -------- | ----------------------------- | ------------------------- |
| SVG      | scalable                      | Primary, web              |
| PNG      | 32, 64, 128, 256, 512, 1024px | App icons, social         |
| ICO      | 16 + 32px                     | Favicon                   |
| OG image | 1200x630                      | Social cards (Open Graph) |

Two variants: dark background (primary) and light background (external use).

## Mascot

The axolotl. Illustrations needed:

- Primary (full body, detail)
- Minimal (logomark, small sizes)
- Expressions/states for UI feedback (optional)

The axolotl should feel approachable but precise. Not cartoonish, not clinical.

## Usage rules

**Do:**

- Use dark background variant by default
- Maintain clear space around the logo (minimum 1x logo height)
- Use tier colors only for their trust tier
- Keep monospace typography consistent across all materials
- Use the opacity scales as defined -- don't invent new stops

**Don't:**

- Place the logo on busy or low-contrast backgrounds
- Recolor outside the defined palette
- Use tier colors for decoration
- Introduce non-monospace typefaces
- Add emojis or decorative icons

## Repo structure

```
/
  README.md
  LICENSE.md
  logo/
    xochi-logo.svg
    xochi-logo-{size}.png
    xochi-favicon.ico
    xochi-og-card.png
  mascot/
    axolotl-primary.svg
    axolotl-minimal.svg
  palette/
    xochi-palette.css          # CSS custom properties (copy of base.css tokens)
    xochi-palette.json         # Machine-readable for tooling
    xochi-palette.ase          # Adobe Swatch Exchange
    xochi-palette.figma        # Figma color styles (export)
  typography/
    README.md                  # Monaspace setup, CDN links, fallback stacks
  guidelines/
    brand-guidelines.pdf       # Print-ready brand book
    spacing-and-sizing.md      # Layout grid, component spacing
```

## License

Brand assets are proprietary. All rights reserved. Contact hello@xochi.fi for usage permissions.

Code samples (CSS custom properties, JSON palette) are CC0.
