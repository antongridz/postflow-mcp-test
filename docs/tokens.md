# Postflow Design Tokens (Rebuild Phase)

Source: [Figma](https://www.figma.com/design/eGseYgAFT9ojaMJB5TnBxZ/Untitled?node-id=0-50). All values verified 2025-11-28.

## Color Palette

| Token | Hex | Usage |
| --- | --- | --- |
| `--stone-100` | `#F5F5F4` | Hero headline, highlights |
| `--stone-200` | `#E7E5E4` | Primary body text, totals |
| `--stone-300` | `#D6D3D1` | Labels, metadata |
| `--stone-400` | `#A6A09B` | Secondary text (Klarna) |
| `--stone-500` | `#79716B` | Placeholders, helper copy |
| `--stone-700` | `#44403B` | Muted borders |
| `--stone-800` | `#292524` | Dividers, card outlines |
| `--stone-900` | `#1C1917` | Card surfaces |
| `--stone-950` | `#0C0A09` | Page background |
| `--lime-300` | `#BBF451` | Active border, discount value |
| `--lime-400` | `#96B800` | CTA gradient base |
| `--lime-500` | `#DAFF33` | CTA gradient highlight |
| `--lime-600` | `#E1FF5C` | CTA outline |
| `--lime-700` | `#EEFFA2` | CTA inset glow |

## Typography

| Token | Value | Notes |
| --- | --- | --- |
| `--font-sans` | `'Switzer', sans-serif` | Global font |
| `--weight-regular` | `400` | Body text |
| `--weight-medium` | `500` | Labels, totals |
| `--weight-semibold` | `600` | Headings, CTA |
| `--text-hero-size` | `30px` | Hero title |
| `--text-hero-leading` | `36px` | Hero line height |
| `--text-section-size` | `20px` | Card titles |
| `--text-section-leading` | `24px` | Card title leading |
| `--text-body-size` | `14px` | Inputs, summary rows |
| `--text-body-leading` | `20px` | Body leading |
| `--text-caption-size` | `12px` | Footnotes |
| `--text-caption-leading` | `16px` | Footnote leading |

## Spacing & Radii

| Token | Value | Usage |
| --- | --- | --- |
| `--radius-2xl` | `20px` | Outer wrappers |
| `--radius-xl` | `16px` | Cards |
| `--radius-lg` | `12px` | Payment method tiles |
| `--radius-md` | `8px` | Inputs, CTA |
| `--space-8` | `32px` | Card gaps, hero spacing |
| `--space-6` | `24px` | Card padding |
| `--space-4` | `16px` | Field vertical rhythm |
| `--space-3` | `12px` | Inline gaps |
| `--space-2` | `8px` | Label/input spacing |

## Shadows & Effects

| Token | Value | Usage |
| --- | --- | --- |
| `--shadow-header` | `0 4px 8px rgba(0,0,0,0.08)` | Frosted header bar |
| `--shadow-text-dark` | `0 -1px 0 rgba(12,10,9,0.25)` | Embossed light text |
| `--shadow-text-light` | `0 -1px 0 rgba(255,255,255,0.25)` | CTA text highlight |
| `--shadow-cta-inset` | `inset 0 2px 1px rgba(238,255,162,1)` | CTA glow |

## Assets to Export

| Asset | Description |
| --- | --- |
| `postflow-logo.svg` | Wordmark in header |
| `cross-large.svg` | Close button icon |
| `lines.svg` | Background grid |
| `background-glow` | Radial glow (can be CSS gradient) |
| `credit-card.svg` | Card payment icon |
| `klarna.svg` | Klarna badge |

These tokens should be imported into `styles.css` immediately so subsequent tasks reference consistent values.
