# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based marketing blog called "Marketers Weekly Info" using the Mediumish theme. The site focuses on marketing insights, tips, and trends with multiple authors contributing content.

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve the site locally (development mode)
bundle exec jekyll serve

# Using Docker (alternative)
docker-compose up
```

### Build Commands
```bash
# Build the site for production
bundle exec jekyll build

# Build with environment variable
JEKYLL_ENV=production bundle exec jekyll build
```

## Architecture & Structure

### Core Jekyll Structure
- `_config.yml` - Main Jekyll configuration with site metadata, authors, plugins
- `_layouts/` - HTML templates for different page types (post, page, default, archive)
- `_includes/` - Reusable HTML components (pagination, search, sharing, ads)
- `_posts/` - Blog posts in Markdown format with YAML front matter
- `_pages/` - Static pages (about, categories, tags)
- `_sass/` - Sass stylesheets for custom styling
- `assets/` - Static assets (CSS, JS, images, fonts)

### Content Management
- Posts use YAML front matter with fields: layout, title, author, categories, image, featured
- Authors are defined in `_config.yml` with social links and avatars
- Categories and tags are automatically generated into archive pages
- Featured posts are highlighted on the homepage

### Key Features
- Multi-author support with author profiles
- Category-based archives using jekyll-archives plugin
- Pagination (6 posts per page)
- Search functionality using Lunr.js
- Social sharing buttons
- Disqus comments integration
- Optional Google AdSense integration (currently disabled)
- SEO optimization with jekyll-seo-tag

### Deployment
- Configured for Netlify deployment (netlify.toml specifies Ruby 3.4.4)
- Docker support available for containerized development
- Site excludes development files from build (Gemfile, README, etc.)

## Content Creation Guidelines

### Blog Posts
- Place new posts in `_posts/` directory
- Use filename format: `YYYY-MM-DD-title-slug.md`
- Include required front matter: layout, title, author, categories, image
- Use `featured: true` for homepage highlighting
- Author must match a key in `_config.yml` authors section

### Images
- Store images in `assets/images/`
- Reference in posts as `assets/images/filename.jpg`
- Authors have avatar images referenced in config