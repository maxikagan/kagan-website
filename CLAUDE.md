# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static academic personal website for Max Kagan (maxkagan.com), hosted on GitHub Pages.

## Technology Stack

- **HTML5/CSS3**: Static site with no build system or framework
- **Bootstrap 5.3.2**: Layout and responsive components (CDN)
- **Font Awesome 6.5.1**: Icons (CDN)
- **Google Fonts**: DM Sans (sans-serif, similar to Neue Haas Grotesk) + Playfair Display (headings)

## Site Structure

```
index.html              # Home page with bio and social links
research.html           # Research papers with abstract toggles
politics-at-work.html   # Featured project page (VRscores dataset)
cv.html                 # PDF viewer for CV
styles.css              # All custom styles (CSS variables, components)
images/
  └── headshot.jpg      # Profile photo
docs/
  └── KAGAN_CV.pdf      # CV document
```

## Development

No build step required. Edit HTML/CSS files directly and preview in browser.

**Local preview:** Open any `.html` file directly in a browser, or use a local server:
```bash
python -m http.server 8000
# Then visit http://localhost:8000
```

**Deploy:** Push to `main` branch. GitHub Pages automatically deploys within 1-2 minutes.

## Key Patterns

### CSS Architecture
- CSS variables defined in `:root` for colors, fonts, spacing
- Columbia Business School color palette (`--primary-color: #011E41`)
- Component classes: `.surface-card`, `.paper-card`, `.featured-card`
- Responsive breakpoints at 480px, 768px, and 992px

### Adding Research Papers
In `research.html`, copy an existing `<article class="paper-row">` block and modify. Status classes:
- `status-working`: Working Paper (gray)
- `status-review`: Revise & Resubmit (purple)
- `status-accepted`: Conditionally Accepted (amber)
- `status-published`: Published (green)

### Pipeline Visualization
The publication pipeline in `research.html` shows paper icons at each stage. To add papers to "Conditionally Accepted", add `<i class="fas fa-file-alt"></i>` icons inside the `.stage-dots.accepted` div.

### Navigation
Each page has identical navbar markup. When adding pages, update nav links in all HTML files.

