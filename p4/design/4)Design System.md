:root {
  /* Tech Glass Palette */
  --bg-tech-light: #f8fafc;
  --glass-surface: rgba(255, 255, 255, 0.65);
  --glass-border: rgba(255, 255, 255, 0.8);
  
  /* Accent Gradients */
  --grad-tech-primary: linear-gradient(135deg, #3b82f6 0%, #8b5cf6 100%);
  --grad-tech-cyan: linear-gradient(135deg, #06b6d4 0%, #3b82f6 100%);

  /* Typography */
  --font-tech-ar: 'Readex Pro', sans-serif;
  --font-body-ar: 'IBM Plex Sans Arabic', sans-serif;
}
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        tech: {
          bg: '#F8FAFC',
          dark: '#0F172A',
          blue: '#3B82F6',
          cyan: '#06B6D4',
          violet: '#8B5CF6',
          muted: '#64748B',
        }
      },
      backgroundImage: {
        'tech-gradient': 'linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%)',
        'cyan-gradient': 'linear-gradient(135deg, #06B6D4 0%, #3B82F6 100%)',
        'glass-card': 'linear-gradient(180deg, rgba(255, 255, 255, 0.7) 0%, rgba(255, 255, 255, 0.4) 100%)',
      },
      backdropBlur: {
        glass: '16px',
      }
    }
  }
}