# ODE Design System Specification

**Version:** 1.0
**Last Updated:** 2026-04-12
**Platform:** ODE - AI-Native Engineering Platform

---

## 1. Design Principles

### 1.1 Clarity
- Every element serves a purpose. Remove visual noise so engineers can focus on their work.
- Information hierarchy is immediately obvious through typography, spacing, and contrast.
- Labels, units, and statuses are always explicit, never ambiguous.

### 1.2 Precision
- Pixel-perfect alignment to the base grid. No "close enough."
- Numerical values are displayed with appropriate significant figures.
- Visual feedback is immediate and deterministic -- engineers must trust what the UI reports.

### 1.3 Intelligence
- The interface anticipates user needs through context-aware suggestions and smart defaults.
- AI-generated content and recommendations are visually distinct from user-authored content.
- Progressive disclosure: show what matters now, make everything else accessible on demand.

### 1.4 Accessibility
- WCAG 2.1 AA compliance is the minimum bar, not the goal.
- Keyboard-first interaction model -- every action reachable without a mouse.
- Color is never the sole indicator of meaning; always pair with shape, text, or iconography.

---

## 2. Grid System

### 2.1 Base Grid
- **Base unit:** 8px
- All spatial values (margins, padding, sizing) are multiples of 8px.
- For fine-grained adjustments (icon alignment, border offsets), 4px half-grid increments are permitted.

### 2.2 Column Grid
- **Columns:** 12
- **Gutter:** 24px (3 base units)
- **Margin (outer):** 24px minimum on mobile, 48px on desktop and above.

### 2.3 Breakpoints

| Name       | Min Width | Columns | Gutter | Outer Margin |
|------------|-----------|---------|--------|--------------|
| Mobile     | 0px       | 4       | 16px   | 16px         |
| Tablet     | 768px     | 8       | 24px   | 24px         |
| Desktop    | 1024px    | 12      | 24px   | 48px         |
| Wide       | 1280px    | 12      | 32px   | 48px         |
| Ultra-wide | 1536px    | 12      | 32px   | 64px         |

The `640px` value is used as a content breakpoint for internal component reflow (e.g., stacking parameter panels) even when the viewport itself is wider -- this supports embedded panels and split-pane layouts where available width is less than the viewport.

---

## 3. Color Modes

### 3.1 Dark Mode (Default)
Dark mode is the default for ODE. Engineers spend extended hours in the platform; a dark surface reduces eye strain, improves focus, and is the de facto standard in engineering and development tools.

