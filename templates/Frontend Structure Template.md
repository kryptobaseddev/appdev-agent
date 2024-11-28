# Frontend Structure Documentation

This document outlines the **best practices** and **standardized structure** for frontend development using **Next.js**, **Tailwind CSS**, and **shadcn/ui**. It serves as a repeatable guide for creating comprehensive documentation for frontend development standards, ensuring consistency, scalability, and maintainability across projects.

This document aligns with the **Development Documentation** and **Development Guidelines** established by AppDev.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Purpose](#purpose)
3. [Project Structure](#project-structure)
   - 3.1 [Directory Structure](#31-directory-structure)
   - 3.2 [Folder Descriptions](#32-folder-descriptions)
4. [Reusable Component Architecture](#reusable-component-architecture)
   - 4.1 [Component Standards](#41-component-standards)
   - 4.2 [Modular Design](#42-modular-design)
5. [Styling and Theming](#styling-and-theming)
   - 5.1 [Tailwind CSS Configuration](#51-tailwind-css-configuration)
   - 5.2 [shadcn/ui Integration](#52-shadcnui-integration)
   - 5.3 [Global Styles and Theme Management](#53-global-styles-and-theme-management)
6. [State Management](#state-management)
   - 6.1 [Local State](#61-local-state)
   - 6.2 [Global State](#62-global-state)
   - 6.3 [Remote State (Data Fetching)](#63-remote-state-data-fetching)
7. [Routing](#routing)
   - 7.1 [Next.js Routing Conventions](#71-nextjs-routing-conventions)
   - 7.2 [Dynamic Routes](#72-dynamic-routes)
8. [API Integration](#api-integration)
   - 8.1 [Supabase Integration](#81-supabase-integration)
   - 8.2 [RPC Calls and Endpoints](#82-rpc-calls-and-endpoints)
   - 8.3 [AI LLM Integration](#83-ai-llm-integration)
9. [Environment Variables](#environment-variables)
   - 9.1 [Configuration Management](#91-configuration-management)
   - 9.2 [Best Practices for Secrets](#92-best-practices-for-secrets)
10. [Accessibility and Performance](#accessibility-and-performance)
    - 10.1 [Accessibility Standards](#101-accessibility-standards)
    - 10.2 [Performance Optimization](#102-performance-optimization)
11. [Testing and Validation](#testing-and-validation)
    - 11.1 [Unit Testing](#111-unit-testing)
    - 11.2 [Integration Testing](#112-integration-testing)
    - 11.3 [End-to-End Testing](#113-end-to-end-testing)
12. [Additional Best Practices](#additional-best-practices)
    - 12.1 [Code Quality and Linting](#121-code-quality-and-linting)
    - 12.2 [Documentation and Comments](#122-documentation-and-comments)
    - 12.3 [Version Control](#123-version-control)
13. [Conclusion](#conclusion)

---

## Introduction

This document provides a comprehensive guide for frontend development using **Next.js**, **Tailwind CSS**, and **shadcn/ui**. It emphasizes modular design, reusable components, centralized theming, and best practices to ensure consistency and scalability across applications.

**Frontend Stack**:

- **Framework**: Next.js
- **Styling**: Tailwind CSS, shadcn/ui
- **API Integration**: Supabase endpoints, RPC calls, AI LLMs (OpenRouter AI, OpenAI, Claude Anthropic)
- **State Management**: React Context API, Zustand, or similar libraries

**Guiding Principles**:

- **Modularity**: Build reusable components and modals
- **Consistency**: Centralize configurations and theming
- **Scalability**: Design with future growth in mind
- **Performance**: Optimize for speed and responsiveness
- **Accessibility**: Ensure inclusive design practices

---

## Purpose

- **Define the organization and structure of the frontend codebase**, tailored to Next.js with Tailwind CSS and shadcn/ui.
- **Ensure consistency** across the application by adopting a top-down approach, starting with global configurations and cascading uniformity to all components.
- **Leverage reusable components and centralized configuration** to enhance maintainability, scalability, and efficiency.
- **Centralize theme management** with a single location for color themes; avoid defining colors at lower levels.
- **Design API structures** around Supabase endpoints, RPC calls, and integrate AI LLMs effectively.

---

## Project Structure

### 3.1 Directory Structure

```plaintext
src/
├── app/                  # Next.js App Router directory
│   ├── api/              # API routes and endpoints
│   ├── components/       # Reusable UI components
│   ├── layouts/          # Layout components
│   ├── modules/          # Feature-specific modules
│   ├── styles/           # Global styles and theming
│   ├── utils/            # Utility functions and helpers
│   ├── hooks/            # Custom React hooks
│   ├── context/          # Context providers for state management
│   ├── services/         # API and external service integrations
│   └── pages/            # Page components (if using Pages Router)
├── public/               # Public assets (images, fonts, etc.)
├── tests/                # Test files
├── .env.local            # Environment variables (local development)
├── tailwind.config.js    # Tailwind CSS configuration
├── postcss.config.js     # PostCSS configuration
├── next.config.js        # Next.js configuration
└── package.json          # Project dependencies and scripts
```

### 3.2 Folder Descriptions

1. **`app/`**: Root folder for Next.js App Router. Contains the main application code.

2. **`app/components/`**: Modular and reusable UI components. Each component has its own folder containing:

   - Component file (e.g., `Button.tsx`)
   - Test file (e.g., `Button.test.tsx`)
   - Index file for exports (e.g., `index.ts`)

3. **`app/layouts/`**: Layout components that define the structure of pages (e.g., headers, footers, navigation).

4. **`app/modules/`**: Feature-specific modules grouping related components, pages, and logic (e.g., `user`, `dashboard`).

5. **`app/styles/`**:

   - `globals.css`: Import Tailwind CSS and define global styles.
   - `theme.css`: Centralized theming variables (colors, typography).

6. **`app/utils/`**: Shared utility functions and helpers.

7. **`app/hooks/`**: Custom React hooks for reusable logic.

8. **`app/context/`**: React Context providers for global state management.

9. **`app/services/`**: API integrations and configurations for Supabase and AI LLMs.

10. **`public/`**: Static assets accessible directly (e.g., images, fonts).

11. **`tests/`**: Contains unit, integration, and end-to-end test files.

---

## Reusable Component Architecture

### 4.1 Component Standards

- **Naming Conventions**:

  - Use **PascalCase** for component names and directories.
  - Component files should be named after the component (e.g., `Button.tsx`).

- **File Structure**:

  ```plaintext
  components/
  ├── ComponentName/
  │   ├── ComponentName.tsx        # Component implementation
  │   ├── ComponentName.test.tsx   # Component tests
  │   ├── index.ts                 # Export statement
  ```

- **Exporting Components**:

  - Use `index.ts` files for barrel exports to simplify import statements.

- **Props and Interfaces**:

  - Define clear and consistent props using TypeScript interfaces.
  - Document props for better maintainability.

### 4.2 Modular Design

- **Atomic Design Principles**:

  - Build from simple components (atoms) to complex ones (molecules and organisms).
  - Example: A `Button` component can be used within a `Form` component.

- **Reusability**:

  - Design components to be generic and reusable.
  - Avoid hardcoding values; use props and theme variables.

- **Hierarchical Structure**:

  - Organize components in a hierarchy reflecting their usage and dependencies.

---

## Styling and Theming

### 5.1 Tailwind CSS Configuration

- **Installation**:

  ```bash
  npm install tailwindcss postcss autoprefixer
  npx tailwindcss init -p
  ```

- **Configuration**:

  - Customize `tailwind.config.js` to include paths to all components and pages.
  - Extend the default theme to include custom colors and fonts.

  ```javascript
  // tailwind.config.js
  module.exports = {
    content: [
      './src/**/*.{js,ts,jsx,tsx}',
      './node_modules/@shadcn/ui/components/**/*.{js,ts,jsx,tsx}',
    ],
    theme: {
      extend: {
        colors: {
          primary: '#1E3A8A',
          secondary: '#9333EA',
          accent: '#F59E0B',
        },
      },
    },
    plugins: [],
  };
  ```

### 5.2 shadcn/ui Integration

- **Installation**:

  ```bash
  npx shadcn-ui init
  ```

- **Usage**:

  - Import shadcn/ui components as needed.
  - Ensure components align with Tailwind CSS classes and theme.

### 5.3 Global Styles and Theme Management

- **Single Location for Colors**:

  - Define all colors and styles in `app/styles/theme.css` or within the Tailwind configuration.
  - Avoid defining colors directly in component files.

- **Example**:

  ```css
  /* app/styles/theme.css */
  :root {
    --color-primary: theme('colors.primary');
    --color-secondary: theme('colors.secondary');
    --font-sans: 'Inter', sans-serif;
  }
  ```

- **Applying Styles**:

  - Use Tailwind utility classes and theme variables for consistent styling.

  ```tsx
  // Example component
  const Header: React.FC = () => {
    return (
      <header className="bg-primary text-white">
        {/* Content */}
      </header>
    );
  };
  ```

---

## State Management

### 6.1 Local State

- Use React's `useState` and `useReducer` hooks for component-specific state.

### 6.2 Global State

- **Options**:

  - **React Context API**: For simple global state needs.
  - **Zustand**: Lightweight state management library.
  - **Redux Toolkit**: For more complex applications requiring advanced state management.

- **Best Practices**:

  - Keep global state minimal to what is truly global.
  - Organize state logic in `app/context/` or `app/store/`.

### 6.3 Remote State (Data Fetching)

- Use **React Query** for data fetching, caching, and updating server state.

  ```bash
  npm install @tanstack/react-query
  ```

- **Setup**:

  ```tsx
  // app/_app.tsx
  import { QueryClient, QueryClientProvider } from '@tanstack/react-query';

  const queryClient = new QueryClient();

  function MyApp({ Component, pageProps }) {
    return (
      <QueryClientProvider client={queryClient}>
        <Component {...pageProps} />
      </QueryClientProvider>
    );
  }

  export default MyApp;
  ```

---

## Routing

### 7.1 Next.js Routing Conventions

- Utilize Next.js **App Router** (`app/` directory) for routing.

- **File-Based Routing**:

  - Each file in the `app/` directory corresponds to a route.

  ```plaintext
  app/
  ├── page.tsx               # Renders at '/'
  ├── about/
  │   └── page.tsx           # Renders at '/about'
  ├── blog/
  │   ├── page.tsx           # Renders at '/blog'
  │   └── [slug]/
  │       └── page.tsx       # Renders at '/blog/:slug'
  ```

### 7.2 Dynamic Routes

- Use square brackets `[param]` for dynamic segments.

  - Example: `app/users/[id]/page.tsx` renders at `/users/:id`

- **Nested Routes**:

  - Organize routes hierarchically for nested layouts and components.

---

## API Integration

### 8.1 Supabase Integration

- **Installation**:

  ```bash
  npm install @supabase/supabase-js
  ```

- **Configuration**:

  - Create a centralized Supabase client in `app/services/supabaseClient.ts`.

  ```typescript
  // app/services/supabaseClient.ts
  import { createClient } from '@supabase/supabase-js';

  const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL!;
  const supabaseAnonKey = process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!;

  export const supabase = createClient(supabaseUrl, supabaseAnonKey);
  ```

### 8.2 RPC Calls and Endpoints

- Use Supabase's **RPC (Remote Procedure Calls)** to interact with database functions.

- **Example**:

  ```typescript
  // app/services/userService.ts
  import { supabase } from './supabaseClient';

  export const fetchUserData = async (userId: string) => {
    const { data, error } = await supabase.rpc('get_user_data', { user_id: userId });
    if (error) throw error;
    return data;
  };
  ```

### 8.3 AI LLM Integration

- **Integrate AI Services**:

  - **OpenRouter AI**, **OpenAI**, **Claude Anthropic**.

- **Configuration**:

  - Store API keys and endpoints in environment variables.

  ```env
  NEXT_PUBLIC_OPENAI_API_KEY=your_openai_api_key
  ```

- **Service Clients**:

  - Create clients in `app/services/` for each AI service.

  ```typescript
  // app/services/openaiClient.ts
  import { Configuration, OpenAIApi } from 'openai';

  const configuration = new Configuration({
    apiKey: process.env.NEXT_PUBLIC_OPENAI_API_KEY,
  });

  export const openai = new OpenAIApi(configuration);
  ```

---

## Environment Variables

### 9.1 Configuration Management

- Use `.env.local` for local development environment variables.

- **Accessing Variables**:

  - Use `process.env.NEXT_PUBLIC_*` for variables needed in the browser.
  - Server-only variables should not have the `NEXT_PUBLIC_` prefix.

### 9.2 Best Practices for Secrets

- **Never Commit Secrets**:

  - Do not commit `.env.local` or any files containing secrets to version control.

- **Server-Side Protection**:

  - Ensure sensitive operations are performed server-side to protect secrets.

---

## Accessibility and Performance

### 10.1 Accessibility Standards

- **Follow WCAG Guidelines**:

  - Ensure the application meets Web Content Accessibility Guidelines (WCAG) 2.1 AA.

- **Best Practices**:

  - Use semantic HTML elements.
  - Provide alternative text for images.
  - Ensure keyboard navigability.
  - Use ARIA attributes appropriately.

### 10.2 Performance Optimization

- **Code Splitting**:

  - Utilize dynamic imports and lazy loading for components.

- **Optimized Images**:

  - Use Next.js `Image` component for automatic image optimization.

- **Caching and Memoization**:

  - Implement caching strategies with React Query.
  - Use `useMemo` and `useCallback` to prevent unnecessary re-renders.

- **Static Generation and Server-Side Rendering**:

  - Leverage Next.js features like `getStaticProps` and `getServerSideProps` for data fetching.

---

## Testing and Validation

### 11.1 Unit Testing

- **Tools**:

  - **Jest** for testing framework.
  - **React Testing Library** for component testing.

- **Example Test**:

  ```typescript
  // components/Button/Button.test.tsx
  import { render, screen } from '@testing-library/react';
  import Button from './Button';

  test('renders Button with correct text', () => {
    render(<Button>Click Me</Button>);
    expect(screen.getByText('Click Me')).toBeInTheDocument();
  });
  ```

### 11.2 Integration Testing

- Test interactions between components and state management.

- **Best Practices**:

  - Simulate real user interactions.
  - Test critical user flows.

### 11.3 End-to-End Testing

- **Tools**:

  - **Cypress** or **Playwright** for E2E testing.

- **Setup**:

  ```bash
  npm install --save-dev cypress
  ```

- **Example Test**:

  ```javascript
  // cypress/integration/sample_spec.js
  describe('My First Test', () => {
    it('Visits the home page', () => {
      cy.visit('/');
      cy.contains('Welcome');
    });
  });
  ```

---

## Additional Best Practices

### 12.1 Code Quality and Linting

- **ESLint and Prettier**:

  - Install and configure for consistent code formatting and linting.

  ```bash
  npm install --save-dev eslint prettier eslint-plugin-react eslint-config-prettier eslint-plugin-prettier
  ```

- **Configuration Files**:

  - Create `.eslintrc.js` and `.prettierrc` with preferred rules.

### 12.2 Documentation and Comments

- **Component Documentation**:

  - Use JSDoc comments for functions and components.

- **Code Comments**:

  - Write meaningful comments for complex logic or important decisions.

- **README and Docs**:

  - Maintain updated documentation in `README.md` and other relevant markdown files.

### 12.3 Version Control

- **Git Best Practices**:

  - Use meaningful commit messages.
  - Follow a branching strategy (e.g., GitFlow).

- **Pull Requests**:

  - Code reviews should be part of the development process.

---

## Conclusion

By following this standardized structure and best practices, development teams can create modular, scalable, and maintainable frontend applications using **Next.js**, **Tailwind CSS**, and **shadcn/ui**. Centralized theming, reusable components, and adherence to best practices ensure consistency and efficiency throughout the development lifecycle.

---

**Note**: This document should be kept up-to-date as technologies evolve and new best practices emerge.