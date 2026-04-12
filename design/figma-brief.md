# ODE Figma Design Brief

## Project Structure

### Figma File Organization

```
ODE Design System
├── Cover (project overview, version, date)
├── Brand
│   ├── Logo & Usage
│   ├── Color Palette (light + dark mode)
│   ├── Typography Specimens
│   └── Iconography
├── Foundations
│   ├── Grid & Layout
│   ├── Spacing
│   ├── Elevation (shadows)
│   └── Motion (documentation)
├── Components
│   ├── Primitives (button, input, select, etc.)
│   ├── Layout (card, panel, tabs, etc.)
│   ├── Feedback (toast, alert, dialog, etc.)
│   ├── Data Display (table, badge, stat, etc.)
│   ├── Engineering (parameter panel, viewport, etc.)
│   └── Navigation (command palette, breadcrumb, etc.)
├── Patterns
│   ├── Forms
│   ├── Data Tables
│   ├── Empty States
│   ├── Error States
│   └── Loading States
├── Screens
│   ├── Marketing (landing, pricing, about)
│   ├── Auth (sign-up, login, onboarding)
│   ├── App (dashboard, project, editor, simulation)
│   └── Settings (account, team, billing)
└── Prototypes
    ├── Onboarding Flow
    ├── AI Model Generation
    └── Simulation Workflow
```

---

## Key Screens to Design

### Marketing Screens

| Screen | Priority | Description |
|--------|:--------:|-------------|
| Landing Page | P0 | Hero, features, AI demo embed, pricing, CTA |
| Pricing Page | P0 | Tier comparison, FAQ, CTA to sign up |
| About / Company | P1 | Mission, team, investors, contact |
| Blog Layout | P1 | Article template, sidebar, related posts |
| Case Study Template | P2 | Customer story layout |

### Application Screens

| Screen | Priority | Description |
|--------|:--------:|-------------|
| Dashboard | P0 | Recent projects, quick actions, usage stats |
| Project View | P0 | File browser, project settings, team members |
| Modelica Editor | P0 | Code editor + AI panel + model tree + console |
| 3D Viewport | P0 | Vision tool: 3D viz + controls + result overlay |
| Simulation Results | P0 | Charts, data tables, AI analysis summary |
| Geometry Editor | P1 | CAD tool with toolbar, viewport, properties |
| System Diagram | P1 | SysML diagram editor with component palette |
| Paper (Docs) | P1 | Collaborative document editor |
| Interaction View | P2 | Real-time parameter exploration dashboard |
| Settings | P2 | Account, team management, billing, API keys |

### Auth / Onboarding Screens

| Screen | Priority | Description |
|--------|:--------:|-------------|
| Sign Up | P0 | Email + Google SSO, minimal fields |
| Login | P0 | Email + SSO, forgot password |
| Onboarding (3 steps) | P0 | Role, industry, first project wizard |

---

## Design Tokens → Figma Variables

Map `design-tokens.json` to Figma variables:

### Color Variables
```
Collection: Colors
├── Mode: Dark (default)
│   ├── primary/600: #6366F1
│   ├── surface/primary: #0F172A
│   ├── surface/secondary: #1E293B
│   ├── text/primary: #F8FAFC
│   └── ...
└── Mode: Light
    ├── primary/600: #4F46E5
    ├── surface/primary: #FFFFFF
    ├── surface/secondary: #F8FAFC
    ├── text/primary: #0F172A
    └── ...
```

### Spacing Variables
```
Collection: Spacing
├── space/1: 4px
├── space/2: 8px
├── space/3: 12px
├── space/4: 16px
├── space/6: 24px
├── space/8: 32px
└── space/12: 48px
```

### Typography Styles
```
Text Styles:
├── heading/h1: Inter 36px/1.1 ExtraBold
├── heading/h2: Inter 30px/1.2 Bold
├── heading/h3: Inter 24px/1.3 SemiBold
├── heading/h4: Inter 20px/1.4 SemiBold
├── body/base: Inter 15px/1.6 Regular
├── body/sm: Inter 13px/1.5 Regular
├── body/xs: Inter 11px/1.5 Regular
├── code/base: JetBrains Mono 14px/1.7 Regular
└── code/sm: JetBrains Mono 12px/1.6 Regular
```

---

## Component Design Guidelines

### Naming Convention
- Use kebab-case with category prefix
- Format: `category/component-name/variant/state`
- Examples:
  - `primitive/button/primary/default`
  - `primitive/button/primary/hover`
  - `engineering/parameter-panel/expanded`
  - `layout/sidebar/collapsed`

### Component Properties
Each component should expose:
- **Size**: sm, md, lg (where applicable)
- **Variant**: primary, secondary, ghost, etc.
- **State**: default, hover, active, disabled, focus
- **Theme**: dark (default), light
- **Content**: text, icon, or both (using instance swap)

### Auto Layout
- All components must use auto layout
- Consistent padding and gap values from spacing tokens
- Hug contents by default, fill container when in layouts

---

## Responsive Variants

Design each screen at these breakpoints:

| Breakpoint | Width | Columns | Gutter | Margin |
|-----------|------:|:-------:|-------:|-------:|
| Mobile | 375px | 4 | 16px | 16px |
| Tablet | 768px | 8 | 24px | 32px |
| Desktop | 1280px | 12 | 24px | 40px |
| Wide | 1536px | 12 | 32px | 64px |

**Application UI (desktop only for V1):**
- Minimum viewport: 1024px wide
- Sidebar: 240px expanded, 48px collapsed
- Right panel: 300px default, 0px collapsed
- Bottom panel: 200px default, 0px collapsed

---

## Handoff Guidelines

### Developer Notes Format
Each screen should include annotations for:
1. Component names matching the component library
2. Spacing values (use token names, not pixel values)
3. Interaction notes (hover, click, keyboard)
4. Animation specifications (duration, easing)
5. Responsive behavior notes
6. Accessibility requirements (ARIA labels, focus order)

### Export Specifications
- Icons: SVG, 24x24 base, 1.5px stroke
- Illustrations: SVG (scalable)
- Screenshots: 2x resolution PNG
- Animations: Lottie JSON or CSS spec

### Version Control
- Use Figma branching for feature work
- Main branch = approved, production-ready designs
- Feature branches named: `feature/[screen-name]`
- Review process: designer → design review → merge to main
