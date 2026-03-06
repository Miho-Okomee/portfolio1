# Portfolio Project - Agent Team Guide

## Project Overview
This is a Japanese-language frontend developer portfolio website. It is a single-page application built with vanilla HTML, CSS, and JavaScript.

## File Structure
- `index.html` — The single HTML file containing all markup, styles (embedded `<style>`), and scripts (embedded `<script>`)

## Design System
- **Primary color**: `#C9A961` (gold)
- **Background light**: `#FEFEFE`
- **Background beige**: `#F5F1EB`
- **Background dark**: `#2C2C2C`
- **Text dark**: `#2C2C2C`
- **Text gray**: `#6B6B6B`
- **Font**: System font stack with Japanese support (`-apple-system`, `Hiragino Sans`, `Meiryo`)

## Sections
1. **Navigation** — Fixed top nav with mobile hamburger menu
2. **Hero** — Full-viewport hero with CTA button
3. **About** — Two-column layout with profile image and bio text
4. **Skills** — 3-column grid of skill cards
5. **Projects** — 3-column grid of project cards
6. **Testimonials** — 3-column grid of client testimonials
7. **CTA** — Dark background call-to-action section
8. **Footer** — Social links and copyright

## Language & Content
- All visible content is in Japanese (日本語)
- Placeholder name: 山田太郎 (Yamada Taro)
- Placeholder images use `placehold.co`

## Development Notes
- All CSS is inline in `<style>` tags in `<head>`
- All JS is inline in `<script>` tags before `</body>`
- No build tools, bundlers, or external dependencies
- Uses CSS custom properties (variables) for theming
- Responsive breakpoints: 768px and 480px
- Uses IntersectionObserver for scroll-based animations

## Agent Team Guidelines
- Each teammate should focus on their assigned section to avoid file conflicts
- All changes go in `index.html` — coordinate to avoid overwriting each other's work
- Maintain the existing design system (colors, spacing variables, border-radius: 2px style)
- Keep all code inline (no separate CSS/JS files unless explicitly requested)
- Preserve Japanese content and language throughout
