# Tech Stack

> **Project**: Node.js API Service
> **Last Updated**: 2026-04-30

---

## 1. Technology Selection Principles

1. **Performance First**: High-throughput API requires efficient runtime and framework
2. **Type Safety**: Full-stack TypeScript for compile-time correctness
3. **Developer Experience**: Auto-generated types, good debugging tools

---

## 2. Backend Tech Stack

### 2.1 Core Framework

| Technology | Version | Purpose | Selection Reason |
|------------|---------|---------|-----------------|
| Node.js | 20.x | Runtime | LTS, excellent async performance |
| Fastify | 4.24.0 | Web Framework | Faster than Express, built-in schema validation |
| TypeScript | 5.0.4 | Type System | Strict mode required |

### 2.2 Database

- **Primary DB**: PostgreSQL 15
- **ORM**: Prisma 5.6.0
- **Migrations**: Prisma Migrate

### 2.3 Validation

- **Solution**: Zod 3.22.4
- **Reason**: TypeScript-first, runtime type safety, excellent error messages

### 2.4 Testing

| Type | Tool | Version |
|------|------|---------|
| Unit Testing | Vitest | 1.0.0 |
| API Testing | Supertest | 6.3.0 |

---

## 3. Infrastructure

### 3.1 Deployment

| Technology | Purpose |
|-----------|---------|
| Docker | Containerization |
| Docker Compose | Local development orchestration |
| GitHub Actions | CI/CD |

### 3.2 Logging

- **Solution**: Pino (Fastify's built-in logger)

---

## 4. Technical Constraints

### 4.1 API Standards

- RESTful design with standard HTTP methods
- Unified response format: `{ code, data, message }`
- Standard pagination: `page`, `pageSize`
- Global error code management

### 4.2 Database Standards

- All tables must include `created_at` and `updated_at`
- Foreign keys must have indexes
- Enum types use database constraints
- Sensitive fields must be encrypted

### 4.3 Performance

- **API Response**: P95 < 200ms
- **Connection Pool**: Max 20 connections
