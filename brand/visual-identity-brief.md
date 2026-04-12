# ODE Visual Identity Brief

## Design Philosophy

ODE's visual identity embodies **AI-native engineering**: intelligent, precise, forward-looking, and accessible. Every visual element should communicate that this is a next-generation platform — not a legacy tool with a fresh coat of paint.

### Core Principles
1. **Clarity First** — Engineering tools demand zero ambiguity. Every UI element has a clear purpose.
2. **Dark Mode Default** — Engineers spend hours in front of screens. Dark mode reduces eye strain and looks modern.
3. **Data-Dense, Not Cluttered** — Engineering dashboards need information density with visual hierarchy.
4. **AI-Forward Aesthetic** — Subtle visual cues that signal intelligence: smooth gradients, responsive animations, luminous accents.
5. **Professional Warmth** — Technical but not cold. Approachable but not playful.

---

## Color Palette

### Primary Colors

| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `primary-600` | `#4F46E5` (Indigo) | `#6366F1` | Primary actions, links, active states |
| `primary-500` | `#6366F1` | `#818CF8` | Hover states, secondary emphasis |
| `primary-700` | `#4338CA` | `#4F46E5` | Pressed states, strong emphasis |
| `primary-50` | `#EEF2FF` | `#1E1B4B` | Subtle backgrounds, badges |

### Secondary / Accent Colors

| Token | Value | Usage |
|-------|-------|-------|
| `accent-cyan` | `#06B6D4` | AI features, intelligence indicators, simulation data |
| `accent-violet` | `#8B5CF6` | Premium features, AI processing states |
| `accent-emerald` | `#10B981` | Success states, valid simulations, positive metrics |

### Neutral Palette (Slate)

| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `surface-primary` | `#FFFFFF` | `#0F172A` (slate-900) | Main background |
| `surface-secondary` | `#F8FAFC` | `#1E293B` (slate-800) | Cards, panels |
| `surface-tertiary` | `#F1F5F9` | `#334155` (slate-700) | Elevated surfaces |
| `border-default` | `#E2E8F0` | `#475569` (slate-600) | Borders, dividers |
| `text-primary` | `#0F172A` | `#F8FAFC` | Primary text |
| `text-secondary` | `#475569` | `#94A3B8` | Secondary text |
| `text-muted` | `#94A3B8` | `#64748B` | Disabled, placeholder text |

### Semantic Colors

| State | Color | Token |
|-------|-------|-------|
| Success | `#10B981` (Emerald) | Simulation complete, valid models |
| Warning | `#F59E0B` (Amber) | Approaching limits, non-critical issues |
| Error | `#EF4444` (Red) | Simulation failed, invalid parameters |
| Info | `#3B82F6` (Blue) | Informational, tips |

### Data Visualization Palette
For CAE results, charts, and simulation outputs:
```
Series 1: #6366F1 (Indigo)
Series 2: #06B6D4 (Cyan)
Series 3: #10B981 (Emerald)
Series 4: #F59E0B (Amber)
Series 5: #EF4444 (Red)
Series 6: #8B5CF6 (Violet)
Series 7: #EC4899 (Pink)
Series 8: #F97316 (Orange)
```

Gradient for continuous data (thermal, stress, flow):
```
Cool: #3B82F6 → #06B6D4 → #10B981 → #F59E0B → #EF4444 :Hot
```

---

## Typography

### Font Stack

| Category | Font | Fallback | Usage |
|----------|------|----------|-------|
| **UI / Headings** | Inter | system-ui, -apple-system, sans-serif | All UI text, headings, body |
| **Code / Engineering** | JetBrains Mono | Fira Code, Consolas, monospace | Modelica code, parameters, console |
| **Marketing / Display** | Inter (700-800 weight) | system-ui, sans-serif | Hero sections, landing page |

### Type Scale

| Token | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| `text-xs` | 11px | 400 | 1.5 | Labels, captions |
| `text-sm` | 13px | 400 | 1.5 | Secondary text, table data |
| `text-base` | 15px | 400 | 1.6 | Body text, form inputs |
| `text-lg` | 17px | 500 | 1.5 | Subheadings, emphasis |
| `text-xl` | 20px | 600 | 1.4 | Section headers |
| `text-2xl` | 24px | 600 | 1.3 | Page titles |
| `text-3xl` | 30px | 700 | 1.2 | Hero subheadings |
| `text-4xl` | 36px | 800 | 1.1 | Hero headlines |
| `text-5xl` | 48px | 800 | 1.1 | Landing page hero |
| `code-sm` | 12px | 400 | 1.6 | Inline code, small blocks |
| `code-base` | 14px | 400 | 1.7 | Code editor, Modelica |

---

## Logo

### Wordmark: "ODE"

**Direction:** Clean, geometric, minimal. The wordmark should feel mathematical and precise — honoring the acronym's dual meaning (Orthogonal Design Engineering + Ordinary Differential Equation).

**Guidelines:**
- Primary: "ODE" in custom geometric sans-serif (similar to Inter Black or custom)
- The "O" could subtly reference an engineering concept (a differential symbol, a coordinate axis, or an orbital path)
- Weight should feel substantial but not heavy
- Works at small sizes (favicon, mobile nav)

