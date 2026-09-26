# Capstone Project: Frontend Web Application

A modern, high-performance frontend single-page application built with React, Vite, and TypeScript as a capstone project.

## Overview
This project is an interactive, responsive web application designed with modern web standards, modular architecture, and accessibility in mind. It demonstrates production-grade frontend engineering principles, including typed component interfaces, clean state separation, and automated testing workflows.

## Key Features & Stack
- **Framework:** React 18+ with TypeScript
- **Build Tooling:** Vite for lightning-fast HMR and optimized production bundles
- **Routing:** React Router v6 for declarative client-side navigation
- **State Management:** TanStack Query for server state and custom hooks for local UI state
- **Styling:** Modern CSS Modules / Tailwind CSS with accessible UI design
- **Testing & Quality:** Vitest, React Testing Library, ESLint, and Prettier

## Project Structure
```text
src/
├── assets/         # Static assets and icons
├── components/     # Reusable UI primitives and design system elements
├── features/       # Domain-specific modules and feature components
├── hooks/          # Shared custom React hooks
├── layouts/        # Page layout wrappers
├── pages/          # Application views/routes
├── services/       # API clients and HTTP integrations
├── types/          # Shared TypeScript type definitions
└── utils/          # Pure utility functions and helpers
```

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) (v9+) or [pnpm](https://pnpm.io/)

### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd my-capstone-project
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Configure environment variables (if applicable):
   ```bash
   cp .env.example .env.local
   ```

### Available Scripts

In the project directory, you can run:

| Command | Purpose |
|---|---|
| `npm run dev` | Starts the Vite local development server with HMR |
| `npm run build` | Compiles TypeScript and builds production-optimized assets |
| `npm run preview` | Locally previews the production build output |
| `npm test` | Executes unit and component tests with Vitest |
| `npm run lint` | Runs ESLint to check for code quality and style issues |
| `npm run format` | Formats code according to Prettier rules |

## Contributing & Guidelines
See [GEMINI.md](./GEMINI.md) for coding conventions, component guidelines, and commit standards.

## License
Distributed under the MIT License. See [LICENSE](./LICENSE) for details.
