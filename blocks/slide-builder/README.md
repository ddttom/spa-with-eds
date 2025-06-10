# Slide Builder Block for Adobe Edge Delivery Services

A lightweight, responsive slide gallery component built with vanilla JavaScript and modern ES modules for Adobe Edge Delivery Services (EDS). Designed for performance and simplicity without framework dependencies.

This component demonstrates how to build dynamic, interactive experiences with EDS while maintaining excellent performance scores through modern web development practices.

## Overview

This slide builder demonstrates how to build dynamic, interactive experiences with Edge Delivery Services while preserving perfect Lighthouse scores. It uses a content-first approach where authors create individual pages for each slide, making content management straightforward and familiar within the EDS ecosystem.

## Architecture Principles

- **EDS Integration**: Leverages EDS query-index and .plain.html endpoints for content management
- **Hybrid Approach**: Keep landing pages as pure EDS for perfect performance, use SPA functionality for interactive galleries
- **Content-First**: Each slide is a full EDS page with its own URL and content
- **Progressive Enhancement**: Mobile gets essential features, desktop receives enriched content
- **Framework-less**: Pure vanilla JavaScript maintains EDS simplicity and performance principles</search>
</search_and_replace>

## Features

- **Lazy Loading**: Images load only when approaching viewport for optimal performance
- **WebP Support**: Automatic detection and optimization for modern browsers
- **Responsive Design**: Adapts content based on screen size (mobile-first approach)
- **Interactive Panels**: Click slides to view full content without navigation
- **JSON-Powered**: Uses EDS query-index for dynamic data
- **Plain HTML Fragments**: Leverages `.plain.html` endpoint for content reuse

## Content Structure

### 1. Create Slide Pages

Create individual pages in your Google Drive for each slide:
```
/slides/
├── york-minster/
├── the-shambles/
└── city-walls/
```

Each page should include:
- Title
- Hero image
- Descriptive text
- Metadata block

### 2. Set Up Query Index

Create a `query-index` spreadsheet in your slides folder with columns:
- path
- title  
- image
- description
- lastModified

### 3. Publish Pages

**Important**: Pages must be published to appear in the JSON endpoint. The query-index only includes published pages, not drafts.

## JSON Endpoint

EDS automatically generates a JSON endpoint at `/slides/query-index.json`:

```json
{
  "total": 5,
  "offset": 0,
  "limit": 5,
  "data": [
    {
      "path": "/slides/york-minster",
      "title": "York Minster",
      "image": "/slides/media_188fa5.png",
      "description": "A magnificent Gothic cathedral...",
      "lastModified": "1719573871"
    }
  ]
}
```</search>
</search_and_replace>

## Installation

1. Add block files to your EDS project:
   ```
   /blocks/slide-builder/
   ├── slide-builder.js
   └── slide-builder.css
   ```

2. Ensure query-index is configured at `/slides/query-index.json`

3. Add the block to your page:
   ```html
   <div class="slide-builder"></div>
   ```

## How It Works

### Data Loading Strategy

```javascript
// Fetch slide data from query-index
const response = await fetch("/slides/query-index.json");

// Desktop: Pre-fetch HTML content
// Mobile: Load on-demand only
if (window.innerWidth > 799) {
  slide.html = await fetchSlideHtml(slide.path);
}
```

### Plain HTML Fragments

The `.plain.html` endpoint returns content without headers/footers:

```javascript
const response = await fetch(`${path}.plain.html`);
```

This enables content reuse while treating the DOM as a first-class citizen - a core EDS principle.

### Progressive Enhancement

- **Mobile (≤800px)**: Title + description only, HTML loaded on-demand
- **Desktop (>800px)**: Full content with supporting text pre-loaded

## Performance Optimization

1. **Intersection Observer**: Images load 100px before entering viewport
2. **Conditional Loading**: Mobile skips HTML until requested
3. **WebP Detection**: Automatic format optimization
4. **DOM Parsing**: Extract content directly without complex transformations

## Styling Components

- **Slide Height**: Fixed 600px with cover positioning
- **Roundels**: Numbered indicators (1, 2, 3...) in top-left
- **Text Overlay**: Semi-transparent container at bottom-left
- **Modal Panels**: Full-screen overlays for detailed content

## Customization Options

### Image Optimization
```javascript
// Modify WebP parameters
`${imageUrl}?width=2000&format=webply&optimize=medium`
```

### Lazy Loading Threshold
```javascript
// Adjust when images start loading
{ rootMargin: "100px" }
```

### Content Extraction
```javascript
// Customize which paragraph becomes supporting text
const firstParagraph = h2.nextElementSibling;
```

## Browser Support

- Modern browsers with ES6+ support
- Intersection Observer API required
- WebP detection for progressive enhancement
- DOMParser for content extraction

## Error Handling

- Graceful degradation if JSON fetch fails
- Console logging for debugging
- Missing HTML content doesn't break functionality
- Failed images logged but don't stop execution

## Best Practices

1. **Author Experience**: Keep slide creation simple - one page per slide
2. **Performance**: Use home/landing pages as pure EDS, SPAs for galleries
3. **Mobile First**: Essential features for all, enhancements for desktop
4. **Content Reuse**: Leverage `.plain.html` for DRY principles

## Future Enhancements

This vanilla JavaScript implementation can be extended to:
- Product catalogues with filtering and search
- Interactive media galleries
- Data visualizations and dashboards
- Integration with modern frameworks (React, Vue, Web Components)
- Advanced animation and transition effects

## Development Notes

This component follows modern web development best practices:
- **ES Modules**: Clean, maintainable code organization
- **Progressive Enhancement**: Works on all devices, enhanced on capable ones
- **Performance-First**: Lazy loading, efficient DOM manipulation, minimal dependencies
- **Accessibility**: Semantic HTML, keyboard navigation, screen reader support

## Summary

This approach demonstrates that Edge Delivery Services isn't limited to static pages. With thoughtful architecture and modern JavaScript techniques, you can build rich, interactive experiences while maintaining the platform's core performance strengths - achieving the best of both worlds.
