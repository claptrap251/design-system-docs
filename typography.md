# Typography System

## Font Stack

### Primary: Inter
Used for all UI text — headings, body, labels, buttons.
- Weights: 400 (Regular), 500 (Medium), 600 (Semibold), 700 (Bold)
- Load via Google Fonts or self-host the variable font

### Monospace: JetBrains Mono
Used for code blocks, data tables, and technical content.
- Weights: 400, 500

## Type Scale

Based on a 1.25 ratio (Major Third):

| Token | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| `display` | 48px | Bold | 1.1 | Hero sections |
| `h1` | 36px | Bold | 1.2 | Page titles |
| `h2` | 28px | Semibold | 1.3 | Section headers |
| `h3` | 22px | Semibold | 1.3 | Subsections |
| `h4` | 18px | Medium | 1.4 | Card titles |
| `body-lg` | 16px | Regular | 1.6 | Primary content |
| `body-sm` | 14px | Regular | 1.5 | Secondary content |
| `caption` | 12px | Medium | 1.4 | Labels, metadata |

## Responsive Behavior

- Scale down one step on viewports below 768px
- Minimum body text size: 16px (prevents iOS zoom on focus)
- Maximum line length: 75 characters for readability
