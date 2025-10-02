# 🛍️ E-commerce Platform in Next.js

A minimalist e-commerce platform built with Next.js 15 App Router and TypeScript.
The project demonstrates server-side rendering for product pages, client-side interactions for search and filters using searchParams, includes CRUD operations in the admin panel via server actions and GraphQL mutations, features lazy loading with Suspense for performance, and integrates authentication with Clerk for protected routes. It also uses Tailwind CSS for responsive design, shadcn/ui components for UI consistency, and fallback mock data for development. The purpose is to practice modern web development techniques, including API integration, form validation with Zod, and modal overlays for seamless user experiences.

---

## 📑 Table of Contents
- 📖 [About the Project](#-about-the-project)
- ✨ [Features](#-features)
- 🛠 [Technologies](#-technologies)
- ⚙️ [Installation](#-installation)
- 🚀 [Usage](#-usage)
- 📂 [Project Structure](#-project-structure)
- 📈 [Workflow](#-workflow)
- 🗓 [Sprint Plan](#-sprint-plan)
- 🤝 [Contributing](#-contributing)
- 📚 [Learnings](#-learnings)
- 📜 [License](#-license)
- ✍️ [Contact](#-contact)

---

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

---

## ✨ Features
- ✅ Homepage with product overview - Hero section with CTA, featured products grid, and new arrivals grid.
- ✅ Different pages - Static pages like About us, Contact, and dynamic pages like Products list, individual product details and Admin dashboard.
- ✅ Search - Global search via Command dialog (Ctrl+K), product filtering by query and categories
- ✅ Add - Add to cart functionality (placeholder), and admin forms for adding new products.
- ✅ CRUD functions in /admin - Create, read, update, and delete products and categories via tables, forms, and server actions.  

---

## 🛠 Technologies
- Next.js 15 (App Router) [Framework] - For server-side rendering, routing, and app structure.
- TypeScript [Language] - For type-safe development.
- Tailwind CSS [Styling] - For utility-first CSS and responsive design.
- Clerk [Authentication] - For user sign-in, sign-out, and protected routes.
- GraphQL [API] - For querying product and category data from external API.
- Radix UI [UI Components] - For accessible primitives like dropdowns, tooltips, and navigation menus.
- shadcn/ui [UI Library] - For pre-built components like buttons, inputs, and tables.
- React Hot Toast [Notifications] - For toast messages on auth events.
- Embla Carousel [Carousel] - For image sliders in product details.
- Lucide React [Icons] - For consistent iconography.
- Zod [Validation] - For form schema validation.
- ESLint & Prettier [Linting/Formatting] - For code quality and consistency.
- Husky [Git Hooks] - For pre-commit checks.  

---

## ⚙️ Installation
```bash
# Clone repo
git clone https://github.com/jplimmer/next-cart.git

# Go into project folder
cd repo-name

# Install dependencies
npm install

# Start development server
npm run dev
```

---

## 🚀 Usage
* Homepage (/) -> Shows hero section with random products, featured products grid, and new arrivals grid.
* About us (/about) -> Static page with text, images, and sections on story, goals, and environment.
* Contact (/contact) -> Static page with a contact form for user inquiries.
* Products (/products) -> Displays filtered and paginated product list with search, category filters, and sorting; supports query params for categories, query, and page number.
* Product detail (/products/[slug]) -> Shows individual product details, including image carousel, description, price, and category.
* Admin (/admin) -> Protected page for managing catalog; tabs for products and categories with data tables, add/edit/delete actions.
* Create product (/admin/create-product) -> Form page/modal for creating new products with validation.
* Create category (/admin/create-category) -> Form page/modal for creating new categories.
* Update product (/admin/update-product/[id]) -> Form page/modal for editing existing products.
* Modal overlays (e.g., @modal/(.)products/[slug], @modal/(.)admin/create-product) -> Modal versions of product details or admin forms for quick access without full page navigation.

---

## 📂 Project Structure
```
├── app                         # Next.js App Router pages and routes
│   ├── about                   # About page route
│   ├── admin                   # Admin dashboard routes
│   │   ├── create-category     # Page for creating product categories
│   │   ├── create-product      # Page for creating products
│   │   └── update-product      # Pages for updating existing products
│   │       └── [id]            # Dynamic route for editing a specific product by ID
│   ├── contact                 # Contact page route
│   ├── merchandise             # Merchandise listing page route
│   ├── @modal                  # Parallel route for modal-based navigation
│   │   ├── (.)admin            # Modal version of admin pages
│   │   │   ├── create-category # Modal for creating categories
│   │   │   ├── create-product  # Modal for creating products
│   │   │   └── update-product  # Modal for updating products
│   │   │       └── [id]        # Modal for updating product by ID
│   │   └── (.)products         # Modal version of product details
│   │       └── [slug]          # Modal for specific product by slug
│   └── products                # Products listing and detail routes
│       └── [slug]              # Dynamic route for product detail page
├── components                  # Reusable React components
│   ├── admin                   # Components for admin dashboards and forms
│   ├── contact                 # Contact form and related components
│   ├── layout                  # Layout components (header, footer, modal, etc.)
│   ├── loading                 # Skeleton loaders and spinners
│   ├── merchandise-card        # Components for displaying merchandise cards
│   ├── navigation              # Navigation bar and menu components
│   ├── products                # Components for product listing and details
│   ├── root-page               # Components for homepage sections (hero, featured, etc.)
│   ├── table                   # Data table components (sortable, expandable, etc.)
│   └── ui                      # Shared UI primitives (buttons, cards, inputs, dialogs, etc.)
├── fonts                       # Custom font files
├── hooks                       # Custom React hooks
├── lib                         # Core logic and utilities
│   ├── actions                 # Server actions for cart, products, etc.
│   ├── constants               # App-wide constants (routes, assets, params, etc.)
│   ├── data                    # Data layer (GraphQL, services, helpers)
│   │   ├── graphql             # GraphQL queries, mutations, and fetch utils
│   │   └── services            # API service implementations (mock and real)
│   ├── hooks                   # Data-fetching and cart-related hooks
│   ├── mocks                   # Mock and fallback data for development/testing
│   │   └── fallback-data       # Fallback data management
│   ├── schemas                 # Validation schemas (Zod, etc.)
│   └── types                   # TypeScript type definitions

```

---

## 📈 Workflow
* 👥 Group work in agile sprints (SCRUM)  
* 🌱 Feature branches  
* 🔍 PR + code review  
* DSUs  
* Keep team meeting open  

---

## 🗓 Sprint Plan

### Sprint 1 - Basic Structure
* Set up Next.js project  
* Created menus & static pages  

### Sprint 2 - Basic Structure
* Uses [slug] for dynamic routing  
* Filter and search for /products  

### Sprint 3 - Basic Structure
* Created /admin route with a DataTable  
* Create, Update, and Delete functionality for products with server actions  
* Zod validation on create/update forms  

### Sprint 4 - Fine Tuning
* WAVE and Lighthouse analysis  
* Refactor fetch and GraphQL functions  
* Responsive styling  

---

## 🤝 Contributing
Want to contribute?  

1. Fork the project  
2. Create a feature branch (`git checkout ......`)  
3. Commit & push  
4. Send a Pull Request  

---

## 📚 Learnings
* Difference between Server & Client Components in Next.js  
* Agile methods  
* API  
* Responsiveness  

---

## 📜 License
This project is developed for educational purposes and is not intended for production.  

---

## ✍️ Contact
Any contact details  
