# Tech Stack

> **Project**: React Admin Dashboard
> **Last Updated**: 2026-04-30

---

## 1. Technology Selection Principles

1. **Mature First**: Prioritize community-active, well-documented technologies
2. **Team Familiarity**: Consider existing team knowledge
3. **Ecosystem Compatibility**: Ensure technologies work well together

---

## 2. Frontend Tech Stack

### 2.1 Core Framework

| Technology | Version | Purpose | Selection Reason |
|------------|---------|---------|-----------------|
| React | 18.2.0 | UI Framework | Mature ecosystem, team experience |
| TypeScript | 5.0.4 | Type System | Strict typing, better DX |
| Vite | 5.0.0 | Build Tool | Fast dev server, tree-shaking |

### 2.2 State Management

- **Solution**: Zustand 4.4.7
- **Reason**: Lightweight, less boilerplate than Redux, excellent TypeScript support

### 2.3 UI Components

- **Component Library**: Ant Design 5.12.0
- **Styling**: CSS Modules + Ant Design tokens

### 2.4 Routing

- **Solution**: React Router v6.20

### 2.5 Testing

| Type | Tool | Version |
|------|------|---------|
| Unit Testing | Vitest | 1.0.0 |
| Component Testing | Testing Library | 14.0.0 |
| E2E Testing | Playwright | 1.40.0 |

---

## 3. Development Environment

### 3.1 Required Tools

```bash
node -v  # >= 18.0.0
npm -v   # >= 9.0.0
```

### 3.2 Development Configuration

- **IDE**: VS Code
- **Code Standards**: ESLint + Prettier
- **Git Hooks**: Husky + lint-staged

---

## 4. Technical Constraints

### 4.1 Compatibility

- **Browser Support**: Chrome >= 90, Firefox >= 88, Safari >= 14

### 4.2 Performance

- **Bundle Size**: Initial load < 200KB (gzipped)
- **Component lazy loading**: Required for routes

### 4.3 Security

- **Dependency Audit**: Run `npm audit` monthly
- **No sensitive data**: Never hardcode API keys
