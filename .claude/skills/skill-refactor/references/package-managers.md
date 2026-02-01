# Package Manager Transformations

Reference patterns for transforming between package managers.

## Common Patterns

| Pattern | pnpm | bun | npm | yarn |
|---------|------|-----|-----|-------|
| **add** | `pnpm add` | `bun add` | `npm install` | `yarn add` |
| **install** | `pnpm install` | `bun install` | `npm install` | `yarn install` |
| **remove** | `pnpm remove` | `bun remove` | `npm uninstall` | `yarn remove` |
| **exec** | `pnpm exec` | `bun x` | `npx` | `yarn exec` |
| **run** | `pnpm run` | `bun run` | `npm run` | `yarn run` |
| **test** | `pnpm test` | `bun test` | `npm test` | `yarn test` |
| **dev** | `pnpm dev` | `bun run dev` | `npm run dev` | `yarn dev` |
| **build** | `pnpm build` | `bun run build` | `npm run build` | `yarn build` |
| **lock file** | `pnpm-lock.yaml` | `bun.lockb` | `package-lock.json` | `yarn.lock` |
| **workspace config** | `pnpm-workspace.yaml` | none | none | in package.json |
| **hook file** | `.pnpmfile.cjs` | none | none | none |
| **frozen install** | `pnpm install --frozen-lockfile` | `bun install --frozen-lockfile` | `npm ci` | `yarn install --frozen-lockfile` |

## Name Variations

When transforming tool names in text (commands, docs, etc.):

| From | To |
|------|-----|
| `pnpm`, `pnpm's` | `bun`, `bun's` |
| `using pnpm`, `Using pnpm` | `using bun`, `Using bun` |
| `with pnpm` | `with bun` |
| `"pnpm"`, `'pnpm'` | `"bun"`, `'bun'` |

(Repeat same pattern for npm/yarn transformations)

## Files to Check

- `SKILL.md`
- `references/**/*.md`
- `scripts/**/*.sh`
- `templates/**/*`

## Notes

- Some package managers don't have direct equivalents for certain commands
- Workspace configuration differs between pnpm (`pnpm-workspace.yaml`) and yarn (in `package.json`)
- Bun uses binary lock file format (`bun.lockb`)
- Always verify transformed commands are valid for the target package manager
