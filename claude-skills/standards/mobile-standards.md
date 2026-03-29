# Mobile Standards

These are non-negotiable quality rules for mobile experiences. They define the minimum bar for any app that will be used on phone-sized screens.

## Layout Rules

- No horizontal overflow unless intentionally scrollable (e.g., carousels)
- No content clipped at viewport edges
- Safe handling of sticky headers and bottom bars -- they must not overlap content
- Mobile-first stacking for dense layouts (side-by-side should stack on small screens)
- Respect safe area insets on notched and rounded-corner devices
- Modals must be fully usable on small screens -- no clipped buttons or hidden content

## Interaction Rules

- Touch targets must be at least 44x44 points
- No hidden actions obscured by the on-screen keyboard
- Avoid nested scroll containers that fight each other
- Primary actions should be reachable with thumb-friendly placement
- Gestures should feel natural and not conflict with platform gestures
- Ensure forms are usable when the keyboard is open (inputs not hidden)

## Content Rules

- Reduce redundant copy on small screens -- every word must earn its space
- Use compact card layouts when possible
- Surface only high-value information above the fold
- Don't make users scroll through noise to reach core actions
- Avoid information density that requires horizontal scrolling to read

## Performance / Feel Rules

- Avoid heavy layout jitter (Cumulative Layout Shift)
- Avoid laggy interactions -- prioritize responsiveness on the main thread
- Keep animations simple and smooth; avoid unnecessary complexity
- Prioritize smooth core actions over fancy visual effects
- Images should be lazy-loaded and appropriately sized for mobile

## Testing Expectations

- Test on iPhone-width viewports (375px) as the primary mobile target
- Test portrait mode as the default orientation
- Verify modals, drawers, and overlays on small screens
- Check keyboard interactions with all form inputs
- Verify tap targets are accessible and not overlapping
