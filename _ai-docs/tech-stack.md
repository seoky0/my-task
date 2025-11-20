# AI Tech Stack Documentation

This document outlines the technology stack and coding guidelines for the `my-task` project. AI agents should follow these rules to ensure code consistency and quality.

## Core Stack

- **Framework**: Next.js 16.0.3 (App Router)
- **UI Library**: React 19.2.0
- **Language**: TypeScript 5+
- **Runtime**: Node.js 24.11.1 (Managed by `mise`)
- **Package Manager**: pnpm (latest)

## Coding Guidelines

### Next.js & React
- **App Router**: Use the App Router (`app/` directory).
- **Server Components**: By default, all components are Server Components. Use them for data fetching and static content.
- **Client Components**: Add `"use client"` directive at the top of the file only when necessary (e.g., using hooks like `useState`, `useEffect`, or event listeners).
- **Images**: Use `next/image` for image optimization.
- **Fonts**: Use `next/font` (Geist) as configured in `app/layout.tsx`.

### TypeScript
- **Strict Typing**: Avoid `any`. Use specific types or generics.
- **Interfaces vs Types**: Be consistent. Prefer `interface` for object definitions and `type` for unions/intersections.
- **Props**: Define component props explicitly.

### Styling
- **CSS Modules**: Use CSS Modules for component-level styling (`*.module.css`).
  - Naming convention: `camelCase` for class names in JS/TS, `kebab-case` or `camelCase` in CSS (match the project style).
- **Global Styles**: Use `app/globals.css` for global variables (colors, fonts) and resets.
- **No Inline Styles**: Avoid inline styles unless for dynamic values.

### Linting & Formatting (Biome)
- **Tool**: Biome 2.2.0
- **Rules**: Follow the recommended rules in `biome.json`.
- **Formatting**:
  - Indent style: Space
  - Indent width: 2
  - Quote style: Double quotes (as per Biome default)
  - Semicolons: Always
- **Imports**: Organize imports automatically using Biome.

## Project Structure

```
my-task/
├── app/                 # Next.js App Router source
│   ├── globals.css      # Global styles & CSS variables
│   ├── layout.tsx       # Root layout
│   ├── page.tsx         # Home page
│   └── ...
├── public/              # Static assets
├── _docs/               # Human-readable documentation
├── _ai-docs/            # AI-specific documentation
├── biome.json           # Biome configuration
├── mise.toml            # Tool version management
├── next.config.ts       # Next.js configuration
└── package.json         # Dependencies & scripts
```

## Development Workflow

### Commands (via `mise` or `pnpm`)

- **Install**: `mise run install` or `pnpm install`
- **Dev Server**: `pnpm dev` (http://localhost:3000)
- **Build**: `mise run build` or `pnpm build`
- **Lint**: `mise run lint` or `pnpm biome check`
- **Format**: `mise run fmt` or `pnpm biome format --write`

### Version Control
- **Commits**: Follow Conventional Commits (feat, fix, docs, style, refactor, test, chore).
