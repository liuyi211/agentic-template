# Stage 00 - Project Initialization

> **Stage**: 00
> **Name**: 项目初始化
> **Time Range**: 2026-04-30 ~ (ongoing)
> **Status**: 🔄 In Progress

---

## Goal

搭建可运行的 Next.js 14 基础框架，配置开发环境（lint、format、git hooks）。

---

## Completed Tasks

- [x] Create Next.js 14 project with App Router
- [x] Configure TypeScript strict mode
- [x] Configure ESLint + Prettier
- [ ] Configure Prisma + PostgreSQL
- [ ] Configure Tailwind CSS + shadcn/ui
- [ ] Set up folder structure

---

## Technical Decisions

### ADR-001: Choose App Router over Pages Router

- **Reason**: Server Components, better performance, modern Next.js pattern
- **Alternative**: Pages Router - more mature but App Router is the future

### ADR-002: Choose shadcn/ui over Ant Design

- **Reason**: More customizable, tree-shakeable, based on Radix UI primitives
- **Alternative**: Ant Design - more components but heavier bundle

---

## Verification Results

| Check Item | Result |
|-----------|--------|
| `npm run dev` starts | ✅ Success |
| `npm run build` succeeds | ✅ Success |

---

## Stage Summary

**Completion**: 2/5 tasks completed

---

## Next Stage Preparation

- Project scaffolding ready
- Stage 01 dependencies:
  - [ ] Prisma schema defined
  - [ ] Database migrations ready
