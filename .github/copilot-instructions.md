# Copilot Instructions for arron-2026

## Project Overview
This is an Astro 5.0 project using the "basics" starter template with TypeScript support. It's a static site generator focused on performance and developer experience.

## Architecture & File Structure
- **Pages**: `src/pages/` - File-based routing. Each `.astro` file becomes a route
- **Layouts**: `src/layouts/Layout.astro` - Base HTML structure with `<slot />` for content injection
- **Components**: `src/components/` - Reusable Astro components (`.astro` files)
- **Assets**: `src/assets/` - Images and static assets imported as modules
- **Public**: `public/` - Static files served directly (favicon, etc.)

## Key Patterns & Conventions

### UI
Gravitate towards simple Swiss design principles—clean lines, ample whitespace, and a neutral color palette. Prioritize usability and accessibility in all components.

### Astro Component Structure
All `.astro` files follow this pattern:
```astro
---
// Component script (TypeScript)
import statements
// Server-side logic
---

<!-- Template (HTML + Astro syntax) -->
<div>Content with {expressions}</div>

<style>
/* Scoped CSS */
</style>
```

### Import Patterns
- Components: `import ComponentName from '../components/ComponentName.astro'`
- Assets: `import imageSrc from '../assets/image.svg'` then use `imageSrc.src`
- Use relative imports consistently

### Asset Handling
- SVG assets in `src/assets/` are imported as modules with `.src` property
- Static assets in `public/` are referenced with absolute paths (`/favicon.svg`)
- Astro optimizes imported assets automatically

## Development Workflow

### Essential Commands
- `pnpm dev` - Start dev server at `localhost:4321`
- `pnpm build` - Build for production to `./dist/`
- `pnpm preview` - Preview production build locally

### TypeScript Configuration
- Uses `astro/tsconfigs/strict` for strict type checking
- Include `.astro/types.d.ts` for Astro-specific types
- Astro generates types automatically during development

## Integration Points
- **Package Manager**: pnpm (use pnpm commands, not npm)
- **TypeScript**: Strict mode enabled via extends
- **Build Tool**: Astro's built-in Vite-based build system

## Common Tasks
- **New Page**: Create `.astro` file in `src/pages/` - automatically becomes a route
- **New Component**: Create `.astro` file in `src/components/` and import where needed
- **Styling**: Use scoped `<style>` blocks in components or global styles in Layout
- **Static Assets**: Place in `public/` for direct serving or `src/assets/` for optimization

## Project-Specific Notes
- This is a minimal Astro setup - no additional integrations or frameworks
- Uses file-based routing (no complex routing configuration)
- Components are server-rendered by default (zero JS shipped unless needed)
- Layout component provides basic HTML structure and global styles