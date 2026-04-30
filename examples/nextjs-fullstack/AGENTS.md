# Next.js Fullstack App - AI Agent Entry

> **Role**: You are an expert fullstack engineer AI assistant working on this Next.js application.
> **Read this file first** before any action or response.

---

## 1. Project Overview

| Attribute | Value |
|-----------|-------|
| **Project Name** | Next.js Fullstack App |
| **Description** | 一个全栈博客平台，支持文章发布、评论、用户管理 |
| **Status** | In Development |
| **Current Stage** | Stage 00 - Project Initialization |

---

## 2. Required Reading Order

**Before providing any technical advice or executing any operation, you MUST read these files in order:**

```
1. AGENTS.md (this file)
2. memory-bank/agents.md
3. memory-bank/design-document.md
4. memory-bank/tech-stack.md
5. memory-bank/implementation-plan.md
6. memory-bank/todo.md
7. memory-bank/progress/stage_00_init.md
```

---

## 3. Context Recovery Checklist

After reading all documents, output this summary:

```markdown
## Context Recovery Summary

**Project**: Next.js Fullstack App
**Current Stage**: Stage 00 - Project Initialization
**Stage Progress**: 40%
**Active Tasks**:
  - 配置 Next.js 14 + App Router
  - 配置 Prisma 和数据库连接
**Recently Completed**: 项目目录创建，基础依赖安装
**Blockers**: 无
**Tech Stack**: Next.js 14.2 + React 18 + TypeScript 5 + Prisma 5.6 + PostgreSQL 15 + Tailwind CSS 3.4 + shadcn/ui
```

---

## 4. Your Responsibilities

1. Follow the workflow defined in `memory-bank/agents.md`
2. Prefer Server Components unless interactivity is required
3. Use Prisma for all database operations
4. Follow the Next.js App Router conventions

---

## 5. Constraints

- Do NOT use the Pages Router (App Router only)
- Do NOT use raw SQL (Prisma ORM only)
- Server Components should handle data fetching
- Client Components only for interactive UI
