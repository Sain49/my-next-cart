# 🛍️ NextCart

A minimalist e-commerce platform built with Next.js 15 App Router and TypeScript.
The project demonstrates server-side rendering for product pages, client-side interactions for search and filters using searchParams, includes CRUD operations in the admin panel via server actions and GraphQL mutations, features lazy loading with Suspense for performance, and integrates authentication with Clerk for protected routes. It also uses Tailwind CSS for responsive design, shadcn/ui components for UI consistency, and fallback mock data for development. The purpose is to practice modern web development techniques, including API integration, form validation with Zod, and modal overlays for seamless user experiences.

## 📑 Contents

- 📖 [About the Project](#-about-the-project)
- ✨ [Features](#-features)
- 🛠 [Technologies](#-technologies)
- ⚙️ [Installation](#-installation)
- 🚀 [Usage](#-usage)
- 📂 [Project Structure](#-project-structure)
- 📈 [Workflow](#-workflow)
- 🤝 [Contributing](#-contributing)
- 📚 [Learnings](#-learnings)
- 📜 [License](#-license)

## 📖 About the Project

This is a group exercise where the goal was to build a **minimalist e-commerce platform**.  
The purpose is to practice:

- Next.js 15 with App Router for server-side rendering and routing
- TypeScript for type-safe development
- GraphQL API integration with fallback to mock data
- Tailwind CSS and shadcn/ui for responsive UI components
- Clerk for authentication and protected routes
- CRUD operations via server actions and forms
- Lazy loading and Suspense for performance optimization
- Search, filtering, and pagination with searchParams
- Modal overlays and client-side interactions
- Also, handling image validation and fallback data management

## ✨ Features

- ✅ Homepage with product overview - Hero section with CTA, featured products grid, and new arrivals grid.
- ✅ Different pages - Static pages like About us, Contact, and dynamic pages like Products list, individual product details and Admin dashboard.
- ✅ Search - Global search via Command dialog (Ctrl+K), product filtering by query and categories
- ✅ Add - Add to cart functionality (placeholder), and admin forms for adding new products.
- ✅ CRUD functions in /admin - Create, read, update, and delete products and categories via tables, forms, and server actions.

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

## 🚀 Usage

- Homepage (/) -> Shows hero section with random products, featured products grid, and new arrivals grid.
- About us (/about) -> Static page with text, images, and sections on story, goals, and environment.
- Contact (/contact) -> Static page with a contact form for user inquiries.
- Products (/products) -> Displays filtered and paginated product list with search, category filters, and sorting; supports query params for categories, query, and page number.
- Product detail (/products/[slug]) -> Shows individual product details, including image carousel, description, price, and category.
- Admin (/admin) -> Protected page for managing catalog; tabs for products and categories with data tables, add/edit/delete actions.
- Create product (/admin/create-product) -> Form page/modal for creating new products with validation.
- Create category (/admin/create-category) -> Form page/modal for creating new categories.
- Update product (/admin/update-product/[id]) -> Form page/modal for editing existing products.
- Modal overlays (e.g., @modal/(.)products/[slug], @modal/(.)admin/create-product) -> Modal versions of product details or admin forms for quick access without full page navigation.

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

## 📚 Learnings

- Difference between Server & Client Components in Next.js - Understanding when to use server components for data fetching and SEO, vs. client components for interactivity and state management.
- Agile methods - Applying iterative development, daily stand-ups, and feedback loops in a group project to adapt to changes quickly.
- API - Integrating GraphQL APIs with queries, mutations, and error handling, including fallback to mock data.
- Responsiveness - Implementing responsive design with Tailwind CSS, ensuring layouts work across devices using grid, flexbox, and media queries.

## 📜 License

This project is developed for educational purposes and is not intended for production.
