# CLAUDE.md — SCSOK Hackathon Website

## Project Overview

Static informational website for the **Single Cell & Spatial Omics Korea (SCSOK) Hackathon** series. Lists three hackathon editions (1st & 2nd past, 3rd upcoming) with dedicated pages for about, schedule, and results.

## Tech Stack

- **Framework:** SvelteKit 2 (Svelte 4) with TypeScript (strict mode)
- **Build:** Vite 5
- **Styling:** TailwindCSS 3 + Flowbite-Svelte (UI component library) + Flowbite-Svelte-Icons
- **Deployment:** SvelteKit adapter-auto (likely Vercel based on .gitignore)
- **Package Manager:** pnpm (pnpm-lock.yaml present), npm also works

## Commands

```bash
pnpm dev          # Start dev server (localhost:5173)
pnpm build        # Production build
pnpm preview      # Preview production build
pnpm check        # TypeScript/Svelte type checking
pnpm check:watch  # Continuous type checking
```

## Project Structure

```
src/
├── routes/
│   ├── +layout.svelte           # Root layout: navbar + footer
│   ├── +page.svelte             # (unused, kept for reference)
│   ├── +page.server.ts          # Redirects / → /hackathon/3 (latest)
│   └── hackathon/
│       ├── 1/                   # 1st hackathon (past)
│       │   ├── +layout.svelte   # Tab navigation (Main/Schedule/Results)
│       │   ├── +page.svelte     # About, agenda, organizers
│       │   ├── schedule/+page.svelte
│       │   └── results/+page.svelte
│       ├── 2/                   # 2nd hackathon (past) — same structure
│       └── 3/                   # 3rd hackathon (upcoming) — same structure
├── lib/
│   └── index.ts                 # Shared utilities (currently empty placeholder)
├── app.html                     # HTML shell
├── app.css                      # Tailwind base/components/utilities imports
└── app.d.ts                     # TypeScript declarations
static/
├── favicon.png
├── gijang.jpg                   # Background image (hackathons 1 & 3)
├── cau.png                      # Background image (hackathon 2)
└── hackathon.jpg
```

## Architecture & Patterns

### Routing
- SvelteKit file-based routing. `/` redirects (302) to the latest hackathon (`/hackathon/3`).
- Each hackathon has a nested route group (`/hackathon/{1,2,3}/`) with sub-routes for `schedule` and `results`.
- Each hackathon directory has its own `+layout.svelte` providing tab navigation (Main / Schedule / Results).
- Active route detection uses `$page.url.pathname` store.

### Data
- **All data is static/hardcoded** in component `<script>` blocks — no backend, no API calls, no database.
- Hackathon list, schedules, organizers, and results are JS arrays/objects defined directly in each page's script section.
- To update content, edit the relevant `+page.svelte` file directly.

### Styling
- Utility-first TailwindCSS with Flowbite-Svelte components for structured UI (Navbar, Table, Button, Heading, Dropdown).
- Custom primary color palette: orange/coral (#FE795D) defined in `tailwind.config.ts`.
- Dark mode configured via `darkMode: 'selector'` but not actively used.
- Responsive design using Tailwind breakpoints (sm:, md:).

### Component Conventions
- No custom reusable components — all pages use Flowbite-Svelte components directly.
- Section pattern: `<section id="..." class="mb-12">` with `<Heading>` + content.
- Card pattern: `<div class="bg-gray-50 p-6 rounded-lg shadow">`.
- Tab navigation pattern is repeated across hackathon layouts (potential extraction target).

## External Links (not APIs)

- Zulip community: https://zulip.scsok.io
- Google Forms for registration (hackathon 3)
- KASRA events: https://events.kasra.kr/event/3

## Key Files for Common Tasks

| Task | Files |
|------|-------|
| Update navbar/footer | `src/routes/+layout.svelte` |
| Change which hackathon is "latest" | `src/routes/+page.server.ts` (redirect) + navbar in `+layout.svelte` |
| Update hackathon N info | `src/routes/hackathon/{N}/+page.svelte` |
| Update hackathon N schedule | `src/routes/hackathon/{N}/schedule/+page.svelte` |
| Update hackathon N results | `src/routes/hackathon/{N}/results/+page.svelte` |
| Change tab navigation | `src/routes/hackathon/{N}/+layout.svelte` |
| Modify color palette | `tailwind.config.ts` |
| Add global styles | `src/app.css` |