**Variations:**
| Variant | Usage |
|---------|-------|
| Full wordmark: "ODE" | Primary logo, headers, marketing |
| Icon: "O" mark | Favicon, app icon, small spaces |
| Lockup: "ODE" + "by Orthogonal" | First brand exposure, formal context |
| Inverted | Dark backgrounds |

**Clear Space:** Minimum clear space = height of the "O" on all sides

**Minimum Sizes:**
- Wordmark: 24px height (digital), 10mm (print)
- Icon: 16px (digital), 5mm (print)

**Color Usage:**
- On dark: White wordmark with optional indigo accent
- On light: Slate-900 wordmark with optional indigo accent
- Single color: Works in solid white or solid black

---

## Iconography

### Style
- **Type:** Line icons (not filled)
- **Stroke Width:** 1.5px at 24x24 canvas
- **Corners:** Rounded (2px radius)
- **Grid:** 24x24 base grid, 2px padding
- **Style:** Geometric, engineering-appropriate, consistent with Lucide or Phosphor

### Engineering-Specific Icons
Custom icons needed for:
- Modelica model / Component
- Simulation running / complete / failed
- 3D viewport / perspective
- Parameter panel
- System diagram / hierarchy
- FMI connection
- AI processing / co-pilot active
- Real-time collaboration indicator

---

## Imagery Style

### Product Screenshots
- Show real engineering workflows, not empty states
- Dark mode by default in all screenshots
- Highlight AI features with subtle cyan glow effects
- Data-rich: show simulation results, models, parameters

### Marketing Imagery
- Abstract: Geometric patterns, wave forms, differential equation curves
- Technical: Circuit-board-inspired patterns, mesh grids, node networks
- Avoid: Stock photos of engineers, generic "futuristic" imagery, excessive gradients
- Color treatment: Predominantly dark with indigo/cyan accents

### Photography (if needed)
- Candid, not staged
- Real engineering environments (labs, workshops, offices)
- Diverse representation
- Natural lighting, slightly desaturated to match brand palette

---

## Motion Design

### Principles
1. **Functional, not decorative** — Every animation serves a purpose
2. **Fast and responsive** — Users should never wait for animations
3. **Physically grounded** — Use easing curves that feel natural

### Timing

| Token | Duration | Easing | Usage |
|-------|----------|--------|-------|
| `transition-fast` | 150ms | ease-out | Hover, focus, toggle |
| `transition-normal` | 200ms | ease-in-out | Panel open/close, tab switch |
| `transition-slow` | 300ms | ease-in-out | Modal, page transition |
| `transition-expand` | 400ms | cubic-bezier(0.16, 1, 0.3, 1) | Sidebar expand, accordion |

### Specific Animations
- **AI Processing:** Subtle pulse animation on the AI indicator (cyan glow, 2s cycle)
- **Simulation Running:** Progress indicator with flowing gradient
- **Data Loading:** Skeleton screens, not spinners (for large datasets)
- **Panel Transitions:** Slide + fade, not just appear/disappear
- **3D Viewport:** Smooth camera transitions with momentum

### Reduced Motion
All animations must respect `prefers-reduced-motion: reduce`. When active:
- Remove all decorative animations
- Keep functional transitions but reduce to opacity changes only
- Maintain progress indicators (essential for simulation status)

---

## Layout Principles

### Spacing System
Based on 4px unit, primary intervals at 8px:
```
4px  — Tight: icon-text gap, inline elements
8px  — Compact: list items, form element gap
12px — Default: paragraph spacing, card padding (mobile)
16px — Comfortable: section padding, card padding (desktop)
24px — Generous: section gaps
32px — Spacious: major section breaks
48px — Page: top-level section separators
64px — Hero: landing page major sections
```

### Grid
- Marketing pages: 12-column grid, 1280px max width, 24px gutter
- Application UI: Flexible panels with resizable split panes
- Engineering dashboard: Dense grid with collapsible sidebars

### Z-Index Scale
```
z-base:      0     — Default content
z-raised:    10    — Cards, panels
z-dropdown:  100   — Dropdowns, select menus
z-sticky:    200   — Sticky headers, toolbars
z-modal:     300   — Modal overlays
z-popover:   400   — Popovers, tooltips
z-toast:     500   — Toast notifications
z-maximum:   999   — Loading overlays
```

---

## Application Contexts

### Landing Page / Marketing
- Large hero with product screenshot (dark mode)
- Generous whitespace
- Bold typography hierarchy
- Accent color highlights on key features
- Smooth scroll animations

### Engineering Dashboard
- Dense information display
- Collapsible panels (left: model tree, right: properties, bottom: console)
- Tabbed interface for multiple models/files
- Status bar at bottom (simulation status, AI status, collaboration)
- Keyboard-first navigation

### Simulation View
- Full-width 3D viewport
- Floating control panel
- Color-coded results overlay
- Timeline scrubber at bottom
- Split view option (3D + charts)

---

## Brand Misuse (Don't)

- Don't use light mode as default in product screenshots
- Don't use gradients as backgrounds (only for data visualization and subtle accents)
- Don't use rounded/bubble fonts — keep it geometric and precise
- Don't use clip art or cartoon illustrations
- Don't add excessive decorative elements — let the engineering data speak
- Don't use colors outside the defined palette
- Don't stretch or modify the logo proportions
- Don't place the logo on busy or low-contrast backgrounds
