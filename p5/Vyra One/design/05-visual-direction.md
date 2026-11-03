# Visual Direction

Source: `01-product-requirements.md`, `02-sitemap.md`

## Concept

**"Cinematic, bold, in motion."** A single saturated color world per chapter, one huge phone render as the hero, oversized type, and frosted-glass cards. Inspired by scroll-driven product sites (Scowlby / Parrot / Braix / NAÏADE style): big subject, big headline, soft gradients, minimal UI chrome.

## Mood

Premium, energetic, modern, high contrast, generous whitespace. Not a spec sheet, not a template.

## Color

The page changes background tone per chapter, driven by the selected phone color.

| Role | Value | Use |
|------|-------|-----|
| Base dark | `#0B0B10` | Default background, statement and trust sections |
| Hero gradient | `#FF5A1F` → `#B3122A` | Hero background (burnt orange to deep red) |
| Accent | `#FFD23F` | CTAs, highlights, active states |
| Surface light | `#F4F1EA` | Specs and FAQ sections |
| Text on dark | `#FFFFFF` / `#FFFFFFB3` | Headings / body |
| Text on light | `#111114` / `#111114AA` | Headings / body |
| Glass | `rgba(255,255,255,0.12)` + 1px `rgba(255,255,255,0.25)` border + `backdrop-filter: blur(20px)` | Stat cards |

Phone color options (swap accent and hero tint):
Ember Orange · Midnight Black · Glacier Mint · Pearl White.

## Typography

- Display: **Anton** or **Bebas Neue**, uppercase, tight leading (0.95), for headlines.
- Accent: **Playfair Display Italic**, one word per headline in italics, e.g. "BUILT *to* MOVE".
- Body/UI: **Inter**, 16–18px, 1.6 line height.
- Labels: Inter 11–12px uppercase, letter-spacing 0.12em.
- Arabic version: Tajawal or Cairo for body, Amiri for the italic-style accent.

Scale: H1 clamp(56px, 9vw, 160px) · H2 clamp(36px, 5vw, 80px) · H3 24–32px · body 16–18px.

## Imagery

- Hero: one large phone render, cut out, slightly rotated (-8° to 8°), overlapping the headline.
- Chapter visuals: camera close-up, display macro, battery/charging render, exploded view for performance.
- Photography style: sharp, dramatic lighting, shallow depth of field, no stock-photo look.
- Format: WebP/AVIF, lazy-loaded below the fold; hero preloaded.

## Components

- **Pill header:** logo, 4 links, white pill "Pre-order" button, round menu button on mobile.
- **Buttons:** pill shape, 56px tall, primary = yellow accent with black text and arrow; secondary = round play button with "Watch film".
- **Glass cards:** 24px radius, soft shadow, stat number big + tiny label.
- **Chapter label:** small uppercase tag with number ("01 / CAMERA").
- **Color swatches:** 40px circles, active ring in accent color.
- **Accordion (specs, FAQ):** thin dividers, plus/minus icon.
- **Watermark:** giant faded brand name at the page bottom.

## Motion

- Scroll-driven: phone rotates, scales, and slides between chapters (GSAP ScrollTrigger or CSS scroll-timeline).
- Headline lines reveal with a mask slide-up (0.6s, ease-out).
- Glass cards float with slight parallax (±20px).
- Color picker transitions: 400ms crossfade of phone image and background gradient.
- Respect `prefers-reduced-motion`: disable parallax and rotation, keep fades.

## Do / Don't

- Do keep one idea per screen and large type.
- Do keep contrast AA or better on text.
- Don't use more than two fonts plus the italic accent.
- Don't show a full spec table above the fold.
- Don't autoplay sound.
