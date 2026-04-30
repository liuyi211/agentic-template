# 示例：Node.js API 服务

本示例展示如何在 Agentic Template 下开发一个 Node.js + Fastify + Prisma + PostgreSQL 的 REST API 服务。

## 项目信息

| 属性 | 值 |
|------|-----|
| 项目名称 | Node.js API Service |
| 技术栈 | Node.js 20 + Fastify 4 + Prisma 5 + PostgreSQL 15 + Zod |
| 当前阶段 | Stage 01 - 核心基础设施 |
| 进度 | 80% |

## 文件结构

```
node-api/
├── AGENTS.md                          # AI 入口文件
├── memory-bank/
│   ├── agents.md                      # 详细行为规范
│   ├── design-document.md             # 设计文档（已填写）
│   ├── tech-stack.md                  # 技术栈（已填写）
│   ├── implementation-plan.md         # 实现计划（已填写）
│   ├── todo.md                        # 当前任务
│   └── progress/
│       └── stage_01_infra.md          # 阶段 01 进行中
```

## 如何使用

1. 复制本示例到你的项目目录
2. 根据实际项目修改 `AGENTS.md` 和 `memory-bank/` 中的内容
3. 开始与 AI 协作开发

## 关键决策

- **Web 框架用 Fastify**：比 Express 性能更好，内置 JSON Schema 验证
- **ORM 用 Prisma**：类型安全，迁移管理完善
- **验证用 Zod**：与 TypeScript 集成好，运行时类型安全
