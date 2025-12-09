# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page personal website for David Campbell (mrcampbell.org) showcasing AI Security & Engineering Leadership expertise. The site is built as a static HTML website using Tailwind CSS via CDN with vanilla JavaScript for interactions.

**Key Characteristics:**
- Zero build process - pure static HTML/CSS/JS
- Tailwind CSS loaded via CDN (not compiled)
- No package.json or dependencies
- Self-contained in a single index.html file
- No backend or server-side logic

## Local Development

Start a local web server to view the site:

```bash
# Using Python (recommended)
python3 -m http.server 8000

# Using Node.js http-server (if installed)
npx http-server

# Or open directly in browser
open index.html
```

Navigate to `http://localhost:8000` to view the site.

## Architecture

### Single-Page Application Structure

The entire site is in `index.html` with the following sections (in order):
1. **Hero Section** - Main value proposition with CTAs
2. **Recognition Section** - Government/industry recognition badges
3. **Why Operator Section** - Comparison table
4. **Capabilities Section** - AI Security vs Engineering Leadership offerings
5. **Engagement Models** - Three service tier options
6. **Assessment CTA** - Lead magnet with email capture
7. **Experience Timeline** - Professional history (Scale AI, DoorDash, Uber, etc.)
8. **Contact Section** - Contact form and information
9. **Footer** - Basic footer with links

### JavaScript Components

All JavaScript is inline in `<script>` tags at the bottom of index.html:

- **Mobile menu toggle** - Hamburger menu for responsive navigation
- **Smooth scrolling** - Anchor link behavior for section navigation
- **Sticky CTA button** - Shows after 800px scroll
- **Timeline rendering** - Dynamically generates government recognition timeline
- **Form handling** - Contact form and checklist form (console logging only, no backend)

### Styling Architecture

- **Tailwind CSS via CDN** - No build process, all utilities available
- **Custom CSS** - Embedded in `<style>` tag for animations and specific overrides:
  - Focus indicators for accessibility
  - Fade-in and slide-in animations
  - Mobile menu transitions
  - Timeline visual connector
- **Color scheme** - Blue/purple gradient theme with semantic color usage
- **Font** - Inter from Google Fonts

### Assets

- `banner.png`, `clock.png`, `footer.png`, `icon-sheet.png` - Visual assets
- `hero-ai-security.jpg` - Hero section background image
- `government-recognition.jpg` - Recognition section image
- `lead-magnet-checklist.jpg` - Lead magnet visual
- `favicon/` - Complete favicon set (multiple sizes, formats)

## Deployment

The site is designed for static hosting platforms. No build process required - deploy the directory as-is.

### Deployment Targets (per README.md)

1. **Netlify** (Recommended) - Drag and drop or CLI: `netlify deploy --prod`
2. **Vercel** - CLI: `vercel --prod`
3. **GitHub Pages** - Enable in repository settings
4. **AWS S3 + CloudFront** - Upload to S3 bucket with static website hosting
5. **Cloudflare Pages** - Connect repository or direct upload

### Custom Domain Configuration

The site is configured for `mrcampbell.org`. DNS configuration varies by platform (see README.md for specific DNS records).

## Content Management

To update website content, edit `index.html` directly:

- **Contact info** - Email, phone, LinkedIn URL scattered throughout
- **Professional experience** - Update timeline section with dates/descriptions
- **Expertise areas** - Modify the two-card capability section
- **Achievements** - Edit the `timelineData` array in JavaScript
- **Service offerings** - Update engagement model cards
- **Meta tags** - SEO and social media preview tags in `<head>`

## Forms and Lead Generation

Both forms (contact and checklist) currently use `console.log()` only:

```javascript
// Contact form - index.html:865
document.getElementById('contact-form').addEventListener('submit', ...)

// Checklist form - index.html:837
document.getElementById('inline-checklist-form').addEventListener('submit', ...)
```

**To implement real form handling:** Integrate with email service (e.g., EmailJS, FormSpree, Netlify Forms) by modifying these event listeners.

## Performance and SEO

The site includes:
- Semantic HTML5 structure
- Meta description and title tags
- Open Graph and Twitter Card meta tags
- Accessibility features (skip links, ARIA labels, focus indicators)
- Font preconnect for Google Fonts
- Lazy-loaded images via browser defaults

**Not included** (mentioned in README as future enhancements):
- Self-hosted Tailwind CSS (would require build process)
- Analytics integration (Google Analytics, Plausible)
- JSON-LD structured data
- sitemap.xml or robots.txt

## Accessibility Features

- Skip link to main content (keyboard navigation)
- Proper heading hierarchy (H1 → H2 → H3)
- ARIA labels on interactive elements
- Custom focus indicators (3px blue outline)
- Semantic HTML elements (`<nav>`, `<main>`, `<section>`, `<footer>`)

## Important Notes

- **No Git Repository** - This directory is not a git repo (per env info)
- **No Backend** - Forms are client-side only, no server processing
- **No Build Tools** - No npm, webpack, or compilation required
- **CDN Dependencies** - Tailwind CSS and Google Fonts loaded from CDN
- **Responsive Design** - Mobile-first with Tailwind breakpoints (sm, md, lg)

## Common Modifications

**Changing colors:** Replace Tailwind color classes (e.g., `bg-blue-600` → `bg-purple-600`)

**Adding sections:** Insert new `<section>` elements between existing sections in index.html

**Modifying navigation:** Update nav links in both desktop menu (line 107) and mobile menu (line 120)

**Updating timeline:** Edit `timelineData` array in JavaScript (line 789)

**Changing fonts:** Replace Google Fonts URL in `<head>` and update `font-family` in CSS
