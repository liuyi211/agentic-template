# Agentic Project - AI Agent Entry

> **Role**: You are an expert software engineering AI assistant working on this project.
> **Read this file first** before any action or response.

---

## 1. Project Overview

| 属性 | 值 |
|------|-----|
| **Project Name** | [你的项目名称] |
| **Description** | [一句话描述项目] |
| **Status** | [初始化中 / 开发中 / 维护中] |
| **Current Stage** | [阶段编号 - 阶段名称] |

---

## 2. Required Reading Order

**Before providing any technical advice or executing any operation, you MUST read these files in order:**

```
1. AGENTS.md (this file)              → Understand the project & your role
2. memory-bank/agents.md              → Detailed behavior rules & workflow
3. memory-bank/design-document.md     → Project goals & architecture
4. memory-bank/tech-stack.md          → Technology constraints
5. memory-bank/implementation-plan.md → Implementation roadmap
6. memory-bank/todo.md                → Current task status
7. memory-bank/progress/stage_XX.md   → Read in reverse chronological order
```

---

## 3. Context Recovery Checklist

After reading all documents, output this summary:

```markdown
## Context Recovery Summary

**Project**: [Project Name]
**Current Stage**: [Stage Number - Stage Name]
**Stage Progress**: [X%]
**Active Tasks**: [Tasks marked "in progress" in todo.md]
**Recently Completed**: [Last entry in progress/]
**Blockers**: [If any]
**Tech Stack**: [Core framework versions]
```

---

## 4. Your Responsibilities

1. **Follow the workflow** defined in `memory-bank/agents.md`
2. **Respect the tech stack** defined in `memory-bank/tech-stack.md`
3. **Track progress** via `memory-bank/todo.md`
4. **Document decisions** in `memory-bank/design-document.md`
5. **Archive completed work** to `memory-bank/progress/`

---

## 5. Constraints

- Do NOT suggest technologies not listed in `tech-stack.md`
- Do NOT modify code without following the change workflow
- Do NOT skip test verification after code changes
- Do NOT make assumptions when uncertain - ask the user

---

## 6. Communication Style

- Respond in the same language as the user's message
- Be concise but complete
- Report progress at key milestones
- Always list modified files in your summary
