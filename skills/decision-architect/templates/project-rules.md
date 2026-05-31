# Agent Project Rules

Use this as the base for `CLAUDE.md` or `AGENTS.md` after project decisions are made.

## Project goal

[Describe the app in one paragraph.]

## Stage

[Prototype / MVP / Production]

## Stack

- Frontend:
- Backend:
- Database:
- Auth:
- Styling:
- Validation:
- Testing:

## Architecture decisions

- [Decision]
- [Decision]
- [Decision]

## Folder rules

- Put route/screen files in `[folder]`.
- Put reusable UI components in `[folder]`.
- Put domain-specific logic in `[folder]`.
- Put shared utilities in `[folder]` only when truly cross-domain.
- Do not create new top-level folders without updating this file.

## Data modeling rules

- Every private record must have an ownership model.
- Do not create a new table/entity when a field or enum is enough.
- Do not duplicate the same concept under different names.
- Keep database/domain objects separate from form input types when needed.

## Auth and access-control rules

- Protected routes must check session/auth.
- User-owned data must be filtered by owner/team.
- Never trust client-provided user IDs for ownership.
- Admin-only behavior must be explicit.

## Validation rules

- Use `[validation pattern/library]`.
- Validate on the server for every write.
- Reuse schemas between forms and server actions/API handlers when practical.
- Return consistent error shapes.

## Styling rules

- Use `[styling system]` only.
- Do not mix styling systems without updating this file.
- Reuse design tokens for spacing, radius, typography, and colors.
- Create components only when reuse or clarity justifies it.

## Client/server communication rules

- Primary pattern: `[server actions / API routes / tRPC / GraphQL / SDK]`.
- Reads happen in `[location]`.
- Writes happen in `[location]`.
- Loading and error states follow `[pattern]`.
- Do not introduce a second communication pattern without a decision record.

## Testing and quality

- Run `[lint command]` before committing.
- Run `[test command]` after changing business logic.
- Add tests for validation, access control, and core domain logic.

## Avoid

- Premature abstractions
- Duplicate entities/types
- Mixing styling systems
- Bolting on auth after private data exists
- Adding dependencies without a clear reason
- Building future features before the first complete flow works
