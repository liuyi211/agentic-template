# Design Document

> **Project**: Next.js Fullstack App
> **Status**: 设计阶段
> **Last Updated**: 2026-04-30

---

## 1. Project Overview

### 1.1 Project Goal

构建一个全栈博客平台，支持文章发布、Markdown 编辑、评论互动、用户管理，具备良好的 SEO 和性能表现。

### 1.2 Core Features

- **文章系统**: Markdown 编辑、文章发布、草稿管理、分类标签
- **评论系统**: 嵌套评论、评论审核、点赞功能
- **用户系统**: 注册登录、个人主页、文章收藏
- **SEO 优化**: 服务端渲染、Meta 标签、Sitemap

### 1.3 Non-Functional Requirements

| Dimension | Requirement | Priority |
|-----------|-------------|----------|
| Performance | First Load < 1.5s, TTI < 2s | P0 |
| SEO | Lighthouse SEO score >= 95 | P0 |
| Security | CSRF protection, XSS prevention | P0 |
| Accessibility | WCAG 2.1 AA compliance | P1 |

---

## 2. Architecture Design

### 2.1 System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      Next.js 14 App                          │
│  ┌─────────────┐  ┌─────────────┐  ┌──────────────────────┐│
│  │   Server    │  │   Server    │  │      Client          ││
│  │ Components  │  │  Actions    │  │    Components        ││
│  │  (RSC)      │  │  (Server)   │  │    (RCC)             ││
│  └──────┬──────┘  └──────┬──────┘  └──────────┬───────────┘│
│         │                │                     │            │
│         └────────────────┼─────────────────────┘            │
│                          │                                  │
│                   ┌──────┴──────┐                          │
│                   │   Prisma    │                          │
│                   │  (ORM)      │                          │
│                   └──────┬──────┘                          │
│                          │                                  │
│                   ┌──────┴──────┐                          │
│                   │ PostgreSQL  │                          │
│                   └─────────────┘                          │
└─────────────────────────────────────────────────────────────┘
```

### 2.2 Module Division

```
app/
├── (auth)/             # Auth route group
│   ├── login/
│   └── register/
├── (main)/             # Main route group
│   ├── page.tsx        # Home page
│   ├── posts/
│   │   ├── page.tsx    # Post list
│   │   └── [slug]/
│   │       └── page.tsx # Post detail
│   └── about/
├── api/                # API routes (if needed)
├── layout.tsx          # Root layout
└── globals.css

components/
├── ui/                 # shadcn/ui components
├── editor/             # Markdown editor
├── comments/           # Comment components
└── shared/             # Shared components

lib/
├── prisma.ts           # Prisma client
├── auth.ts             # NextAuth config
└── utils.ts            # Utilities

prisma/
└── schema.prisma       # Database schema
```

---

## 3. Domain Model

### 3.1 Core Entities

```prisma
model User {
  id        String   @id @default(cuid())
  email     String   @unique
  name      String?
  image     String?
  posts     Post[]
  comments  Comment[]
  createdAt DateTime @default(now())
}

model Post {
  id          String    @id @default(cuid())
  title       String
  slug        String    @unique
  content     String
  excerpt     String?
  published   Boolean   @default(false)
  author      User      @relation(fields: [authorId], references: [id])
  authorId    String
  comments    Comment[]
  tags        Tag[]
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
}

model Comment {
  id        String   @id @default(cuid())
  content   String
  author    User?    @relation(fields: [authorId], references: [id])
  authorId  String?
  post      Post     @relation(fields: [postId], references: [id])
  postId    String
  parent    Comment? @relation("CommentReplies", fields: [parentId], references: [id])
  parentId  String?
  replies   Comment[] @relation("CommentReplies")
  createdAt DateTime @default(now())
}

model Tag {
  id    String @id @default(cuid())
  name  String @unique
  posts Post[]
}
```

---

## 4. Decision Records (ADR)

### ADR-001: Choose App Router over Pages Router

- **Date**: 2026-04-30
- **Status**: Accepted
- **Background**: Next.js 13+ introduces App Router with Server Components
- **Decision**: Use App Router exclusively
- **Consequences**: Better performance with RSC; newer, less documentation

### ADR-002: Choose NextAuth.js for Authentication

- **Date**: 2026-04-30
- **Status**: Accepted
- **Background**: Need authentication with social login support
- **Decision**: Use NextAuth.js (Auth.js) v5
- **Consequences**: Seamless Next.js integration; flexible provider system
