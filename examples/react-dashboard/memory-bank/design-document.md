# Design Document

> **Project**: React Admin Dashboard
> **Status**: 开发中
> **Last Updated**: 2026-04-30

---

## 1. Project Overview

### 1.1 Project Goal

构建一个企业级管理后台，支持多角色用户管理、数据可视化看板、权限控制，并提供可复用的后台组件体系。

### 1.2 Core Features

- **用户管理**: 用户的增删改查、角色分配、状态管理
- **数据看板**: 实时数据图表、统计卡片、趋势分析
- **权限控制**: 基于角色的菜单和按钮级权限
- **系统设置**: 主题切换、个人设置、操作日志

### 1.3 Non-Functional Requirements

| Dimension | Requirement | Priority |
|-----------|-------------|----------|
| Performance | First load < 2s, route switch < 300ms | P0 |
| Usability | Support Chrome/Firefox/Safari latest 2 versions | P1 |
| Security | All API requests carry JWT, route guards | P0 |
| Scalability | Support 50+ menu items without performance degradation | P2 |

---

## 2. Architecture Design

### 2.1 System Architecture

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   React     │────▶│  Vite Dev   │────▶│  API Server │
│  (AntD UI)  │◄────│   Server    │◄────│  (Node.js)  │
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
│   ├── auth/           # Authentication module (login/register/logout)
│   ├── dashboard/      # Data dashboard
│   ├── user/           # User management
│   ├── system/         # System settings
│   └── shared/         # Shared components, utilities
├── components/         # Common UI components
├── hooks/              # Custom React hooks
├── stores/             # Zustand state stores
├── utils/              # Utility functions
└── api/                # API request encapsulation
```

### 2.3 Data Flow

1. User interaction triggers event
2. Event handler calls API (via Axios)
3. API response updates Zustand store
4. Store update triggers component re-render
5. UI displays updated data

---

## 3. Domain Model

### 3.1 Core Entities

```typescript
interface User {
  id: string;
  username: string;
  email: string;
  avatar?: string;
  role: 'admin' | 'editor' | 'viewer';
  status: 'active' | 'disabled';
  createdAt: Date;
}

interface MenuItem {
  id: string;
  name: string;
  path: string;
  icon: string;
  parentId?: string;
  permissions: string[];
  sort: number;
}
```

---

## 4. Interface Design

### 4.1 REST API Overview

| Method | Path | Description | Status |
|--------|------|-------------|--------|
| POST | /api/auth/login | User login | ✅ Implemented |
| POST | /api/auth/register | User registration | 🔄 In Progress |
| GET | /api/users | Get user list | ⏳ Not Started |
| GET | /api/dashboard/stats | Dashboard statistics | ⏳ Not Started |

---

## 5. Decision Records (ADR)

### ADR-001: Choose Ant Design as UI Library

- **Date**: 2026-04-28
- **Status**: Accepted
- **Background**: Need a comprehensive component library for admin dashboard
- **Decision**: Use Ant Design 5.x
- **Consequences**: Rich components, mature ecosystem; larger bundle size

### ADR-002: Choose Zustand for State Management

- **Date**: 2026-04-28
- **Status**: Accepted
- **Background**: Need lightweight state management
- **Decision**: Use Zustand instead of Redux
- **Consequences**: Less boilerplate, simpler API; smaller learning curve
