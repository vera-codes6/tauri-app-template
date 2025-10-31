# Tauri App Template

Template for building a desktop app with Tauri v2, Vite, and TypeScript (vanilla-ts).

## Prerequisites

- Rust toolchain and platform prerequisites for Tauri v2. See Tauri docs: https://tauri.app/v2/guides/getting-started/prerequisites
- Node.js 22+ (see `engines` in `package.json`)
- Bun package manager: https://bun.sh

On first run, Rust will compile dependencies which can take a few minutes. Subsequent runs are much faster.

## Monorepo layout

- `packages/src-tauri` — Tauri (Rust) app
- `packages/src-renderer` — Web renderer built with Vite + TypeScript

## Install

Run at the repository root:

```sh
bun install
```

## Scripts

- Start app in development with live reload
	- `bun run dev`
- Build production bundles (app binary + installer)
	- `bun run build`
- Work on the renderer only
	- `bun run dev:renderer`
	- `bun run build:renderer`
- Lint renderer TypeScript
	- `bun run lint`
- Generate platform icons (place `packages/src-tauri/app-icon.png` first)
	- `bun run icons`

Notes
- Dev server runs at http://localhost:8080 and is orchestrated via Tauri (`beforeDevCommand` in `packages/src-tauri/tauri.conf.json`).
- Build artifacts are under `packages/src-tauri/target/release/` and installers under `packages/src-tauri/target/release/bundle/`.

## Customize

- The renderer is plain TypeScript. Swap to React/Vue/Svelte by replacing `packages/src-renderer` with your preferred Vite template and adjusting deps.
- If you remove TypeScript, replace `.ts` files with `.js` and drop TS-specific config (e.g., `tsconfig.json`, eslint TS plugins).

## Useful links

- Tauri: https://github.com/tauri-apps/tauri
- Vite: https://vitejs.dev
- TypeScript: https://www.typescriptlang.org

## License

MIT — see [LICENSE](./LICENSE).
