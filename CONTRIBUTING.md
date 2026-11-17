# Contributing to Kanigara Bloom

For bugs, open an issue with steps to reproduce, the expected result, the actual result, and your Windows version. Remove tokens, credentials, and private conversation content from logs or screenshots.

For substantial features, open an issue to discuss the scope before implementing them.

## Development setup

Install Node.js/npm, Rust with the MSVC toolchain, Microsoft C++ Build Tools, and WebView2. Follow the [Tauri prerequisites](https://v2.tauri.app/start/prerequisites/) for Windows.

Fork this repository on GitHub, then clone your fork. Replace `YOUR_USERNAME` with your GitHub username:

```powershell
git clone https://github.com/YOUR_USERNAME/kanigara-bloom.git
cd kanigara-bloom
git remote add upstream https://github.com/kanigaraa/kanigara-bloom.git
npm ci
npm run tauri dev
```

Maintainers with write access can clone the original repository and use `origin` in place of `upstream` below.

## Branches and commits

Create a branch for each feature or fix from the latest `main`:

```powershell
git switch main
git fetch upstream
git merge --ff-only upstream/main
git switch -c feat/pixel-companion
```

Use `feat/` for features, `fix/` for bug fixes, and `docs/` for documentation changes. Keep unrelated work in separate branches.

Use Conventional Commits, for example:

```text
feat: add companion visibility control
fix: reject stale approval requests
docs: clarify Windows development setup
```

The initial `init` commit is the only exception.

## Pull requests

Push your branch to your fork:

```powershell
git push -u origin feat/pixel-companion
```

On GitHub, open a pull request from your fork's branch to `kanigaraa/kanigara-bloom`, targeting `main`. Describe what changed, why it changed, and which checks you ran. Report any checks you could not run and explain why. Keep private planning documents and ignored local files out of commits.

Before submitting, run the checks relevant to your changes:

```powershell
npm run build
cargo fmt --manifest-path src-tauri/Cargo.toml -- --check
cargo check --manifest-path src-tauri/Cargo.toml
git diff --check
```

For UI changes, check the affected flow in the desktop app and include screenshots when they help explain the change. For behavior changes, add a focused regression test where practical. Do not claim a check passed unless you ran it.

Wait for review and resolve relevant findings before merging. Avoid new production dependencies unless they are needed and agreed upon in the issue or pull request.

## License

Contributions are licensed under the project's [MIT License](LICENSE).
