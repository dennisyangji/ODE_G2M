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

### Color Variables (Figma Variables → CSS tokens)
```
Collection: Colors
├── Mode: Light (Marketing default)
│   ├── brand/midnight:  #0A2540
│   ├── brand/accent:    #0071E3
│   ├── bg/primary:      #FFFFFF
│   ├── bg/secondary:    #F5F5F7
│   ├── text/primary:    #1D1D1F
│   ├── text/secondary:  #6E6E73
│   ├── border/default:  #D2D2D7
│   └── ...
└── Mode: Dark (Product UI default)
    ├── bg/primary:      #000000
    ├── bg/secondary:    #1C1C1E
    ├── bg/tertiary:     #2C2C2E
    ├── text/primary:    #F5F5F7
    ├── text/secondary:  #AEAEB2
    ├── border/default:  #3A3A3C
    └── ...
```

### Spacing Variables (8pt grid)
```
Collection: Spacing
├── space/1:  4px
├── space/2:  8px
├── space/3:  12px
├── space/4:  16px
├── space/6:  24px
├── space/8:  32px
├── space/12: 48px
├── space/16: 64px
└── space/20: 80px
```

### Typography Styles (SF Pro System)
```
Text Styles:
├── display/hero:    SF Pro Display 96px/-0.06em Bold
├── display/xl:      SF Pro Display 80px/-0.05em Bold
├── display/lg:      SF Pro Display 56px/-0.04em Bold
├── heading/h1:      SF Pro Display 40px/-0.03em Bold
├── heading/h2:      SF Pro Display 28px/-0.02em SemiBold
├── heading/h3:      SF Pro Text   21px/-0.01em SemiBold
├── body/base:       SF Pro Text   17px/0      Regular   (Apple standard)
├── body/sm:         SF Pro Text   13px/0      Regular
├── body/xs:         SF Pro Text   11px/+0.01  Regular
├── code/base:       SF Mono       15px/0      Regular
└── code/sm:         SF Mono       13px/0      Regular
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

## Design Workstation: Figma + Claude Code

**No design handoff. Designer IS the code generator.**

```
Figma (visual truth)
  → Claude Code reads Figma specs / DESIGN.md
  → Outputs production-ready code directly
  → No separate developer translation needed
```

### Workflow

| Step | Tool | Output |
|------|------|--------|
| 1. Visual design | Figma | Screens, components, tokens |
| 2. Token export | Figma Variables → JSON | `design-tokens.json` |
| 3. Code generation | Claude Code + DESIGN.md | `design-tokens.css`, `tailwind.config.ts`, `components.tsx` |
| 4. Review | Designer reviews code output | Confirm visual match |
| 5. Ship | Frontend integrates files | Production code, no re-work |

### Claude Code Prompt Patterns (Designer uses these)

```
# Generate component from Figma spec
"Generate a React button component using our design tokens.
Variants: primary, secondary, ghost, danger.
Sizes: sm (28px), md (36px), lg (44px).
Use Tailwind + cva. Match the Apple design system in DESIGN.md."

# Update tokens after Figma changes
"Update design-tokens.css: change --color-brand-accent from
#0071E3 to #0066CC. Propagate to tailwind.config.ts."

# Generate full page from wireframe description
"Build the pricing page layout using our component library.
Three tiers: Free, Pro $99, Team $199/seat.
Apple-style: off-white background, SF Pro, minimal.
Token consumption chart below each tier."
```

### File Ownership

| File | Owner | Source of truth |
|------|-------|----------------|
| `design/design-tokens.css` | Designer → Claude Code | Figma Variables |
| `design/tailwind.config.ts` | Designer → Claude Code | design-tokens.css |
| `design/components.tsx` | Designer → Claude Code | Figma Components |
| `design/figma-brief.md` | Designer | Figma file structure |
| Figma file | Designer | Visual reference |

### Version Control
- Figma: branch per feature (`feature/pricing-page-v2`)
- Code: PR per design system update (`design: update token accent colour`)
- Designer commits design system code directly to `design/` branch
