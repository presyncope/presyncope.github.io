# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Academic Pages Jekyll website - a GitHub Pages template for personal and professional portfolio-oriented websites. It's built using Jekyll and uses the Academic Pages theme, providing a clean layout for showcasing publications, talks, teaching, and personal information.

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve the site locally (recommended)
jekyll serve -l -H localhost

# Alternative command if you encounter dependency issues
bundle exec jekyll serve -l -H localhost
```

The site will be available at `http://localhost:4000` with automatic rebuilding and refreshing on changes.

### Docker Development
```bash
# Set permissions and run with Docker Compose
chmod -R 777 .
docker compose up
```

### JavaScript Build Commands
```bash
# Build and minify JavaScript assets
npm run build:js

# Watch JavaScript files for changes and rebuild
npm run watch:js

# Direct uglify command
npm run uglify
```

## Site Architecture

### Core Configuration
- **_config.yml**: Main Jekyll configuration file containing site settings, author information, social media links, collections configuration, and plugin settings
- **Gemfile**: Ruby dependencies including Jekyll plugins and GitHub Pages compatibility
- **package.json**: Node.js dependencies for JavaScript asset processing

### Content Structure
- **_pages/**: Main site pages (about, CV, publications, etc.)
- **_posts/**: Blog posts in Markdown format
- **_publications/**: Academic publications collection
- **_talks/**: Conference talks and presentations
- **_teaching/**: Teaching-related content
- **_portfolio/**: Portfolio items
- **_data/**: Site data files including navigation.yml and ui-text.yml

### Asset Management
- **_sass/**: Sass stylesheets organized by layout, themes, and vendor libraries
- **assets/js/**: JavaScript files that get processed and minified
- **images/**: Static images and media files
- **files/**: Downloadable files (PDFs, documents, etc.)

### Content Generation
The `markdown_generator/` directory contains Python scripts and Jupyter notebooks for automatically generating markdown files from structured data:
- **publications.py/ipynb**: Generate publication pages from TSV data
- **talks.py/ipynb**: Generate talk pages from TSV data
- **PubsFromBib.ipynb**: Import publications from BibTeX files
- **OrcidToBib.ipynb**: Import publications from ORCID

### Collections and Data
Jekyll collections are configured for different content types:
- Publications: Output enabled, publicly accessible pages
- Teaching, Portfolio, Talks: Output disabled, data-only collections
- Navigation structure defined in `_data/navigation.yml`

## Key Features

### Multi-language Support
- Site configured for English (en-US) locale
- UI text customizable via `_data/ui-text.yml`

### Social Integration
- Comprehensive author profile with academic and social media links
- Google Scholar, ORCID, GitHub, LinkedIn integration
- Configurable analytics and SEO settings

### Theme System
- Default theme with dark theme support available
- Customizable via `_sass/theme/` directory
- Responsive design with mobile-friendly navigation

## Development Notes

- The site uses Kramdown for Markdown processing with GitHub Flavored Markdown input
- Syntax highlighting provided by Rouge
- Font Awesome icons included via vendor stylesheets
- Magnific Popup for image galleries and modals
- Susy grid system for responsive layouts

## File Upload
Static files should be placed in the `files/` directory and will be accessible at `https://[username].github.io/files/filename.ext`