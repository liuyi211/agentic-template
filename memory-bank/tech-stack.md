# Tech Stack

> **项目**: [你的项目名称]
> **最后更新**: 2026-04-30

---

## 1. 技术选型原则

1. **成熟优先**：优先选择社区活跃、文档完善的技术
2. **团队熟悉**：考虑团队现有技术栈和学习成本
3. **生态兼容**：确保技术之间能够良好协作
4. **长期维护**：选择有长期支持计划的技术

---

## 2. 前端技术栈

### 2.1 核心框架

| 技术 | 版本 | 用途 | 选型理由 |
|------|------|------|----------|
| [React/Vue/Angular] | [x.x.x] | UI框架 | [理由] |
| [TypeScript] | [x.x.x] | 类型系统 | [理由] |
| [Vite/Webpack] | [x.x.x] | 构建工具 | [理由] |

### 2.2 状态管理

- **方案**: [Zustand/Redux/Pinia/Context]
- **理由**: [选型原因]

### 2.3 UI 组件

- **组件库**: [Ant Design/Material-UI/Tailwind]
- **样式方案**: [CSS Modules/Styled Components/Tailwind]

### 2.4 测试工具

| 类型 | 工具 | 版本 |
|------|------|------|
| 单元测试 | [Vitest/Jest] | [x.x.x] |
| E2E测试 | [Playwright/Cypress] | [x.x.x] |
| 组件测试 | [Testing Library] | [x.x.x] |

---

## 3. 后端技术栈

### 3.1 核心框架

| 技术 | 版本 | 用途 | 选型理由 |
|------|------|------|----------|
| [Node.js/Go/Python] | [x.x.x] | 运行时 | [理由] |
| [Express/Fastify/NestJS] | [x.x.x] | Web框架 | [理由] |

### 3.2 数据库

- **主数据库**: [PostgreSQL/MySQL/MongoDB] v[x.x.x]
- **缓存**: [Redis] v[x.x.x]
- **ORM/查询**: [Prisma/TypeORM/Drizzle]

### 3.3 中间件

- **认证**: [JWT/Auth0/Clerk]
- **消息队列**: [RabbitMQ/Kafka/Bull]
- **文件存储**: [S3/MinIO/本地存储]

---

## 4. 基础设施

### 4.1 部署与运维

| 技术 | 用途 |
|------|------|
| [Docker] | 容器化 |
| [Kubernetes/Docker Compose] | 编排 |
| [GitHub Actions/GitLab CI] | CI/CD |

### 4.2 监控与日志

- **日志**: [Winston/Pino/ELK Stack]
- **监控**: [Prometheus/Grafana/Datadog]
- **告警**: [PagerDuty/OpsGenie]

---

## 5. 开发环境

### 5.1 必需工具

```bash
# 运行时
node -v  # >= 18.0.0
npm -v   # >= 9.0.0

# 数据库
docker --version  # >= 20.0.0
```

### 5.2 开发配置

- **IDE**: VS Code (推荐插件列表见 `.vscode/extensions.json`)
- **代码规范**: ESLint + Prettier
- **Git Hooks**: Husky + lint-staged

---

## 6. 技术约束

### 6.1 兼容性要求

- **浏览器支持**: [Chrome >= 90, Firefox >= 88, Safari >= 14]
- **Node.js 版本**: [>= 18.0.0]

### 6.2 性能约束

- **Bundle 大小**: [首屏 < 200KB]
- **API 响应**: [P95 < 200ms]

### 6.3 安全约束

- **依赖审计**: 每月运行 `npm audit`
- **漏洞响应**: 高危漏洞 24h 内修复

---

## 7. 技术债务追踪

| 编号 | 描述 | 影响 | 计划处理时间 |
|------|------|------|-------------|
| TD-001 | [描述] | [高/中/低] | [日期] |
