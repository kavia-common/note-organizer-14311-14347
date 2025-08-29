# Notes Frontend (Astro)

A minimalistic light-themed notes application built with Astro. Features:
- Create, edit, delete notes
- List and search notes
- Local persistence by default (localStorage)
- Optional backend API via PUBLIC_API_BASE_URL

## Quick start

1) Install dependencies
   npm install

2) Configure environment (optional)
   Copy .env.example to your .env and set PUBLIC_API_BASE_URL to your backend URL.
   If not set, the app will store notes in your browser (localStorage).

3) Run in development
   npm run dev
   Open the printed URL (default configured port: 3000)

4) Build for production
   npm run build
   npm run preview

## Environment variables

- PUBLIC_API_BASE_URL: Base URL of the notes backend. When defined, the UI will call:
  - GET    {PUBLIC_API_BASE_URL}/notes?q=...
  - POST   {PUBLIC_API_BASE_URL}/notes
  - PUT    {PUBLIC_API_BASE_URL}/notes/:id
  - DELETE {PUBLIC_API_BASE_URL}/notes/:id

If missing, all operations are handled purely in the browser with localStorage.

## Design

- Layout: Header with app title, left sidebar navigation, main area with list and editor.
- Theme: Minimalistic light palette
  - Primary:  #3B82F6
  - Secondary:#64748B
  - Accent:   #F59E42
- Dark mode is supported via the existing ThemeToggle component for convenience.

```text
src/
  layouts/Layout.astro    # App frame (header + sidebar + main)
  pages/index.astro       # Notes UI (list, search, editor)
  components/ThemeToggle.astro
```

No backend required to try it out. Set PUBLIC_API_BASE_URL later to connect to your API.
