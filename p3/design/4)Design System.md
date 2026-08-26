:root {
  /* Brand Luxury Palette */
  --color-luxury-bg: #f9f8f6;
  --color-luxury-dark: #0a0a0a;
  --color-luxury-gold: #c5a880;
  --color-luxury-gray: #404040;
  --color-luxury-border: #e5e5e5;

  /* Typography Settings */
  --font-serif-ar: 'Noto Serif Arabic', serif;
  --font-sans-ar: 'IBM Plex Sans Arabic', sans-serif;
}
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        luxury: {
          bg: '#F9F8F6',
          dark: '#0A0A0A',
          gold: '#C5A880',
          muted: '#737373',
          border: '#E5E5E5',
        }
      },
      fontFamily: {
        serifAr: ['Noto Serif Arabic', 'serif'],
        sansAr: ['IBM Plex Sans Arabic', 'sans-serif'],
      },
      letterSpacing: {
        extra: '0.15em',
      }
    }
  }
}