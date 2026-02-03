# Astro Portfolio

A modern, performant portfolio website built with Astro 5.x, TypeScript, Tailwind CSS, and smooth animations powered by GSAP and Lenis.

## Features

- ** Lightning Fast**: Built with Astro's static site generation for optimal performance
- ** Modern Styling**: Tailwind CSS 4.x with Vite integration for rapid development
- ** Smooth Animations**: GSAP for complex animations and transitions
- ** Smooth Scrolling**: Lenis for buttery-smooth scroll experiences
- ** Responsive Design**: Mobile-first approach with custom breakpoints
- ** Accessible**: Semantic HTML and accessibility best practices
- ** Type-Safe**: TypeScript with strict mode enabled

## Project Structure

```text
portfolio/
 public/              # Static assets served as-is
    favicon.ico
    favicon.svg
 src/
    assets/          # Optimized assets (images, icons)
       hero.avif
    components/      # Reusable Astro components
       global/      # Global UI components
          Button.astro
          ButtonWrap.astro
          Clickable.astro
          Footer.astro
          Menu.astro
          Navbar.astro
       Guide.astro
       Welcome.astro
    layouts/         # Page layouts
       Layout.astro
    pages/           # File-based routing
       index.astro
    styles/          # Global styles and CSS variables
        custom.css
        global.css
        variables/
            base.css
            spacing.css
            text-style.css
            theme.css
            typography.css
 astro.config.mjs     # Astro configuration
 package.json         # Dependencies and scripts
 tsconfig.json        # TypeScript configuration
```

## Tech Stack

- **Framework**: [Astro](https://astro.build) 5.17.1
- **Styling**: [Tailwind CSS](https://tailwindcss.com) 4.1.18
- **Animations**: [GSAP](https://greensock.com/gsap/) 3.14.2
- **Smooth Scrolling**: [Lenis](https://lenis.darkroom.engineering/) 1.3.17
- **Language**: TypeScript (strict mode)
- **Build Tool**: Vite

## Development

### Prerequisites

- Node.js 18.x or higher
- npm or yarn

### Installation

```bash
# Install dependencies
npm install
```

### Commands

All commands are run from the root of the project:

| Command           | Action                               |
| :---------------- | :----------------------------------- |
| `npm install`     | Install dependencies                 |
| `npm run dev`     | Start dev server at `localhost:4321` |
| `npm run build`   | Build production site to `./dist/`   |
| `npm run preview` | Preview production build locally     |
| `npm run astro`   | Run Astro CLI commands               |

## Architecture

### Component Pattern

Astro components follow this structure:

```astro
---
// Frontmatter: TypeScript logic, imports
import Component from '../components/Component.astro';

interface Props {
  title: string;
}

const { title } = Astro.props;
---

<!-- Template: HTML with component slots -->
<Component />

<style>
  /* Scoped styles */
</style>
```

### File-Based Routing

Pages in `src/pages/` automatically become routes:

- `src/pages/index.astro` `/`
- `src/pages/about.astro` `/about`
- `src/pages/blog/post.astro` `/blog/post`

### Asset Optimization

- **Optimized Images**: Import from `src/assets/` for automatic optimization
- **Static Files**: Place in `public/` for direct serving

```astro
---
import heroImage from '../assets/hero.avif';
---
<Image src={heroImage} alt="Description" />
```

## Styling System

### CSS Variables

Custom CSS variables are organized in `src/styles/variables/`:

- **base.css**: Core design tokens
- **spacing.css**: Consistent spacing scale
- **text-style.css**: Typography styles
- **theme.css**: Theme colors and modes
- **typography.css**: Font families and sizes

### Tailwind Integration

Tailwind CSS 4.x is integrated via Vite for JIT compilation and optimal performance.

## Configuration

### TypeScript

Strict mode enabled in `tsconfig.json` extending Astro's strict configuration:

```json
{
  "extends": "astro/tsconfigs/strict"
}
```

### Astro Config

Configuration in `astro.config.mjs` for integrations and build settings.

## Best Practices

1. **Components**: Keep components focused and reusable
2. **Assets**: Use `src/assets/` for images that need optimization
3. **Styling**: Prefer Tailwind utilities, use scoped styles for component-specific CSS
4. **TypeScript**: Define interfaces for component props
5. **Performance**: Lazy load heavy components and images

## Deployment

Build the production site:

```bash
npm run build
```

The static files in `./dist/` can be deployed to any static hosting service:

- Vercel
- Netlify
- GitHub Pages
- Cloudflare Pages

## Resources

- [Astro Documentation](https://docs.astro.build)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [GSAP Documentation](https://greensock.com/docs/)
- [Lenis Documentation](https://lenis.darkroom.engineering/)

## License

MIT
