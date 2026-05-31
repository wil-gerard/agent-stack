# Project Agent Instructions

Use the `decision-architect` skill before implementing new features or making major architecture changes.

## Non-Negotiables

- Never run `git revert`, `git restore`, `git reset --hard`, or other destructive Git commands without explicit permission.
- Never leave TODOs, placeholder implementations, or no-op stubs. If something must work, wire it now. If it cannot be wired yet, the task is not done.
- User-owned or private data must have ownership checks from the start.

## Planning Agreement

- Do not start coding until product shape, data model, auth/access, validation, routing, styling, client/server communication, and folder structure are clear enough for future agents to follow.
- Recommend one coherent direction instead of listing endless options.
- Challenge assumptions that would create duplicated concepts, mixed patterns, auth retrofits, or unnecessary abstractions.
- Ask only the minimum questions needed to unblock the next decision.
- Once decisions are made, generate or update project-specific agent instructions when useful.

## Implementation Posture

- Prefer simple, explicit structure.
- Prefer a vertical slice over broad scaffolding.
- Avoid incidental refactors.
- Do not introduce new frameworks, tooling, dependencies, or build changes unless the task clearly requires them.
- Explain why any new dependency is necessary.
- Do not mix styling systems or API communication styles without a clear decision record.

## Code Organization

- Keep feature-specific stores, types, components, and tests together in the same feature folder when the project has an established feature layout.
- Reserve shared/global locations for truly cross-feature modules only, such as app-wide stores.
- Do not place feature-specific files in global buckets when they only serve one feature.
- Never define a reusable utility beside the call site. Put reusable pure helpers in the project's established utilities location and import them.
- Before adding a helper, check existing utilities and extend existing helpers when appropriate.
- Prefer inline expressions for trivial one-off formatting.
- Extract helpers only when there is meaningful reuse or domain logic.
- Name extracted helpers for their domain meaning. Avoid aliases that add indirection without behavior.
- Do not add pass-through wrappers that only call another function with the same arguments.

## Code Style

### Formatting

- Follow the existing style in each touched file.
- Avoid reformatting unrelated lines.
- Use semicolons consistently.
- Prefer trailing commas where already in use.

### Imports

- Group imports in this order: Node built-ins (`node:*`), external packages, internal relative modules.
- Keep type imports explicit with `import type`.
- Avoid wildcard imports.
- Never re-export code or types. Import directly from the source module.

### TypeScript

- Preserve strict typing.
- Do not use `any`. Prefer `unknown` at trust boundaries.
- Narrow `unknown` before property access.
- Use literal unions for finite statuses and events.
- Use `type` for unions and aliases.
- Use `interface` for object contracts when useful.
- Add explicit return types for exported functions and APIs.

### Naming

- Use `PascalCase` for classes, interfaces, and UI components.
- Use `camelCase` for variables, functions, and methods.
- Use `SCREAMING_SNAKE_CASE` for top-level constants.
- Name booleans by intent, such as `is*`, `has*`, and `should*`.
- Prefer descriptive cross-process names over abbreviations.

## UI, HTML, and CSS

- Use the simplest, flattest HTML structure that communicates the content.
- Keep HTML semantic and minimal.
- Do not add wrapper elements or semantic tags unless they provide real value.
- Less UI is better than too much UI.
- Do not add text that explains basic UI usage. The correct path should be obvious from the interface.
- Do not add refresh buttons. Data should be fresh by design.
- Do not add save buttons for ordinary forms. Forms should autosave on data change, never via `setInterval`.
- Keep CSS systemic. Avoid one-off route styles unless the route truly needs them.
- Put CSS customization in a global imported CSS file or scope it to a component.

## Errors, Async, and State

- Fail fast for bad input with clear `TypeError` or `Error` messages.
- For best-effort persistence, catch and continue intentionally.
- Log with context, such as `console.error("message", error)`.
- Do not silently swallow errors unless it is clearly intentional.
- Prefer `async/await` over long promise chains.
- If a promise is intentionally not awaited, handle rejection with `.catch`.
- Keep shared mutable state localized.

## Testing

- Unit tests live near code as `*.test.ts` or `*.spec.ts`.
- Component tests should use the project's existing testing library.
- Prefer role/text-based assertions over brittle selectors.
- Keep tests deterministic and independent.
- During iteration, run one file or one test title first.
