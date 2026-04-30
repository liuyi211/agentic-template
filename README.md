# Agentic Template

> 一个用于 **Vibe Coding** 的 AI Agent 项目模板，帮助开发者在长期项目中控制 AI 的上下文、权限、实现计划和交付质量。

---

## 什么是 Vibe Coding？

**Vibe Coding** = 你描述需求，AI 写代码。你审核、测试、提反馈，AI 继续改。

这种模式在**新项目启动、快速原型、独立功能模块**时非常高效。但当项目变大、对话变长，AI 会：

- **遗忘**之前的架构决策和设计约定
- **重复**问同样的问题
- **偏离**既定的技术路线
- **擅自**修改不应碰的代码

**Agentic Template** 就是为了解决这个问题而生。

---

## 核心设计

```
┌─────────────────────────────────────────────────────────────┐
│                      AI Agent 会话层                          │
│                    (Claude Code / Cursor / Copilot)          │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                    AGENTS.md (入口文件)                        │
│         告诉 AI：你是谁、你能做什么、你应该先读什么              │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                      memory-bank/                             │
│  ┌─────────────┐  ┌─────────────┐  ┌──────────────────────┐  │
│  │ design-doc  │  │ tech-stack  │  │ implementation-plan  │  │
│  │ (设计文档)   │  │ (技术约束)   │  │ (实现路线图)          │  │
│  └─────────────┘  └─────────────┘  └──────────────────────┘  │
│  ┌─────────────┐  ┌────────────────────────────────────────┐  │
│  │ todo.md     │  │ progress/                              │  │
│  │ (当前任务)   │  │ (阶段成果记录)                          │  │
│  └─────────────┘  └────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### 关键机制

| 机制 | 说明 | 效果 |
|------|------|------|
| **上下文恢复协议** | 每次新会话强制按顺序读取文档 | AI 30 秒内恢复完整上下文 |
| **行为规范** | 定义权限边界、操作流程、决策原则 | AI 不越界、不瞎猜 |
| **阶段化计划** | 将项目拆分为可独立交付的阶段 | 每阶段有明确目标和验收标准 |
| **进度追踪** | 用 `todo.md` + `progress/` 记录状态 | AI 知道该做什么、已做了什么 |
| **技术锁定** | 在 `tech-stack.md` 中固化选型 | AI 不会突然换技术栈 |

---

## 快速开始

### 1. 使用模板创建项目

```bash
# 方式一：直接复制
git clone https://github.com/yourname/agentic-template.git my-project
cd my-project
rm -rf .git

# 方式二：GitHub Template
# 点击仓库页面的 "Use this template" 按钮
```

### 2. 初始化项目信息

编辑以下文件，填入你的项目信息。

你可以直接把这些提示词发给 AI，让它帮你填写：

| 文件 | 需要修改的内容 | 示例提示词 |
|------|----------------|-----------|
| `AGENTS.md` | 项目简介、AI 角色定义 | `更新 AGENTS.md：项目名是"电商管理后台"，用 React + Ant Design + Zustand 开发，你是前端专家 AI。当前 Stage 01。` |
| `memory-bank/design-document.md` | 项目目标、架构设计 | `更新 design-document.md：做一个电商管理后台，核心功能有商品管理、订单管理、用户管理、数据报表。画一下架构图，用 React 前端 + Node.js 后端 + PostgreSQL。` |
| `memory-bank/tech-stack.md` | 具体技术选型 | `更新 tech-stack.md：前端 React 18 + Vite + TypeScript + Ant Design 5 + Zustand，后端 Node.js 20 + Fastify + Prisma + PostgreSQL 15。` |
| `memory-bank/implementation-plan.md` | 里程碑规划 | `更新 implementation-plan.md：分 5 个阶段：0 初始化、1 数据库、2 认证、3 商品/订单模块、4 报表/优化。每个阶段写清楚验收标准。` |
| `memory-bank/todo.md` | 当前阶段任务 | `更新 todo.md：当前 Stage 01 - 数据库设计。高优先级任务：设计 Prisma Schema（用户、商品、订单表），预计 4 小时。` |

### 3. 开始 Vibe Coding

打开你的 AI 编程工具（Claude Code / Cursor / Windsurf 等），AI 会自动读取 `AGENTS.md`，然后按规范执行。

#### 常用开发提示词

| 场景 | 提示词 |
|------|--------|
| **从零初始化项目** | `我要做一个 [目标描述]。请按 AGENTS.md 的规范执行：1）更新 AGENTS.md 填入项目信息；2）分析项目的[技术栈],写入tech-stack.md;3)制定实现计划写入 implementation-plan.md；4）设计数据库写入 design-document.md。全部确认后再开始写代码。` |
| **设计数据库** | `设计数据库 Schema，需要支持 [功能]。更新 design-document.md 和 prisma/schema.prisma，先给我方案确认。` |
| **实现页面/功能** | `实现 [功能名称]。要求：[具体需求]。这是 Stage 0X 的任务，参考 implementation-plan.md。先出方案，确认后写代码。` |
| **修复 Bug** | `修复 [Bug 描述]。先分析原因，再修复。修复后运行测试验证，更新 todo.md。` |
| **重构代码** | `重构 [模块/文件]。目标是 [重构目标]。确保现有测试全部通过，不要改变外部接口。` |
| **阶段收尾** | `Stage 0X 完成，执行收尾：1）归档 progress/stage_XX_xxx.md；2）更新 todo.md；3）更新 implementation-plan.md。准备进入下一阶段。` |
| **代码审查** | `审查本次修改的代码，按 agents.md 的审查清单检查，输出审查报告。` |

> **技巧**：首次使用某个功能时加上"先出方案，确认后写代码"，避免 AI 擅自执行。熟悉后可直接说"确认，开始执行"。

---

## 文件结构

```
agentic-template/
├── AGENTS.md                          # AI 行为规范与操作流程（必读）
├── README.md                          # 本文件
├── LICENSE                            # MIT 协议
├── .gitignore                         # Git 忽略规则
│
├── memory-bank/                       # AI 上下文记忆库（项目特定）
│   ├── design-document.md             # 项目设计文档
│   ├── tech-stack.md                  # 技术栈与约束
│   ├── implementation-plan.md         # 实现计划与里程碑
│   ├── todo.md                        # 当前任务追踪
│   └── progress/                      # 阶段成果归档
│       ├── stage_01_xxx.md
│       ├── stage_02_xxx.md
│       └── ...
│
└── examples/                          # 使用示例
    ├── react-dashboard/
    ├── node-api/
    └── nextjs-fullstack/
