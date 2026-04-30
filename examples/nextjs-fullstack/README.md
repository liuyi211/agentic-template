# 示例：Next.js 全栈应用

本示例展示如何在 Agentic Template 下开发一个 Next.js 14 + Prisma + PostgreSQL 的全栈应用。

## 项目信息

| 属性 | 值 |
|------|-----|
| 项目名称 | Next.js Fullstack App |
| 技术栈 | Next.js 14 (App Router) + TypeScript + Prisma + PostgreSQL + Tailwind CSS + shadcn/ui |
| 当前阶段 | Stage 00 - 项目初始化 |
| 进度 | 40% |

## 文件结构

```
nextjs-fullstack/
├── AGENTS.md                          # AI 入口文件
├── memory-bank/
│   ├── agents.md                      # 详细行为规范
│   ├── design-document.md             # 设计文档（已填写）
│   ├── tech-stack.md                  # 技术栈（已填写）
│   ├── implementation-plan.md         # 实现计划（已填写）
│   ├── todo.md                        # 当前任务
│   └── progress/
│       └── stage_00_init.md           # 阶段 00 进行中
```

## 如何使用

1. 复制本示例到你的项目目录
2. 根据实际项目修改 `AGENTS.md` 和 `memory-bank/` 中的内容
3. 开始与 AI 协作开发

## 关键决策

- **App Router**：Next.js 13+ 推荐的新路由模式，支持 Server Components
- **Prisma + PostgreSQL**：类型安全的 ORM + 关系型数据库
- **shadcn/ui**：基于 Radix UI 的组件库，可定制性强
- **Tailwind CSS**：原子化 CSS，开发效率高
