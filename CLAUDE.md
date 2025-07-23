# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

SyncJS is a JavaScript middleware library that synchronizes API between browsers, providing cross-browser compatibility through polyfills and normalized APIs. It's a fork of https://github.com/NekR/Sync.

## Build Commands

```bash
# Install dependencies
npm install

# Build all distribution files (standard, IE, and pointer events versions)
npm run build
# or
gulp build-dist

# Clean build artifacts
npm run clean
```

## Architecture

The library uses a modular architecture with separate components for different functionalities:

1. **ES5/ES6 Polyfills** (`src/es/`): Provides compatibility for older browsers
2. **Core Module** (`src/core.js`): Main Sync object with utility functions
3. **DOM Utilities** (`src/dom.js`): Cross-browser DOM manipulation
4. **Event System** (`src/events.js`, `src/events.ie.js`): Normalized event handling
5. **AJAX** (`src/xhr.js`): Cross-browser XHR functionality
6. **Effects** (`src/effects.js`): Animation and visual effects
7. **Window Utilities** (`src/window.js`): Window-related operations
8. **Pointer Events** (`src/pointer.js`): Touch/pointer event support

## Build System

Uses Gulp with three build configurations in `/build/`:
- `build.conf.json`: Standard build
- `build.ie.json`: Internet Explorer compatible build (includes events.ie.js)
- `build.pointers.json`: Build with pointer events support

Each build generates regular and minified versions in `/dist/`.

## Important Notes

- No test framework is currently configured
- No linting configuration exists
- The current branch is "ui" (main branch for PRs)
- When modifying the library, ensure changes are compatible with all three build configurations
- The library focuses on browser compatibility, so test changes across different browsers when possible