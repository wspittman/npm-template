# npm-template

A template with a standard starting point when making npm-based repositories.

## Goals

[One-liner]

Development Goals

- TBD

Development Non-goals

- TBD

## Workflows

- Create or continue a plan: use the `planning-with-files` skill. When continuing, only implement changes in the **next phase** of the plan before stopping for feedback.
- Write unit tests: use the `write-unit-test` skill.

### Verifying Changes

- Take a step back and consider if the changes solve the right problem.
- If you are working with or from a plan, review to ensure that the plan files are structured correctly and up to date.
- Ensure error cases are handled gracefully, predictably, and provide enough information for future maintainers.
- Always run `npm run pre-checkin` before committing code or handing back for human review. This does not apply to plan- or document-only changes.

## Important Commands

- `npm run pre-checkin`: Run lint, format, and test
- `npm run test`: Run tests.
- `npm run test-details`: Run tests with the default reporter for full (but more verbose) output. Better for debugging failed tests due to an issue with the dot reporter.

Do NOT run `node --test` directly as your harness will likely require human intervention.

## Conventions

- We believe strongly in YAGNI. A change should it do only what's needed, in a way that both humans and machines can understand now and maintain in the future.
- While maintaining YAGNI, is is also important not to write code that makes future changes more difficult. This is a balance that requires thoughtful judgement.
- Avoid adding new dependencies and warn when you do.
- Use red/green TDD for new features and bug fixes when practical.
- Our tests are always written in Node's built-in `node:test` framework.
- The project uses TypeScript with strict type checking.

### Documentation

- Keep `README.md` and `AGENTS.md` files updated when code or workflow changes affect them.
- Add non-obvious findings to the root `Learnings.md` intake queue for later promotion to `AGENTS.md` or the appropriate routed reference.

### Comments

Use JSDoc comments for all public APIs and complex logic. This helps with code readability and provides useful information for developers using the code. Go light on comments otherwise. Never put comments at the end of lines. When writing @returns comments for async functions, prefer to describe the resolved value rather than the promise itself.
