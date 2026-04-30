# Implementation Plan

> **Project**: Next.js Fullstack App
> **Status**: Planning
> **Last Updated**: 2026-04-30

---

## 1. Plan Description

This document defines the project's implementation roadmap. Each stage is an independently deliverable minimum viable unit.

**Basic Principles**:
- Small and specific steps
- Each step includes test verification
- Server Components first, Client Components only when needed
- No code: only clear, specific instructions

---

## 2. Milestone Planning

### Stage 0: Project Initialization
**Goal**: Set up runnable Next.js 14 framework

- [x] Initialize Next.js 14 with App Router
- [ ] Configure TypeScript strict mode
- [ ] Configure Tailwind CSS + shadcn/ui
- [ ] Configure Prisma + PostgreSQL
- [ ] Set up folder structure
- [ ] **Verification**: `npm run dev` starts, `npm run build` succeeds

### Stage 1: Database and Schema
**Goal**: Establish data layer

- [ ] Design Prisma schema (User, Post, Comment, Tag)
- [ ] Run initial migration
- [ ] Set up seed data
- [ ] **Verification**: Prisma Client works, seed data inserts correctly

### Stage 2: Authentication
**Goal**: Implement user authentication

- [ ] Configure NextAuth.js
- [ ] Implement login page
- [ ] Implement registration page
- [ ] Add protected routes middleware
- [ ] **Verification**: Auth flow works end-to-end

### Stage 3: Core Features
**Goal**: Implement blog functionality

- [ ] Post list page (Server Component)
- [ ] Post detail page (Server Component)
- [ ] Markdown editor (Client Component)
- [ ] Create/edit post (Server Actions)
- [ ] **Verification**: CRUD operations work

### Stage 4: Comments and Polish
**Goal**: Add comments and optimize

- [ ] Comment system (nested)
- [ ] SEO optimization (metadata, sitemap)
- [ ] Performance optimization
- [ ] **Verification**: Lighthouse score >= 90

---

## 3. Technical Constraints

### 3.1 Code Standards

```
- All code must pass TypeScript strict mode
- Prefer Server Components unless interactivity needed
- Use Server Actions for mutations
- Follow Next.js App Router conventions
```

---

## 4. Current Stage

**Current Execution**: Stage 00 - Project Initialization

**Current Stage Goal**:
Set up runnable Next.js 14 basic framework with development environment configured.

**Current Stage Progress**:
- [x] Next.js 14 project initialized
- [ ] Prisma + PostgreSQL configured
- [ ] Tailwind CSS + shadcn/ui configured
- [ ] Folder structure set up

**Current Stage Blockers**:
None
