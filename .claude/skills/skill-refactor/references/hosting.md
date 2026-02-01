# Hosting Platform Transformations

Reference patterns for transforming between hosting platforms.

## Environment Variables

| Vercel | Cloudflare | Netlify |
|--------|------------|---------|
| `VERCEL_URL` | `CLOUDFLARE_URL` or `env.CLOUDFLARE_URL` | `NETLIFY_URL` or `URL` |
| `VERCEL_ENV` | `ENV` (or env bindings) | `CONTEXT` |
| `VERCEL_GIT_COMMIT_SHA` | (use CF-specific git env vars) | `COMMIT_REF` |
| `VERCEL_GIT_COMMIT_REF` | (none) | `BRANCH` |
| `VERCEL_GIT_REPO_SLUG` | (none) | `REPOSITORY_URL` |
| `process.env.VERCEL` | `env.CLOUDFLARE` or `env` | `process.env.NETLIFY` |

## Storage Services

| Vercel | Cloudflare | Netlify |
|--------|------------|---------|
| `@vercel/blob` | (use R2 storage) | (use Netlify Blobs) |
| `@vercel/kv` | (use KV namespace) | (none) |
| `@vercel/postgres` | (use D1 database) | (none) |
| `@vercel/edge-config` | (use Durable Objects) | (none) |

## Configuration Files

| Vercel | Cloudflare | Netlify |
|--------|------------|---------|
| `vercel.json` | `wrangler.toml` | `netlify.toml` |
| `.vercelignore` | (none) | `.netlifyignore` |

## Deployment Commands

| Vercel | Cloudflare | Netlify |
|--------|------------|---------|
| `vercel build` | (framework-specific) | `npm run build` or framework-specific |
| `vercel deploy` | `wrangler deploy` | `netlify deploy` |
| `vercel dev` | `wrangler dev` | `netlify dev` |

## Name Variations

When transforming platform names in text:

| From | To |
|------|-----|
| `Vercel`, `Vercel's` | `Cloudflare`, `Cloudflare's` |
| `on Vercel` | `on Cloudflare` |
| `deployed to Vercel` | `deployed to Cloudflare` |
| `Deploy to Vercel` | `Deploy to Cloudflare` |
| `Using Vercel` | `Using Cloudflare` |
| `"Vercel"`, `'Vercel'` | `"Cloudflare"`, `'Cloudflare'` |
| `https://vercel.com` | `https://developers.cloudflare.com` |

(Repeat same pattern for Netlify transformations)

## Files to Check

- `SKILL.md`
- `references/**/*.md`
- `scripts/**/*.sh`
- `templates/**/*`
- Config files (`vercel.json`, `netlify.toml`, `wrangler.toml`)
- Environment config (`.env.example`, `.env.production.example`)

## Notes

- Hosting platforms have fundamentally different architectures (serverless vs edge vs workers)
- Environment variable naming conventions differ significantly
- Storage solutions are platform-specific and may not have direct equivalents
- Some transformations may require architectural changes beyond simple text replacement
- Always verify platform-specific features after transformation
