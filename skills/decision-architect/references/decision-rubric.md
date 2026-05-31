# Decision Rubric

When comparing project directions, recommend the option that best satisfies these criteria.

## Prefer

1. A boring default that will still make sense in six months
2. One clear home for every concept
3. One primary pattern per layer
4. Fewer dependencies
5. Explicit ownership and access checks
6. A vertical slice over broad scaffolding
7. Simple files and functions before frameworks or abstractions

## Be cautious with

- Premature tables/entities
- Feature flags before a real need exists
- Multiple styling systems
- Multiple API communication patterns
- Generic folders like `utils` becoming junk drawers
- “Admin” systems before there is an actual admin workflow
- Auth added after private data already exists
- Complex state management before URL/server state is understood

## Recommendation language

Use direct labels:

- **Strong recommend:** best default for this project
- **Acceptable:** workable, but not the cleanest
- **Avoid for now:** likely to create cleanup or complexity
- **Needs user decision:** product/business preference, irreversible tradeoff, or external constraint
