# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based website for "Studentische Elterninitiative Hänsel & Gretel e.V." (a student-run parental initiative for childcare). The site is designed to be hosted on GitHub Pages and uses a simple, static structure with German content.

## Development Commands

### Local Development
```bash
# Install dependencies (first time setup)
gem install bundler
bundle install

# Run local development server (auto-reloads on changes)
bundle exec jekyll serve
# Site will be available at http://localhost:4000
```

### Deployment
The site deploys automatically to GitHub Pages when pushed to the main branch. No manual build commands are needed for deployment.

## Architecture

### Site Structure
- **Layouts** (`_layouts/`): Single `default.html` layout that includes header and footer
- **Includes** (`_includes/`): Reusable components
  - `header.html`: Main navigation with logo and menu links
  - `footer.html`: Footer with logo and duplicate navigation
- **Content**:
  - `index.md`: Homepage with all main sections (Lage, Verein, Konzept, Team, Galerie, etc.)
  - `pages/`: Static pages (impressum.md, datenschutz.md, about.md)
- **Assets**:
  - `assets/css/style.css`: Site-wide styles
  - `assets/images/`: Image files (logo, photos)
- **Design** (`design/`): Design mockups and references (excluded from site build)

### Navigation Pattern
The site uses a single-page design with anchor links for main sections (#lage, #verein, #konzept, #team, #galerie) and separate pages for legal content (Impressum, Datenschutzerklärung). Navigation is duplicated in both header and footer.

### Layout Hierarchy
- All pages use the `default` layout
- The default layout includes the header and footer, wraps content in a `<main>` tag
- Page-specific content is injected via `{{ content }}` variable
- Site title is set in `_config.yml` and available as `{{ site.title }}`

### Jekyll Configuration
- Markdown processor: kramdown
- Key plugins: jekyll-feed, jekyll-seo-tag (defined in Gemfile)
- Excluded from build: README.md, design/ directory
- Language: German (lang="de" in default.html)

## Content Management

### Adding/Editing Pages
- Pages use Jekyll front matter with `layout`, `title`, and optionally `permalink`
- Homepage sections are defined directly in index.md using HTML section tags
- Section styling uses classes: `content-section`, `section-centered`, `section-with-image`, `reverse`

### Image Handling
- Images should be placed in `assets/images/`
- Reference in Markdown: `![alt text](/assets/images/filename.jpg)`
- Use Liquid filter for proper paths: `{{ '/assets/images/logo.svg' | relative_url }}`

## Important Notes

- The site is designed for GitHub Pages deployment with no custom domain initially configured
- When deployed, update `url` and `baseurl` in `_config.yml` to match the GitHub Pages URL
- The site uses German language throughout (meta tags, content)
- Design references in `design/` directory are not published to the live site
