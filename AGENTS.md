# AGENTS.md

## Project Overview

This repository is a Cosmic Studio fork of Helios Launcher.

The current goal is not to rewrite the launcher.  
The short-term goal is to prepare a minimally modified Cosmic Client launcher build based on Helios Launcher.

Cosmic terms:

- Cosmic Studio: top-level brand and operator.
- Cosmic Network: Discord-centered community, announcements, support, events, and user communication.
- Cosmic Server: Minecraft server, API, bot, database, authentication, and operations backend.
- Cosmic Client: end-user launcher/client application for Minecraft server access, mod profile management, official server configuration, and future account-linked features.

## Current Development Phase

This repository is currently in Phase 1.

Phase 1 scope:

- Update external links.
- Update visible brand text where safe.
- Update support/community URLs.
- Keep launcher behavior unchanged.
- Keep authentication behavior unchanged.
- Keep server distribution behavior unchanged unless explicitly requested.

Do not implement account linking, payments, cosmetics, currencies, custom authentication, or new API integration during Phase 1.

## Safety Rules

Do not change security-sensitive behavior unless explicitly requested.

Avoid modifying:

- Microsoft authentication flow.
- Mojang/Yggdrasil authentication flow.
- Credential handling.
- Auto-update behavior.
- File validation behavior.
- Java validation/install behavior.
- Server distribution parsing.
- Launcher bootstrap logic.

When in doubt, prefer the smallest possible change.

## Development Commands

Use Node.js 22.x.

Install dependencies:

```bash
npm ci
```

If `npm ci` fails due to lockfile or environment issues:

```bash
npm install
```

Run the launcher locally:

```bash
npm start
```

Run lint:

```bash
npm run lint
```

Build for the current platform:

```bash
npm run dist
```

Build for a specific platform:

```bash
npm run dist:win
npm run dist:mac
npm run dist:linux
```

## Branch Policy

Use `develop` as the integration branch.

Recommended branches:

- `feature/link-update`
- `feature/brand-assets`
- `feature/menu-structure`
- `release/v0.1.0-cosmic-linkpatch`
- `hotfix/v0.1.1-link-fix`

Do not commit directly to `main`.

`main` should contain only reviewed release-ready builds.

## Coding Guidelines

Keep changes small and easy to review.

Prefer:

- Minimal diffs.
- Existing project conventions.
- Existing file structure.
- Existing naming style.
- Existing UI behavior.

Avoid:

- Large refactors.
- Unrelated formatting changes.
- Moving files without a clear reason.
- Replacing working logic with new abstractions.
- Adding new dependencies unless explicitly requested.

## UI and Menu Guidelines

For Phase 1, only update labels and links.

For Phase 2 menu work:

- First identify the current menu rendering structure.
- Preserve existing navigation behavior.
- Hide or rename menu items before deleting them.
- Do not remove code paths that may still be used by the launcher.
- Keep changes reversible.

## Brand Guidelines

Use Cosmic Client when referring to the launcher product.

Use Cosmic Network for Discord/community links.

Use Cosmic Server for official Minecraft server/backend service references.

Use Cosmic Studio for the parent brand/operator.

Do not mix these terms casually.

## Testing Checklist

Before finishing a task, verify:

- The app starts with `npm start`.
- `npm run lint` passes or any existing lint issue is clearly identified.
- Updated links open the intended Cosmic destination.
- Login UI still appears normally.
- Existing server selection behavior is not broken.
- No credentials, tokens, or private URLs are committed.

## Commit Message Style

Use simple conventional-style messages:

- `chore: update Cosmic launcher links`
- `chore: update Cosmic branding`
- `feat: adjust launcher menu labels`
- `fix: correct support link target`
- `docs: add agent instructions`

## Important Constraint

This fork is a transitional Cosmic Client build.

Do not treat this repository as the final long-term Cosmic Client architecture unless explicitly requested.