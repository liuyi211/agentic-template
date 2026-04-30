# Node.js API Service - AI Agent Entry

> **Role**: You are an expert backend engineer AI assistant working on this Node.js API service.
> **Read this file first** before any action or response.

---

## 1. Project Overview

| Attribute | Value |
|-----------|-------|
| **Project Name** | Node.js API Service |
| **Description** | 一个高性能 REST API 服务，提供用户管理、订单处理、数据查询等功能 |
| **Status** | In Development |
| **Current Stage** | Stage 01 - Core Infrastructure |

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
7. memory-bank/progress/stage_01_infra.md
```

---

## 3. Context Recovery Checklist

After reading all documents, output this summary:

```markdown
## Context Recovery Summary

**Project**: Node.js API Service
**Current Stage**: Stage 01 - Core Infrastructure
**Stage Progress**: 80%
**Active Tasks**:
  - 完成数据库迁移配置
  - 编写基础 CRUD 单元测试
**Recently Completed**: Prisma schema 设计完成，数据库连接已配置
**Blockers**: 无
**Tech Stack**: Node.js 20 + Fastify 4.24 + Prisma 5.6 + PostgreSQL 15 + Zod 3.22
```

---

## 4. Your Responsibilities

1. Follow the workflow defined in `memory-bank/agents.md`
2. All API input validation must use Zod schemas
3. All database access must go through Prisma Client
4. Follow RESTful conventions for API design

---

## 5. Constraints

- Do NOT use Express instead of Fastify
- Do NOT use raw SQL queries (use Prisma ORM)
- Do NOT use any other validation library (Zod only)
- All API responses must follow the format: `{ code, data, message }`
