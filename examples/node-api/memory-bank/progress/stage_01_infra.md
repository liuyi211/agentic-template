# Stage 01 - Core Infrastructure

> **Stage**: 01
> **Name**: 核心基础设施
> **Time Range**: 2026-04-28 ~ (ongoing)
> **Status**: 🔄 In Progress

---

## Goal

建立数据层和基础服务，包括数据库连接、迁移工具、基础 CRUD。

---

## Completed Tasks

- [x] Initialize Node.js project with TypeScript
- [x] Configure Fastify with TypeScript
- [x] Set up Prisma with PostgreSQL
- [x] Design database schema (User, Order, Product)
- [ ] Database migrations
- [ ] Base CRUD operations
- [ ] Unit tests

---

## Technical Decisions

### ADR-001: Choose Fastify over Express

- **Reason**: ~2x faster, built-in schema validation, better TypeScript support
- **Alternative**: Express - slower, middleware-based, less type-safe

### ADR-002: Choose Prisma over TypeORM

- **Reason**: Better type generation, migration tooling, query performance
- **Alternative**: TypeORM - more mature but less reliable in production

---

## Verification Results

| Check Item | Result |
|-----------|--------|
| `npm run dev` starts | ✅ Success |
| `npm run test` passes | ⬜ Not yet |
| `npm run lint` no errors | ✅ Pass |
| Database connection | ✅ Success |

---

## Stage Summary

**Completion**: 4/7 tasks completed

**Lessons Learned**:
- Prisma's type generation is excellent for API development
- Fastify's plugin system makes modular architecture easy

---

## Next Stage Preparation

- Database schema ready for auth module
- Stage 02 dependencies:
  - [ ] Migration files committed
  - [ ] Base repository pattern established
