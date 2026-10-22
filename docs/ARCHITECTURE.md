# Architecture Notes

## High-level layout

```text
Browser
  └── React + TypeScript UI
       ├── Pond scene and animation
       ├── Navigation and content pages
       ├── Wallpaper cards / preview / download
       └── Admin interface
            └── HTTP requests to /api/*
                  └── Express server
                       ├── Wallpaper directory scanner
                       ├── Metadata and list endpoints
                       ├── Upload endpoint (Multer)
                       ├── Delete endpoint
                       └── Image processing (Sharp)
```

## Frontend
The React app is bootstrapped from `src/main.tsx` and assembled through `src/App.tsx`. Feature-specific UI lives in `src/components/`. Shared gallery filtering and pond behavior live in `src/utils/`.

## Server
`server.ts` creates the Express application. It scans `public/wallpapers`, collects image metadata, and exposes routes for listing, uploading, and deleting wallpaper files. Uploads are written to local disk.

## Deployment boundary
A local filesystem is not durable storage on static hosting and may be ephemeral on some application hosts. If uploads must remain available after redeploys/restarts, use persistent storage. Every mutation endpoint must validate an authenticated admin on the server; frontend-only checks are not sufficient.