```

---

## 文档说明

### AGENTS.md

**AI 进入项目时第一个读取的文件。** 定义 Agent 的完整行为规范，包含：
- 核心原则（确定性、透明性）
- 文档读取顺序与上下文恢复协议
- 操作流程（理解→分析→设计→实现→验证→文档→汇报）
- 测试流程（自动化 + 手动验证）
- 代码审查清单
- 权限边界
- 决策原则
- 代码质量标准
- 沟通规范

### memory-bank/design-document.md

**项目设计文档。** 包含：
- 项目目标与核心功能
- 系统架构图
- 模块划分
- 领域模型
- 接口设计
- 架构决策记录 (ADR)

### memory-bank/tech-stack.md

**技术栈锁定。** 包含：
- 前端/后端/数据库/基础设施技术选型
- 版本号
- 选型理由
- 兼容性要求
- 性能约束
- 安全约束

### memory-bank/implementation-plan.md

**实现路线图。** 包含：
- 分阶段里程碑（每个阶段可独立交付）
- 技术约束与规范
- 风险与应对措施
- 当前阶段进度

### memory-bank/todo.md

**任务追踪。** 包含：
- 按优先级分类的任务列表
- 今日工作状态
- 阻塞项
- 待手动验证项
- 验证结果

### memory-bank/progress/stage_XX_xxx.md

**阶段成果记录。** 每个阶段完成后归档：
- 阶段目标与完成情况
- 技术决策记录
- 遇到的问题与解决方案
- 验证结果
- 经验教训
- 下一阶段准备

---

## 使用示例

### 示例 1：新会话开始

```
用户：继续开发用户模块

AI：[读取 AGENTS.md] → [读取 memory-bank 全部文档]
    → 输出上下文恢复总结
    → "当前处于阶段 2，认证模块开发中，
        你是指继续开发注册/登录 API 吗？"

用户：对，加上邮箱验证

AI：按规范执行 → 分析 → 设计 → 实现 → 测试 → 更新 todo → 汇报
```

### 示例 2：防止技术栈漂移

```
用户：我想换个更快的 ORM

AI：[读取 tech-stack.md] → "当前已选定 Prisma 作为 ORM，
    变更需要更新 tech-stack.md 并说明理由。
    建议：如无性能瓶颈，保持现有选型以降低风险。
    你确定要更换吗？"
```

### 示例 3：上下文恢复

```
用户：（三天后新会话）修复那个排序 bug

AI：[读取 AGENTS.md → design-document → todo.md → progress/]
    → "根据记录，列表排序功能在 stage_03 实现，
       相关文件在 src/modules/items/sort.ts。
       请问具体是什么排序问题？"
```

---

## 最佳实践

### Do

- ✅ 每次重要决策都记录到 `design-document.md` 的 ADR 部分
- ✅ 每完成一个任务就更新 `todo.md`
- ✅ 每个阶段结束都创建 `progress/stage_XX_xxx.md`
- ✅ 技术选型变更时同步更新 `tech-stack.md`
- ✅ 让 AI 在执行操作前先读取相关文档

### Don't

- ❌ 让 AI 在没有读取文档的情况下直接开始编码
- ❌ 手动修改代码后不更新 `todo.md` 和 `progress`
- ❌ 在对话中重复说明已经写在文档里的信息
- ❌ 一个阶段未完成就跳到下一个阶段（除非已更新计划）

---

## 支持的 AI 工具

| 工具 | 兼容性 | 说明 |
|------|--------|------|
| [Claude Code](https://claude.ai/code) | 完美支持 | 自动读取 AGENTS.md，支持 MCP |
| [Cursor](https://cursor.sh) | 完美支持 | 在 `.cursorrules` 中引用 AGENTS.md |
| [Windsurf](https://codeium.com/windsurf) | 完美支持 | Cascade 模式自动读取 |
| [GitHub Copilot](https://copilot.github.com) | 良好支持 | 结合自定义指令使用 |
| [Cline](https://github.com/cline/cline) | 良好支持 | 在系统提示中引用 AGENTS.md |

### 配置提示

**Cursor**：创建 `.cursorrules` 文件：
```
Always read AGENTS.md first before any action.
Follow the workflow defined in AGENTS.md.
```

**Cline**：在设置中添加系统提示：
```
You must read AGENTS.md before responding.
Follow the context recovery protocol in AGENTS.md.
```

---

## 贡献

欢迎提交 Issue 和 PR！

如果你：
- 发现模板有漏洞（AI 可以绕过某些约束）
- 有新的场景需要覆盖
- 想添加更多示例项目

请随时贡献。

---

## 许可证

[MIT](./LICENSE)

---

<div align="center">

**让 AI 听话，让项目可控。**

</div>
"# agentic-template" 
