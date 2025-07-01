# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based static website for the Tap Map app (tapmapapp.org). It uses the Ananke theme and supports multilingual content (English US/GB and French).

## Commands

### Development
- `hugo server -D` - Start development server with drafts
- `hugo server --cleanDestinationDir` - Start server with clean destination

### Deployment
- `hugo deploy` - Deploy the site

### Build
- `hugo` - Build the static site (outputs to /public)

## Architecture

### Content Structure
- **Multilingual setup**: Content organized by language codes in `/content/`
  - `en-US/` - English (US) content
  - `en-GB/` - English (UK) content  
  - `fr-FR/` - French content
- **Page types**: Each language has identical structure with Home, FAQ, Support, Privacy, and EULA pages
- **Configuration**: hugo.toml defines language-specific menus and parameters

### Theme
- Uses Ananke Hugo theme from `/themes/ananke/`
- Theme provides responsive layout with Tachyons CSS
- Custom layouts in `/layouts/` override theme defaults
- Custom shortcodes: betastamp, buymeacoffee, downloadapp, welcome-guide

### Static Assets
- `/static/` - Files copied directly to site root
- `/assets/` - Processed assets
- **IMPORTANT**: Never edit files in `/public/` - they are generated

### Key Files
- `hugo.toml` - Main configuration with multilingual setup
- `/layouts/partials/i18nlist.html` - Language switcher
- `/content/*/images/` - Page-specific images per language
- `/data/` - Data files for Hugo

## Development Notes

- Hugo minimum version: 0.128.0 (per theme requirements)
- Theme supports posts, shortcodes, related content, and comments
- Site uses unsafe HTML rendering enabled in goldmark configuration
- Caching configured for images in `:cacheDir/images`