# Component Patterns

## Overview

This document defines the shared patterns that all design system components must follow. These patterns ensure consistency, accessibility, and predictable behavior across the component library.

## Anatomy of a Component

Every component follows this structure:
1. **Container** — Wraps the component, handles layout
2. **Label** — Describes the component's purpose
3. **Interactive area** — Where the user interacts
4. **Feedback** — Visual response to interaction (hover, focus, error)
5. **Help text** — Additional context or error messages

## State Management

All interactive components support these states:
- **Default** — Resting state
- **Hover** — Mouse over (desktop only)
- **Focus** — Keyboard focus with visible indicator
- **Active** — Being clicked/pressed
- **Disabled** — Non-interactive, reduced opacity (0.5)
- **Error** — Invalid input, red border + error message
- **Loading** — Spinner replaces content or shows overlay

## Variant System

Components use a consistent variant naming:
- `primary` — High emphasis actions
- `secondary` — Medium emphasis actions
- `ghost` — Low emphasis, no background
- `danger` — Destructive actions (red)

## Size System

Three sizes for all components:
- `sm` — Compact UIs, dense data tables
- `md` — Default size for most contexts
- `lg` — Touch-friendly, high-emphasis areas

## Dark Mode

All components must render correctly in both light and dark modes. Use design tokens (CSS custom properties) instead of hardcoded colors. Reference the [Color Palette](../colors.md) for token definitions.
