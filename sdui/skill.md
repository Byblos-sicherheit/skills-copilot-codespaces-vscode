# Server-Driven UI (SDUI) — Copilot Skill

This skill teaches GitHub Copilot how to generate Server-Driven UI components and configs for the Byblos CRM ecosystem.

## Skill: Generate SDUI Config

**Trigger**: User asks to "add a new screen" or "create an SDUI config for..."

### Pattern: New Screen Definition

```typescript
// screens/meinScreen.ts
import type { SDUIScreen } from '../types';

export const meinScreen: SDUIScreen = {
  id: 'mein_screen',
  title: 'Mein Screen',
  root: {
    type: 'stack',
    children: [
      {
        type: 'page_header',
        props: { title: 'Mein Screen', subtitle: 'Beschreibung hier' }
      },
      {
        type: 'grid',
        props: { cols: 3 },
        children: [
          {
            type: 'stat_card',
            props: {
              label: 'Metrik A',
              value: '0',
              trend: { direction: 'up', label: '+0%' }
            }
          }
        ]
      }
    ]
  }
};
```

### Pattern: Register New Component

```typescript
// In registry.tsx — add a new component type:
import MyComponent from './components/MyComponent';

// Inside the REGISTRY object:
'my_component': (component, navigate) => (
  <MyComponent
    key={component.id}
    {...(component.props as MyComponentProps)}
  />
),
```

### Pattern: New Component File

```typescript
// components/MyComponent.tsx
import React from 'react';

interface MyComponentProps {
  label: string;
  value: string;
}

export const MyComponent: React.FC<MyComponentProps> = ({ label, value }) => (
  <div className="bg-white rounded-lg border border-gray-200 p-4">
    <p className="text-sm text-gray-500">{label}</p>
    <p className="text-2xl font-bold text-gray-900">{value}</p>
  </div>
);
```

## Component Type Reference

| Type | Props | Children? |
|------|-------|----------|
| `stack` | — | Yes |
| `grid` | `cols: 1\|2\|3\|4` | Yes |
| `page_header` | `title`, `subtitle?`, `tag?` | No |
| `stat_card` | `label`, `value`, `trend?` | No |
| `data_table` | `columns[]`, `rows[]` | No |
| `pipeline_board` | `columns[]` (with `cards[]`) | No |
| `metric_chart` | `title`, `bars[]` | No |
| `badge` | `label`, `color` | No |
| `button` | `label`, `variant`, `action?` | No |
| `section` | `title?` | Yes |

## Copilot Chat Prompts

```
// Add a new stat card to the dashboard
// Add a data table showing [entity] with columns: [col1], [col2], [col3]
// Create an SDUI screen for [feature] with KPIs and a table
// Add a pipeline board with stages: [stage1], [stage2], [stage3]
```

## Codespace Setup

```bash
# Clone and install
git clone https://github.com/Byblos-sicherheit/crm
cd crm
npm install
npm run dev

# The SDUI entry point is src/App.tsx
# Screens are defined in src/sdui/screens/
# Components are in src/sdui/components/
# Registry maps types to components: src/sdui/registry.tsx
```
