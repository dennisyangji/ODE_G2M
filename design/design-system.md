# ODE Design System Specification

**Version:** 2.1 — Warm Neutral Marketing System
**Last Updated:** 2026-04-12  
**Platform:** Orthogonal ODE — The Dassault of the AI Era  
**Design Reference:** Warm neutral editorial system (Plus Jakarta Sans, cinematic white space, orange accent)

---

## 0. Design Philosophy

ODE's visual identity follows the same core principle: **the product is the message**. Every pixel of whitespace communicates confidence. Every typographic choice communicates precision. We do not decorate — we reveal.

> "Design is not just what it looks like and feels like. Design is how it works." — Steve Jobs

Applied to ODE: the interface should feel like a precision instrument, not a dashboard. Engineers should feel that using ODE is the same category of experience as using a premium editorial product — unmistakably high quality, unmistakably purposeful.

---

## 1. Design Principles

### 1.1 Radical Reduction (Apple: "Simplicity is the ultimate sophistication")
- Remove everything that does not carry meaning. A blank page is not emptiness — it is potential.
- Maximum content density per screen: 40%. The rest is intentional whitespace.
- If an element cannot be justified with a single sentence, it should not exist.

### 1.2 Typographic Hierarchy as Structure
- Plus Jakarta Sans does the heavy lifting for public and marketing surfaces. Typography IS the layout.
- Three weights maximum per screen: Light (body), Regular (UI), Semibold (emphasis).
- Numerical values: always monospaced, always right-aligned, always with units.

### 1.3 Cinematic Imagery
- Engineering renders are photography, not illustrations. Treat them accordingly.
- Full-bleed images on marketing surfaces. No borders, no drop shadows on imagery.
- Dark and light modes must both feel intentional, not just inverted.

### 1.4 Precision
- 8pt base grid. Pixel-perfect. No "close enough."
- Visual feedback is immediate and deterministic — engineers must trust what the UI reports.
- AI-generated content is visually distinct from user-authored content (subtle tint, not a banner).

### 1.5 Accessibility
- WCAG 2.1 AA compliance minimum.
- Keyboard-first interaction model.
- Color is never the sole indicator of meaning.

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

### 3.0 Warm Neutral Colour Philosophy

Light is the default marketing mode. Dark is the default product mode. Both must feel equally intentional - not a palette swap.

**Brand Palette:**

| Token | Hex | Usage |
|-------|-----|-------|
| `brand-ink` | `#0A0A09` | Primary brand, hero text, nav |
| `brand-accent` | `#FF5C3A` | CTAs, links, interactive elements |
| `brand-accent-hover` | `#FF7255` | Hover state on accent |
| `surface-base` | `#F7F5F0` | Primary background (light) |
| `surface-raised` | `#EFECE7` | Secondary background / cards |
| `text-primary` | `#0A0A09` | Primary text (light mode) |
| `text-secondary` | `#3C3A36` | Secondary text, captions |
| `border-default` | `#D7D2C8` | Dividers, borders |

### 3.1 Light Mode (Default for Marketing + Public Surfaces)

Light is the hero mode for product marketing. ODE follows this for all public-facing surfaces (website, landing pages, pitch deck, email).

- **Surface hierarchy (light):**
  - `surface-base`: `#F7F5F0` - primary background
  - `surface-raised`: `#EFECE7` - cards, hero sections
  - `surface-overlay`: `#FFFFFF` with shadow `0 2px 8px rgba(0,0,0,0.08)`
  - `surface-subtle`: `#E8E4DC` - hover states, subtle fills
- **Text on light surfaces:**
  - `text-primary`: `#0A0A09`
  - `text-secondary`: `#3C3A36`
  - `text-tertiary`: `#8E8980`
  - `text-disabled`: `#B8B3A8`

### 3.2 Dark Mode (Default for Product UI)

Engineers spend extended hours in the platform; dark surfaces reduce eye strain and align with the engineering tool aesthetic.

- **Surface hierarchy (dark):**
  - `surface-base`: `#0A0A09` - near black
  - `surface-raised`: `#1A1916` - cards, panels
  - `surface-overlay`: `#2E2C28` - dropdowns, dialogs
  - `surface-subtle`: `#3A3733` - hover states, dividers
- **Text on dark surfaces:**
  - `text-primary`: `#F7F5F0`
  - `text-secondary`: `#C8C3BB`
  - `text-tertiary`: `#8E8980`
  - `text-disabled`: `#585450`

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
