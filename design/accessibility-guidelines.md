# ODE Accessibility Guidelines (WCAG 2.1 AA)

## Overview

ODE is committed to WCAG 2.1 Level AA compliance. Engineering tools have unique accessibility challenges — complex visualizations, dense data, and precision inputs — that require thoughtful solutions.

---

## Color & Contrast

### Minimum Contrast Ratios

| Element | Ratio | Standard |
|---------|------:|----------|
| Normal text (<18px) | 4.5:1 | WCAG AA |
| Large text (>=18px or >=14px bold) | 3:1 | WCAG AA |
| UI components (buttons, inputs, icons) | 3:1 | WCAG AA |
| Focus indicators | 3:1 | WCAG AA |
| Decorative elements | No requirement | - |

### Dark Mode Compliance

| Combination | Foreground | Background | Ratio | Pass? |
|------------|-----------|-----------|------:|:-----:|
| Primary text | #F8FAFC | #0F172A | 15.4:1 | Yes |
| Secondary text | #94A3B8 | #0F172A | 6.1:1 | Yes |
| Muted text | #64748B | #0F172A | 3.8:1 | Yes (large) |
| Primary on surface | #818CF8 | #1E293B | 5.2:1 | Yes |
| Error text | #FCA5A5 | #0F172A | 8.4:1 | Yes |

### Color-Blind Safe Visualization

