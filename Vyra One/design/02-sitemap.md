# Sitemap

Source: `01-product-requirements.md`

A single-page landing page. Navigation scrolls to sections (anchors). Secondary pages are optional and only linked from the footer.

## Page Structure (in scroll order)

| # | Section | Anchor | Purpose | Primary action |
|---|---------|--------|---------|----------------|
| 1 | Header (sticky) | — | Brand + navigation + persistent CTA | Pre-order |
| 2 | Hero | `#home` | Instant impression: phone, headline, price hint | Pre-order / Watch film |
| 3 | Statement | `#about` | One big sentence that frames the phone's promise | Scroll |
| 4 | Camera | `#camera` | Show photo quality, 50MP system | Scroll / See samples |
| 5 | Display | `#display` | 120Hz AMOLED, brightness | Scroll |
| 6 | Battery & Charging | `#battery` | 5000mAh, fast charge | Scroll |
| 7 | Performance | `#performance` | Chip, RAM, gaming | Scroll |
| 8 | Design & Colors | `#colors` | Color picker, materials | Choose color |
| 9 | Specs (compact) | `#specs` | Expandable key specs | Expand |
| 10 | Pricing & Storage | `#pricing` | Options and price | Pre-order |
| 11 | Trust | `#trust` | Warranty, shipping, returns | — |
| 12 | FAQ | `#faq` | Remove last objections | Expand |
| 13 | Final CTA | `#order` | Last conversion push + email capture | Pre-order / Notify me |
| 14 | Footer | — | Legal, social, contact | — |

## Navigation (header)

- Logo → `#home`
- Features (Camera, Display, Battery, Performance) → anchors
- Colors → `#colors`
- Specs → `#specs`
- **Pre-order** button → `#order`
- Mobile: logo + Pre-order button + menu icon (full-screen overlay menu)

## Footer Links

- Privacy Policy, Terms, Warranty, Contact, Social links (Instagram, X, TikTok, YouTube)

## Optional Secondary Pages (phase 2)

- `/compare` — compare with previous model
- `/support` — support and warranty info
- `/thank-you` — confirmation after pre-order or sign-up

## User Flows

1. **Pre-order:** Hero CTA → (scroll chapters) → Pricing → choose color/storage → Pre-order → Thank-you.
2. **Undecided visitor:** Scroll features → Specs → FAQ → Notify me (email) → Thank-you.
3. **Returning visitor:** Sticky header Pre-order button from any point.
