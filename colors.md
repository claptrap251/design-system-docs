# Color Palette

## Brand Colors

Our design system uses a semantic color palette that maps intent to specific values.

### Primary
- **Blue 500** `#3B82F6` — Primary actions, links, focus rings
- **Blue 600** `#2563EB` — Primary hover states
- **Blue 700** `#1D4ED8` — Primary active/pressed states

### Secondary
- **Purple 500** `#8B5CF6` — Secondary actions, accents
- **Purple 600** `#7C3AED` — Secondary hover states

### Semantic
- **Success** `#10B981` — Confirmations, positive states
- **Warning** `#F59E0B` — Caution states, pending actions
- **Error** `#EF4444` — Destructive actions, validation errors
- **Info** `#3B82F6` — Informational messages

## Dark Mode

All colors have dark mode equivalents. Use CSS custom properties for automatic switching. The design system provides `--color-primary`, `--color-secondary`, etc. that resolve to the correct value based on the active theme.

## Contrast Requirements

All text colors must meet WCAG 2.1 AA contrast ratios:
- Body text: minimum 4.5:1
- Large text (18px+): minimum 3:1
- UI components and focus indicators: minimum 3:1
