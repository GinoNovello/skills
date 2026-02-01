# Build Tool Transformations

Reference patterns for transforming between build tools.

## Configuration Files

| webpack | vite | esbuild | rollup |
|---------|------|---------|--------|
| `webpack.config.js` | `vite.config.js` | `esbuild.config.js` | `rollup.config.js` |
| `webpack.config.ts` | `vite.config.ts` | `esbuild.config.ts` | `rollup.config.ts` |
| `webpack.dev.js` | (none) | (none) | (none) |
| `webpack.prod.js` | (none) | (none) | (none) |

## Build Commands

| webpack | vite | esbuild | rollup |
|---------|------|---------|--------|
| `webpack --mode production` | `vite build` | `esbuild` | `rollup -c` |
| `webpack serve` | `vite dev` | `esbuild --serve` | `rollup -c --watch` |
| `webpack --watch` | `vite dev --watch` | `esbuild --watch` | `rollup -c --watch` |

## Plugins and Loaders

| webpack | vite | esbuild | rollup |
|---------|------|---------|--------|
| `HtmlWebpackPlugin` | (built-in) | (none) | `@rollup/plugin-html` |
| `MiniCssExtractPlugin` | (built-in) | (use minify) | (none) |
| `CssMinimizerPlugin` | (built-in) | (none) | (none) |
| `DefinePlugin` | `define` | `--define` | `@rollup/plugin-replace` |
| `babel-loader` | (built-in) | (built-in) | (built-in) |
| Loaders (`module: { rules: }`) | (built-in) | (built-in) | Plugins |

## Configuration Concepts

| webpack | vite | esbuild | rollup |
|---------|------|---------|--------|
| `entry:` | (index.html) | `--entry-points=` | `input:` |
| `output:` | `build.outDir` | `--outdir=` | `output:` |
| `publicPath` | `base` | `--servedir=` | (none) |
| `module.exports` | `export default { defineConfig }` | (function API) | `export default` |
| HMR (built-in) | HMR (built-in) | (none) | (none) |

## Package Names

| webpack | vite | esbuild | rollup |
|---------|------|---------|--------|
| `webpack` | `vite` | `esbuild` | `rollup` |
| `webpack-cli` | (none) | (none) | (none) |
| `webpack-dev-server` | (built-in) | (none) | (none) |
| `webpack-merge` | (none) | (none) | (none) |
| `@vitejs/plugin-react` | | | |
| `@vitejs/plugin-vue` | | | |
| `@vitejs/plugin-svelte` | | | |

## Name Variations

When transforming tool names in text:

| From | To |
|------|-----|
| `webpack`, `webpack's` | `vite`, `vite's` |
| `using webpack`, `Using webpack` | `using vite`, `Using vite` |
| `with webpack` | `with vite` |
| `"webpack"`, `'webpack'` | `"vite"`, `'vite'` |

(Repeat same pattern for other tool transformations)

## Files to Check

- `SKILL.md`
- `references/**/*.md`
- `scripts/**/*.sh`
- `templates/**/*`
- Config files (`*.config.js`, `*.config.ts`)
- `package.json` (scripts, devDependencies)

## Notes

- Webpack uses loaders; Rollup/Vite use plugins
- Esbuild is a compiler (much faster but fewer features)
- Vite uses Rollup for production builds
- Configuration syntax varies significantly between tools
- Some transformations may require rewriting entire config files
- Always verify build output after transformation
