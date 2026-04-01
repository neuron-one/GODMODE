---
name: frontend
description: React and Next.js frontend development. Components, hooks, state management, routing, Tailwind CSS styling. Don't use for React Native mobile or backend API development.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep, Glob
paths: "src/**/*.tsx,src/**/*.jsx,src/**/*.css,*.html"
---

# Frontend Development

## React Patterns
- Functional components only (no class components)
- Custom hooks for shared logic
- Context API for global state, local state for component state
- Lazy loading for heavy components
- Error boundaries for graceful failures

## Component Structure
```
ComponentName/
  ├── index.tsx        # Main component
  ├── styles.css       # Styles (or Tailwind)
  └── types.ts         # TypeScript interfaces
```

## Styling
- Tailwind CSS as primary
- CSS Modules when Tailwind insufficient
- Mobile-first responsive design
- Design tokens for consistency

## Performance
- React.memo for expensive renders
- useMemo/useCallback where measurably beneficial
- Image optimization (lazy loading, proper formats)
- Code splitting with dynamic imports

## Accessibility
- Semantic HTML elements
- ARIA labels where needed
- Keyboard navigation support
- Color contrast compliance