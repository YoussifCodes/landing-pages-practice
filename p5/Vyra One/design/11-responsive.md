# Responsive Behavior

Source: `01-product-requirements.md`, `02-sitemap.md`, `05-visual-direction.md`, `08-wireframes.md`

Approach: **mobile-first** (most traffic arrives from phones). Design for 375px, then scale up.

## Breakpoints

| Name | Width | Notes |
|------|-------|-------|
| Mobile | 0–639px | Single column, stacked |
| Tablet | 640–1023px | Two columns where useful |
| Desktop | 1024–1439px | Full layout |
| Wide | 1440px+ | Max content width 1320px, centered |

Container padding: 16px mobile, 32px tablet, 64px desktop.

## Section Behavior

| Section | Mobile | Tablet | Desktop |
|---------|--------|--------|---------|
| Header | Logo + Pre-order pill + menu icon; full-screen overlay menu | Same as mobile | Full links + Pre-order |
| Hero | Phone on top (centered, 70% width), headline below, CTA full width; glass cards hidden or reduced to 2 under the phone | Phone right, text left, 2 cards | Full composition with floating cards |
| Statement | H2 at 36px, centered, padding 96px 16px | 48px | 80px |
| Feature chapters | Image first, then text, then one glass card; stacked | Two columns | Alternating left/right |
| Colors | Phone on top, swatches below in a row, name and description under | Side by side | Side by side, larger phone |
| Specs | 2x2 stat tiles, accordions full width | 4 tiles in a row | 4 tiles + accordions |
| Pricing | Cards stacked, recommended option first; sticky bottom CTA | 3 columns | 3 columns |
| Trust | Stacked list (3 rows) | 3 in a row | 3 in a row |
| FAQ | Full width accordions | Same | Centered, max 800px |
| Final CTA | Stacked: button then email form | Inline | Inline |
| Footer | Stacked links, social icons centered | 2 columns | 4 columns |

## Typography Scaling

- H1: `clamp(44px, 12vw, 160px)` on mobile → `clamp(56px, 9vw, 160px)` on desktop.
- H2: `clamp(32px, 6vw, 80px)`.
- Body: 16px mobile, 18px desktop.
- Minimum tap target: 44x44px.

## Mobile-Specific Rules

- Sticky bottom bar with "Pre-order" CTA after the hero is passed.
- Disable heavy parallax and 3D rotation under 768px; use simple fade/slide reveals.
- Glass `backdrop-filter` limited to 2–3 elements on mobile for performance; fall back to semi-opaque backgrounds.
- Hover effects replaced by tap/active states.
- Color swatches are tappable and swipeable.

## Performance Budget (mobile)

- LCP under 2.5s on 4G; total page weight under 2 MB on first load.
- Hero image: WebP/AVIF, `srcset` 480/800/1200w, preloaded.
- Below-the-fold images: `loading="lazy"`, explicit width/height to avoid layout shift.
- Fonts: max 3 families, `font-display: swap`, subset.
- Videos: not autoplayed on mobile; poster image only until tapped.

## Accessibility

- Contrast ratio AA minimum.
- `prefers-reduced-motion` disables scroll-driven animations.
- Keyboard accessible nav, accordions, and color picker; visible focus ring in accent color.
- Alt text on all phone and feature images.
- Respect RTL: use logical CSS properties (`margin-inline`, `padding-inline`) so an Arabic version works without rewriting.

## Test Matrix

- 360x800 (Android), 390x844 (iPhone), 768x1024 (tablet), 1280x720, 1440x900, 1920x1080.
- Check: no horizontal scroll, readable text, CTAs visible, animations smooth at 60fps.
