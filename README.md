# Studio Pond — Fluid High-Res Wallpaper Haven

An immersive wallpaper gallery by **gp_ai_lab** featuring an animated koi pond, interactive water effects, high-resolution wallpaper browsing, PC/mobile categories, and an admin interface.

## Features
- Animated pond scene with koi, ripples, lighting, and interactive effects
- Laptop/PC and mobile wallpaper galleries
- Wallpaper preview and original-file download flow
- Admin interface for adding and removing wallpapers
- Express API for wallpaper indexing, thumbnails, uploads, and downloads
- Vite + React + TypeScript frontend
- Tests for wallpaper filtering, pond physics, and scroll blur utilities

## Local development
Requirements: Node.js 22.12+.

```bash
npm install
npm run dev
```

Open the local URL printed in the terminal (normally http://localhost:3000).

## Build and check
```bash
npm run lint
npm run build
```

## Project layout
- `src/components/` — UI components and gallery/admin modals
- `src/hooks/` — React hooks and tests
- `src/utils/` — wallpaper filters, pond physics, and tests
- `public/assets/` — images and media used by the site
- `public/wallpapers/` — sample PC and mobile wallpapers
- `scripts/` — wallpaper generation utilities
- `server.ts` — Express API and local development server

## Security and deployment
Never commit real environment files, API keys, admin passwords, or session tokens. Review the prototype's admin authentication and upload/delete API before exposing it publicly. The Express API writes files to local disk, so static-only hosting cannot provide persistent uploads; production uploads need a persistent backend/object store and server-side authentication.

The frontend can be built with `npm run build`. The full API requires a Node-capable host or a separately implemented serverless API.

## Repository hygiene
Generated `.aistudio/` and `.cache/` folders are intentionally excluded. Do not commit secrets, `node_modules/`, or build output.

No license has been specified yet; all rights remain with their respective owners until a license is added.
