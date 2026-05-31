# Implementation Plan

## Phase 1: Project setup

Do:
- Initialize project
- Add baseline tooling
- Add formatting/linting
- Add basic environment config

Do not do yet:
- Full feature implementation
- Complex folder trees
- Extra dependencies

## Phase 2: Data/types/validation foundation

Do:
- Define core entities
- Define key TypeScript/domain types
- Define validation schemas
- Create first persistence layer only if needed

Do not do yet:
- Admin features
- Analytics
- Complex background jobs

## Phase 3: Auth/access control

Do:
- Implement auth provider/flow
- Protect routes
- Add ownership checks
- Verify cross-user access is impossible

Do not do yet:
- Roles/permissions unless required for v1

## Phase 4: Core UI shell

Do:
- Layout
- Navigation
- Design tokens
- Empty/loading/error states

Do not do yet:
- Polished animations
- Secondary screens

## Phase 5: First complete user flow

Do:
- Build the smallest end-to-end flow
- Include validation, persistence, access checks, and UI feedback

Do not do yet:
- Parallel feature tracks

## Phase 6: Remaining MVP features

Do:
- Add features one vertical slice at a time
- Update project rules if architecture changes

Do not do yet:
- Nice-to-have features not tied to the MVP goal

## Phase 7: Polish/testing

Do:
- Add tests around core logic
- Tighten UX copy
- Clean up naming and folders
- Remove dead code
