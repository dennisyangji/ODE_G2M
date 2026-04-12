# ODE Component Library

## Overview

ODE's component library is built on **shadcn/ui + Tailwind CSS v4**, extended with engineering-specific components. Dark mode is the default theme.

---

## Primitives

### Button
| Variant | Usage | Keyboard |
|---------|-------|----------|
| **Primary** | Main actions (Run Simulation, Create Model) | Enter |
| **Secondary** | Supporting actions (Export, Share) | - |
| **Ghost** | Toolbar actions, low emphasis | - |
| **Danger** | Destructive actions (Delete, Reset) | - |

Sizes: `sm` (28px), `md` (36px), `lg` (44px)
States: default, hover, active, disabled, loading, focus (2px indigo ring)

### Input
Text, number (with unit suffix), search (with icon), password
States: default, focus, error, disabled
Validation: inline error message below, red border on error

### Select / Dropdown
Single select, multi-select, searchable, grouped options
Engineering use: unit selector, material picker, solver options

### Toggle / Switch
On/off binary control. Used for: dark mode, feature flags, simulation options

### Slider
Single value, range. With numeric input for precision.
Engineering use: parameter exploration, tolerance ranges

---

## Layout Components

### Card
Elevated surface for grouping related content.
Variants: default, interactive (hover effect), selected, compact

### Panel
Resizable container within split layouts.
Props: collapsible, min/max width, drag handle

### SplitPane
Horizontal or vertical split with draggable divider.
Engineering layout: left (model tree) | center (viewport) | right (properties)
Bottom panel for console/output

### Tabs
Horizontal tab bar for switching contexts.
Variants: underline (default), pill, vertical
Engineering use: file tabs (like IDE), property group tabs

### Sidebar
Collapsible navigation panel (left side).
States: expanded (240px), collapsed (48px icons only), hidden
Keyboard: Cmd+B to toggle

### Toolbar
Horizontal action bar at top of work area.
Contains: tool buttons, dropdowns, separators, search
Fixed position, scrolls with content below

### StatusBar
Bottom bar showing system state.
Sections: simulation status | AI status | collaboration users | zoom level | notifications

---

## Feedback Components

### Toast
Non-blocking notification at bottom-right.
Types: success (green), error (red), warning (amber), info (blue)
Auto-dismiss: 5 seconds (configurable)
Action button optional ("Undo", "View Details")

### Alert
In-page persistent message.
Types: info, success, warning, error
Dismissible with X button

### Dialog / Modal
Centered overlay for important actions.
Sizes: sm (400px), md (560px), lg (720px), full
Always include: title, close button (X + Escape key), primary action

### Tooltip
Hover/focus information popup.
Delay: 500ms show, 0ms hide
Position: auto (prefers top)
Engineering use: parameter descriptions, unit info, formula preview

### Progress
**Bar**: Linear progress for file uploads, simulation progress (0-100%)
**Circular**: Indeterminate spinner for AI processing
**Stepped**: Multi-step wizard progress (onboarding, export)

### Skeleton
Loading placeholder matching content shape.
Used for: model tree loading, simulation results loading, dashboard widgets

---

## Data Display

### Table
Sortable, filterable, paginated data table.
Features: column resize, row selection, export, sticky header
Engineering use: parameter lists, simulation results comparison

### DataGrid
High-performance table for large datasets (1000+ rows).
Features: virtual scrolling, cell editing, column pinning
Engineering use: time-series data, mesh results

### Badge / Tag
Small label for status or category.
Variants: solid, outline. Sizes: sm, md
Engineering use: model status (valid/invalid), physics domain labels

### Stat
Large number with label and trend indicator.
Engineering use: dashboard KPIs, simulation metrics

---

## Engineering-Specific Components

### ParameterPanel
Name-value pairs with units, organized by group.

```
[Group: Thermal Properties]
  Conductivity    [0.5   ] W/(m·K)  [?]
  Specific Heat   [4186  ] J/(kg·K) [?]
  Density         [998   ] kg/m³    [?]
  
[Group: Boundary Conditions]
  Inlet Temp      [293.15] K        [?]
  Flow Rate       [0.01  ] kg/s     [?]
```

Features: inline editing, unit conversion, reset to default, parameter linking
Keyboard: Tab between fields, Enter to confirm, Escape to cancel

### SimulationControl
Transport-style controls for simulation execution.

```
[▶ Run] [⏸ Pause] [⏹ Stop] [⏭ Step] | Time: 0.0s → 10.0s | Step: 0.001s | [Progress ████░░ 67%]
```

States: idle, running, paused, completed, failed, queued

### ViewportFrame
Container for 3D visualization canvas (WebGL/Three.js).

Features: orbit/pan/zoom controls, view cube, background grid, axis indicator
Toolbar: perspective/orthographic toggle, view presets (front/top/iso), screenshot
Accessibility: Text description of scene, keyboard navigation for view presets

### ModelTree
Hierarchical tree view of model components.

```
▼ HeatExchanger
  ▼ ThermalCircuit
    ● HotFluid (FluidPort)
    ● ColdFluid (FluidPort)
    ● WallConduction (ThermalConductor)
  ▶ Controller
  ▶ Sensors
```

Features: expand/collapse, drag-and-drop reorder, context menu, search/filter, multi-select
Icons: component type indicators, status badges (valid/error/warning)

### PropertyInspector
Right panel showing selected object properties.

Sections: Identity (name, type), Parameters (editable), Connections (ports), Documentation
Tabs for different property groups
Linked to ModelTree selection

### ConsoleOutput
Terminal-style output panel for logs and AI responses.

```
[12:34:56] Simulation started: HeatExchanger
[12:34:57] Solver: DASSL, tolerance: 1e-6
[12:35:02] ✓ Simulation completed (5.2s, 1,247 steps)
[12:35:02] AI: Maximum temperature reached 352K at t=4.2s. Consider increasing cooling flow rate.
```

Features: log levels (info/warn/error), timestamp, copy, clear, search, filter
Auto-scroll with pause on user scroll-up

### Timeline
Horizontal timeline for simulation time navigation.

```
|◄──────────●──────────────────────►|
0s          4.2s                   10s
```

Features: scrub, zoom, keyframe markers (events), region select for analysis

### CodeEditor
Monaco-based editor with Modelica syntax highlighting.

Features: syntax highlighting, auto-complete, error markers, fold regions, minimap
AI integration: inline suggestions, "Generate" button, "Explain" hover
Keyboard: Standard editor shortcuts + Cmd+Enter to run

---

## Navigation

### CommandPalette (Cmd+K)
Global search and action palette.
Categories: Files, Commands, Components, Settings, AI Actions
Fuzzy search, keyboard navigation, recent items

### Breadcrumb
Path indicator for nested navigation.
Format: Workspace > Project > Model > Component
Clickable segments, dropdown for siblings

### SideNav
Primary navigation (left sidebar).
Items: Projects, Templates, AI Chat, Documentation, Settings
Collapsible to icon-only mode
