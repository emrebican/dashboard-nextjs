# Next.js Dashboard App Tutorial Project

This is a hands-on project built by following the official [Next.js Dashboard App Tutorial](https://nextjs.org/learn/dashboard-app). It demonstrates how to create a modern, full-stack web application using the latest Next.js features.

---

## What You'll Learn

This project introduces a wide range of **modern web development techniques** using **Next.js 13/14+** with the **App Router**.

### 1. App Router & File-Based Routing

- Uses the new `/app` directory (App Router), introduced in Next.js 13.
- Each folder represents a route, and `page.tsx` inside it becomes the page content.
- Special files like `layout.tsx`, `loading.tsx`, and `error.tsx` provide layout composition, loading states, and error handling.
- Dynamic routes (e.g. `[id]/page.tsx`) allow for parameterized URLs.

**Key Concepts**:  
`app/`, layouts, nested routes, route groups, parallel routes, dynamic segments

---

### 2. Server Components & Client Components

- By default, components in the App Router are **React Server Components (RSC)**.
- RSCs run on the server and reduce JavaScript sent to the client.
- Mark a component as a **Client Component** using `'use client'` at the top.
- Client Components are used for interactivity like buttons and inputs.

**Key Concepts**:  
Component boundaries, client/server rendering strategy, reducing client-side JS

---

### 3. Data Fetching

- Uses native `fetch()` in Server Components to retrieve data.
- Fetching is colocated with components, leading to simpler data flow.
- Supports caching, revalidation, and loading UI using `loading.tsx`.

**Key Concepts**:  
Server-side data fetching, static vs dynamic rendering, loading UI, `cache`, `revalidate`

---

### 4. Server Actions (Mutations Without API Routes)

- Instead of creating traditional API routes, Server Actions allow you to mutate data directly inside a component (e.g., submit a form).
- These actions are declared with the `async function` keyword and used in forms as `action={someFunction}`.

  **Key Concepts**:  
  Mutating data with server actions, forms in React Server Components, no need for `api/`

---

### 5. Authentication with `next-auth`

- Adds login and session management with `next-auth`.
- Demonstrates how to create a protected dashboard where only authenticated users can access certain pages.
- Shows how to persist sessions using cookies and use `getServerSession()` to verify authentication on the server.

**Key Concepts**:  
Session-based auth, securing routes, using `getServerSession`, middleware protection

---

### 6. Database Integration with Prisma & PostgreSQL

- Uses **Prisma** as the ORM to interact with a **PostgreSQL** database.
- Shows how to define a schema, run migrations, and use Prisma Client in Server Components or Server Actions.

**Key Concepts**:  
Prisma schema modeling, migrations, database queries, using Prisma in server components

---

### 7. Styling with Tailwind CSS

- The UI is built using **Tailwind CSS**, a utility-first CSS framework.
- Demonstrates best practices for responsive, clean, and scalable design.

**Key Concepts**:  
Tailwind config, custom theming, utility classes for layout, spacing, typography

---

### 8. Deployment with Vercel

- Tutorial includes deployment instructions for hosting on **Vercel**, the creators of Next.js.
- Covers use of **Environment Variables** and **production-ready setup**.

**Key Concepts**:  
Environment variables, Vercel CLI, GitHub integration, deployment previews

## Project Structure Overview

```bash
├── app/
│   ├── dashboard/
│   │   ├── (overview)/
│   │   │   ├── loading.tsx
│   │   │   └── page.tsx
│   │ 	├── customers
│ 	│	  ├── invoices
│   │   └── layout.tsx
│   ├── lib/
│   │   └── placeholder-data.ts
│   ├── seed/
│   │   └── route.ts
│	  ├── layout.tsx
│	  ├── page.tsx
│   └── ui/
│       ├── dashboard/
│       │    	├── revenue-chart.tsx
│				│     ├── cards.tsx
│				│     ├── latest-invoices.tsx
│				│     ├── nav-links.tsx
│     	│			├── revenue-chart.tsx
│       │    	└── sidenav.tsx
│       ├── invoices/
│       │	    ├── breadcrumbs.tsx
│       │   	├── pagination.tsx
│			  │   	├── button.tsx
│				│     ├── create-form.tsx
│				│     ├── edit-form.tsx
│				│     ├── status.tsx
│       │	   	└── table.tsx
│       ├── customers/
│       │	    └── table.tsx
│       ├── login-form.tsx
│   		├── fonts.ts
│		    ├── search.tsx
│       └── skeletons.tsx
├── postcss.config.js
├── next.config.ts
└── README.md
```

## Setup Instructions

### 1. Clone the Project

```bash
git clone https://github.com/your-username/nextjs-dashboard-app.git
cd nextjs-dashboard-app
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create Environment Variables

```bash
.env
DATABASE_URL=postgresql://USER:PASSWORD@localhost:5432/yourdbname
NEXTAUTH_SECRET=your-random-secret
NEXTAUTH_URL=http://localhost:3000
```

### 4. Setup Database

```bash
npx prisma migrate dev --name init
```

### 5. Setup Database

```bash
npm run dev
```

## Features

- Secure login & protected routes
- Responsive UI with Tailwind
- Form handling via server actions
- Invoice and customer management
- PostgreSQL + Prisma ORM
- Full deployment to Vercel

## Notes

- This app is for educational purposes and closely follows the official tutorial structure.
- Great starting point for a full-stack SaaS dashboard or internal tool.
- Easily extendable with new models, routes, and custom APIs.

## Resources

- [Official Tutorial](https://nextjs.org/learn/dashboard-app)
- [Next.js Documentation](https://nextjs.org/learn/dashboard-app)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [NextAuth.js Docs](https://next-auth.js.org)
