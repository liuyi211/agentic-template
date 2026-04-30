# 示例：React 管理后台

本示例展示如何在 Agentic Template 下开发一个 React + TypeScript + Ant Design 的管理后台。

## 项目信息

| 属性 | 值 |
|------|-----|
| 项目名称 | React Admin Dashboard |
| 技术栈 | React 18 + TypeScript + Vite + Ant Design 5 + Zustand |
| 当前阶段 | Stage 02 - 认证与授权 |
| 进度 | 60% |

## 文件结构

```
react-dashboard/
├── AGENTS.md                          # AI 入口文件
├── memory-bank/
│   ├── agents.md                      # 详细行为规范
│   ├── design-document.md             # 设计文档（已填写）
│   ├── tech-stack.md                  # 技术栈（已填写）
│   ├── implementation-plan.md         # 实现计划（已填写）
│   ├── todo.md                        # 当前任务
│   └── progress/
│       ├── stage_01_init.md           # 阶段 01 完成记录
│       └── stage_02_auth.md           # 阶段 02 进行中
```

## 如何使用

1. 复制本示例到你的项目目录
2. 根据实际项目修改 `AGENTS.md` 和 `memory-bank/` 中的内容
3. 开始与 AI 协作开发

## 关键决策

- **UI 库选择 Ant Design**：团队熟悉，生态完善
- **状态管理用 Zustand**：比 Redux 更轻量，代码更少
- **路由用 React Router v6**：官方推荐，hooks API 友好
