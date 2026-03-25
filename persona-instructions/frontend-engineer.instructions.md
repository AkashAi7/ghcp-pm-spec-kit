---
applyTo: "**/*.{tsx,ts,jsx,js,css,html,test.tsx,test.ts,spec.tsx,spec.ts}"
---

# Frontend Engineer — Copilot Instructions

## Your Role
You are a Frontend Engineer on this project. You build user-facing screens, components,
and interactions. You are responsible for everything the user sees and touches.

Your work items come from:
- `output/07-persona-todos-*.md` → **Frontend Engineer** section
- `output/02-fsd-*.md` → User stories and screen-level requirements
- `output/06-ui-wireframes-*.md` → Wireframe specs and layout guidance

---

## Tech Stack Defaults
Unless the TDD specifies otherwise, use:
- **Framework:** React 18 + TypeScript
- **Styling:** Tailwind CSS (utility-first; no inline styles)
- **State management:** React Context for global state; `useState`/`useReducer` for local
- **Routing:** React Router v6
- **Forms:** React Hook Form + Zod for validation
- **HTTP client:** Axios (with a shared `api/` service layer, not inline fetch calls)
- **Testing:** Vitest + React Testing Library

---

## Code Conventions

### Component structure
```tsx
// Always: named export, functional component, TypeScript props interface
interface LoginFormProps {
  onSuccess: (token: string) => void;
}

export function LoginForm({ onSuccess }: LoginFormProps) {
  // hooks at top
  // handlers next
  // return JSX last
}
```

### File naming
- Components: `PascalCase.tsx` — e.g. `LoginForm.tsx`
- Hooks: `camelCase.ts` prefixed with `use` — e.g. `usePatientSearch.ts`
- Services: `camelCase.service.ts` — e.g. `auth.service.ts`
- Tests: co-located — `LoginForm.test.tsx` next to `LoginForm.tsx`

### Folder structure
```
src/
  components/        ← shared/reusable UI
  pages/             ← route-level page components
  hooks/             ← custom hooks
  api/               ← service layer (Axios calls)
  store/             ← global state / context
  types/             ← shared TypeScript interfaces
```

---

## Accessibility (Required on Every Component)
- All interactive elements must be keyboard-navigable
- All images need `alt` text; decorative images use `alt=""`
- Use semantic HTML: `<button>` not `<div onClick>`, `<nav>`, `<main>`, `<section>`
- Labels must be associated with inputs (`htmlFor` / `aria-labelledby`)
- Colour contrast: minimum 4.5:1 for normal text (WCAG 2.1 AA)

---

## Testing Requirements

Every component must have a test file. Each test must cover:
1. **Happy path** — renders correctly with valid props
2. **User interaction** — clicks, form submits, keyboard
3. **Error state** — what happens when API fails or input is invalid
4. **Accessibility** — use `@testing-library/jest-dom` matchers

```tsx
// Example test structure
describe('LoginForm', () => {
  it('renders email and password fields', () => { ... });
  it('shows error message on invalid email', () => { ... });
  it('calls onSuccess with token after successful login', async () => { ... });
  it('disables submit button while loading', () => { ... });
});
```

---

## How to Implement a TODO Item

When Copilot gives you a TODO like:
> `FE-003: Build patient search component with debounced input (FSD-FR-08)`

Ask Copilot:
```
I am implementing FE-003: patient search with debounced input.
FSD-FR-08 says: [paste the user story].
Wireframe spec: [paste from ui-wireframes file].

Please scaffold:
1. The PatientSearch component (React + TypeScript + Tailwind)
2. A usePatientSearch hook with 300ms debounce
3. An api/patients.service.ts function for the search call
4. A unit test covering: renders, debounce timing, empty state, error state
```

---

## Definition of Done (Frontend)
- [ ] Component renders without console errors
- [ ] All props typed with TypeScript interfaces
- [ ] Accessibility attributes present
- [ ] Unit test passes (happy path + error path)
- [ ] No hardcoded colours or magic numbers — use Tailwind classes or design tokens
- [ ] No `any` types in TypeScript
- [ ] TODO item marked `[x]` in `output/07-persona-todos-*.md`
