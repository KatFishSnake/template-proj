# Template Project

Next.js 16, React 19, TypeScript 5, Tailwind CSS 4, shadcn/ui, Biome, Bun

## Plan Mode

- Make the plan extremely concise. Sacrifice grammar for the sake of concision.
- At the end of each plan, give me a list of unresolved questions to answer, if any.

## Quick Start

```bash
bun install                          # Install deps
bun run dev                          # Dev server (localhost:3000)
bun run verify                       # Type check + lint (before commit)
bunx shadcn@latest add [component]   # Add shadcn component
```

## Key Directories

| Path                    | Purpose                          |
| ----------------------- | -------------------------------- |
| `app/`                  | Next.js App Router pages         |
| `components/`           | React components                 |
| `components/ui/`        | shadcn/ui components             |
| `lib/`                  | Utilities (`cn()` helper)        |
| `.claude/project-info/` | Feature documentation            |

## Import Aliases

- `@/components` - Components
- `@/lib` - Utilities
- `@/hooks` - Hooks
- `@/ui` - shadcn/ui components

## Conventions

- **Server components by default** (no directive)
- **Client components**: Add `"use client"` directive
- **Class merging**: Use `cn()` from `lib/utils.ts`
- **Styling**: CSS variables in `app/globals.css`, OKLCH colors
- **File naming**: Components (PascalCase), utilities (camelCase)

## Feature Documentation System

All features documented in `.claude/project-info/`:

```
.claude/project-info/
├── project-description.md       # Project overview
├── architectural-patterns.md    # Architecture patterns
└── [feature]-[name]/            # Per-feature directory
    ├── feature-info.md          # Requirements (from human)
    └── technical-plan.md        # Implementation (from agent)
```

**Workflow:**
1. Human creates `.claude/project-info/[feature]-[name]/` + `feature-info.md`
2. Agent reads `feature-info.md` and creates `technical-plan.md`
3. Agent always relates plans to a feature - no standalone planning

## Commands Reference

| Task         | Command              |
| ------------ | -------------------- |
| Dev          | `bun run dev`        |
| Build        | `bun run build`      |
| Type check   | `bun run typecheck`  |
| Lint + fix   | `bun run check`      |
| Verify all   | `bun run verify`     |
