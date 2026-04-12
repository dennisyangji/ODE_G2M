# ODE Visual Identity Brief

## Design Philosophy

ODE's visual identity follows the **Apple design tradition**: radical simplicity, typographic authority, premium whitespace, and cinematic imagery. We do not decorate — we reveal. We do not fill space — we command it.

The brief: if you showed a sophisticated engineer an ODE marketing page alongside an Apple product page, they should feel the same level of quality, intentionality, and confidence.

### Core Principles
1. **Premium Whitespace** — Space is not emptiness. It is the most powerful design element we have. Every layout should breathe.
2. **Typography Commands** — SF Pro at large scale says everything. Hero text needs no supporting imagery.
3. **Cinematic Imagery** — Product renders and engineering visualisations are cinema. Full-bleed, no borders, no drop shadows.
4. **Light is the Hero** — Light mode for all marketing, public, and pitch surfaces. Dark for the product tool itself.
5. **Precision without Decoration** — Apple does not add gradients to make things feel premium. The restraint IS the premium.

---

## Color Palette

### Primary Palette (Apple-inspired)

| Token | Hex | Usage |
|-------|-----|-------|
| `brand-midnight` | `#0A2540` | Primary brand colour, hero headlines, nav |
| `brand-accent` | `#0071E3` | CTAs, links, interactive states (Apple Blue) |
| `brand-accent-hover` | `#0077ED` | Hover state |
| `white` | `#FFFFFF` | Primary background (marketing) |
| `off-white` | `#F5F5F7` | Secondary background, section fills |
| `near-black` | `#1D1D1F` | Primary text (Apple standard) |
| `mid-grey` | `#6E6E73` | Secondary text, subheadings, captions |
| `light-grey` | `#D2D2D7` | Borders, dividers |
| `product-black` | `#000000` | Product UI base (dark mode) |
| `product-dark` | `#1C1C1E` | Product cards, panels |

### Semantic Colours (Engineering Contexts)

| State | Colour | Usage |
|-------|--------|-------|
| Success | `#34C759` (Apple green) | Simulation complete, valid |
| Warning | `#FF9F0A` (Apple orange) | Near limit, non-critical |
| Error | `#FF3B30` (Apple red) | Failed, invalid |
| AI Active | `#5E5CE6` (Apple indigo) | AI processing indicator |

### Data Visualisation Palette
For FEM stress maps, CFD flow fields, simulation charts:
```
Cool → Hot: #5AC8FA → #34C759 → #FFD60A → #FF9F0A → #FF3B30
Series: #0071E3 / #34C759 / #FF9F0A / #FF3B30 / #5E5CE6 / #5AC8FA
```

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

### Font Stack (Apple SF Pro System)

| Category | Font | Fallback | Usage |
|----------|------|----------|-------|
| **Display / Hero** | SF Pro Display | -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif | Hero headlines ≥ 40px |
| **UI / Body** | SF Pro Text | -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif | All body, UI, sub-40px |
| **Code / Engineering** | SF Mono | "JetBrains Mono", "Fira Code", Consolas, monospace | Modelica code, parameters, console |

**Web fallback strategy:** Use `-apple-system, BlinkMacSystemFont` as first fallback — native SF Pro on Apple devices, Inter/Helvetica on non-Apple. Do NOT load SF Pro from a CDN; the system font cascade handles it.

### Type Scale (Apple-aligned)

| Token | Size | Weight | Letter Spacing | Line Height | Usage |
|-------|------|--------|---------------|-------------|-------|
| `text-xs` | 11px | 400 | 0 | 1.5 | Labels, captions, legal |
| `text-sm` | 13px | 400 | 0 | 1.5 | Secondary text, metadata |
| `text-base` | 17px | 400 | 0 | 1.6 | Body text (Apple uses 17px as default) |
| `text-lg` | 19px | 400 | 0 | 1.5 | Emphasis body |
| `text-xl` | 21px | 600 | -0.01em | 1.4 | Sub-section headers |
| `text-2xl` | 28px | 600 | -0.02em | 1.3 | Section titles |
| `text-3xl` | 40px | 700 | -0.03em | 1.1 | Page titles, feature headlines |
| `text-4xl` | 56px | 700 | -0.04em | 1.05 | Hero sub-headlines |
| `text-5xl` | 80px | 700 | -0.05em | 1.0 | Hero super-headline (Apple scale) |
| `text-6xl` | 96px | 700 | -0.06em | 0.95 | Full-bleed hero text |
| `code-base` | 15px | 400 | 0 | 1.7 | SF Mono, code, parameters |

**Key principle:** Apple uses very tight letter-spacing (negative) at large sizes, and generous tracking at small sizes. This creates the distinctive "locked-in authority" of Apple display typography.

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

## Motion (Apple Timing)

| Token | Duration | Easing | Usage |
|-------|----------|--------|-------|
| `fast` | 200ms | ease-out | Hover, focus, toggle |
| `normal` | 300ms | ease-in-out | Panel transitions, tab switch |
| `slow` | 500ms | cubic-bezier(0.25, 0.1, 0.25, 1) | Modal, page transition |
| `spring` | 600ms | cubic-bezier(0.16, 1, 0.3, 1) | Sidebar, accordion expand |

Apple Motion Principle: **Purposeful deceleration.** Fast in, slow out. Things arrive with authority.

---

## Brand Misuse (Don't)

- Don't use dark mode on marketing/public surfaces (reserve dark for product UI)
- Don't use gradients as page backgrounds — whitespace is the premium signal
- Don't use rounded/bubbly fonts — SF Pro system stack only
- Don't use clip art, stock photos of engineers, or generic "AI" imagery (brains, circuits)
- Don't fill space with decorative elements — let engineering data and typography carry the page
- Don't use colours outside the defined Apple-inspired palette
- Don't add border-radius > 16px on large containers (too bubbly)
- Don't centre-align body copy blocks wider than 680px — left-aligned body text at scale reads as more authoritative
