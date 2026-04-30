# Stage 01 - Project Initialization

> **Stage**: 01
> **Name**: 项目初始化
> **Time Range**: 2026-04-28 ~ 2026-04-29
> **Status**: ✅ Completed

---

## Goal

搭建可运行的基础框架，建立开发规范和 CI/CD 流程。

---

## Completed Tasks

- [x] Initialize project structure with Vite + React + TypeScript
- [x] Configure ESLint + Prettier
- [x] Configure Husky + lint-staged
- [x] Set up basic CI/CD pipeline (GitHub Actions)
- [x] Implement basic layout (Sider + Header + Content)
- [x] Configure Ant Design theme

---

## Technical Decisions

### ADR-001: Choose Vite over Create React App

- **Reason**: Faster dev server, better tree-shaking, native ESM
- **Alternative**: CRA - slower, less flexible

### ADR-002: Choose Zustand over Redux

- **Reason**: Less boilerplate, simpler API, excellent TypeScript support
- **Alternative**: Redux Toolkit - more boilerplate, heavier

---

## Verification Results

| Check Item | Result |
|-----------|--------|
| `npm run dev` starts | ✅ Success |
| `npm run test` passes | ✅ Pass |
| `npm run lint` no errors | ✅ Pass |
| `npm run build` succeeds | ✅ Success |

---

## Stage Summary

**Completion**: 6/6 tasks completed
**Key Deliverables**:
- Project scaffolding with Vite
- Development tooling configured
- Basic layout components

**Lessons Learned**:
- Vite's plugin ecosystem is mature enough for production
- Ant Design v5 theme customization via ConfigProvider works well

---

## Next Stage Preparation

- Basic project structure ready for feature development
- Stage 02 depends on:
  - [x] API client setup (Axios configured)
  - [x] Basic routing structure
