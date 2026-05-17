# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Appminton is a static website and landing page for a badminton session management application. The site is hosted on GitHub Pages (configured via CNAME file) and serves as a marketing/landing page for the Appminton app targeting badminton players and groups in Malaysia.

## Architecture

The project is entirely static HTML with embedded CSS (no JavaScript build process or frontend framework):

- **Root landing page** (`index.html`) - Main marketing page for Appminton
- **Account deletion page** (`account-deletion/index.html`) - Legal/user account deletion page
- **Privacy policy** (`privacy/index.html`) - Privacy policy page
- **Terms of service** (`terms/index.html`) - Terms of service page
- **Assets** - Logo, favicons, and other static resources (PNG images, ICO files)
- **CNAME file** - DNS configuration for GitHub Pages deployment to `appminton.com`

### Design System

The project uses a consistent design system:
- **Color scheme**: Primary green (`#10b981`), dark backgrounds (`#111827`, `#1f2937`), light text (`#f9fafb`)
- **Typography**: System fonts (`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`)
- **Layout**: CSS flexbox and CSS variables (CSS custom properties) for theming
- **Responsive design**: Uses `clamp()` for fluid typography and mobile-first approach

## Common Tasks

### Viewing the site locally
Open any `.html` file directly in a browser (e.g., `open index.html`). Since these are static files with no build process, they work immediately.

### Editing content
Edit the relevant `.html` files directly:
- Update main marketing copy, features, or calls-to-action in `index.html`
- Update legal pages in `privacy/index.html`, `terms/index.html`, or `account-deletion/index.html`

### Adding or replacing assets
- Place images in the root directory or subdirectories
- Update `<img>` src attributes to reference new assets
- Remember to keep SEO attributes (alt text) descriptive and accurate

### Making styling changes
- Locate the `<style>` block within each HTML file's `<head>` element
- Modify CSS variables (`:root { --primary: ..., --dark: ..., etc }`) to change theme colors
- Add or modify CSS rules as needed
- Test responsive behavior by resizing the browser window

### Publishing changes
The site automatically deploys to `https://www.appminton.com/` via GitHub Pages when commits are pushed to the main branch. No build step is required.

## Important Notes

- **No build system**: This is static HTML only. There's no npm, webpack, build scripts, or asset compilation.
- **Inline CSS**: All styles are embedded in `<style>` tags within each HTML file. There are no separate CSS files.
- **SEO considerations**: The landing page includes structured data (JSON-LD), Open Graph tags, and meta descriptions. Preserve these when editing.
- **Favicon consistency**: The project includes multiple favicon formats for different devices (`favicon.ico`, `apple-touch-icon.png`, Android Chrome icons). Update all if changing the site icon.
- **GitHub Pages hosting**: The CNAME file points to `appminton.com`. Be careful not to modify or delete this file unless DNS configuration is being changed.
