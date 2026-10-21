# nikmtl.dev

Under-construction landing page for nikmtl.dev, built with SvelteKit + Tailwind CSS, plus German
`/legal` (Impressum) and `/privacy` (Datenschutzerklärung) pages.

## Run locally

```sh
npm install
npm run dev -- --open
```

## Deploy (Dokploy or any Docker host)

```sh
docker compose up --build
```

Point your Dokploy app at this repo/branch, build type **Dockerfile**. The image is a multi-stage
build: a Node build stage compiles the SvelteKit app, the final stage runs it with
`@sveltejs/adapter-node` — no `node_modules` needed at runtime, no nginx, no static export.

- Exposed/listening port: `3000` (`PORT` env var, set by the Dockerfile).
- No environment variables or persistent storage required beyond that.

## Structure

- `src/routes/+layout.svelte` — shared chrome: background effects, nav, footer (with links to
  Impressum/Datenschutz)
- `src/routes/+page.svelte` — the under-construction home page
- `src/routes/legal/+page.svelte` — Impressum
- `src/routes/privacy/+page.svelte` — Datenschutzerklärung
- `src/routes/layout.css` — Tailwind v4 entry point + theme tokens (`@theme`) + small custom layers
- `Dockerfile` / `docker-compose.yml` — multi-stage containerization