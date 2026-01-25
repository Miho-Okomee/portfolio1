# CLAUDE.md - AI Assistant Guide for Portfolio Project

## Project Overview

This is a **single-page portfolio website** for a Japanese-speaking frontend developer (山田太郎 / Yamada Taro). The entire site is contained in a single `index.html` file with embedded CSS and JavaScript.

**Primary Language:** Japanese (日本語)
**Target Audience:** Japanese-speaking clients seeking web development services

## Architecture

### Single-File Structure

```
portfolio1/
├── CLAUDE.md          # This file - AI assistant documentation
└── index.html         # Complete single-page application (~947 lines)
    ├── <style>        # Embedded CSS (lines 14-638)
    ├── HTML content   # Semantic markup (lines 640-883)
    └── <script>       # Vanilla JavaScript (lines 885-943)
```

### Why Single-File?

- **Zero dependencies** - No npm, no build tools, no external libraries
- **Instant deployment** - Just serve the HTML file from any web server
- **Easy maintenance** - All code in one place for small portfolio sites
- **No configuration** - No package.json, no bundler configs

## Technology Stack

| Category | Technology |
|----------|------------|
| Markup | HTML5 (semantic) |
| Styling | CSS3 with CSS Custom Properties |
| JavaScript | Vanilla ES6+ (no frameworks) |
| Fonts | System font stack (optimized for Japanese) |
| Icons | Inline SVGs + Unicode emoji |
| Images | External placeholders (placehold.co) |

## Code Organization

### CSS Structure (lines 14-638)

The CSS is organized into clearly labeled sections:

```css
/* Section markers follow this pattern: */
/* ========== SECTION NAME ========== */
```

**Sections in order:**
1. `:root` - CSS Custom Properties (design tokens)
2. Reset and base styles
3. `NAVIGATION` - Fixed header and mobile menu
4. `HERO` - Landing section with CTA
5. `ABOUT` - Profile section with image
6. `SKILLS` - Skill cards grid
7. `PROJECTS` - Project showcase cards
8. `TESTIMONIALS` - Client testimonials
9. `CTA` - Contact call-to-action section
10. `FOOTER` - Social links and copyright
11. `RESPONSIVE` - Media queries (768px, 480px)

### HTML Structure (lines 640-883)

Follows semantic HTML5 patterns:

```html
<!-- Section markers follow this pattern: -->
<!-- ========== SECTION NAME ========== -->
```

**Key sections:**
- `<nav class="nav">` - Fixed navigation
- `<section class="hero-section">` - Hero/landing
- `<section class="about-section" id="about">` - About
- `<section class="skills-section" id="skills">` - Skills
- `<section class="projects-section" id="projects">` - Projects
- `<section class="testimonials-section" id="testimonials">` - Testimonials
- `<section class="cta-section" id="contact">` - Contact CTA
- `<footer class="footer">` - Footer

### JavaScript Structure (lines 885-943)

Organized into functional blocks:

```javascript
// ========== SECTION NAME ==========
```

**Features:**
1. **Navigation Toggle** - Mobile hamburger menu
2. **Scroll Effects** - Header shrink on scroll
3. **Intersection Observer** - Fade-in animations

## Design System

### Color Palette

```css
:root {
  --color-primary: #C9A961;      /* Gold/bronze accent */
  --color-bg-light: #FEFEFE;     /* Off-white background */
  --color-bg-beige: #F5F1EB;     /* Warm beige sections */
  --color-bg-dark: #2C2C2C;      /* Dark sections (CTA) */
  --color-text-dark: #2C2C2C;    /* Primary text */
  --color-text-gray: #6B6B6B;    /* Secondary text */
  --color-text-light: #A0A0A0;   /* Muted text */
}
```

### Spacing Scale

```css
:root {
  --spacing-xl: 120px;  /* Major section padding */
  --spacing-lg: 80px;   /* Section spacing */
  --spacing-md: 48px;   /* Component spacing */
  --spacing-sm: 24px;   /* Minor spacing */
}
```

### Typography

- **Font Stack:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', Meiryo, sans-serif`
- **Responsive Sizing:** Uses `clamp()` for fluid typography
- **Line Height:** 1.6-1.8 for readability

### Breakpoints

| Breakpoint | Usage |
|------------|-------|
| 768px | Tablet - Mobile nav activates |
| 480px | Mobile - CTA buttons stack |

## Code Conventions

### CSS Naming

- **BEM-like pattern:** `.component-element` (e.g., `.nav-link`, `.project-card`)
- **Semantic naming:** Names describe purpose (e.g., `.skill-item`, `.testimonial-card`)
- **Modifier via state:** `.nav-menu.active` for toggled states

### CSS Patterns

