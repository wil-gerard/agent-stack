# Global Agent Instructions

These rules are intentionally short because global files are loaded into every
session.

## Defaults

- Never run `git revert`, `git restore`, `git reset --hard`, or other destructive Git commands without explicit permission.
- When creating commits, always use Conventional Commits.
- Keep changes focused and avoid mixing unrelated work in one commit.
- Prefer small, explicit implementations over broad scaffolding.
- Follow the existing codebase style before introducing new patterns.
- Do not leave TODOs, placeholder implementations, or no-op stubs.
- Ask only when blocked; otherwise make reasonable assumptions and proceed.

## Conventional Commits

- Format commit subjects as `type(scope): summary` or `type: summary`.
- Use imperative present tense.
- Keep the subject concise, ideally 72 characters or less.
- Use these types when applicable: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
