# Tech Stack

> **Project**: Next.js Fullstack App
> **Last Updated**: 2026-04-30

---

## 1. Technology Selection Principles

1. **Fullstack Framework**: Single codebase for frontend and backend
2. **Performance**: Server Components for optimal loading
3. **Developer Experience**: Type-safe end-to-end

---

## 2. Fullstack Tech Stack

### 2.1 Core Framework

| Technology | Version | Purpose | Selection Reason |
|------------|---------|---------|-----------------|
| Next.js | 14.2.0 | Fullstack Framework | App Router, Server Components, excellent DX |
| React | 18.2.0 | UI Framework | Concurrent features, Server Components support |
| TypeScript | 5.0.4 | Type System | Strict mode required |

### 2.2 Styling

- **CSS Framework**: Tailwind CSS 3.4.0
- **Component Library**: shadcn/ui
- **Reason**: Utility-first CSS, accessible components, fully customizable

### 2.3 Database

- **Primary DB**: PostgreSQL 15
- **ORM**: Prisma 5.6.0
- **Migrations**: Prisma Migrate

### 2.4 Authentication

- **Solution**: NextAuth.js 5.0 (Auth.js)
- **Providers**: Credentials + GitHub OAuth

### 2.5 Testing

| Type | Tool | Version |
|------|------|---------|
| Unit Testing | Vitest | 1.0.0 |
| E2E Testing | Playwright | 1.40.0 |

---

## 3. Infrastructure

### 3.1 Deployment

| Technology | Purpose |
|-----------|---------|
| Vercel | Hosting (Next.js optimized) |
| Docker | Local PostgreSQL |

### 3.2 Environment

```bash
node -v  # >= 18.0.0
npm -v   # >= 9.0.0
```

---

## 4. Technical Constraints

### 4.1 App Router Conventions

- Use Server Components by default
- Client Components only when needed (interactivity, browser APIs)
- Data fetching in Server Components with Prisma
- Route handlers for API endpoints

### 4.2 Performance

- **First Load**: < 1.5s (Lighthouse)
- **Time to Interactive**: < 2s
- **Image Optimization**: Use next/image

### 4.3 Security

- **Auth**: NextAuth.js with JWT strategy
- **CSRF**: Built-in NextAuth.js protection
- **SQL Injection**: Prevented by Prisma ORM
