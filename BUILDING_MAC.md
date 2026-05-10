# Building macOS desktop binaries

This project now targets Electron `13.6.9` and `electron-builder 24.x` for Apple Silicon support.

## Recommended Node.js

Use **Node.js 20.19.0 LTS** (or another Node 20.x LTS release) for the most reliable install/build behavior with this legacy webpack/electron stack.

## Install

From repository root:

```bash
npm install --legacy-peer-deps
```

From `electron/`:

```bash
cd electron
npm install --legacy-peer-deps
```

## Build renderer bundle for Electron

From repository root:

```bash
npm run build-electron
```

This creates/updates the renderer files used by the Electron app in `electron/www`.

## Run desktop app locally

From `electron/`:

```bash
npm start
```

## Build macOS artifacts

From `electron/`:

```bash
npm run build:mac:arm64
```

Optional x64 build:

```bash
npm run build:mac:x64
```

Optional universal build (when your signing/notarization setup supports it):

```bash
npm run build:mac:universal
```

## Notes

- `--legacy-peer-deps` is currently required due to old dependency peer constraints in the legacy web build toolchain.
- macOS packaging still requires running on macOS with Xcode command line tools installed.
