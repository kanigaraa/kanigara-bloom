<div align="center">
  <h1>🌻 Kanigara Bloom</h1>
  <p>A Windows desktop companion for working with one AI provider through a pixel-art sunflower, quick chat, task status, and action approvals.</p>
  <p>
    <a href="https://github.com/kanigaraa/kanigara-bloom/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/kanigaraa/kanigara-bloom?style=flat-square"></a>
    <img alt="Tauri 2" src="https://img.shields.io/badge/Tauri-2-24C8DB?style=flat-square&logo=tauri&logoColor=white">
    <img alt="React and TypeScript" src="https://img.shields.io/badge/React-TypeScript-3178C6?style=flat-square&logo=react&logoColor=white">
    <img alt="In development" src="https://img.shields.io/badge/status-in%20development-orange?style=flat-square">
  </p>
</div>

**Current state:** the repository contains the Tauri, React, and Vite scaffold. AI providers, action approvals, the animated sunflower, and installer are not implemented yet.

## Development

Install Node.js/npm, Rust with the MSVC toolchain, and WebView2. Then run:

```powershell
npm install
npm run tauri dev
```

Build the frontend with `npm run build`.

## Security

Workspace path checks alone do not restrict a provider process. Agent actions must run inside a tested sandbox that enforces file and network scope. Keep agent actions disabled when that boundary is unavailable.

Create a branch for each feature or fix, such as `feat/pixel-companion` or `fix/stale-approval`. Use Conventional Commits except for the initial `init` commit. Open a pull request against `main` before merging.
