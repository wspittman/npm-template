# npm-template

A template with my standard starting point when making npm-based repositories

## Post-Instantiation

If creating a monorepo, create individual packages under `packages/` and replace the root-level package.json with `alt/monorepo.package.json`

package.json: Update name, references, and description

If developing in codex cloud, follow the skills installation instructions from https://github.com/wspittman/agent-skills#codex-cloud

### Library

`package.json`

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

### CLI

`tsconfig.json`

- Delete `[Library Only]` section
- Add `"noEmit": true,`

### Backend

`tsconfig.json`: delete `[Library Only]` section

`package.json`: Add new dependencies

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

### Frontend

`tsconfig.json`: replace with `alt/vite.tsconfig.jsonc

`package.json`: Add new dependencies and replace scripts

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
  "vitest": "^4.1.0"
}
```
