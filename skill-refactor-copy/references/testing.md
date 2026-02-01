# Testing Framework Transformations

Reference patterns for transforming between testing frameworks.

## Configuration Files

| jest | vitest | playwright | node:test |
|------|--------|------------|-----------|
| `jest.config.js` | `vitest.config.js` | `playwright.config.js` | (none - use package.json) |
| `jest.config.ts` | `vitest.config.ts` | `playwright.config.ts` | (none) |
| `@types/jest` | (built-in types) | (none) | (built-in types) |
| `ts-jest` | (uses Vite) | (none) | (built-in) |
| `babel-jest` | (uses Vite) | (none) | (built-in) |

## Test Commands

| jest | vitest | playwright | node:test |
|------|--------|------------|-----------|
| `jest` | `vitest` | `playwright test` | `node --test` |
| `jest --watch` | `vitest --watch` | (none) | `node --test --watch` |
| `jest --coverage` | `vitest --coverage` | (none) | `node --test --coverage` |

## Test Syntax

| jest | vitest | playwright | node:test |
|------|--------|------------|-----------|
| `describe(` | `describe(` | `test.describe(` | `describe(` |
| `test(` | `test(` | `test(` | `test(` |
| `it(` | `it(` | `test(` | `it(` |
| `expect(` | `expect(` | `await expect(` | `assert.` |
| `.toBe(` | `.toBe(` | `.toBe(` | `assert.strictEqual` |
| `.toEqual(` | `.toEqual(` | `.toEqual(` | `assert.deepStrictEqual` |
| `.toMatchSnapshot(` | `.toMatchSnapshot(` | (use `.screenshot()`) | (none) |
| `.toThrow(` | `.toThrow(` | `.toThrow(` | `assert.throws` |

## Mocking

| jest | vitest | playwright | node:test |
|------|--------|------------|-----------|
| `jest.mock(` | `vi.mock(` | (use fixtures) | (none) |
| `jest.fn(` | `vi.fn(` | (none) | (none) |
| `jest.spyOn(` | `vi.spyOn(` | (none) | (none) |
| `jest.clearAllMocks()` | `vi.clearAllMocks()` | (none) | (none) |
| `jest.resetAllMocks()` | `vi.resetAllMocks()` | (none) | (none) |

## Hooks

| jest | vitest | playwright | node:test |
|------|--------|------------|-----------|
| `beforeEach(` | `beforeEach(` | `test.beforeEach(` | `beforeEach(` |
| `beforeAll(` | `beforeAll(` | `test.beforeAll(` | `before(` |
| `afterEach(` | `afterEach(` | `test.afterEach(` | `afterEach(` |
| `afterAll(` | `afterAll(` | `test.afterAll(` | `after(` |

## Platform-Specific Patterns

### Playwright (E2E only)
- `page.locator(`, `page.click(`, `page.fill(` - no direct equivalent in unit test frameworks

### node:test
- Uses `assert` instead of `expect`
- `before(` and `after(` instead of `beforeAll`/`afterAll`
- Built into Node.js (no packages needed)

## Name Variations

When transforming framework names in text:

| From | To |
|------|-----|
| `jest`, `jest's` | `vitest`, `vitest's` |
| `using jest`, `Using jest` | `using vitest`, `Using vitest` |
| `with jest` | `with vitest` |
| `"jest"`, `'jest'` | `"vitest"`, `'vitest'` |

(Repeat same pattern for other framework transformations)

## Files to Check

- `SKILL.md`
- `references/**/*.md`
- `scripts/**/*.sh`
- `templates/**/*`
- Test files (`*.test.js`, `*.test.ts`, `*.spec.js`, `*.spec.ts`)
- Config files (`jest.config.js`, `vitest.config.ts`, `playwright.config.ts`)

## Notes

- Jest and Vitest have very similar APIs (by design)
- Playwright is for E2E testing, not unit testing - transformations may not be 1:1
- node:test uses `assert` instead of `expect`
- Snapshot testing differs between frameworks
- Mocking APIs differ significantly
- Coverage configuration varies between tools
- Always verify tests pass after transformation
