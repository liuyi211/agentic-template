# Design Document

> **Project**: Node.js API Service
> **Status**: 开发中
> **Last Updated**: 2026-04-30

---

## 1. Project Overview

### 1.1 Project Goal

构建一个高性能 REST API 服务，提供用户管理、订单处理、商品管理等核心功能，为前端应用提供稳定的数据接口。

### 1.2 Core Features

- **用户系统**: 注册、登录、JWT 认证、权限管理
- **订单管理**: 创建订单、订单状态流转、订单查询
- **商品管理**: 商品 CRUD、库存管理、分类管理
- **数据接口**: 分页查询、筛选排序、聚合统计

### 1.3 Non-Functional Requirements

| Dimension | Requirement | Priority |
|-----------|-------------|----------|
| Performance | API P95 response < 200ms | P0 |
| Availability | 99.9% uptime | P1 |
| Security | All APIs require authentication except login/register | P0 |
| Scalability | Support horizontal scaling | P2 |

---

## 2. Architecture Design

### 2.1 System Architecture

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Client    │────▶│   Nginx     │────▶│  Fastify    │
│  (React)    │◄────│   (Proxy)   │◄────│  (Node.js)  │
└─────────────┘     └─────────────┘     └──────┬──────┘
                                                │
                                          ┌─────┴─────┐
                                          │  Database │
                                          │(PostgreSQL)│
                                          └───────────┘
```

### 2.2 Module Division

```
src/
├── modules/
│   ├── auth/           # Authentication module
│   ├── users/          # User management
│   ├── orders/         # Order management
│   ├── products/       # Product management
│   └── shared/         # Shared utilities, middleware
├── plugins/            # Fastify plugins
├── prisma/             # Prisma schema and migrations
├── routes/             # Route definitions
└── utils/              # Utility functions
```

### 2.3 Data Flow

1. Request enters through Nginx
2. Fastify routes request to handler
3. Handler validates input with Zod schema
4. Prisma executes database query
5. Response formatted as `{ code, data, message }`
6. Error handled by global error handler

---

## 3. Domain Model

### 3.1 Core Entities

```typescript
// User entity
interface User {
  id: string;
  email: string;
  password: string; // hashed
  name: string;
  role: 'admin' | 'user';
  createdAt: Date;
  updatedAt: Date;
}

// Order entity
interface Order {
  id: string;
  userId: string;
  status: 'pending' | 'paid' | 'shipped' | 'completed' | 'cancelled';
  totalAmount: number;
  items: OrderItem[];
  createdAt: Date;
  updatedAt: Date;
}
```

---

## 4. Interface Design

### 4.1 REST API Overview

| Method | Path | Description | Auth | Status |
|--------|------|-------------|------|--------|
| POST | /api/auth/register | User registration | No | ⏳ Not Started |
| POST | /api/auth/login | User login | No | ⏳ Not Started |
| GET | /api/users | Get user list | Yes | ⏳ Not Started |
| GET | /api/users/:id | Get user detail | Yes | ⏳ Not Started |
| POST | /api/orders | Create order | Yes | ⏳ Not Started |
| GET | /api/orders | Get order list | Yes | ⏳ Not Started |

---

## 5. Decision Records (ADR)

### ADR-001: Choose Fastify over Express

- **Date**: 2026-04-28
- **Status**: Accepted
- **Background**: Need high-performance API framework
- **Decision**: Use Fastify 4.x
- **Consequences**: ~2x faster than Express; smaller ecosystem but growing

### ADR-002: Choose Prisma over TypeORM

- **Date**: 2026-04-28
- **Status**: Accepted
- **Background**: Need type-safe ORM with good migration support
- **Decision**: Use Prisma 5.x
- **Consequences**: Excellent type generation; query engine adds startup time
