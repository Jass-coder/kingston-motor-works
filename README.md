# Kingston Motor Works — Website

Vue 3 + Vite frontend for Kingston Motor Works (Ravenhall, VIC).

## Setup
```bash
npm install
npm run dev
```
Open the local URL Vite prints (usually http://localhost:5173).

## Build for production
```bash
npm run build
```
Output goes to `dist/` — upload that folder to any static host (Netlify, Vercel, cPanel, etc).

## Structure
- `src/views/` — Home, Services, About, Contact pages
- `src/components/` — Navbar, Footer
- `src/router/` — page routing
- `src/style.css` — global design tokens (colors, fonts)

Contact details, address, and services are pulled from the workshop's visiting card. Update `src/components/Footer.vue`, `src/views/Contact.vue`, and `src/views/Home.vue` if any details change.

Images are placeholder stock photos — swap with real Kingston Motor Works workshop photos in `src/views/*.vue`.
