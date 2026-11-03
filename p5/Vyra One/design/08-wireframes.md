# Wireframes

Source: `01-product-requirements.md`, `02-sitemap.md`, `05-visual-direction.md`

Desktop layout (1440px). Mobile behavior is in `11-responsive.md`.

## 1. Header (sticky)

```
┌──────────────────────────────────────────────────────────────┐
│ ◉ VYRA     Camera  Display  Battery  Colors  Specs  [Pre-order]│
└──────────────────────────────────────────────────────────────┘
```

## 2. Hero

```
┌──────────────────────────────────────────────────────────────┐
│ [pill nav]                                                   │
│                                                              │
│  BUILT              ┌───────────┐        ┌──────┐ ┌──────┐  │
│  TO *move*          │           │        │120Hz │ │5000  │  │
│  ────────           │   PHONE   │        │ glass│ │ mAh  │  │
│  Short 2-line copy  │  (large,  │        └──────┘ └──────┘  │
│                     │  tilted)  │                            │
│  [Pre-order →] (▶) Watch film   └───────────┘   scroll ↓    │
└──────────────────────────────────────────────────────────────┘
```

## 3. Statement

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│      EVERY DETAIL, *tuned* FOR THE WAY YOU LIVE.             │
│      (one huge sentence, centered, dark background)          │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

## 4. Feature chapter (repeat for Camera, Display, Battery, Performance)

```
┌──────────────────────────────────────────────────────────────┐
│ 01 / CAMERA                                                  │
│                                                              │
│  50MP  *Night*        ┌──────────────────┐   ┌────────────┐  │
│  that sees more.      │  phone / camera  │   │ glass card │  │
│  Short paragraph      │  close-up image  │   │ 50MP  f/1.7│  │
│                       └──────────────────┘   └────────────┘  │
│                                                  [See samples]│
└──────────────────────────────────────────────────────────────┘
```
Alternate image side left/right per chapter. Background tint changes per chapter.

## 5. Design & Colors

```
┌──────────────────────────────────────────────────────────────┐
│  CHOOSE YOUR *color*                                         │
│                      ┌───────────┐                           │
│     ● ○ ○ ○          │   PHONE   │     Ember Orange          │
│   (swatches)         │ (swaps)   │     Aluminium + glass     │
│                      └───────────┘                           │
└──────────────────────────────────────────────────────────────┘
```

## 6. Specs (compact)

```
┌──────────────────────────────────────────────────────────────┐
│  THE *numbers*                                               │
│  ┌────────┬────────┬────────┬────────┐                       │
│  │ 6.7"   │ 50MP   │ 5000   │ 12GB   │  (4 big stat tiles)   │
│  └────────┴────────┴────────┴────────┘                       │
│  ▸ Display      ▸ Camera      ▸ Battery      ▸ Chip          │
│  (accordion rows with full details)                          │
└──────────────────────────────────────────────────────────────┘
```

## 7. Pricing & Storage

```
┌──────────────────────────────────────────────────────────────┐
│  PICK YOURS                                                  │
│ ┌──────────┐ ┌──────────┐ ┌──────────┐                       │
│ │ 128 GB   │ │ 256 GB ★ │ │ 512 GB   │                       │
│ │ $499     │ │ $549     │ │ $629     │                       │
│ └──────────┘ └──────────┘ └──────────┘                       │
│            [ Pre-order now → ]                               │
└──────────────────────────────────────────────────────────────┘
```

## 8. Trust

```
┌──────────────────────────────────────────────────────────────┐
│  🛡 2-year warranty   🚚 Free shipping   ↩ 14-day returns      │
└──────────────────────────────────────────────────────────────┘
```

## 9. FAQ

```
┌──────────────────────────────────────────────────────────────┐
│  QUESTIONS, *answered*                                       │
│  ▸ When does it ship?                                        │
│  ▸ Is there a charger in the box?                            │
│  ▸ Does it support 5G / eSIM?                                │
│  ▸ How do returns work?                                      │
└──────────────────────────────────────────────────────────────┘
```

## 10. Final CTA + Footer

```
┌──────────────────────────────────────────────────────────────┐
│  READY TO *move*?                                            │
│  [ Pre-order → ]      or   [ your email ........ ][Notify me]│
│                                                              │
│  V Y R A   O N E   (giant faded watermark)                   │
│  Privacy · Terms · Warranty · Contact      ◎ ✕ ♪ ▶           │
└──────────────────────────────────────────────────────────────┘
```

## Interaction Notes

- Sticky header CTA scrolls to `#order`.
- Color swatches update hero phone, color section, and accent color globally.
- Accordions: one open at a time.
- Email form: inline validation, success message replaces the form.