```css
/* Hover effects use translateY for subtle lift */
.element:hover {
  transform: translateY(-8px);
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

/* Transitions are consistently 0.3s ease */
.element {
  transition: all 0.3s ease;
}

/* Glassmorphism for navigation */
.nav {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
}
```

### JavaScript Patterns

```javascript
// Event delegation for menus
navToggle.addEventListener('click', () => {
  navMenu.classList.toggle('active');
});

// Intersection Observer for scroll animations
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.style.opacity = '1';
      entry.target.style.transform = 'translateY(0)';
    }
  });
}, { threshold: 0.1 });
```

## Accessibility Features

- **Semantic HTML:** Proper use of `<nav>`, `<section>`, `<article>`, `<footer>`
- **ARIA labels:** Navigation toggle has `aria-label="メニュー"`
- **External links:** Include `rel="noopener noreferrer"` and `target="_blank"`
- **Image alt text:** All images have descriptive Japanese alt text
- **Lazy loading:** Images use `loading="lazy"`
- **Keyboard navigation:** Native focus states preserved

## Performance Optimizations

- **Lazy loading:** `loading="lazy"` on all images
- **GPU-accelerated animations:** Uses `transform` and `opacity`
- **System fonts:** No external font files to load
- **Inline SVGs:** No extra HTTP requests for icons
- **Single file:** Eliminates multiple HTTP requests

## Development Workflow

### Local Development

```bash
# No build step required - just open in browser
open index.html

# Or use a simple HTTP server
npx serve .
python -m http.server 8000
```

### Deployment

The site can be deployed to any static hosting:
- GitHub Pages
- Netlify
- Vercel
- Any web server (just upload index.html)

### Making Changes

1. Open `index.html` in your editor
2. Make changes to CSS/HTML/JS in their respective sections
3. Refresh browser to see changes
4. No compilation or build step needed

## AI Assistant Guidelines

### When Modifying This Project

1. **Maintain the single-file structure** unless the user explicitly requests modularization
2. **Follow existing naming conventions** - BEM-like CSS classes, semantic HTML
3. **Use CSS Custom Properties** for colors and spacing - never hardcode values
4. **Preserve section comment markers** (`/* ========== NAME ========== */`)
5. **Keep animations performant** - use `transform` and `opacity` only
6. **Maintain Japanese language** for content unless asked otherwise
7. **Test responsive design** at 768px and 480px breakpoints

### Common Tasks

**Adding a new skill:**
```html
<!-- Add to .skills-grid in the SKILLS SECTION -->
<div class="skill-item">
  <div class="skill-icon">🔧</div>
  <h3>Skill Name</h3>
  <p>Skill description in Japanese.</p>
</div>
```

**Adding a new project:**
```html
<!-- Add to .projects-grid in the PROJECTS SECTION -->
<article class="project-card">
  <div class="project-card-image">
    <img src="..." alt="..." loading="lazy">
  </div>
  <div class="project-card-content">
    <p class="project-card-category">Category</p>
    <h3>Project Title</h3>
    <p>Description in Japanese.</p>
    <div class="project-card-tags">
      <span class="project-tag">Tag</span>
    </div>
  </div>
</article>
```

**Adding a new testimonial:**
```html
<!-- Add to .testimonials-grid in the TESTIMONIALS SECTION -->
<div class="testimonial-card">
  <div class="testimonial-quote">"</div>
  <p class="testimonial-text">Testimonial text in Japanese.</p>
  <div class="testimonial-author">
    <div class="testimonial-avatar">
      <img src="..." alt="..." loading="lazy">
    </div>
    <div class="testimonial-info">
      <h4>Name 様</h4>
      <p>Title / Company</p>
    </div>
  </div>
</div>
```

### What NOT to Do

- Don't add npm/build tooling unless explicitly requested
- Don't split into multiple files unless requested
- Don't change the design system colors without user approval
- Don't remove accessibility features
- Don't add external dependencies (keep it vanilla)
- Don't change Japanese content to English without asking

## File Quick Reference

| Line Range | Content |
|------------|---------|
| 1-13 | Head, meta tags, favicon |
| 14-638 | `<style>` - All CSS |
| 640-659 | Navigation HTML |
| 661-669 | Hero section |
| 671-684 | About section |
| 686-726 | Skills section |
| 728-787 | Projects section |
| 789-842 | Testimonials section |
| 844-858 | CTA section |
| 860-883 | Footer |
| 885-943 | `<script>` - All JavaScript |

## Contact Placeholders

The following values should be customized by the user:

- Email: `your-email@example.com` (line 850)
- Phone: `03-1234-5678` (line 855)
- GitHub: `yourusername` (line 864)
- Twitter: `yourusername` (line 869)
- LinkedIn: `yourusername` (line 874)
- Profile image: Currently uses placeholder (line 675)
- Project images: Currently use placeholders (lines 739, 755, 771)
