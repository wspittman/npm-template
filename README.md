# npm-template

A template with my standard starting point when making npm-based repositories

## Post-Instantiation

Update this readme, removing post-installation items as you do them.

If developing in codex cloud, follow the skills installation instructions from https://github.com/wspittman/agent-skills#codex-cloud

Delete `alt/` folder once you've taken anything you need from it.

### package.json

- If creating a monorepo, create individual packages under `packages/` and replace the root-level package.json with `alt/monorepo.package.json`
- Update name, references, and description

#### If Library

```json
"sideEffects": false,
"main": "./dist/index.js",
"module": "./dist/index.js",
"types": "./dist/index.d.ts",
"exports": {
  ".": {
    "types": "./dist/index.d.ts",
    "import": "./dist/index.js",
    "default": "./dist/index.js"
  }
},
"files": [
  "dist"
],
```

If intended to be a wide-support library, also update

```json
"engines": {
"node": ">=20"
},
```

#### If Express Server

```json
  "dependencies": {
    "cors": "^2.8.5",
    "express": "^5.1.0",
    "helmet": "^8.0.0"
  },
  "devDependencies": {
    "@types/cors": "^2.8.17",
    "@types/express": "^5.0.1",
  }
```

#### If Frontend Client

```json
"scripts" {
  "test": "vitest --reporter=dot run",
  "dev": "vite",
  "build": "tsc --noEmit && tsc -p server/tsconfig.json && vite build",
},
"dependencies": {
  "@tanstack/query-core": "^5.90.2",
  "modern-normalize": "^3.0.1"
},
"devDependencies": {
  "lucide-static": "^1.8.0",
  "jsdom": "^30.0.1",
  "vite": "^8.0.8",
  "vite-plugin-compression2": "^2.3.1",
  "vitest": "^5.0.0"
}
```

### tsconfig.base.json

- Update to the correct `[Environment Dependent]` options.
- Update the `[Library Only]`, `[Node Only]`, `[CLI Only]` sections as appropriate

### Frontend

Replace from `alt/` folder:

- `alt/vite.tsconfig.jsonc` -> `tsconfig.base.json`
- `alt/vitest.config.ts.md` -> `vitest.config.ts` (remove wrapper ticks)
- `alt/vite.config.ts.md` -> `vite.config.ts` (remove wrapper ticks)
- `alt/index.html` -> `src/index.html`
