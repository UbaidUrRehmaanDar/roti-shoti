# Rawty Shawty — Vue 3 Demo SPA

Rawty Shawty is a small, self-contained web app built as a personal demo to push my limits and test myself. It is my first attempt with Vue. The focus was on learning modern Vue 3 patterns, client-side routing, icon pipelines, and a fast development workflow with Vite.

This repository is intentionally front-end only and can be deployed as static assets.

## Table of Contents
- Overview
- Features
- Browser Experience and Support
- Tech Stack
- Project Structure
- Getting Started
- Usage
- Build and Deployment
- Contributing
- License
- Credits

## Overview
- Purpose: A demo website to explore Vue 3, routing, icons, and Vite-based builds.
- Scope: Front-end only. No server or database required.
- Outcome: A responsive single-page application that demonstrates component-driven UI and client-side navigation.

## Features
- Single-page application with client-side routing (no full page reloads)
- Fast local development with Hot Module Replacement (HMR)
- SVG icon system with auto-imported components
- Component-based architecture for reusable UI
- Responsive layout targeting common device sizes
- Static deployable build with tree-shaken assets
- Minimal configuration via Vite

## Browser Experience and Support
- Client-side navigation: Pages are swapped using the HTML5 History API, so the URL updates without a full reload.
- Routing: Direct linking to routes works when served with a static host configured for SPA fallbacks (e.g., Netlify “SPA redirect” or a GitHub Pages 404.html fallback).
- Performance: Vite outputs optimized, tree-shaken ESM. Only the icons/components you import are included.
- Icons: Icons are compiled as inline SVG components. There is no runtime icon fetching, which keeps rendering fast and avoids layout shifts.
- Accessibility baseline: Uses semantic HTML and standard link/button interactions. Further accessibility work may be needed for production.
- Browser support: Designed for the latest versions of modern evergreen browsers (Chrome, Firefox, Edge, Safari). Internet Explorer is not supported. Mobile browsers based on these engines should generally work.
- JavaScript requirements: This app relies on ES modules and modern JavaScript features. Ensure JavaScript is enabled and your environment supports ESM.

## Tech Stack
- Frontend: Vue 3 (Single File Components, Composition API)
- Routing: Vue Router 4
- Build tooling: Vite 7
- Icons:
  - mdi-vue and @mdi/js (Material Design Icons)
  - unplugin-icons with auto-imported icon components
  - unplugin-vue-components for automatic component registration

Note: The repository includes some UI-related packages (e.g., @mui/material, @mui/icons-material, @emotion/*). These were part of experimentation and are not required to understand or run the core Vue demo.

## Project Structure
```
.
├─ README.md
├─ package.json
├─ vite.config.js
└─ src/
   ├─ main.js
   ├─ App.vue
   ├─ components/
   ├─ router/
   └─ style.css
```

## Getting Started

### Prerequisites
- Node.js 18+ (recommended)
- npm 8+ (bundled with Node)

Check versions:
```bash
node -v
npm -v
```

### Installation
Install dependencies:
```bash
npm install
```

### Development
Start the dev server:
```bash
npm run dev
```
Open the local URL printed in the terminal (typically http://localhost:5173).

## Usage
- Navigate through the app using the header or in-app links. Routes change without a full page refresh.
- Explore the UI components under different routes to see how state and rendering behave in a Vue SPA.
- Icons are used as Vue components and render as inline SVG. If you add more icons, import them and they will be tree-shaken automatically in production builds.

Because this is a demo and learning project, you may encounter placeholder content, experimental components, or routes meant to test behavior rather than serve a production feature set.

## Build and Deployment

Create a production build:
```bash
npm run build
```

Preview the production build locally:
```bash
npm run preview
```

The output in the dist/ directory can be deployed to any static hosting provider.

Common hosting notes:
- GitHub Pages: Serve the dist/ folder. For Vue Router history mode, configure a 404.html fallback so deep links resolve to index.html.
- Netlify: Set build to `npm run build` and publish to `dist/`. Enable SPA redirect (/* → /index.html).
- Vercel: Use the static build output from `dist/`.

## Contributing
This is a personal demo project. If you want to open an issue or PR to discuss approaches or suggest improvements, feel free.

Basic flow:
1. Fork the repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Commit: `git commit -m "feat: describe your change"`
4. Push and open a Pull Request

## License
No license file is included. Until a license is added, all rights are reserved. If you intend to use this project as open source, consider adding a LICENSE file (e.g., MIT).

## Credits
- Built by @UbaidUrRehmaanDar
- Powered by Vue 3, Vite, Vue Router, and Material Design Icons with unplugin-icons
