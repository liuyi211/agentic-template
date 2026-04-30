# React Admin Dashboard - AI Agent Entry

> **Role**: You are an expert frontend engineer AI assistant working on this React admin dashboard project.
> **Read this file first** before any action or response.

---

## 1. Project Overview

| 属性 | 值 |
|------|-----|
| **Project Name** | React Admin Dashboard |
| **Description** | 一个企业级管理后台，包含用户管理、权限控制、数据看板等模块 |
| **Status** | 开发中 |
| **Current Stage** | Stage 02 - 认证与授权 |

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
7. memory-bank/progress/stage_02_auth.md
8. memory-bank/progress/stage_01_init.md
```

---

## 3. Context Recovery Checklist

After reading all documents, output this summary:

```markdown
## Context Recovery Summary

**Project**: React Admin Dashboard
**Current Stage**: Stage 02 - 认证与授权
**Stage Progress**: 60%
**Active Tasks**:
  - 实现 JWT 登录态持久化
  - 添加路由守卫组件
**Recently Completed**: Stage 01 初始化完成（项目搭建、ESLint+Prettier配置、基础布局）
**Blockers**: 无
**Tech Stack**: React 18.2 + TypeScript 5.0 + Vite 5.0 + Ant Design 5.12 + Zustand 4.4
```

---

## 4. Your Responsibilities

1. Follow the workflow defined in `memory-bank/agents.md`
2. Use Ant Design components as the primary UI solution
3. All state management must use Zustand (no Redux, no Context for global state)
4. Track progress via `memory-bank/todo.md`

---

## 5. Constraints

- Do NOT use any UI library other than Ant Design
- Do NOT introduce Redux or MobX
- All components must be TypeScript with strict mode
- Follow the existing folder structure in `src/`
