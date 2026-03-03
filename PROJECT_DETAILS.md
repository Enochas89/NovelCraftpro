# Project Details

## Overview

NovelCraft Pro Desktop is an Electron-based desktop wrapper for the NovelCraft editor. It uses web technologies for the interface (`index.html`) and Electron runtime files (`main.js`, `preload.js`) for desktop behavior.

## Version and Package Info

- Package name: `novelcraft-pro-desktop`
- Current version: `1.0.1`
- App ID: `com.storyarc.novelcraftpro`
- Product name: `NovelCraft Pro`
- Platforms: Windows and macOS

## Technology Stack

- Electron
- electron-builder
- HTML/CSS/JavaScript
- Node.js

## Repository Structure

- `index.html`: Main UI
- `main.js`: Electron main process entry
- `preload.js`: Renderer preload bridge
- `build/`: Build assets (icons, entitlements)
- `scripts/`: Signing and build helper scripts
- `.github/workflows/build-macos.yml`: macOS CI build workflow
- `licenses/`: Third-party license files

## Build and Release Scripts

- `npm start`: Run app locally
- `npm run build:win`: Build Windows installer
- `npm run build:portable`: Build Windows portable binary
- `npm run build:win:signed`: Build signed Windows installer
- `npm run build:mac`: Build macOS DMG/ZIP for x64 and arm64
- `npm run build:mac:x64`: Build macOS x64 only
- `npm run build:mac:arm64`: Build macOS arm64 only
- `npm run signing:check`: Validate Windows signing setup

## Build Output

- Default output directory: `dist/`
- Windows artifact format: NSIS installer (`.exe`) and optional portable
- macOS artifact formats: `.dmg` and `.zip`

## Signing and Notarization

- Windows signed builds use a `.pfx` certificate through `scripts/build-signed.ps1`
- macOS signing/notarization is configured via `scripts/notarize.js` and environment variables:
  - `CSC_LINK`
  - `CSC_KEY_PASSWORD`
  - `APPLE_ID`
  - `APPLE_APP_SPECIFIC_PASSWORD`
  - `APPLE_TEAM_ID`

## License

- Repository license file: `LICENSE`
- `package.json` package license field: `UNLICENSED`