Data visualization must not rely on color alone. Use:
- Different shapes (circle, square, triangle) for data series
- Pattern fills in addition to colors
- Direct labels where possible
- Color-blind safe palette: Blue (#3B82F6), Orange (#F97316), Teal (#14B8A6), Red (#EF4444), Purple (#8B5CF6)

Test with: Deuteranopia, Protanopia, Tritanopia simulations

---

## Keyboard Navigation

### Global Shortcuts

| Shortcut | Action |
|----------|--------|
| `Cmd+K` | Open command palette |
| `Cmd+B` | Toggle sidebar |
| `Cmd+\` | Toggle right panel |
| `Cmd+J` | Toggle bottom panel |
| `Cmd+Enter` | Run simulation |
| `Cmd+S` | Save |
| `Tab` | Move focus to next interactive element |
| `Shift+Tab` | Move focus to previous element |
| `Escape` | Close modal/panel, deselect |
| `F1` | Help |

### Focus Management

**Focus Indicators:**
- 2px solid ring, `#6366F1` (indigo-500), 2px offset
- Must be visible on all backgrounds (dark and light)
- Never remove focus indicators (`outline: none` is prohibited)

**Tab Order:**
1. Skip-to-content link (first focusable element)
2. Main navigation (sidebar)
3. Toolbar actions
4. Primary content area
5. Secondary panels (right, bottom)
6. Modals trap focus until dismissed

**Focus Trapping:**
- Modals and dialogs trap focus within them
- `Escape` always closes and returns focus to trigger element
- Command palette traps focus, `Escape` to close

### Engineering-Specific Keyboard Navigation

**Code Editor (Monaco):**
- Standard editor shortcuts (Cmd+C, Cmd+V, etc.)
- `Cmd+Enter` to run/simulate
- `Ctrl+Space` for autocomplete
- `F2` to rename symbol
- `Cmd+Shift+P` for editor command palette

**Model Tree:**
- Arrow keys: navigate up/down
- Right arrow: expand node
- Left arrow: collapse node
- Enter: select/edit node
- Delete: remove node (with confirmation)

**3D Viewport (when focused):**
- Arrow keys: rotate view
- `+`/`-`: zoom in/out
- `Home`: reset to default view
- `1-6`: preset views (front, back, left, right, top, bottom)
- `0`: isometric view

---

## Screen Reader Support

### ARIA Landmarks

```html
<header role="banner">           <!-- Top toolbar -->
<nav role="navigation">          <!-- Sidebar -->
<main role="main">               <!-- Primary content area -->
<aside role="complementary">     <!-- Property panel -->
<footer role="contentinfo">      <!-- Status bar -->
```

### Live Regions

Use `aria-live` for dynamic content updates:

| Region | aria-live | Content |
|--------|-----------|---------|
| Simulation status | `assertive` | "Simulation started", "Simulation completed in 5.2s" |
| AI responses | `polite` | "AI generated a model with 5 components" |
| Toast notifications | `polite` | "File saved successfully" |
| Error messages | `assertive` | "Simulation failed: solver convergence error" |
| Progress updates | `polite` | "Simulation 67% complete" |

### Component ARIA Patterns

**Parameter Panel:**
```html
<div role="form" aria-label="Thermal Properties">
  <label for="conductivity">Conductivity</label>
  <input id="conductivity" type="number" aria-describedby="conductivity-unit">
  <span id="conductivity-unit">W/(m·K)</span>
</div>
```

**Model Tree:**
```html
<ul role="tree" aria-label="Model components">
  <li role="treeitem" aria-expanded="true" aria-level="1">
    HeatExchanger
    <ul role="group">
      <li role="treeitem" aria-level="2">HotFluid</li>
    </ul>
  </li>
</ul>
```

**Simulation Control:**
```html
<div role="toolbar" aria-label="Simulation controls">
  <button aria-label="Run simulation">▶</button>
  <button aria-label="Pause simulation" aria-disabled="true">⏸</button>
  <div role="progressbar" aria-valuenow="67" aria-valuemin="0" aria-valuemax="100"
       aria-label="Simulation progress">67%</div>
</div>
```

**3D Viewport:**
```html
<div role="img" aria-label="3D visualization of heat exchanger model showing temperature distribution from 293K (blue) to 352K (red)">
  <canvas><!-- WebGL content --></canvas>
</div>
<!-- Text alternative panel (toggleable) -->
<details>
  <summary>Scene Description</summary>
  <p>Heat exchanger model with hot fluid inlet (left, 352K) and cold fluid inlet (right, 293K). Temperature gradient shown across wall conduction element.</p>
</details>
```

---

## Forms & Inputs

### Requirements
- Every input must have a visible `<label>` (not placeholder-only)
- Required fields: asterisk (*) + `aria-required="true"`
- Error messages: visible text below field + `aria-describedby` linking
- Group related fields with `<fieldset>` and `<legend>`
- Submit buttons must clearly state the action ("Save Parameters", not just "Submit")

### Error Handling
- Show errors inline, below the specific field
- Use both color AND icon to indicate errors (not color alone)
- Announce errors to screen readers via `aria-live="assertive"`
- Don't clear user input on error — let them fix in place

---

## Motion & Animation

### Reduced Motion Support

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

**What to keep with reduced motion:**
- Progress indicators (essential for simulation status)
- Opacity transitions (instant, but still show state change)

**What to remove:**
- Decorative animations
- Sliding transitions
- AI processing pulse effect
- Viewport camera animations (use instant cut)

---

## Touch & Pointer

### Minimum Target Sizes
- Interactive elements: 44x44px minimum touch target
- Dense UI (toolbars): 36x36px with 8px spacing between targets
- Links in text: ensure sufficient line height (1.5+) for tap targets

---

## Testing Checklist

### Automated Testing
- [ ] axe-core: Run on all pages, zero critical/serious violations
- [ ] Lighthouse accessibility: Score >90
- [ ] eslint-plugin-jsx-a11y: Zero warnings in codebase

### Manual Testing
- [ ] Keyboard-only navigation: Complete all core workflows without mouse
- [ ] Screen reader: VoiceOver (macOS) + NVDA (Windows) for all screens
- [ ] Zoom: Content readable at 200% zoom
- [ ] High contrast: Windows High Contrast mode compatible
- [ ] Reduced motion: All animations respect preference
- [ ] Color-blind: Simulation of deuteranopia, protanopia, tritanopia
- [ ] Focus order: Logical tab sequence on all screens

### Engineering-Specific Testing
- [ ] 3D viewport: Accessible description available
- [ ] Data tables: Keyboard navigable (arrow keys between cells)
- [ ] Charts: Text alternatives for all visualizations
- [ ] Simulation controls: Operable via keyboard + screen reader
- [ ] Parameter editing: Keyboard-only value entry with unit awareness
- [ ] Model tree: Full tree navigation via keyboard
- [ ] Console output: Screen reader announces new entries

### Tools
| Tool | Purpose | Frequency |
|------|---------|-----------|
| axe DevTools | Automated page audit | Every PR |
| Lighthouse CI | Automated scoring | Every deploy |
| VoiceOver | macOS screen reader testing | Monthly |
| NVDA | Windows screen reader testing | Monthly |
| Color Oracle | Color blindness simulation | Per design review |
| Stark (Figma) | Contrast checking in design | Per component |
