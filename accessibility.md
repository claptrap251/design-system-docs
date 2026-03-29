# Accessibility Standards

## Commitment

All components in the design system must meet WCAG 2.1 Level AA compliance. This is non-negotiable for any component entering the system.

## Color & Contrast

- All text meets minimum contrast ratios (see [Color Palette](colors.md))
- Never use color as the only means of conveying information
- Provide visual indicators beyond color (icons, patterns, text labels)

## Keyboard Navigation

- All interactive elements must be keyboard accessible
- Focus order follows visual reading order
- Focus indicators must be visible (minimum 3:1 contrast, 2px outline)
- No keyboard traps — users can always Tab away from a component

## Screen Readers

- All images require descriptive `alt` text
- Form inputs have associated `<label>` elements
- Use ARIA landmarks for page structure
- Dynamic content changes announced via `aria-live` regions
- Decorative elements use `aria-hidden="true"`

## Motion & Animation

- Respect `prefers-reduced-motion` system setting
- No auto-playing animations that can't be paused
- Provide static alternatives for animated content
- Keep animations under 5 seconds or provide stop controls

## Touch Targets

- Minimum size: 44x44px for all interactive elements
- Minimum spacing: 8px between adjacent touch targets
- Swipe gestures must have tap/button alternatives

## Testing Requirements

Every component must pass:
- [ ] Automated axe-core scan (zero violations)
- [ ] Manual keyboard navigation test
- [ ] VoiceOver (macOS/iOS) walkthrough
- [ ] TalkBack (Android) walkthrough
- [ ] 200% font scaling test
- [ ] High contrast mode test
