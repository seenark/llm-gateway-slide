# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Slidev** presentation project - a web-based slides maker and presenter for developers. Slidev uses Markdown for slide content with Vue components for interactivity.

## Development Commands

```bash
# Install dependencies (use bun, pnpm, or npm)
bun install  # or pnpm install / npm install

# Start development server (opens at http://localhost:3030)
bun run dev  # or pnpm dev / npm run dev

# Build for production
bun run build  # or pnpm build / npm run build

# Export to PDF/PNG
bun run export  # or pnpm export / npm run export
```

## Architecture

### Core File Structure

- **`slides.md`** - Main presentation entry point. All slide content is written in Markdown with frontmatter configuration.
- **`components/`** - Custom Vue components that can be embedded in slides (e.g., `<Counter />`)
- **`pages/`** - Additional slide files that can be imported into `slides.md` using `src: ./pages/filename.md`
- **`snippets/`** - External code files that can be referenced in slides using `<<< @/snippets/file.ts#snippet`

### Slidev Concepts

- **Frontmatter** - Each slide block is separated by `---` and can have frontmatter for layout, transitions, theme, etc.
- **Layouts** - Pre-built layouts like `two-cols`, `image-right`, `center` can be specified in frontmatter
- **Directives** - Vue directives for interactivity:
  - `v-click` - Show elements on click
  - `v-mark` - Highlight text (underline, circle, etc.)
  - `v-motion` - Animate elements using @vueuse/motion
- **Code Blocks** - Syntax highlighting with Shiki, supports `{monaco}` for editable code and `{monaco-run}` for executable code
- **MDC Syntax** - Enhanced Markdown with component support

### Theme Configuration

The theme is set in `slides.md` frontmatter:
```yaml
---
theme: bricks  # Options: default, seriph, bricks
background: https://cover.sli.dev
transition: slide-left
mdc: true
---
```

## Deployment

- **Netlify**: Uses `netlify.toml` - builds to `dist/` with Node 20
- **Vercel**: Uses `vercel.json` - SPA rewrite to `index.html`

## Slidev

ALWAYS use skill `slidev` when creating slides.
