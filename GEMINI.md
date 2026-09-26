# Project Guidelines: Modern Frontend (React + Vite)

This repository contains a modern frontend web application built with **React** and **Vite**. All contributors and AI assistants should follow the architecture, conventions, and development workflows outlined below.

---

## 1. Technology Stack

- **Runtime & Bundler:** [Node.js](https://nodejs.org/) (>= 18), [Vite](https://vitejs.dev/)
- **Core Library:** [React 18+](https://react.dev/) with [TypeScript](https://www.typescriptlang.org/) (Strict Mode)
- **Routing:** [React Router](https://reactrouter.com/) (v6+)
- **State Management:**
  - Server / Async State: [TanStack Query](https://tanstack.com/query) (React Query)
  - Client / UI State: React Context + hooks for local UI; [Zustand](https://github.com/pmndrs/zustand) for shared global state when needed
- **Styling:** Modern CSS Modules / Tailwind CSS with CSS Variables for theme tokens
- **Testing:** [Vitest](https://vitest.dev/) for unit/integration tests and [React Testing Library](https://testing-library.com/) for component testing
- **Code Quality:** [ESLint](https://eslint.org/) + [Prettier](https://prettier.io/)

---

## 2. Directory Structure

Adopt a feature-aware, modular structure within `src/`:

```
src/
├── assets/         # Static media (svgs, images, global icons)
├── components/     # Shared, reusable UI primitives (Button, Modal, Input)
│   └── ui/         # Base design system components
├── features/       # Feature-driven modules (domain logic, components, hooks)
├── hooks/          # Cross-cutting, generic custom React hooks
├── layouts/        # Page layout wrappers (RootLayout, AuthLayout, etc.)
├── pages/          # Route page components
├── services/       # API clients, HTTP wrappers, external service connectors
├── types/          # Shared TypeScript type definitions and interfaces
├── utils/          # Pure helper functions, formatting, validation schemas
├── App.tsx         # Main application component & route definitions
├── main.tsx        # Application entry point
└── index.css       # Global styles and CSS reset
```

---

## 3. Coding Conventions & Standards

### 3.1 TypeScript
- **Strict Typing:** Always enable strict mode. Avoid `any`; use `unknown`, type assertions, or generic parameters when types are dynamic.
- **Component Props:** Define props using `interface` or `type` named `<ComponentName>Props`. Export types if used by consumer modules.
- **Explicit Returns:** Provide explicit return types on custom hooks, services, and utility functions.

### 3.2 React Best Practices
- **Component Pattern:** Prefer functional components with named function declarations or explicit `React.FC` alternatives:
  ```tsx
  export interface ButtonProps extends React.ButtonHTMLAttributes<HTMLButtonElement> {
    variant?: 'primary' | 'secondary' | 'outline';
  }

  export function Button({ variant = 'primary', children, className, ...props }: ButtonProps) {
    return (
      <button className={`btn btn-${variant} ${className ?? ''}`} {...props}>
        {children}
      </button>
    );
  }
  ```
- **Custom Hooks:** Encapsulate non-trivial state and side-effect logic in reusable hooks inside `hooks/` or `features/<feature>/hooks/`. Prefix with `use`.
- **Pure Functions & Immutability:** Never mutate state directly. Always use functional state updates when next state depends on prior state.
- **Accessibility (a11y):** Ensure semantic HTML elements (`<nav>`, `<main>`, `<header>`, `<button>`). Include ARIA attributes where necessary and ensure interactive elements are keyboard-accessible.

### 3.3 Import Ordering
Organize imports in consistent blocks separated by a blank line:
1. External React & framework imports (`react`, `react-router-dom`)
2. Third-party packages (`zustand`, `lucide-react`)
3. Internal aliases / paths (`@/components`, `@/hooks`, `@/services`, `@/types`)
4. Relative imports (`./ChildComponent`)
5. Style sheets / assets (`./styles.module.css`, `./logo.svg`)

---

## 4. Development Workflow & Commands

| Task | Command |
|---|---|
| Start Dev Server | `npm run dev` |
| Production Build | `npm run build` |
| Preview Production Build | `npm run preview` |
| Run Linter | `npm run lint` |
| Format Code | `npm run format` |
| Run Unit Tests | `npm test` |

---

## 5. Git & Commit Guidelines

- Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:
  - `feat:` A new user-facing feature
  - `fix:` A bug fix
  - `docs:` Documentation changes only
  - `style:` Formatting, missing semicolons, etc. (no functional code changes)
  - `refactor:` Code refactoring without changing public behavior or fixing bugs
  - `test:` Adding or refactoring automated tests
  - `chore:` Maintenance tasks, dependency updates, tooling configuration