- **Surface hierarchy (dark):**
  - `surface-base`: slate-950 (#020617) -- application background
  - `surface-raised`: slate-900 (#0F172A) -- cards, panels
  - `surface-overlay`: slate-800 (#1E293B) -- dropdowns, dialogs
  - `surface-subtle`: slate-700 (#334155) -- hover states, dividers
- **Text on dark surfaces:**
  - `text-primary`: slate-50 (#F8FAFC)
  - `text-secondary`: slate-400 (#94A3B8)
  - `text-tertiary`: slate-500 (#64748B)
  - `text-disabled`: slate-600 (#475569)

### 3.2 Light Mode (Secondary)
Provided for user preference and presentation contexts.

- **Surface hierarchy (light):**
  - `surface-base`: white (#FFFFFF)
  - `surface-raised`: slate-50 (#F8FAFC)
  - `surface-overlay`: white (#FFFFFF) with shadow
  - `surface-subtle`: slate-100 (#F1F5F9)
- **Text on light surfaces:**
  - `text-primary`: slate-900 (#0F172A)
  - `text-secondary`: slate-600 (#475569)
  - `text-tertiary`: slate-500 (#64748B)
  - `text-disabled`: slate-400 (#94A3B8)

### 3.3 Mode Switching
- Respect `prefers-color-scheme` on first visit.
- Persist user preference in local storage.
- Transition between modes with a 200ms cross-fade on the `background-color` and `color` properties to avoid flash.

---

## 4. Layout Patterns

### 4.1 Engineering Dashboard
- **Structure:** Fixed sidebar (240px collapsed to 56px) + header (56px) + main content area.
- **Main content:** 12-column grid for widget placement.
- **Widgets:** Cards on the base grid, minimum 2-column span, resizable in 1-column increments.
- **Behavior:** Widgets reflow into fewer columns as breakpoint decreases. Below tablet, sidebar becomes a drawer overlay.

### 4.2 Simulation Viewer
- **Structure:** Full-bleed 3D viewport with floating overlay panels.
- **Overlay panels:** Semi-transparent dark background (slate-900/90), positioned at edges, collapsible.
- **Controls:** Bottom toolbar for playback (play, pause, step, speed), timeline scrubber.
- **Responsive:** On mobile, panels stack vertically below the viewport. Viewport maintains 16:9 minimum aspect ratio.

### 4.3 Parameter Panel
- **Structure:** Vertical scrolling panel, typically 320px wide in a side position.
- **Organization:** Grouped by category with collapsible sections.
- **Controls:** Labeled inputs with units, inline validation, real-time preview feedback.
- **Responsive:** On narrow viewports, parameter panel becomes a bottom sheet (50% height, draggable to full).

### 4.4 Code Editor (Modelica)
- **Structure:** Full-width editor with optional side panels (file tree left, output/console bottom).
- **Typography:** JetBrains Mono, 14px default, configurable 10-20px.
- **Line numbers:** Always visible. Gutter accommodates breakpoints, diagnostics, and fold controls.
- **Split views:** Horizontal and vertical splits supported. Minimum pane width: 320px.
- **Responsive:** On mobile, file tree becomes a slide-over, output panel becomes a swipe-up sheet.

---

## 5. Responsive Behavior for Complex Engineering UI

### 5.1 Principles
- Never hide critical engineering data -- rearrange, reflow, or provide an alternative view.
- Tables become horizontally scrollable with frozen key columns, never collapsed into cards (data fidelity matters).
- Charts maintain aspect ratios; legends move from side to bottom below 768px.
- 3D viewports never shrink below 300x200px; surrounding panels collapse first.

### 5.2 Split Pane Strategy
- Desktop/Wide: Multi-pane layouts (2-3 panes visible simultaneously).
- Tablet: Maximum 2 panes; tertiary panes become tabs or overlays.
- Mobile: Single pane with navigation to switch between views.

### 5.3 Touch Adaptations
- Minimum touch target: 44x44px.
- Sliders and scrubbers gain larger hit areas on touch devices.
- Right-click context menus become long-press menus.
- Pinch-to-zoom for 3D viewport and charts.

---

## 6. Animation Principles

### 6.1 Functional Transitions Only
Animations in ODE are tools, not decoration. Every animation must serve at least one of these purposes:
- **Orientation:** Help the user understand where they are (e.g., panel sliding in from the side it is anchored to).
- **Feedback:** Confirm an action was received (e.g., button press state, toast appearing).
- **Continuity:** Maintain spatial awareness during layout changes (e.g., element reflow).

### 6.2 Duration Guidelines

| Category              | Duration | Easing                | Example                          |
|-----------------------|----------|-----------------------|----------------------------------|
| Micro-interaction     | 150ms    | ease-out              | Button state, toggle, checkbox   |
| Panel transition      | 200ms    | ease-in-out           | Sidebar expand/collapse          |
| Page/view transition  | 300ms    | ease-in-out           | Route change, modal open/close   |
| Data loading skeleton | 1500ms   | linear (pulse)        | Skeleton shimmer                 |

### 6.3 Reduced Motion
- Honor `prefers-reduced-motion: reduce`.
- When reduced motion is active, replace all transitions with instant state changes (0ms duration).
- Loading indicators switch from animated spinners to static progress indicators.

### 6.4 Performance Guardrails
- Only animate `transform` and `opacity` to stay on the compositor thread.
- No animation on elements with more than 50 descendants.
- Pause animations when the tab is not visible (`document.hidden`).
- 3D viewport animations (camera transitions, exploded views) use requestAnimationFrame and target 60fps.
