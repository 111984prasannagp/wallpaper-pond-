<div align="center">

<img src="docs/screenshots/repository-cover.jpg" alt="Studio Pond website preview" width="100%" />

# Studio Pond
### Fluid High-Resolution Wallpaper Haven

**An immersive wallpaper gallery built by G.P. Prasanna · `gp_ai_lab`**

[![Live Website](https://img.shields.io/badge/Live%20Website-Visit%20Studio%20Pond-11cbb5?style=for-the-badge&logo=netlify&logoColor=white)](https://wallpapergpailab.netlify.app/)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-7-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=for-the-badge&logo=vite&logoColor=white)

[Overview](#-overview) · [Features](#-features) · [Screenshots](#-screenshots) · [Technology](#-technology) · [Run locally](#-run-locally) · [Project plan](docs/PROJECT_PLAN.md)

</div>

---

## 🌊 Overview

Studio Pond is a wallpaper gallery built around a living koi pond. Floating lily pads, swimming koi, water-inspired motion, and a curated wallpaper collection create a calm, interactive way to discover high-resolution backgrounds.

**Live website:** [waallpapergpailab.netlify.app](https://waallpapergpailab.netlify.app/)  
**Creator and builder:** **G.P. Prasanna** (`gp_ai_lab`)

## ✨ Features

- **Interactive koi pond** — animated fish, lily pads, and aquatic visuals.
- **Wallpaper discovery** — curated visual collections and responsive wallpaper cards.
- **Laptop / PC and mobile collections** — landscape and portrait formats.
- **High-resolution downloads** — direct wallpaper download actions.
- **Favorites and sorting** — browse and organize wallpapers using available gallery controls.
- **Light and dark presentation** — alternate visual moods for the pond experience.
- **Admin workflow** — interface for wallpaper uploads and deletions.
- **Responsive layout** — designed for desktop and mobile screens.
- **Motion and micro-interactions** — animated states and interactive feedback.

> The frontend and Express API have different hosting needs. Static hosting alone does not make server-side uploads persistent.

## 🖼️ Screenshots

| Homepage — light mode | Homepage — dark mode |
|---|---|
| ![Homepage light mode](docs/screenshots/hero-light.jpg) | ![Homepage dark mode](docs/screenshots/hero-dark.jpg) |

| Laptop / PC gallery | Mobile gallery |
|---|---|
| ![PC gallery](docs/screenshots/pc-gallery.jpg) | ![Mobile gallery](docs/screenshots/mobile-gallery.jpg) |

More screenshots: [docs/screenshots](docs/screenshots/).

## 🧰 Technology

| Technology | Purpose |
|---|---|
| React + TypeScript | Component-based interface and application logic |
| Vite | Development server and production build |
| Tailwind CSS | Styling and responsive layout |
| Motion | UI animation and transitions |
| Lucide React | Interface icons |
| Express | Wallpaper and admin API routes |
| Multer | Multipart image uploads |
| Sharp | Image-processing utilities |
| Netlify | Current public website hosting |

## 🗂️ Project structure

```text
.
├── public/
│   ├── assets/             # Site assets and media
│   └── wallpapers/         # Bundled PC, mobile, and curated wallpapers
├── src/
│   ├── components/         # Gallery, pond, navigation, and admin UI
│   ├── hooks/              # Shared React hooks
│   ├── utils/              # Wallpaper filters and pond physics
│   ├── App.tsx
│   └── main.tsx
├── scripts/                # Wallpaper generation utilities
├── docs/
│   ├── screenshots/        # Project screenshots
│   ├── ARCHITECTURE.md
│   └── PROJECT_PLAN.md
├── server.ts               # Express API and local server entry point
├── package.json
└── vite.config.ts
```

## 🚀 Run locally

**Prerequisite:** Install a Node.js version compatible with the dependencies in `package.json`.

```bash
npm install
npm run dev
```

Open the local URL printed in the terminal (the current server defaults to `http://localhost:3000`).

### Build and type-check

```bash
npm run lint
npm run build
```

Run these checks in your environment before treating a deployment as verified.

## 🧭 How it works

1. The browser loads the React application.
2. The gallery requests wallpaper metadata from the API.
3. The Express server scans the wallpaper directory and collects image details.
4. React renders wallpaper cards, category controls, previews, and download actions.
5. Admin changes use API routes and require a secure server-side configuration.
6. The public frontend is hosted on Netlify; persistent uploads require a backend and durable storage.

See [Architecture](docs/ARCHITECTURE.md) and the [Project Plan](docs/PROJECT_PLAN.md).

## 🔐 Security and deployment

- Never commit `.env` files, API keys, access tokens, or real credentials.
- The supplied project archive contains prototype admin-authentication logic. Audit and replace hardcoded client/server credentials before exposing admin features publicly.
- Do not trust a client-side localStorage flag as authentication.
- Validate and authorize every upload/delete endpoint; validate image types and sizes and rate-limit login attempts.
- Static Netlify hosting cannot permanently write uploads into the deployed project directory. Use a secured backend plus persistent storage for durable uploads.
- Treat admin features as a prototype until the safeguards above are implemented and tested.

## 👨‍💻 About the creator

**G.P. Prasanna — `gp_ai_lab`** is the builder and creator of Studio Pond. The project explores web development, visual design, interactive animation, and AI-assisted building workflows.

The goal is to make wallpaper browsing feel like entering a small, living digital sanctuary rather than scrolling through a static file list.

## 🛣️ Roadmap

- [ ] Replace prototype admin authentication and protect every write endpoint.
- [ ] Move production uploads to persistent object storage.
- [ ] Add CI checks for type-checking and production builds.
- [ ] Verify accessibility, reduced-motion preferences, and keyboard navigation.
- [ ] Optimize image delivery, responsive thumbnails, and caching.
- [ ] Document deployment variables, backups, and restore steps.

## 🤝 Contributing

This is a creator-led project. Keep changes focused, describe what changed, and include screenshots for visual updates. See [CONTRIBUTING.md](CONTRIBUTING.md).

## 📄 License

No license has been added. Until one is chosen, do not assume permission to reuse or redistribute this project.
