# TODO - Current Stage Task Tracking

> **Project**: React Admin Dashboard
> **Current Stage**: Stage 02 - 认证与授权
> **Last Updated**: 2026-04-30

---

## Current Stage Goal

建立完整的用户认证体系，包括登录、注册、Token 刷新、路由守卫。

---

## Task List

### 🔴 High Priority

- [ ] **[AUTH-001]** Implement JWT login with persistent storage
  - **Description**: 实现基于 JWT 的登录功能，Token 存储在 localStorage
  - **Acceptance Criteria**: 登录成功后 Token 持久化，刷新页面不丢失登录态
  - **Status**: 🔄 In Progress
  - **Estimated Hours**: 4h

- [ ] **[AUTH-002]** Add route guard component
  - **Description**: 创建 RequireAuth 组件，未登录用户重定向到登录页
  - **Acceptance Criteria**: 访问 `/dashboard` 等受保护路由时自动跳转登录页
  - **Status**: ⏳ Not Started

### 🟡 Medium Priority

- [ ] **[AUTH-003]** Implement user registration page
  - **Description**: 注册页面，包含表单校验
  - **Status**: ⏳ Not Started

### 🟢 Low Priority

- [ ] **[AUTH-004]** Add logout functionality
  - **Description**: 退出登录，清除 Token 和状态
  - **Status**: ⏳ Not Started

---

## Today's Work

### Completed ✅

1. [AUTH-000] 登录页面 UI 布局完成

### In Progress 🔄

1. [AUTH-001] JWT 登录持久化 - 50%

### Pending ⏳

1. [AUTH-002] 路由守卫组件
2. [AUTH-003] 注册页面

---

## Blockers

| Task | Block Reason | Solution | ETA |
|------|-------------|----------|-----|
| None | - | - | - |

---

## Manual Verification Items

- [ ] 登录成功跳转 Dashboard
- [ ] Token 刷新后保持登录态
- [ ] 未登录访问受保护路由跳转登录页
- [ ] 登录页表单校验正常工作

---

## Verification Results

| Check Item | Status | Notes |
|-----------|--------|-------|
| Unit tests pass | ⬜ | |
| Integration tests pass | ⬜ | |
| Code review pass | ⬜ | |
| Documentation updated | ⬜ | |

---

## Notes

- Backend API base URL: `http://localhost:3001/api`
- JWT Token structure: `{ accessToken, refreshToken }`
