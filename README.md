# 🛍️ NextCart

A minimalist e-commerce platform built with Next.js 15 and TypeScript, using data from [Platzi's GraphQL API](https://fakeapi.platzi.com/en/gql/products/). Features server-side rendering and streaming, real-time search, authentication with Clerk and an admin dashboard with CRUD functionality.

## 📑 Contents

- 📖 [About the project](#-about-the-project)
- ✨ [Features](#-features)
- 🛠 [Technologies Used](#-technologies)
- ⚙️ [Installation](#-installation)
- 📂 [Project Structure](#-project-structure)
- 🚀 [Workflow](#-workflow)
- 🤝 [Contributing](#-contributing)
- 📜 [License](#-license)

## 📖 About the project

This is a group exercise focused on building a minimalist e-commerce platform to practise modern web development patterns.

**Key learnings:**

- Server-side rendering and routing with Next.js 15 App Router
- Type-safe development with TypeScript and Zod validation
- GraphQL API integration with queries, mutations and error-handling
- Implementing mock data fallback for development with environment variables
- Authentication and route protection using Clerk
- Form management with server actions for CRUD operations and contact forms
- Advanced routing patterns with parallel routes and route interception for modals
- Performance optimization through lazy loading and React Suspense
- Dynamic routing with searchParams for filtering and pagination
- Building accessible, responsive UI with Tailwind CSS and shadcn/ui
- Agile methodology with iterative development and continuous feedback & communication.

## ✨ Features

### 🏠 Storefront

- **Product Discovery** - Browse featured products and new arrivals with a clean, responsive grid layout
- **Search** - Global command palette (⌘K/Ctrl+K) for instant product search
- **Smart Filtering** - Filter products by category, search query, and combine multiple filters
- **Product Details** - Dynamic product pages with image carousels, descriptions, and specifications
- **Modal Overlays** - Product quick-view and search in modal windows

### 🛒 Shopping Experience

- **Add to Cart** - Simple add-to-cart functionality using cookies, with toast notifications
- **Responsive Design** - Optimised for mobile, tablet, and desktop viewing
- **Contact Form** - Get in touch with validated server-side form handling

### 🔐 Authentication

- **User Management** - Sign in with Clerk authentication to access protected admin areas

### ⚙️ Admin Dashboard

- **Product Management** - Create, edit, and delete products in Platzi's public API server
- **Data Tables** - Sortable, filterable tables for managing inventory
- **Server Actions** - secure mutations handled server-side with real-time feedback

### 🚀 Performance

- **SSR & Streaming** - Server-side rendering with React Suspense for optimal loading
- **Image Optimization** - Automatic image optimization with Next.js Image component
- **Fallback Data** - Develop with mock data when API is unavailable

## 🛠 Technologies Used

#### Core Framework & Language

- **[Next.js 15 (App Router)](https://nextjs.org/docs)** - React framework for server-side rendering, routing, and modern app architecture
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe JavaScript for improved developer experience and code reliability

#### Styling & UI

- **[Tailwind CSS](https://tailwindcss.com/docs/styling-with-utility-classes)** - Utility-first CSS framework for responsive design
- **[shadcn/ui](https://ui.shadcn.com/docs)** - Composable UI component library built on Radix UI
- **[Radix UI](https://www.radix-ui.com/primitives/docs/overview/introduction)** - Unstyled, accessible component primitives
- **[Lucide React](https://lucide.dev/icons/)** - Modern icon library

#### Features & Functionality

- **[Clerk](https://clerk.com/)** - Authentication and protected routes
- **[GraphQL](https://graphql.org/)** - API queries for product and category data
- **[React Hot Toast](https://react-hot-toast.com/)** - Toast notification system for user feedback
- **[Zod](https://zod.dev/)** - Runtime type validation for forms and data schemas

#### Development Tools

- **[ESLint](https://eslint.org/) & [Prettier](https://prettier.io/)** - Code linting and formatting for consistent code style
- **[Husky](https://typicode.github.io/husky/)** - Git hooks for automated pre-commit quality checks

## ⚙️ Installation

1. Clone this repository and navigate to the folder:

```bash
git clone https://github.com/jplimmer/next-cart.git
cd next-cart
```

2. Install dependencies:

```bash
npm install
```

3. Run the development server:

```bash
npm run dev
```

4. Open http://localhost:3000 in your browser to view the site.

## 📂 Project Structure

```
├── public/                         # Static assets
├── src/
│   ├── app/                        # Next.js App Router pages and routes
│   │   ├── about/
│   │   ├── admin/
│   │   │   ├── create-category/
│   │   │   ├── create-product/
│   │   │   └── update-product/
│   │   │       └── [id]/
│   │   ├── contact/
│   │   ├── products/
│   │   │   └── [slug]/
│   │   └── @modal/                 # Parallel slot for intercepting modal routes
│   │       ├── (.)admin/
│   │       │   ├── create-category/
│   │       │   ├── create-product/
│   │       │   └── update-product/
│   │       │       └── [id]/
│   │       └── (.)products/
│   │           └── [slug]/
│   ├── components/                 # Reusable React components organised by feature
│   │   ├── admin/
│   │   ├── contact/
│   │   ├── layout/
│   │   ├── loading/
│   │   ├── navigation/
│   │   ├── products/
│   │   ├── root-page/
│   │   ├── table/
│   │   └── ui/                     # Shared UI primitives (buttons, cards, inputs, dialogs, etc.)
│   ├── fonts/                      # Custom font files
│   ├── hooks/                      # Custom React hooks
│   ├── lib/                        # Core shared logic and utilities
│   │   ├── actions/
│   │   ├── constants/
│   │   ├── data/
│   │   │   ├── graphql/            # GraphQL queries, mutations, and fetch utils
│   │   │   └── services/           # API service implementations (mock and real)
│   │   ├── hooks/
│   │   ├── mocks/                  # Mock and experimental data for development/testing
│   │   ├── schemas/                # Zod validation schemas
│   │   ├── types/
│   │   └── utils.ts
│   └── middleware.ts               # Clerk configuration
├── .gitignore
├── next.config.ts
├── package.json
└── README.md
```

## 📈 Workflow

- 👥 Group work in agile sprints (SCRUM)
- 🌱 Feature branches
- 🔍 PR + code review
- DSUs
- Keep team meeting open

### 🗓 Sprint Plan

#### Sprint 1 - Basic Structure

- Set up Next.js project
- Created menus & static pages

#### Sprint 2 - Basic Structure

- Uses [slug] for dynamic routing
- Filter and search for /products

#### Sprint 3 - Basic Structure

- Created /admin route with a DataTable
- Create, Update, and Delete functionality for products with server actions
- Zod validation on create/update forms

#### Sprint 4 - Fine Tuning

- WAVE and Lighthouse analysis
- Refactor fetch and GraphQL functions
- Responsive styling

## 🤝 Contributing

Want to contribute? Great! Here's how to get started:

#### Quick Start

1. Fork and clone the repo:

```bash
git clone https://github.com/<your-username>/next-cart.git
```

2. Navigate to your repo root and install dependencies:

```bash
cd next-cart
npm install
```

3. Create a feature branch:

```bash
git checkout -b feature/your-feature
```

4. Make changes, commit, and push.
5. Open a Pull Request (PR) with a clear description.

#### Guidelines

- Follow code style with ESLint/Prettier config.
- Use clear commit messages.
- All PRs need review.

For questions, use GitHub Issues. Thanks for helping! 🚀

## 📜 License

This project is developed for educational purposes and is not intended for production.

## My Primary Contribution
My primary contribution to the NextCart project was building and refining core e-commerce functionalities, focusing on user interface components, data fetching, performance optimizations, and documentation. I implemented features like cart management, product display with image handling, API integration with pagination, and loading states, while also enhancing the project's README with comprehensive sections for better usability and collaboration.

* Cart Functionality: Implemented cart counter (using cookis for now), add-to-cart actions, and optimistic UI updates in ProductCard and navigation components.
* Product Display and Image Handling: Created ProductCard, ProductImageSlider with navigation arrows, and image validation logic for fallback handling.
* Featured Products and Merchandise: Developed FeaturedProducts component, integrated merchandise card with product card, and added responsive images to the about page.
* API and Data Fetching: Set up GraphQL queries, server-side fetching functions, pagination support, and fallback data managers for products and categories.
* Loading and Suspense: Added Suspense wrappers, LoadingSpinner components, and improved loading indications for better user experience.
* Navigation and UI: Enhanced navigation content and ensured responsive design for product card, featured products and about us page.
* README Documentation: added sections for usage, technologies, features, contributing, and project overview.

I utilized Next.js App Router with server components for data fetching and SEO, client components for interactivity (e.g., useState, useEffect hooks), and Suspense for loading states. Technologies included GraphQL for API queries with custom hooks, Tailwind CSS and shadcn/ui for responsive styling, Zod for validation, and server actions for form handling. Components like CardGrid, ProductCard, and navigation items were built or refactored, with error handling via try-catch and fallback data.

## Improvements and Additions for NextCart
If I were to continue working on this project, I would prioritize the following areas:

1. Implement proper state management for the shopping cart - Currently, there's only a placeholder button for "Add to Cart" which uses a counter function with help of cookies to dsiplay the number of items in the basket without actual functionality. I would add global state using Context API to manage cart items, quantities, and totals, including persistence in localStorage to retain the cart between sessions.

2. Add unit tests and integration tests - The project lacks tests entirely. I would implement Jest and React Testing Library to test components like ProductCard, AdminForm, and API calls, plus Cypress for end-to-end testing of user flows such as search and CRUD in admin.

3. Improve performance and optimization - Lazy loading is already in use, but I would add image optimization with Next.js Image component for all images, and memoization (React.memo) for heavy components like ProductGrid to reduce unnecessary re-renders.

4. Add more e-commerce features - Such as a checkout process with payment integration (e.g., Stripe), user profiles for order history, and product reviews to make the app more complete.

