# Astro Portfolio - AI Coding Agent Instructions

## Project Overview

This is an Astro 5.x static site portfolio project using TypeScript with strict mode. The codebase follows Astro's standard "basics" template structure with file-based routing.

## Architecture & Structure

### Component Hierarchy

- **Pages** ([src/pages/](src/pages/)): File-based routing. `index.astro` is the entry point
- **Layouts** ([src/layouts/Layout.astro](src/layouts/Layout.astro)): Wrapper for HTML structure, includes global styles reset
- **Components** ([src/components/](src/components/)): Reusable `.astro` components like `Welcome.astro`
- **Assets** ([src/assets/](src/assets/)): SVG images imported directly in components (e.g., `import astroLogo from '../assets/astro.svg'`)
- **Public** ([public/](public/)): Static files served as-is (favicon files)

### Astro Component Pattern

```astro
---
// Frontmatter: TypeScript logic, imports
import Component from '../components/Component.astro';
---
<!-- Template: HTML with component slots -->
<Component />
<style>/* Scoped styles */</style>
```

## Key Conventions

- **No framework UI dependencies**: Pure Astro components (no React/Vue/Svelte currently)
- **TypeScript strict mode**: Extends `astro/tsconfigs/strict`
- **Asset imports**: Images from [src/assets/](src/assets/) are imported as modules with `.src` property
- **Global styles**: Applied in [Layout.astro](src/layouts/Layout.astro) via scoped `<style>` tags
- **Slot pattern**: Layout uses `<slot />` for content injection from pages

## Development Workflows

### Commands (run from project root)

```bash
npm run dev      # Dev server at localhost:4321
npm run build    # Production build to ./dist/
npm run preview  # Preview production build locally
```

### Adding New Pages

1. Create `.astro` file in [src/pages/](src/pages/) (e.g., `about.astro` → `/about`)
2. Import and wrap with [Layout.astro](src/layouts/Layout.astro)
3. Use existing components or create new ones in [src/components/](src/components/)

### Working with Assets

- **Optimized images**: Import from [src/assets/](src/assets/), use `import.src` for src attribute
- **Static files**: Place in [public/](public/) and reference as `/filename.ext`

## Configuration

- **[astro.config.mjs](astro.config.mjs)**: Currently minimal default config; modify here for integrations
- **[tsconfig.json](tsconfig.json)**: Strict TypeScript settings from Astro
- No custom build tools, preprocessors, or additional integrations configured

## Patterns in the Codebase

- **Inline styles**: See [Welcome.astro](src/components/Welcome.astro) - extensive scoped CSS for component styling
- **HTML structure**: [Layout.astro](src/layouts/Layout.astro) sets up document shell with meta tags, favicons
- **Link patterns**: External links with descriptive text, e.g., "Read our docs", "Join our Discord"
