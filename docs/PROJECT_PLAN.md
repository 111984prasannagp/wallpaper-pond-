# Studio Pond — Project Plan

## 1. Project identity
- **Project:** Studio Pond — Fluid High-Resolution Wallpaper Haven
- **Creator / builder:** G.P. Prasanna (`gp_ai_lab`)
- **Live website:** https://waallpapergpailab.netlify.app/
- **Goal:** Present curated high-resolution wallpapers through a calm, interactive koi-pond experience.

## 2. Product overview
Studio Pond combines an animated aquatic homepage, wallpaper collections for different device formats, browsing controls, download actions, favorites, and an admin interface for content management.

## 3. Intended users
- People looking for high-resolution desktop and mobile wallpapers.
- Visitors who enjoy polished, motion-rich web experiences.
- The site owner, who needs a workflow for maintaining wallpaper files.

## 4. Main user journeys

### Visitor
1. Open the website and explore the animated pond.
2. Browse the Laptop / PC or Mobile collection.
3. Preview a wallpaper and download the original file.
4. Optionally use available sorting and favorites controls.

### Admin
1. Open the admin interface.
2. Authenticate using server-validated credentials.
3. Upload files to the correct device category.
4. Verify the gallery reflects the change.
5. Delete outdated items when authorized.

**Security gate:** The supplied archive contains prototype authentication logic. Replace hardcoded credentials and client-side authentication flags, protect every mutation endpoint, validate uploads, and test authorization before production use.

## 5. Feature inventory
- Animated pond scene, koi, and lily-pad visuals.
- PC and mobile wallpaper collections.
- Wallpaper cards, metadata, preview, and download controls.
- Gallery sorting and favorites.
- Light/dark presentation controls.
- Admin UI for upload/delete workflows.
- Express API for scanning wallpaper folders and serving metadata.
- Scripts for generating sample wallpaper assets.
- Tests for selected filtering and pond-physics utilities.

## 6. Technology stack

| Layer | Technology | Responsibility |
|---|---|---|
| UI | React + TypeScript | Components and app behavior |
| Build | Vite | Development and production build |
| Styling | Tailwind CSS | Layout and responsive styling |
| Animation | Motion | Transitions and interactive motion |
| Icons | Lucide React | Interface iconography |
| Server | Node.js + Express | API routes |
| Uploads | Multer | Multipart image handling |
| Image tools | Sharp | Image processing and thumbnails |
| Hosting | Netlify | Current public website frontend |

## 7. How data flows
1. Browser loads the frontend.
2. Gallery requests wallpaper metadata from the API.
3. Server scans the configured wallpaper folder and returns file metadata.
4. UI renders cards, previews, and download actions.
5. Admin uploads/deletions call API endpoints and refresh the gallery after success.

## 8. Repository layout
- `src/components/`: UI components and dialogs.
- `src/hooks/`: shared hooks and hook tests.
- `src/utils/`: wallpaper filtering and pond physics.
- `public/wallpapers/`: bundled wallpaper files.
- `public/assets/`: site media.
- `scripts/`: wallpaper generation utilities.
- `server.ts`: Express server and API endpoints.
- `docs/screenshots/`: screenshots used in documentation.

## 9. Deployment model
Netlify hosts the current public website. Static hosting can serve bundled files but cannot permanently write uploaded files into the deployed directory. The Express API expects a Node runtime and local filesystem access.

For persistent production uploads, use either:
- A Node-capable host with durable storage; or
- Serverless functions with persistent object storage and server-side authorization.

Never expose upload/delete routes without authentication and authorization.

## 10. Prioritized roadmap

### P0 — Security
- [ ] Replace hardcoded credentials with server-side environment variables.
- [ ] Use server-issued sessions/tokens and enforce authorization on upload/delete routes.
- [ ] Remove localStorage-only authentication trust.
- [ ] Add upload type/size validation, safe filenames, and rate limiting.
- [ ] Keep secrets out of Git.

### P1 — Production hosting
- [ ] Separate frontend and API deployment configuration.
- [ ] Move uploads to durable object storage.
- [ ] Configure HTTPS, CORS, cache headers, and backups.
- [ ] Test upload/download/delete in the deployed environment.

### P2 — Quality
- [ ] Add CI for type-checking and build validation.
- [ ] Test API endpoints and admin authorization.
- [ ] Audit keyboard navigation, contrast, reduced motion, and mobile layout.
- [ ] Optimize image delivery and lazy loading.

### P3 — Product polish
- [ ] Document wallpaper licensing and attribution.
- [ ] Add developer setup and deployment guides.
- [ ] Document backup and restore procedures.

## 11. Production acceptance checklist
- [ ] `npm run lint` passes.
- [ ] `npm run build` passes.
- [ ] Tests pass, including API authorization.
- [ ] No hardcoded secrets remain.
- [ ] Unauthenticated upload/delete requests are rejected.
- [ ] Uploaded wallpapers persist across redeploys and restarts.
- [ ] Desktop and mobile flows are verified.
- [ ] Documentation matches the deployed architecture.
